[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionServlet.html.md)


    1   /*
    2    * $Id: ActionServlet.java 592630 2007-11-07 06:47:58Z pbenedict $
    3    *
    4    * Licensed to the Apache Software Foundation (ASF) under one
    5    * or more contributor license agreements.  See the NOTICE file
    6    * distributed with this work for additional information
    7    * regarding copyright ownership.  The ASF licenses this file
    8    * to you under the Apache License, Version 2.0 (the
    9    * "License"); you may not use this file except in compliance
    10   * with the License.  You may obtain a copy of the License at
    11   *
    12   *  http://www.apache.org/licenses/LICENSE-2.0
    13   *
    14   * Unless required by applicable law or agreed to in writing,
    15   * software distributed under the License is distributed on an
    16   * "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    17   * KIND, either express or implied.  See the License for the
    18   * specific language governing permissions and limitations
    19   * under the License.
    20   */
    21  package org.apache.struts.action;
    22  
    23  import org.apache.commons.beanutils.BeanUtils;
    24  import org.apache.commons.beanutils.ConvertUtils;
    25  import org.apache.commons.beanutils.PropertyUtils;
    26  import org.apache.commons.beanutils.converters.BigDecimalConverter;
    27  import org.apache.commons.beanutils.converters.BigIntegerConverter;
    28  import org.apache.commons.beanutils.converters.BooleanConverter;
    29  import org.apache.commons.beanutils.converters.ByteConverter;
    30  import org.apache.commons.beanutils.converters.CharacterConverter;
    31  import org.apache.commons.beanutils.converters.DoubleConverter;
    32  import org.apache.commons.beanutils.converters.FloatConverter;
    33  import org.apache.commons.beanutils.converters.IntegerConverter;
    34  import org.apache.commons.beanutils.converters.LongConverter;
    35  import org.apache.commons.beanutils.converters.ShortConverter;
    36  import org.apache.commons.chain.CatalogFactory;
    37  import org.apache.commons.chain.config.ConfigParser;
    38  import org.apache.commons.digester.Digester;
    39  import org.apache.commons.digester.RuleSet;
    40  import org.apache.commons.logging.Log;
    41  import org.apache.commons.logging.LogFactory;
    42  import org.apache.struts.Globals;
    43  import org.apache.struts.config.ActionConfig;
    44  import org.apache.struts.config.ConfigRuleSet;
    45  import org.apache.struts.config.ExceptionConfig;
    46  import org.apache.struts.config.FormBeanConfig;
    47  import org.apache.struts.config.FormPropertyConfig;
    48  import org.apache.struts.config.ForwardConfig;
    49  import org.apache.struts.config.MessageResourcesConfig;
    50  import org.apache.struts.config.ModuleConfig;
    51  import org.apache.struts.config.ModuleConfigFactory;
    52  import org.apache.struts.config.PlugInConfig;
    53  import org.apache.struts.util.MessageResources;
    54  import org.apache.struts.util.MessageResourcesFactory;
    55  import org.apache.struts.util.ModuleUtils;
    56  import org.apache.struts.util.RequestUtils;
    57  import org.xml.sax.InputSource;
    58  import org.xml.sax.SAXException;
    59  
    60  import javax.servlet.ServletContext;
    61  import javax.servlet.ServletException;
    62  import javax.servlet.UnavailableException;
    63  import javax.servlet.http.HttpServlet;
    64  import javax.servlet.http.HttpServletRequest;
    65  import javax.servlet.http.HttpServletResponse;
    66  
    67  import java.io.IOException;
    68  import java.io.InputStream;
    69  
    70  import java.math.BigDecimal;
    71  import java.math.BigInteger;
    72  
    73  import java.net.MalformedURLException;
    74  import java.net.URL;
    75  import java.net.URLConnection;
    76  
    77  import java.util.ArrayList;
    78  import java.util.Enumeration;
    79  import java.util.Iterator;
    80  import java.util.List;
    81  import java.util.MissingResourceException;
    82  
    83  /**
    84   * <p><strong>ActionServlet</strong> provides the "controller" in the
    85   * Model-View-Controller (MVC) design pattern for web applications that is
    86   * commonly known as "Model 2".  This nomenclature originated with a
    87   * description in the JavaServerPages Specification, version 0.92, and has
    88   * persisted ever since (in the absence of a better name).</p>
    89   *
    90   * <p>Generally, a "Model 2" application is architected as follows:</p>
    91   *
    92   * <ul>
    93   *
    94   * <li>The user interface will generally be created with server pages, which
    95   * will not themselves contain any business logic. These pages represent the
    96   * "view" component of an MVC architecture.</li>
    97   *
    98   * <li>Forms and hyperlinks in the user interface that require business logic
    99   * to be executed will be submitted to a request URI that is mapped to this
    100  * servlet.</li>
    101  *
    102  * <li>There can be <b>one</b> instance of this servlet class, which receives
    103  * and processes all requests that change the state of a user's interaction
    104  * with the application. The servlet delegates the handling of a request to a
    105  * {@link RequestProcessor} object. This component represents the "controller"
    106  * component of an MVC architecture. </li>
    107  *
    108  * <li>The <code>RequestProcessor</code> selects and invokes an {@link Action}
    109  * class to perform the requested business logic, or delegates the response to
    110  * another resource.</li>
    111  *
    112  * <li>The <code>Action</code> classes can manipulate the state of the
    113  * application's interaction with the user, typically by creating or modifying
    114  * JavaBeans that are stored as request or session attributes (depending on
    115  * how long they need to be available). Such JavaBeans represent the "model"
    116  * component of an MVC architecture.</li>
    117  *
    118  * <li>Instead of producing the next page of the user interface directly,
    119  * <code>Action</code> classes generally return an {@link ActionForward} to
    120  * indicate which resource should handle the response. If the
    121  * <code>Action</code> does not return null, the <code>RequestProcessor</code>
    122  * forwards or redirects to the specified resource (by utilizing
    123  * <code>RequestDispatcher.forward</code> or <code>Response.sendRedirect</code>)
    124  * so as to produce the next page of the user interface.</li>
    125  *
    126  * </ul>
    127  *
    128  * <p>The standard version of <code>RequestsProcessor</code> implements the
    129  * following logic for each incoming HTTP request. You can override some or
    130  * all of this functionality by subclassing this object and implementing your
    131  * own version of the processing.</p>
    132  *
    133  * <ul>
    134  *
    135  * <li>Identify, from the incoming request URI, the substring that will be
    136  * used to select an action procedure.</li>
    137  *
    138  * <li>Use this substring to map to the Java class name of the corresponding
    139  * action class (an implementation of the <code>Action</code> interface).
    140  * </li>
    141  *
    142  * <li>If this is the first request for a particular <code>Action</code>
    143  * class, instantiate an instance of that class and cache it for future
    144  * use.</li>
    145  *
    146  * <li>Optionally populate the properties of an <code>ActionForm</code> bean
    147  * associated with this mapping.</li>
    148  *
    149  * <li>Call the <code>execute</code> method of this <code>Action</code> class,
    150  * passing on a reference to the mapping that was used, the relevant form-bean
    151  * (if any), and the request and the response that were passed to the
    152  * controller by the servlet container (thereby providing access to any
    153  * specialized properties of the mapping itself as well as to the
    154  * ServletContext). </li>
    155  *
    156  * </ul>
    157  *
    158  * <p>The standard version of <code>ActionServlet</code> is configured based
    159  * on the following servlet initialization parameters, which you will specify
    160  * in the web application deployment descriptor (<code>/WEB-INF/web.xml</code>)
    161  * for your application.  Subclasses that specialize this servlet are free to
    162  * define additional initialization parameters. </p>
    163  *
    164  * <ul>
    165  *
    166  * <li><strong>config</strong> - Comma-separated list of context-relative
    167  * path(s) to the XML resource(s) containing the configuration information for
    168  * the default module.  (Multiple files support since Struts 1.1)
    169  * [/WEB-INF/struts-config.xml].</li>
    170  *
    171  * <li><strong>config/${module}</strong> - Comma-separated list of
    172  * Context-relative path(s) to the XML resource(s) containing the
    173  * configuration information for the module that will use the specified prefix
    174  * (/${module}). This can be repeated as many times as required for multiple
    175  * modules. (Since Struts 1.1)</li>
    176  *
    177  * <li><strong>configFactory</strong> - The Java class name of the
    178  * <code>ModuleConfigFactory</code> used to create the implementation of the
    179  * ModuleConfig interface. </li>
    180  *
    181  * <li><strong>convertNull</strong> - Force simulation of the Struts 1.0
    182  * behavior when populating forms. If set to true, the numeric Java wrapper
    183  * class types (like <code>java.lang.Integer</code>) will default to null
    184  * (rather than 0). (Since Struts 1.1) [false] </li>
    185  *
    186  * <li><strong>rulesets </strong> - Comma-delimited list of fully qualified
    187  * classnames of additional <code>org.apache.commons.digester.RuleSet</code>
    188  * instances that should be added to the <code>Digester</code> that will be
    189  * processing <code>struts-config.xml</code> files.  By default, only the
    190  * <code>RuleSet</code> for the standard configuration elements is loaded.
    191  * (Since Struts 1.1)</li>
    192  *
    193  * <li><strong>validating</strong> - Should we use a validating XML parser to
    194  * process the configuration file (strongly recommended)? [true]</li>
    195  *
    196  * <li><strong>chainConfig</strong> - Comma-separated list of either
    197  * context-relative or classloader path(s) to load commons-chain catalog
    198  * definitions from.  If none specified, the default Struts catalog that is
    199  * provided with Struts will be used.</li>
    200  *
    201  * </ul>
    202  *
    203  * @version $Rev: 592630 $ $Date: 2005-10-14 19:54:16 -0400 (Fri, 14 Oct 2005)
    204  *          $
    205  */
    206 public class ActionServlet extends HttpServlet {
    207     /**
    208      * <p>Commons Logging instance.</p>
    209      *
    210      * @since Struts 1.1
    211      */
    212     protected static Log log = LogFactory.getLog(ActionServlet.class);
    213 
    214     // ----------------------------------------------------- Instance Variables
    215 
    216     /**
    217      * <p>Comma-separated list of context-relative path(s) to our
    218      * configuration resource(s) for the default module.</p>
    219      */
    220     protected String config = "/WEB-INF/struts-config.xml";
    221 
    222     /**
    223      * <p>Comma-separated list of context or classloader-relative path(s) that
    224      * contain the configuration for the default commons-chain
    225      * catalog(s).</p>
    226      */
    227     protected String chainConfig = "org/apache/struts/chain/chain-config.xml";
    228 
    229     /**
    230      * <p>The Digester used to produce ModuleConfig objects from a Struts
    231      * configuration file.</p>
    232      *
    233      * @since Struts 1.1
    234      */
    235     protected Digester configDigester = null;
    236 
    237     /**
    238      * <p>The flag to request backwards-compatible conversions for form bean
    239      * properties of the Java wrapper class types.</p>
    240      *
    241      * @since Struts 1.1
    242      */
    243     protected boolean convertNull = false;
    244 
    245     /**
    246      * <p>The resources object for our internal resources.</p>
    247      */
    248     protected MessageResources internal = null;
    249 
    250     /**
    251      * <p>The Java base name of our internal resources.</p>
    252      *
    253      * @since Struts 1.1
    254      */
    255     protected String internalName = "org.apache.struts.action.ActionResources";
    256 
    257     /**
    258      * <p>The set of public identifiers, and corresponding resource names, for
    259      * the versions of the configuration file DTDs that we know about.  There
    260      * <strong>MUST</strong> be an even number of Strings in this list!</p>
    261      */
    262     protected String[] registrations =
    263         {
    264             "-//Apache Software Foundation//DTD Struts Configuration 1.0//EN",
    265             "/org/apache/struts/resources/struts-config_1_0.dtd",
    266             "-//Apache Software Foundation//DTD Struts Configuration 1.1//EN",
    267             "/org/apache/struts/resources/struts-config_1_1.dtd",
    268             "-//Apache Software Foundation//DTD Struts Configuration 1.2//EN",
    269             "/org/apache/struts/resources/struts-config_1_2.dtd",
    270             "-//Apache Software Foundation//DTD Struts Configuration 1.3//EN",
    271             "/org/apache/struts/resources/struts-config_1_3.dtd",
    272             "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN",
    273             "/org/apache/struts/resources/web-app_2_3.dtd"
    274         };
    275 
    276     /**
    277      * <p>The URL pattern to which we are mapped in our web application
    278      * deployment descriptor.</p>
    279      */
    280     protected String servletMapping = null; // :FIXME: - multiples?
    281 
    282     /**
    283      * <p>The servlet name under which we are registered in our web
    284      * application deployment descriptor.</p>
    285      */
    286     protected String servletName = null;
    287 
    288     // ---------------------------------------------------- HttpServlet Methods
    289 
    290     /**
    291      * <p>Gracefully shut down this controller servlet, releasing any
    292      * resources that were allocated at initialization.</p>
    293      */
    294     public void destroy() {
    295         if (log.isDebugEnabled()) {
    296             log.debug(internal.getMessage("finalizing"));
    297         }
    298 
    299         destroyModules();
    300         destroyInternal();
    301         getServletContext().removeAttribute(Globals.ACTION_SERVLET_KEY);
    302 
    303         CatalogFactory.clear();
    304         PropertyUtils.clearDescriptors();
    305 
    306         // Release our LogFactory and Log instances (if any)
    307         ClassLoader classLoader =
    308             Thread.currentThread().getContextClassLoader();
    309 
    310         if (classLoader == null) {
    311             classLoader = ActionServlet.class.getClassLoader();
    312         }
    313 
    314         try {
    315             LogFactory.release(classLoader);
    316         } catch (Throwable t) {
    317             ; // Servlet container doesn't have the latest version
    318 
    319             // of commons-logging-api.jar installed
    320             // :FIXME: Why is this dependent on the container's version of
    321             // commons-logging? Shouldn't this depend on the version packaged
    322             // with Struts?
    323 
    324             /*
    325               Reason: LogFactory.release(classLoader); was added as
    326               an attempt to investigate the OutOfMemory error reported on
    327               Bugzilla #14042. It was committed for version 1.136 by craigmcc
    328             */
    329         }
    330     }
    331 
    332     /**
    333      * <p>Initialize this servlet.  Most of the processing has been factored
    334      * into support methods so that you can override particular functionality
    335      * at a fairly granular level.</p>
    336      *
    337      * @throws ServletException if we cannot configure ourselves correctly
    338      */
    339     public void init() throws ServletException {
    340         final String configPrefix = "config/";
    341         final int configPrefixLength = configPrefix.length() - 1;
    342 
    343         // Wraps the entire initialization in a try/catch to better handle
    344         // unexpected exceptions and errors to provide better feedback
    345         // to the developer
    346         try {
    347             initInternal();
    348             initOther();
    349             initServlet();
    350             initChain();
    351 
    352             getServletContext().setAttribute(Globals.ACTION_SERVLET_KEY, this);
    353             initModuleConfigFactory();
    354 
    355             // Initialize modules as needed
    356             ModuleConfig moduleConfig = initModuleConfig("", config);
    357 
    358             initModuleMessageResources(moduleConfig);
    359             initModulePlugIns(moduleConfig);
    360             initModuleFormBeans(moduleConfig);
    361             initModuleForwards(moduleConfig);
    362             initModuleExceptionConfigs(moduleConfig);
    363             initModuleActions(moduleConfig);
    364             moduleConfig.freeze();
    365 
    366             Enumeration names = getServletConfig().getInitParameterNames();
    367 
    368             while (names.hasMoreElements()) {
    369                 String name = (String) names.nextElement();
    370 
    371                 if (!name.startsWith(configPrefix)) {
    372                     continue;
    373                 }
    374 
    375                 String prefix = name.substring(configPrefixLength);
    376 
    377                 moduleConfig =
    378                     initModuleConfig(prefix,
    379                         getServletConfig().getInitParameter(name));
    380                 initModuleMessageResources(moduleConfig);
    381                 initModulePlugIns(moduleConfig);
    382                 initModuleFormBeans(moduleConfig);
    383                 initModuleForwards(moduleConfig);
    384                 initModuleExceptionConfigs(moduleConfig);
    385                 initModuleActions(moduleConfig);
    386                 moduleConfig.freeze();
    387             }
    388 
    389             this.initModulePrefixes(this.getServletContext());
    390 
    391             this.destroyConfigDigester();
    392         } catch (UnavailableException ex) {
    393             throw ex;
    394         } catch (Throwable t) {
    395             // The follow error message is not retrieved from internal message
    396             // resources as they may not have been able to have been
    397             // initialized
    398             log.error("Unable to initialize Struts ActionServlet due to an "
    399                 + "unexpected exception or error thrown, so marking the "
    400                 + "servlet as unavailable.  Most likely, this is due to an "
    401                 + "incorrect or missing library dependency.", t);
    402             throw new UnavailableException(t.getMessage());
    403         }
    404     }
    405 
    406     /**
    407      * <p>Saves a String[] of module prefixes in the ServletContext under
    408      * Globals.MODULE_PREFIXES_KEY.  <strong>NOTE</strong> - the "" prefix for
    409      * the default module is not included in this list.</p>
    410      *
    411      * @param context The servlet context.
    412      * @since Struts 1.2
    413      */
    414     protected void initModulePrefixes(ServletContext context) {
    415         ArrayList prefixList = new ArrayList();
    416 
    417         Enumeration names = context.getAttributeNames();
    418 
    419         while (names.hasMoreElements()) {
    420             String name = (String) names.nextElement();
    421 
    422             if (!name.startsWith(Globals.MODULE_KEY)) {
    423                 continue;
    424             }
    425 
    426             String prefix = name.substring(Globals.MODULE_KEY.length());
    427 
    428             if (prefix.length() > 0) {
    429                 prefixList.add(prefix);
    430             }
    431         }
    432 
    433         String[] prefixes =
    434             (String[]) prefixList.toArray(new String[prefixList.size()]);
    435 
    436         context.setAttribute(Globals.MODULE_PREFIXES_KEY, prefixes);
    437     }
    438 
    439     /**
    440      * <p>Process an HTTP "GET" request.</p>
    441      *
    442      * @param request  The servlet request we are processing
    443      * @param response The servlet response we are creating
    444      * @throws IOException      if an input/output error occurs
    445      * @throws ServletException if a servlet exception occurs
    446      */
    447     public void doGet(HttpServletRequest request, HttpServletResponse response)
    448         throws IOException, ServletException {
    449         process(request, response);
    450     }
    451 
    452     /**
    453      * <p>Process an HTTP "POST" request.</p>
    454      *
    455      * @param request  The servlet request we are processing
    456      * @param response The servlet response we are creating
    457      * @throws IOException      if an input/output error occurs
    458      * @throws ServletException if a servlet exception occurs
    459      */
    460     public void doPost(HttpServletRequest request, HttpServletResponse response)
    461         throws IOException, ServletException {
    462         process(request, response);
    463     }
    464 
    465     // --------------------------------------------------------- Public Methods
    466 
    467     /**
    468      * <p>Remember a servlet mapping from our web application deployment
    469      * descriptor, if it is for this servlet.</p>
    470      *
    471      * @param servletName The name of the servlet being mapped
    472      * @param urlPattern  The URL pattern to which this servlet is mapped
    473      */
    474     public void addServletMapping(String servletName, String urlPattern) {
    475         if (servletName == null) {
    476             return;
    477         }
    478 
    479         if (servletName.equals(this.servletName)) {
    480             if (log.isDebugEnabled()) {
    481                 log.debug("Process servletName=" + servletName
    482                     + ", urlPattern=" + urlPattern);
    483             }
    484 
    485             this.servletMapping = urlPattern;
    486         }
    487     }
    488 
    489     /**
    490      * <p>Return the <code>MessageResources</code> instance containing our
    491      * internal message strings.</p>
    492      *
    493      * @return the <code>MessageResources</code> instance containing our
    494      *         internal message strings.
    495      * @since Struts 1.1
    496      */
    497     public MessageResources getInternal() {
    498         return (this.internal);
    499     }
    500 
    501     // ------------------------------------------------------ Protected Methods
    502 
    503     /**
    504      * <p>Gracefully terminate use of any modules associated with this
    505      * application (if any).</p>
    506      *
    507      * @since Struts 1.1
    508      */
    509     protected void destroyModules() {
    510         ArrayList values = new ArrayList();
    511         Enumeration names = getServletContext().getAttributeNames();
    512 
    513         while (names.hasMoreElements()) {
    514             values.add(names.nextElement());
    515         }
    516 
    517         Iterator keys = values.iterator();
    518 
    519         while (keys.hasNext()) {
    520             String name = (String) keys.next();
    521             Object value = getServletContext().getAttribute(name);
    522 
    523             if (!(value instanceof ModuleConfig)) {
    524                 continue;
    525             }
    526 
    527             ModuleConfig config = (ModuleConfig) value;
    528 
    529             if (this.getProcessorForModule(config) != null) {
    530                 this.getProcessorForModule(config).destroy();
    531             }
    532 
    533             getServletContext().removeAttribute(name);
    534 
    535             PlugIn[] plugIns =
    536                 (PlugIn[]) getServletContext().getAttribute(Globals.PLUG_INS_KEY
    537                     + config.getPrefix());
    538 
    539             if (plugIns != null) {
    540                 for (int i = 0; i < plugIns.length; i++) {
    541                     int j = plugIns.length - (i + 1);
    542 
    543                     plugIns[j].destroy();
    544                 }
    545 
    546                 getServletContext().removeAttribute(Globals.PLUG_INS_KEY
    547                     + config.getPrefix());
    548             }
    549         }
    550     }
    551 
    552     /**
    553      * <p>Gracefully release any configDigester instance that we have created.
    554      * </p>
    555      *
    556      * @since Struts 1.1
    557      */
    558     protected void destroyConfigDigester() {
    559         configDigester = null;
    560     }
    561 
    562     /**
    563      * <p>Gracefully terminate use of the internal MessageResources.</p>
    564      */
    565     protected void destroyInternal() {
    566         internal = null;
    567     }
    568 
    569     /**
    570      * <p>Return the module configuration object for the currently selected
    571      * module.</p>
    572      *
    573      * @param request The servlet request we are processing
    574      * @return The module configuration object for the currently selected
    575      *         module.
    576      * @since Struts 1.1
    577      */
    578     protected ModuleConfig getModuleConfig(HttpServletRequest request) {
    579         ModuleConfig config =
    580             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    581 
    582         if (config == null) {
    583             config =
    584                 (ModuleConfig) getServletContext().getAttribute(Globals.MODULE_KEY);
    585         }
    586 
    587         return (config);
    588     }
    589 
    590     /**
    591      * <p>Look up and return the {@link RequestProcessor} responsible for the
    592      * specified module, creating a new one if necessary.</p>
    593      *
    594      * @param config The module configuration for which to acquire and return
    595      *               a RequestProcessor.
    596      * @return The {@link RequestProcessor} responsible for the specified
    597      *         module,
    598      * @throws ServletException If we cannot instantiate a RequestProcessor
    599      *                          instance a {@link UnavailableException} is
    600      *                          thrown, meaning your application is not loaded
    601      *                          and will not be available.
    602      * @since Struts 1.1
    603      */
    604     protected synchronized RequestProcessor getRequestProcessor(
    605         ModuleConfig config) throws ServletException {
    606         RequestProcessor processor = this.getProcessorForModule(config);
    607 
    608         if (processor == null) {
    609             try {
    610                 processor =
    611                     (RequestProcessor) RequestUtils.applicationInstance(config.getControllerConfig()
    612                                                                               .getProcessorClass());
    613             } catch (Exception e) {
    614                 throw new UnavailableException(
    615                     "Cannot initialize RequestProcessor of class "
    616                     + config.getControllerConfig().getProcessorClass() + ": "
    617                     + e);
    618             }
    619 
    620             processor.init(this, config);
    621 
    622             String key = Globals.REQUEST_PROCESSOR_KEY + config.getPrefix();
    623 
    624             getServletContext().setAttribute(key, processor);
    625         }
    626 
    627         return (processor);
    628     }
    629 
    630     /**
    631      * <p>Returns the RequestProcessor for the given module or null if one
    632      * does not exist.  This method will not create a RequestProcessor.</p>
    633      *
    634      * @param config The ModuleConfig.
    635      * @return The <code>RequestProcessor</code> for the given module, or
    636      *         <code>null</code> if one does not exist.
    637      */
    638     private RequestProcessor getProcessorForModule(ModuleConfig config) {
    639         String key = Globals.REQUEST_PROCESSOR_KEY + config.getPrefix();
    640 
    641         return (RequestProcessor) getServletContext().getAttribute(key);
    642     }
    643 
    644     /**
    645      * <p>Initialize the factory used to create the module configuration.</p>
    646      *
    647      * @since Struts 1.2
    648      */
    649     protected void initModuleConfigFactory() {
    650         String configFactory =
    651             getServletConfig().getInitParameter("configFactory");
    652 
    653         if (configFactory != null) {
    654             ModuleConfigFactory.setFactoryClass(configFactory);
    655         }
    656     }
    657 
    658     /**
    659      * <p>Initialize the module configuration information for the specified
    660      * module.</p>
    661      *
    662      * @param prefix Module prefix for this module
    663      * @param paths  Comma-separated list of context-relative resource path(s)
    664      *               for this modules's configuration resource(s)
    665      * @return The new module configuration instance.
    666      * @throws ServletException if initialization cannot be performed
    667      * @since Struts 1.1
    668      */
    669     protected ModuleConfig initModuleConfig(String prefix, String paths)
    670         throws ServletException {
    671         if (log.isDebugEnabled()) {
    672             log.debug("Initializing module path '" + prefix
    673                 + "' configuration from '" + paths + "'");
    674         }
    675 
    676         // Parse the configuration for this module
    677         ModuleConfigFactory factoryObject = ModuleConfigFactory.createFactory();
    678         ModuleConfig config = factoryObject.createModuleConfig(prefix);
    679 
    680         // Configure the Digester instance we will use
    681         Digester digester = initConfigDigester();
    682 
    683         List urls = splitAndResolvePaths(paths);
    684         URL url;
    685 
    686         for (Iterator i = urls.iterator(); i.hasNext();) {
    687             url = (URL) i.next();
    688             digester.push(config);
    689             this.parseModuleConfigFile(digester, url);
    690         }
    691 
    692         getServletContext().setAttribute(Globals.MODULE_KEY
    693             + config.getPrefix(), config);
    694 
    695         return config;
    696     }
    697 
    698     /**
    699      * <p>Parses one module config file.</p>
    700      *
    701      * @param digester Digester instance that does the parsing
    702      * @param path     The path to the config file to parse.
    703      * @throws UnavailableException if file cannot be read or parsed
    704      * @since Struts 1.2
    705      * @deprecated use parseModuleConfigFile(Digester digester, URL url)
    706      *             instead
    707      */
    708     protected void parseModuleConfigFile(Digester digester, String path)
    709         throws UnavailableException {
    710         try {
    711             List paths = splitAndResolvePaths(path);
    712 
    713             if (paths.size() > 0) {
    714                 // Get first path as was the old behavior
    715                 URL url = (URL) paths.get(0);
    716 
    717                 parseModuleConfigFile(digester, url);
    718             } else {
    719                 throw new UnavailableException("Cannot locate path " + path);
    720             }
    721         } catch (UnavailableException ex) {
    722             throw ex;
    723         } catch (ServletException ex) {
    724             handleConfigException(path, ex);
    725         }
    726     }
    727 
    728     /**
    729      * <p>Parses one module config file.</p>
    730      *
    731      * @param digester Digester instance that does the parsing
    732      * @param url      The url to the config file to parse.
    733      * @throws UnavailableException if file cannot be read or parsed
    734      * @since Struts 1.3
    735      */
    736     protected void parseModuleConfigFile(Digester digester, URL url)
    737         throws UnavailableException {
    738 
    739         try {
    740             digester.parse(url);
    741         } catch (IOException e) {
    742             handleConfigException(url.toString(), e);
    743         } catch (SAXException e) {
    744             handleConfigException(url.toString(), e);
    745         }
    746     }
    747 
    748     /**
    749      * <p>Simplifies exception handling in the parseModuleConfigFile
    750      * method.<p>
    751      *
    752      * @param path The path to which the exception relates.
    753      * @param e    The exception to be wrapped and thrown.
    754      * @throws UnavailableException as a wrapper around Exception
    755      */
    756     private void handleConfigException(String path, Exception e)
    757         throws UnavailableException {
    758         String msg = internal.getMessage("configParse", path);
    759 
    760         log.error(msg, e);
    761         throw new UnavailableException(msg);
    762     }
    763 
    764     /**
    765      * <p>Handle errors related to creating an instance of the specified
    766      * class.</p>
    767      *
    768      * @param className The className that could not be instantiated.
    769      * @param e         The exception that was caught.
    770      * @throws ServletException to communicate the error.
    771      */
    772     private void handleCreationException(String className, Exception e)
    773         throws ServletException {
    774         String errorMessage =
    775             internal.getMessage("configExtends.creation", className);
    776 
    777         log.error(errorMessage, e);
    778         throw new UnavailableException(errorMessage);
    779     }
    780 
    781     /**
    782      * <p>General handling for exceptions caught while inheriting config
    783      * information.</p>
    784      *
    785      * @param configType The type of configuration object of configName.
    786      * @param configName The name of the config that could not be extended.
    787      * @param e          The exception that was caught.
    788      * @throws ServletException to communicate the error.
    789      */
    790     private void handleGeneralExtensionException(String configType,
    791         String configName, Exception e)
    792         throws ServletException {
    793         String errorMessage =
    794             internal.getMessage("configExtends", configType, configName);
    795 
    796         log.error(errorMessage, e);
    797         throw new UnavailableException(errorMessage);
    798     }
    799 
    800     /**
    801      * <p>Handle errors caused by required fields that were not
    802      * specified.</p>
    803      *
    804      * @param field      The name of the required field that was not found.
    805      * @param configType The type of configuration object of configName.
    806      * @param configName The name of the config that's missing the required
    807      *                   value.
    808      * @throws ServletException to communicate the error.
    809      */
    810     private void handleValueRequiredException(String field, String configType,
    811         String configName) throws ServletException {
    812         String errorMessage =
    813             internal.getMessage("configFieldRequired", field, configType,
    814                 configName);
    815 
    816         log.error(errorMessage);
    817         throw new UnavailableException(errorMessage);
    818     }
    819 
    820     /**
    821      * <p>Initialize the plug ins for the specified module.</p>
    822      *
    823      * @param config ModuleConfig information for this module
    824      * @throws ServletException if initialization cannot be performed
    825      * @since Struts 1.1
    826      */
    827     protected void initModulePlugIns(ModuleConfig config)
    828         throws ServletException {
    829         if (log.isDebugEnabled()) {
    830             log.debug("Initializing module path '" + config.getPrefix()
    831                 + "' plug ins");
    832         }
    833 
    834         PlugInConfig[] plugInConfigs = config.findPlugInConfigs();
    835         PlugIn[] plugIns = new PlugIn[plugInConfigs.length];
    836 
    837         getServletContext().setAttribute(Globals.PLUG_INS_KEY
    838             + config.getPrefix(), plugIns);
    839 
    840         for (int i = 0; i < plugIns.length; i++) {
    841             try {
    842                 plugIns[i] =
    843                     (PlugIn) RequestUtils.applicationInstance(plugInConfigs[i]
    844                         .getClassName());
    845                 BeanUtils.populate(plugIns[i], plugInConfigs[i].getProperties());
    846 
    847                 // Pass the current plugIn config object to the PlugIn.
    848                 // The property is set only if the plugin declares it.
    849                 // This plugin config object is needed by Tiles
    850                 try {
    851                     PropertyUtils.setProperty(plugIns[i],
    852                         "currentPlugInConfigObject", plugInConfigs[i]);
    853                 } catch (Exception e) {
    854                     ;
    855 
    856                     // FIXME Whenever we fail silently, we must document a valid
    857                     // reason for doing so.  Why should we fail silently if a
    858                     // property can't be set on the plugin?
    859 
    860                     /**
    861                      * Between version 1.138-1.140 cedric made these changes.
    862                      * The exceptions are caught to deal with containers
    863                      * applying strict security. This was in response to bug
    864                      * #15736
    865                      *
    866                      * Recommend that we make the currentPlugInConfigObject part
    867                      * of the PlugIn Interface if we can, Rob
    868                      */
    869                 }
    870 
    871                 plugIns[i].init(this, config);
    872             } catch (ServletException e) {
    873                 throw e;
    874             } catch (Exception e) {
    875                 String errMsg =
    876                     internal.getMessage("plugIn.init",
    877                         plugInConfigs[i].getClassName());
    878 
    879                 log(errMsg, e);
    880                 throw new UnavailableException(errMsg);
    881             }
    882         }
    883     }
    884 
    885     /**
    886      * <p>Initialize the form beans for the specified module.</p>
    887      *
    888      * @param config ModuleConfig information for this module
    889      * @throws ServletException if initialization cannot be performed
    890      * @since Struts 1.3
    891      */
    892     protected void initModuleFormBeans(ModuleConfig config)
    893         throws ServletException {
    894         if (log.isDebugEnabled()) {
    895             log.debug("Initializing module path '" + config.getPrefix()
    896                 + "' form beans");
    897         }
    898 
    899         // Process form bean extensions.
    900         FormBeanConfig[] formBeans = config.findFormBeanConfigs();
    901 
    902         for (int i = 0; i < formBeans.length; i++) {
    903             FormBeanConfig beanConfig = formBeans[i];
    904 
    905             processFormBeanExtension(beanConfig, config);
    906         }
    907 
    908         for (int i = 0; i < formBeans.length; i++) {
    909             FormBeanConfig formBean = formBeans[i];
    910 
    911             // Verify that required fields are all present for the form config
    912             if (formBean.getType() == null) {
    913                 handleValueRequiredException("type", formBean.getName(),
    914                     "form bean");
    915             }
    916 
    917             // ... and the property configs
    918             FormPropertyConfig[] fpcs = formBean.findFormPropertyConfigs();
    919 
    920             for (int j = 0; j < fpcs.length; j++) {
    921                 FormPropertyConfig property = fpcs[j];
    922 
    923                 if (property.getType() == null) {
    924                     handleValueRequiredException("type", property.getName(),
    925                         "form property");
    926                 }
    927             }
    928 
    929             // Force creation and registration of DynaActionFormClass instances
    930             // for all dynamic form beans
    931             if (formBean.getDynamic()) {
    932                 formBean.getDynaActionFormClass();
    933             }
    934         }
    935     }
    936 
    937     /**
    938      * <p>Extend the form bean's configuration as necessary.</p>
    939      *
    940      * @param beanConfig   the configuration to process.
    941      * @param moduleConfig the module configuration for this module.
    942      * @throws ServletException if initialization cannot be performed.
    943      */
    944     protected void processFormBeanExtension(FormBeanConfig beanConfig,
    945         ModuleConfig moduleConfig)
    946         throws ServletException {
    947         try {
    948             if (!beanConfig.isExtensionProcessed()) {
    949                 if (log.isDebugEnabled()) {
    950                     log.debug("Processing extensions for '"
    951                         + beanConfig.getName() + "'");
    952                 }
    953 
    954                 beanConfig =
    955                     processFormBeanConfigClass(beanConfig, moduleConfig);
    956 
    957                 beanConfig.processExtends(moduleConfig);
    958             }
    959         } catch (ServletException e) {
    960             throw e;
    961         } catch (Exception e) {
    962             handleGeneralExtensionException("FormBeanConfig",
    963                 beanConfig.getName(), e);
    964         }
    965     }
    966 
    967     /**
    968      * <p>Checks if the current beanConfig is using the correct class based on
    969      * the class of its ancestor form bean config.</p>
    970      *
    971      * @param beanConfig   The form bean to check.
    972      * @param moduleConfig The config for the current module.
    973      * @return The form bean config using the correct class as determined by
    974      *         the config's ancestor and its own overridden value.
    975      * @throws UnavailableException if an instance of the form bean config
    976      *                              class cannot be created.
    977      * @throws ServletException     on class creation error
    978      */
    979     protected FormBeanConfig processFormBeanConfigClass(
    980         FormBeanConfig beanConfig, ModuleConfig moduleConfig)
    981         throws ServletException {
    982         String ancestor = beanConfig.getExtends();
    983 
    984         if (ancestor == null) {
    985             // Nothing to do, then
    986             return beanConfig;
    987         }
    988 
    989         // Make sure that this bean is of the right class
    990         FormBeanConfig baseConfig = moduleConfig.findFormBeanConfig(ancestor);
    991 
    992         if (baseConfig == null) {
    993             throw new UnavailableException("Unable to find " + "form bean '"
    994                 + ancestor + "' to extend.");
    995         }
    996 
    997         // Was our bean's class overridden already?
    998         if (beanConfig.getClass().equals(FormBeanConfig.class)) {
    999             // Ensure that our bean is using the correct class
    1000             if (!baseConfig.getClass().equals(beanConfig.getClass())) {
    1001                 // Replace the bean with an instance of the correct class
    1002                 FormBeanConfig newBeanConfig = null;
    1003                 String baseConfigClassName = baseConfig.getClass().getName();
    1004 
    1005                 try {
    1006                     newBeanConfig =
    1007                         (FormBeanConfig) RequestUtils.applicationInstance(baseConfigClassName);
    1008 
    1009                     // copy the values
    1010                     BeanUtils.copyProperties(newBeanConfig, beanConfig);
    1011 
    1012                     FormPropertyConfig[] fpc =
    1013                         beanConfig.findFormPropertyConfigs();
    1014 
    1015                     for (int i = 0; i < fpc.length; i++) {
    1016                         newBeanConfig.addFormPropertyConfig(fpc[i]);
    1017                     }
    1018                 } catch (Exception e) {
    1019                     handleCreationException(baseConfigClassName, e);
    1020                 }
    1021 
    1022                 // replace beanConfig with newBeanConfig
    1023                 moduleConfig.removeFormBeanConfig(beanConfig);
    1024                 moduleConfig.addFormBeanConfig(newBeanConfig);
    1025                 beanConfig = newBeanConfig;
    1026             }
    1027         }
    1028 
    1029         return beanConfig;
    1030     }
    1031 
    1032     /**
    1033      * <p>Initialize the forwards for the specified module.</p>
    1034      *
    1035      * @param config ModuleConfig information for this module
    1036      * @throws ServletException if initialization cannot be performed
    1037      */
    1038     protected void initModuleForwards(ModuleConfig config)
    1039         throws ServletException {
    1040         if (log.isDebugEnabled()) {
    1041             log.debug("Initializing module path '" + config.getPrefix()
    1042                 + "' forwards");
    1043         }
    1044 
    1045         // Process forwards extensions.
    1046         ForwardConfig[] forwards = config.findForwardConfigs();
    1047 
    1048         for (int i = 0; i < forwards.length; i++) {
    1049             ForwardConfig forward = forwards[i];
    1050 
    1051             processForwardExtension(forward, config, null);
    1052         }
    1053 
    1054         for (int i = 0; i < forwards.length; i++) {
    1055             ForwardConfig forward = forwards[i];
    1056 
    1057             // Verify that required fields are all present for the forward
    1058             if (forward.getPath() == null) {
    1059                 handleValueRequiredException("path", forward.getName(),
    1060                     "global forward");
    1061             }
    1062         }
    1063     }
    1064 
    1065     /**
    1066      * <p>Extend the forward's configuration as necessary.  If actionConfig is
    1067      * provided, then this method will process the forwardConfig as part
    1068      * of that actionConfig.  If actionConfig is null, the forwardConfig
    1069      * will be processed as a global forward.</p>
    1070      *
    1071      * @param forwardConfig the configuration to process.
    1072      * @param moduleConfig  the module configuration for this module.
    1073      * @param actionConfig  If applicable, the config for the current action.
    1074      * @throws ServletException if initialization cannot be performed.
    1075      */
    1076     protected void processForwardExtension(ForwardConfig forwardConfig,
    1077         ModuleConfig moduleConfig, ActionConfig actionConfig)
    1078         throws ServletException {
    1079         try {
    1080             if (!forwardConfig.isExtensionProcessed()) {
    1081                 if (log.isDebugEnabled()) {
    1082                     log.debug("Processing extensions for '"
    1083                         + forwardConfig.getName() + "'");
    1084                 }
    1085 
    1086                 forwardConfig =
    1087                     processForwardConfigClass(forwardConfig, moduleConfig,
    1088                         actionConfig);
    1089 
    1090                 forwardConfig.processExtends(moduleConfig, actionConfig);
    1091             }
    1092         } catch (ServletException e) {
    1093             throw e;
    1094         } catch (Exception e) {
    1095             handleGeneralExtensionException("Forward", forwardConfig.getName(),
    1096                 e);
    1097         }
    1098     }
    1099 
    1100     /**
    1101      * <p>Checks if the current forwardConfig is using the correct class based
    1102      * on the class of its configuration ancestor.  If actionConfig is
    1103      * provided, then this method will process the forwardConfig as part
    1104      * of that actionConfig.  If actionConfig is null, the forwardConfig
    1105      * will be processed as a global forward.</p>
    1106      *
    1107      * @param forwardConfig The forward to check.
    1108      * @param moduleConfig  The config for the current module.
    1109      * @param actionConfig  If applicable, the config for the current action.
    1110      * @return The forward config using the correct class as determined by the
    1111      *         config's ancestor and its own overridden value.
    1112      * @throws UnavailableException if an instance of the forward config class
    1113      *                              cannot be created.
    1114      * @throws ServletException     on class creation error
    1115      */
    1116     protected ForwardConfig processForwardConfigClass(
    1117         ForwardConfig forwardConfig, ModuleConfig moduleConfig,
    1118         ActionConfig actionConfig)
    1119         throws ServletException {
    1120         String ancestor = forwardConfig.getExtends();
    1121 
    1122         if (ancestor == null) {
    1123             // Nothing to do, then
    1124             return forwardConfig;
    1125         }
    1126 
    1127         // Make sure that this config is of the right class
    1128         ForwardConfig baseConfig = null;
    1129         if (actionConfig != null) {
    1130             // Look for this in the actionConfig
    1131             baseConfig = actionConfig.findForwardConfig(ancestor);
    1132         }
    1133 
    1134         if (baseConfig == null) {
    1135             // Either this is a forwardConfig that inherits a global config,
    1136             //  or actionConfig is null
    1137             baseConfig = moduleConfig.findForwardConfig(ancestor);
    1138         }
    1139 
    1140         if (baseConfig == null) {
    1141             throw new UnavailableException("Unable to find " + "forward '"
    1142                 + ancestor + "' to extend.");
    1143         }
    1144 
    1145         // Was our forwards's class overridden already?
    1146         if (forwardConfig.getClass().equals(ActionForward.class)) {
    1147             // Ensure that our forward is using the correct class
    1148             if (!baseConfig.getClass().equals(forwardConfig.getClass())) {
    1149                 // Replace the config with an instance of the correct class
    1150                 ForwardConfig newForwardConfig = null;
    1151                 String baseConfigClassName = baseConfig.getClass().getName();
    1152 
    1153                 try {
    1154                     newForwardConfig =
    1155                         (ForwardConfig) RequestUtils.applicationInstance(
    1156                                 baseConfigClassName);
    1157 
    1158                     // copy the values
    1159                     BeanUtils.copyProperties(newForwardConfig, forwardConfig);
    1160                 } catch (Exception e) {
    1161                     handleCreationException(baseConfigClassName, e);
    1162                 }
    1163 
    1164                 // replace forwardConfig with newForwardConfig
    1165                 if (actionConfig != null) {
    1166                     actionConfig.removeForwardConfig(forwardConfig);
    1167                     actionConfig.addForwardConfig(newForwardConfig);
    1168                 } else {
    1169                     // this is a global forward
    1170                     moduleConfig.removeForwardConfig(forwardConfig);
    1171                     moduleConfig.addForwardConfig(newForwardConfig);
    1172                 }
    1173                 forwardConfig = newForwardConfig;
    1174             }
    1175         }
    1176 
    1177         return forwardConfig;
    1178     }
    1179 
    1180     /**
    1181      * <p>Initialize the exception handlers for the specified module.</p>
    1182      *
    1183      * @param config ModuleConfig information for this module
    1184      * @throws ServletException if initialization cannot be performed
    1185      * @since Struts 1.3
    1186      */
    1187     protected void initModuleExceptionConfigs(ModuleConfig config)
    1188         throws ServletException {
    1189         if (log.isDebugEnabled()) {
    1190             log.debug("Initializing module path '" + config.getPrefix()
    1191                 + "' forwards");
    1192         }
    1193 
    1194         // Process exception config extensions.
    1195         ExceptionConfig[] exceptions = config.findExceptionConfigs();
    1196 
    1197         for (int i = 0; i < exceptions.length; i++) {
    1198             ExceptionConfig exception = exceptions[i];
    1199 
    1200             processExceptionExtension(exception, config, null);
    1201         }
    1202 
    1203         for (int i = 0; i < exceptions.length; i++) {
    1204             ExceptionConfig exception = exceptions[i];
    1205 
    1206             // Verify that required fields are all present for the config
    1207             if (exception.getKey() == null) {
    1208                 handleValueRequiredException("key", exception.getType(),
    1209                     "global exception config");
    1210             }
    1211         }
    1212     }
    1213 
    1214     /**
    1215      * <p>Extend the exception's configuration as necessary. If actionConfig is
    1216      * provided, then this method will process the exceptionConfig as part
    1217      * of that actionConfig.  If actionConfig is null, the exceptionConfig
    1218      * will be processed as a global forward.</p>
    1219      *
    1220      * @param exceptionConfig the configuration to process.
    1221      * @param moduleConfig    the module configuration for this module.
    1222      * @param actionConfig  If applicable, the config for the current action.
    1223      * @throws ServletException if initialization cannot be performed.
    1224      */
    1225     protected void processExceptionExtension(ExceptionConfig exceptionConfig,
    1226         ModuleConfig moduleConfig, ActionConfig actionConfig)
    1227         throws ServletException {
    1228         try {
    1229             if (!exceptionConfig.isExtensionProcessed()) {
    1230                 if (log.isDebugEnabled()) {
    1231                     log.debug("Processing extensions for '"
    1232                         + exceptionConfig.getType() + "'");
    1233                 }
    1234 
    1235                 exceptionConfig =
    1236                     processExceptionConfigClass(exceptionConfig, moduleConfig,
    1237                         actionConfig);
    1238 
    1239                 exceptionConfig.processExtends(moduleConfig, actionConfig);
    1240             }
    1241         } catch (ServletException e) {
    1242             throw e;
    1243         } catch (Exception e) {
    1244             handleGeneralExtensionException("Exception",
    1245                 exceptionConfig.getType(), e);
    1246         }
    1247     }
    1248 
    1249     /**
    1250      * <p>Checks if the current exceptionConfig is using the correct class
    1251      * based on the class of its configuration ancestor. If actionConfig is
    1252      * provided, then this method will process the exceptionConfig as part
    1253      * of that actionConfig.  If actionConfig is null, the exceptionConfig
    1254      * will be processed as a global forward.</p>
    1255      *
    1256      * @param exceptionConfig The config to check.
    1257      * @param moduleConfig    The config for the current module.
    1258      * @param actionConfig  If applicable, the config for the current action.
    1259      * @return The exception config using the correct class as determined by
    1260      *         the config's ancestor and its own overridden value.
    1261      * @throws ServletException if an instance of the exception config class
    1262      *                          cannot be created.
    1263      */
    1264     protected ExceptionConfig processExceptionConfigClass(
    1265         ExceptionConfig exceptionConfig, ModuleConfig moduleConfig,
    1266         ActionConfig actionConfig)
    1267         throws ServletException {
    1268         String ancestor = exceptionConfig.getExtends();
    1269 
    1270         if (ancestor == null) {
    1271             // Nothing to do, then
    1272             return exceptionConfig;
    1273         }
    1274 
    1275         // Make sure that this config is of the right class
    1276         ExceptionConfig baseConfig = null;
    1277         if (actionConfig != null) {
    1278             baseConfig = actionConfig.findExceptionConfig(ancestor);
    1279         }
    1280 
    1281         if (baseConfig == null) {
    1282             // This means either there's no actionConfig anyway, or the
    1283             // ancestor is not defined within the action.
    1284             baseConfig = moduleConfig.findExceptionConfig(ancestor);
    1285         }
    1286 
    1287         if (baseConfig == null) {
    1288             throw new UnavailableException("Unable to find "
    1289                 + "exception config '" + ancestor + "' to extend.");
    1290         }
    1291 
    1292         // Was our config's class overridden already?
    1293         if (exceptionConfig.getClass().equals(ExceptionConfig.class)) {
    1294             // Ensure that our config is using the correct class
    1295             if (!baseConfig.getClass().equals(exceptionConfig.getClass())) {
    1296                 // Replace the config with an instance of the correct class
    1297                 ExceptionConfig newExceptionConfig = null;
    1298                 String baseConfigClassName = baseConfig.getClass().getName();
    1299 
    1300                 try {
    1301                     newExceptionConfig =
    1302                         (ExceptionConfig) RequestUtils.applicationInstance(
    1303                             baseConfigClassName);
    1304 
    1305                     // copy the values
    1306                     BeanUtils.copyProperties(newExceptionConfig,
    1307                         exceptionConfig);
    1308                 } catch (Exception e) {
    1309                     handleCreationException(baseConfigClassName, e);
    1310                 }
    1311 
    1312                 // replace exceptionConfig with newExceptionConfig
    1313                 if (actionConfig != null) {
    1314                     actionConfig.removeExceptionConfig(exceptionConfig);
    1315                     actionConfig.addExceptionConfig(newExceptionConfig);
    1316                 } else {
    1317                     moduleConfig.removeExceptionConfig(exceptionConfig);
    1318                     moduleConfig.addExceptionConfig(newExceptionConfig);
    1319                 }
    1320                 exceptionConfig = newExceptionConfig;
    1321             }
    1322         }
    1323 
    1324         return exceptionConfig;
    1325     }
    1326 
    1327     /**
    1328      * <p>Initialize the action configs for the specified module.</p>
    1329      *
    1330      * @param config ModuleConfig information for this module
    1331      * @throws ServletException if initialization cannot be performed
    1332      * @since Struts 1.3
    1333      */
    1334     protected void initModuleActions(ModuleConfig config)
    1335         throws ServletException {
    1336         if (log.isDebugEnabled()) {
    1337             log.debug("Initializing module path '" + config.getPrefix()
    1338                 + "' action configs");
    1339         }
    1340 
    1341         // Process ActionConfig extensions.
    1342         ActionConfig[] actionConfigs = config.findActionConfigs();
    1343 
    1344         for (int i = 0; i < actionConfigs.length; i++) {
    1345             ActionConfig actionConfig = actionConfigs[i];
    1346 
    1347             processActionConfigExtension(actionConfig, config);
    1348         }
    1349 
    1350         for (int i = 0; i < actionConfigs.length; i++) {
    1351             ActionConfig actionConfig = actionConfigs[i];
    1352 
    1353             // Verify that required fields are all present for the forward
    1354             // configs
    1355             ForwardConfig[] forwards = actionConfig.findForwardConfigs();
    1356 
    1357             for (int j = 0; j < forwards.length; j++) {
    1358                 ForwardConfig forward = forwards[j];
    1359 
    1360                 if (forward.getPath() == null) {
    1361                     handleValueRequiredException("path", forward.getName(),
    1362                         "action forward");
    1363                 }
    1364             }
    1365 
    1366             // ... and the exception configs
    1367             ExceptionConfig[] exceptions = actionConfig.findExceptionConfigs();
    1368 
    1369             for (int j = 0; j < exceptions.length; j++) {
    1370                 ExceptionConfig exception = exceptions[j];
    1371 
    1372                 if (exception.getKey() == null) {
    1373                     handleValueRequiredException("key", exception.getType(),
    1374                         "action exception config");
    1375                 }
    1376             }
    1377         }
    1378     }
    1379 
    1380     /**
    1381      * <p>Extend the action's configuration as necessary.</p>
    1382      *
    1383      * @param actionConfig the configuration to process.
    1384      * @param moduleConfig the module configuration for this module.
    1385      * @throws ServletException if initialization cannot be performed.
    1386      */
    1387     protected void processActionConfigExtension(ActionConfig actionConfig,
    1388         ModuleConfig moduleConfig)
    1389         throws ServletException {
    1390         try {
    1391             if (!actionConfig.isExtensionProcessed()) {
    1392                 if (log.isDebugEnabled()) {
    1393                     log.debug("Processing extensions for '"
    1394                         + actionConfig.getPath() + "'");
    1395                 }
    1396 
    1397                 actionConfig =
    1398                     processActionConfigClass(actionConfig, moduleConfig);
    1399 
    1400                 actionConfig.processExtends(moduleConfig);
    1401             }
    1402 
    1403             // Process forwards extensions.
    1404             ForwardConfig[] forwards = actionConfig.findForwardConfigs();
    1405             for (int i = 0; i < forwards.length; i++) {
    1406                 ForwardConfig forward = forwards[i];
    1407                 processForwardExtension(forward, moduleConfig, actionConfig);
    1408             }
    1409 
    1410             // Process exception extensions.
    1411             ExceptionConfig[] exceptions = actionConfig.findExceptionConfigs();
    1412             for (int i = 0; i < exceptions.length; i++) {
    1413                 ExceptionConfig exception = exceptions[i];
    1414                 processExceptionExtension(exception, moduleConfig,
    1415                     actionConfig);
    1416             }
    1417         } catch (ServletException e) {
    1418             throw e;
    1419         } catch (Exception e) {
    1420             handleGeneralExtensionException("Action", actionConfig.getPath(), e);
    1421         }
    1422     }
    1423 
    1424     /**
    1425      * <p>Checks if the current actionConfig is using the correct class based
    1426      * on the class of its ancestor ActionConfig.</p>
    1427      *
    1428      * @param actionConfig The action config to check.
    1429      * @param moduleConfig The config for the current module.
    1430      * @return The config object using the correct class as determined by the
    1431      *         config's ancestor and its own overridden value.
    1432      * @throws ServletException if an instance of the action config class
    1433      *                          cannot be created.
    1434      */
    1435     protected ActionConfig processActionConfigClass(ActionConfig actionConfig,
    1436         ModuleConfig moduleConfig)
    1437         throws ServletException {
    1438         String ancestor = actionConfig.getExtends();
    1439 
    1440         if (ancestor == null) {
    1441             // Nothing to do, then
    1442             return actionConfig;
    1443         }
    1444 
    1445         // Make sure that this config is of the right class
    1446         ActionConfig baseConfig = moduleConfig.findActionConfig(ancestor);
    1447 
    1448         if (baseConfig == null) {
    1449             throw new UnavailableException("Unable to find "
    1450                 + "action config for '" + ancestor + "' to extend.");
    1451         }
    1452 
    1453         // Was our actionConfig's class overridden already?
    1454         if (actionConfig.getClass().equals(ActionMapping.class)) {
    1455             // Ensure that our config is using the correct class
    1456             if (!baseConfig.getClass().equals(actionConfig.getClass())) {
    1457                 // Replace the config with an instance of the correct class
    1458                 ActionConfig newActionConfig = null;
    1459                 String baseConfigClassName = baseConfig.getClass().getName();
    1460 
    1461                 try {
    1462                     newActionConfig =
    1463                         (ActionConfig) RequestUtils.applicationInstance(baseConfigClassName);
    1464 
    1465                     // copy the values
    1466                     BeanUtils.copyProperties(newActionConfig, actionConfig);
    1467 
    1468                     // copy the forward and exception configs, too
    1469                     ForwardConfig[] forwards =
    1470                         actionConfig.findForwardConfigs();
    1471 
    1472                     for (int i = 0; i < forwards.length; i++) {
    1473                         newActionConfig.addForwardConfig(forwards[i]);
    1474                     }
    1475 
    1476                     ExceptionConfig[] exceptions =
    1477                         actionConfig.findExceptionConfigs();
    1478 
    1479                     for (int i = 0; i < exceptions.length; i++) {
    1480                         newActionConfig.addExceptionConfig(exceptions[i]);
    1481                     }
    1482                 } catch (Exception e) {
    1483                     handleCreationException(baseConfigClassName, e);
    1484                 }
    1485 
    1486                 // replace actionConfig with newActionConfig
    1487                 moduleConfig.removeActionConfig(actionConfig);
    1488                 moduleConfig.addActionConfig(newActionConfig);
    1489                 actionConfig = newActionConfig;
    1490             }
    1491         }
    1492 
    1493         return actionConfig;
    1494     }
    1495 
    1496     /**
    1497      * <p>Initialize the application <code>MessageResources</code> for the
    1498      * specified module.</p>
    1499      *
    1500      * @param config ModuleConfig information for this module
    1501      * @throws ServletException if initialization cannot be performed
    1502      * @since Struts 1.1
    1503      */
    1504     protected void initModuleMessageResources(ModuleConfig config)
    1505         throws ServletException {
    1506         MessageResourcesConfig[] mrcs = config.findMessageResourcesConfigs();
    1507 
    1508         for (int i = 0; i < mrcs.length; i++) {
    1509             if ((mrcs[i].getFactory() == null)
    1510                 || (mrcs[i].getParameter() == null)) {
    1511                 continue;
    1512             }
    1513 
    1514             if (log.isDebugEnabled()) {
    1515                 log.debug("Initializing module path '" + config.getPrefix()
    1516                     + "' message resources from '" + mrcs[i].getParameter()
    1517                     + "'");
    1518             }
    1519 
    1520             String factory = mrcs[i].getFactory();
    1521 
    1522             MessageResourcesFactory.setFactoryClass(factory);
    1523 
    1524             MessageResourcesFactory factoryObject =
    1525                 MessageResourcesFactory.createFactory();
    1526 
    1527             factoryObject.setConfig(mrcs[i]);
    1528 
    1529             MessageResources resources =
    1530                 factoryObject.createResources(mrcs[i].getParameter());
    1531 
    1532             resources.setReturnNull(mrcs[i].getNull());
    1533             resources.setEscape(mrcs[i].isEscape());
    1534             getServletContext().setAttribute(mrcs[i].getKey()
    1535                 + config.getPrefix(), resources);
    1536         }
    1537     }
    1538 
    1539     /**
    1540      * <p>Create (if needed) and return a new <code>Digester</code> instance
    1541      * that has been initialized to process Struts module configuration files
    1542      * and configure a corresponding <code>ModuleConfig</code> object (which
    1543      * must be pushed on to the evaluation stack before parsing begins).</p>
    1544      *
    1545      * @return A new configured <code>Digester</code> instance.
    1546      * @throws ServletException if a Digester cannot be configured
    1547      * @since Struts 1.1
    1548      */
    1549     protected Digester initConfigDigester()
    1550         throws ServletException {
    1551         // :FIXME: Where can ServletException be thrown?
    1552         // Do we have an existing instance?
    1553         if (configDigester != null) {
    1554             return (configDigester);
    1555         }
    1556 
    1557         // Create a new Digester instance with standard capabilities
    1558         configDigester = new Digester();
    1559         configDigester.setNamespaceAware(true);
    1560         configDigester.setValidating(this.isValidating());
    1561         configDigester.setUseContextClassLoader(true);
    1562         configDigester.addRuleSet(new ConfigRuleSet());
    1563 
    1564         for (int i = 0; i < registrations.length; i += 2) {
    1565             URL url = this.getClass().getResource(registrations[i + 1]);
    1566 
    1567             if (url != null) {
    1568                 configDigester.register(registrations[i], url.toString());
    1569             }
    1570         }
    1571 
    1572         this.addRuleSets();
    1573 
    1574         // Return the completely configured Digester instance
    1575         return (configDigester);
    1576     }
    1577 
    1578     /**
    1579      * <p>Add any custom RuleSet instances to configDigester that have been
    1580      * specified in the <code>rulesets</code> init parameter.</p>
    1581      *
    1582      * @throws ServletException if an error occurs
    1583      */
    1584     private void addRuleSets()
    1585         throws ServletException {
    1586         String rulesets = getServletConfig().getInitParameter("rulesets");
    1587 
    1588         if (rulesets == null) {
    1589             rulesets = "";
    1590         }
    1591 
    1592         rulesets = rulesets.trim();
    1593 
    1594         String ruleset;
    1595 
    1596         while (rulesets.length() > 0) {
    1597             int comma = rulesets.indexOf(",");
    1598 
    1599             if (comma < 0) {
    1600                 ruleset = rulesets.trim();
    1601                 rulesets = "";
    1602             } else {
    1603                 ruleset = rulesets.substring(0, comma).trim();
    1604                 rulesets = rulesets.substring(comma + 1).trim();
    1605             }
    1606 
    1607             if (log.isDebugEnabled()) {
    1608                 log.debug("Configuring custom Digester Ruleset of type "
    1609                     + ruleset);
    1610             }
    1611 
    1612             try {
    1613                 RuleSet instance =
    1614                     (RuleSet) RequestUtils.applicationInstance(ruleset);
    1615 
    1616                 this.configDigester.addRuleSet(instance);
    1617             } catch (Exception e) {
    1618                 log.error("Exception configuring custom Digester RuleSet", e);
    1619                 throw new ServletException(e);
    1620             }
    1621         }
    1622     }
    1623 
    1624     /**
    1625      * <p>Check the status of the <code>validating</code> initialization
    1626      * parameter.</p>
    1627      *
    1628      * @return true if the module Digester should validate.
    1629      */
    1630     private boolean isValidating() {
    1631         boolean validating = true;
    1632         String value = getServletConfig().getInitParameter("validating");
    1633 
    1634         if ("false".equalsIgnoreCase(value) || "no".equalsIgnoreCase(value)
    1635             || "n".equalsIgnoreCase(value) || "0".equalsIgnoreCase(value)) {
    1636             validating = false;
    1637         }
    1638 
    1639         return validating;
    1640     }
    1641 
    1642     /**
    1643      * <p>Initialize our internal MessageResources bundle.</p>
    1644      *
    1645      * @throws ServletException     if we cannot initialize these resources
    1646      * @throws UnavailableException if we cannot load  resources
    1647      */
    1648     protected void initInternal()
    1649         throws ServletException {
    1650         try {
    1651             internal = MessageResources.getMessageResources(internalName);
    1652         } catch (MissingResourceException e) {
    1653             log.error("Cannot load internal resources from '" + internalName
    1654                 + "'", e);
    1655             throw new UnavailableException(
    1656                 "Cannot load internal resources from '" + internalName + "'");
    1657         }
    1658     }
    1659 
    1660     /**
    1661      * <p>Parse the configuration documents specified by the
    1662      * <code>chainConfig</code> init-param to configure the default {@link
    1663      * org.apache.commons.chain.Catalog} that is registered in the {@link
    1664      * CatalogFactory} instance for this application.</p>
    1665      *
    1666      * @throws ServletException if an error occurs.
    1667      */
    1668     protected void initChain()
    1669         throws ServletException {
    1670         // Parse the configuration file specified by path or resource
    1671         try {
    1672             String value;
    1673 
    1674             value = getServletConfig().getInitParameter("chainConfig");
    1675 
    1676             if (value != null) {
    1677                 chainConfig = value;
    1678             }
    1679 
    1680             ConfigParser parser = new ConfigParser();
    1681             List urls = splitAndResolvePaths(chainConfig);
    1682             URL resource;
    1683 
    1684             for (Iterator i = urls.iterator(); i.hasNext();) {
    1685                 resource = (URL) i.next();
    1686                 log.info("Loading chain catalog from " + resource);
    1687                 parser.parse(resource);
    1688             }
    1689         } catch (Exception e) {
    1690             log.error("Exception loading resources", e);
    1691             throw new ServletException(e);
    1692         }
    1693     }
    1694 
    1695     /**
    1696      * <p>Initialize other global characteristics of the controller
    1697      * servlet.</p>
    1698      *
    1699      * @throws ServletException if we cannot initialize these resources
    1700      */
    1701     protected void initOther()
    1702         throws ServletException {
    1703         String value;
    1704 
    1705         value = getServletConfig().getInitParameter("config");
    1706 
    1707         if (value != null) {
    1708             config = value;
    1709         }
    1710 
    1711         // Backwards compatibility for form beans of Java wrapper classes
    1712         // Set to true for strict Struts 1.0 compatibility
    1713         value = getServletConfig().getInitParameter("convertNull");
    1714 
    1715         if ("true".equalsIgnoreCase(value) || "yes".equalsIgnoreCase(value)
    1716             || "on".equalsIgnoreCase(value) || "y".equalsIgnoreCase(value)
    1717             || "1".equalsIgnoreCase(value)) {
    1718             convertNull = true;
    1719         }
    1720 
    1721         if (convertNull) {
    1722             ConvertUtils.deregister();
    1723             ConvertUtils.register(new BigDecimalConverter(null),
    1724                 BigDecimal.class);
    1725             ConvertUtils.register(new BigIntegerConverter(null),
    1726                 BigInteger.class);
    1727             ConvertUtils.register(new BooleanConverter(null), Boolean.class);
    1728             ConvertUtils.register(new ByteConverter(null), Byte.class);
    1729             ConvertUtils.register(new CharacterConverter(null), Character.class);
    1730             ConvertUtils.register(new DoubleConverter(null), Double.class);
    1731             ConvertUtils.register(new FloatConverter(null), Float.class);
    1732             ConvertUtils.register(new IntegerConverter(null), Integer.class);
    1733             ConvertUtils.register(new LongConverter(null), Long.class);
    1734             ConvertUtils.register(new ShortConverter(null), Short.class);
    1735         }
    1736     }
    1737 
    1738     /**
    1739      * <p>Initialize the servlet mapping under which our controller servlet is
    1740      * being accessed.  This will be used in the <code>.html.md:form&gt;</code>
    1741      * tag to generate correct destination URLs for form submissions.</p>
    1742      *
    1743      * @throws ServletException if error happens while scanning web.xml
    1744      */
    1745     protected void initServlet()
    1746         throws ServletException {
    1747         // Remember our servlet name
    1748         this.servletName = getServletConfig().getServletName();
    1749 
    1750         // Prepare a Digester to scan the web application deployment descriptor
    1751         Digester digester = new Digester();
    1752 
    1753         digester.push(this);
    1754         digester.setNamespaceAware(true);
    1755         digester.setValidating(false);
    1756 
    1757         // Register our local copy of the DTDs that we can find
    1758         for (int i = 0; i < registrations.length; i += 2) {
    1759             URL url = this.getClass().getResource(registrations[i + 1]);
    1760 
    1761             if (url != null) {
    1762                 digester.register(registrations[i], url.toString());
    1763             }
    1764         }
    1765 
    1766         // Configure the processing rules that we need
    1767         digester.addCallMethod("web-app/servlet-mapping", "addServletMapping", 2);
    1768         digester.addCallParam("web-app/servlet-mapping/servlet-name", 0);
    1769         digester.addCallParam("web-app/servlet-mapping/url-pattern", 1);
    1770 
    1771         // Process the web application deployment descriptor
    1772         if (log.isDebugEnabled()) {
    1773             log.debug("Scanning web.xml for controller servlet mapping");
    1774         }
    1775 
    1776         InputStream input =
    1777             getServletContext().getResourceAsStream("/WEB-INF/web.xml");
    1778 
    1779         if (input == null) {
    1780             log.error(internal.getMessage("configWebXml"));
    1781             throw new ServletException(internal.getMessage("configWebXml"));
    1782         }
    1783 
    1784         try {
    1785             digester.parse(input);
    1786         } catch (IOException e) {
    1787             log.error(internal.getMessage("configWebXml"), e);
    1788             throw new ServletException(e);
    1789         } catch (SAXException e) {
    1790             log.error(internal.getMessage("configWebXml"), e);
    1791             throw new ServletException(e);
    1792         } finally {
    1793             try {
    1794                 input.close();
    1795             } catch (IOException e) {
    1796                 log.error(internal.getMessage("configWebXml"), e);
    1797                 throw new ServletException(e);
    1798             }
    1799         }
    1800 
    1801         // Record a servlet context attribute (if appropriate)
    1802         if (log.isDebugEnabled()) {
    1803             log.debug("Mapping for servlet '" + servletName + "' = '"
    1804                 + servletMapping + "'");
    1805         }
    1806 
    1807         if (servletMapping != null) {
    1808             getServletContext().setAttribute(Globals.SERVLET_KEY, servletMapping);
    1809         }
    1810     }
    1811 
    1812     /**
    1813      * <p>Takes a comma-delimited string and splits it into paths, then
    1814      * resolves those paths using the ServletContext and appropriate
    1815      * ClassLoader.  When loading from the classloader, multiple resources per
    1816      * path are supported to support, for example, multiple jars containing
    1817      * the same named config file.</p>
    1818      *
    1819      * @param paths A comma-delimited string of paths
    1820      * @return A list of resolved URL's for all found resources
    1821      * @throws ServletException if a servlet exception is thrown
    1822      */
    1823     protected List splitAndResolvePaths(String paths)
    1824         throws ServletException {
    1825         ClassLoader loader = Thread.currentThread().getContextClassLoader();
    1826 
    1827         if (loader == null) {
    1828             loader = this.getClass().getClassLoader();
    1829         }
    1830 
    1831         ArrayList resolvedUrls = new ArrayList();
    1832 
    1833         URL resource;
    1834         String path = null;
    1835 
    1836         try {
    1837             // Process each specified resource path
    1838             while (paths.length() > 0) {
    1839                 resource = null;
    1840 
    1841                 int comma = paths.indexOf(',');
    1842 
    1843                 if (comma >= 0) {
    1844                     path = paths.substring(0, comma).trim();
    1845                     paths = paths.substring(comma + 1);
    1846                 } else {
    1847                     path = paths.trim();
    1848                     paths = "";
    1849                 }
    1850 
    1851                 if (path.length() < 1) {
    1852                     break;
    1853                 }
    1854 
    1855                 if (path.charAt(0) == '/') {
    1856                     resource = getServletContext().getResource(path);
    1857                 }
    1858 
    1859                 if (resource == null) {
    1860                     if (log.isDebugEnabled()) {
    1861                         log.debug("Unable to locate " + path
    1862                             + " in the servlet context, "
    1863                             + "trying classloader.");
    1864                     }
    1865 
    1866                     Enumeration e = loader.getResources(path);
    1867 
    1868                     if (!e.hasMoreElements()) {
    1869                         String msg = internal.getMessage("configMissing", path);
    1870 
    1871                         log.error(msg);
    1872                         throw new UnavailableException(msg);
    1873                     } else {
    1874                         while (e.hasMoreElements()) {
    1875                             resolvedUrls.add(e.nextElement());
    1876                         }
    1877                     }
    1878                 } else {
    1879                     resolvedUrls.add(resource);
    1880                 }
    1881             }
    1882         } catch (MalformedURLException e) {
    1883             handleConfigException(path, e);
    1884         } catch (IOException e) {
    1885             handleConfigException(path, e);
    1886         }
    1887 
    1888         return resolvedUrls;
    1889     }
    1890 
    1891     /**
    1892      * <p>Perform the standard request processing for this request, and create
    1893      * the corresponding response.</p>
    1894      *
    1895      * @param request  The servlet request we are processing
    1896      * @param response The servlet response we are creating
    1897      * @throws IOException      if an input/output error occurs
    1898      * @throws ServletException if a servlet exception is thrown
    1899      */
    1900     protected void process(HttpServletRequest request,
    1901         HttpServletResponse response)
    1902         throws IOException, ServletException {
    1903         ModuleUtils.getInstance().selectModule(request, getServletContext());
    1904 
    1905         ModuleConfig config = getModuleConfig(request);
    1906 
    1907         RequestProcessor processor = getProcessorForModule(config);
    1908 
    1909         if (processor == null) {
    1910             processor = getRequestProcessor(config);
    1911         }
    1912 
    1913         processor.process(request, response);
    1914     }
    1915 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
