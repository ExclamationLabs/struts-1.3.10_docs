[View Javadoc](../../../../../apidocs/org/apache/struts/chain/ComposableRequestProcessor.html.md)


    1   /*
    2    * $Id: ComposableRequestProcessor.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain;
    22  
    23  import org.apache.commons.beanutils.ConstructorUtils;
    24  import org.apache.commons.chain.Catalog;
    25  import org.apache.commons.chain.CatalogFactory;
    26  import org.apache.commons.chain.Command;
    27  import org.apache.commons.logging.Log;
    28  import org.apache.commons.logging.LogFactory;
    29  import org.apache.struts.action.ActionServlet;
    30  import org.apache.struts.action.RequestProcessor;
    31  import org.apache.struts.chain.contexts.ActionContext;
    32  import org.apache.struts.chain.contexts.ServletActionContext;
    33  import org.apache.struts.config.ControllerConfig;
    34  import org.apache.struts.config.ModuleConfig;
    35  import org.apache.struts.upload.MultipartRequestWrapper;
    36  import org.apache.struts.util.RequestUtils;
    37  
    38  import javax.servlet.ServletContext;
    39  import javax.servlet.ServletException;
    40  import javax.servlet.UnavailableException;
    41  import javax.servlet.http.HttpServletRequest;
    42  import javax.servlet.http.HttpServletResponse;
    43  
    44  import java.io.IOException;
    45  
    46  import java.lang.reflect.Constructor;
    47  
    48  /**
    49   * <p> ComposableRequestProcessor uses the Chain Of Resposibility design
    50   * pattern (as implemented by the commons-chain package in Jakarta Commons) to
    51   * support external configuration of command chains to be used.  It is
    52   * configured via the following context initialization parameters: </p>
    53   *
    54   * <ul>
    55   *
    56   * <li>[org.apache.struts.chain.CATALOG_NAME] - Name of the Catalog in which
    57   * we will look up the Command to be executed for each request.  If not
    58   * specified, the default value is struts. </li>
    59   *
    60   * <li> org.apache.struts.chain.COMMAND_NAME - Name of the Command which we
    61   * will execute for each request, to be looked up in the specified Catalog.
    62   * If not specified, the default value is servlet-standard. </li>
    63   *
    64   * </ul>
    65   *
    66   * @version $Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005)
    67   *          $
    68   * @since Struts 1.1
    69   */
    70  public class ComposableRequestProcessor extends RequestProcessor {
    71      // ------------------------------------------------------ Instance Variables
    72  
    73      /**
    74       * <p> Cache for constructor discovered by setActionContextClass method.
    75       * </p>
    76       */
    77      private static final Class[] SERVLET_ACTION_CONTEXT_CTOR_SIGNATURE =
    78          new Class[] {
    79              ServletContext.class, HttpServletRequest.class,
    80              HttpServletResponse.class
    81          };
    82  
    83      /**
    84       * <p> Token for ActionContext clazss so that it can be stored in the
    85       * ControllerConfig. </p>
    86       */
    87      public static final String ACTION_CONTEXT_CLASS = "ACTION_CONTEXT_CLASS";
    88  
    89      /**
    90       * <p>The <code>Log</code> instance for this class.</p>
    91       */
    92      protected static final Log LOG =
    93          LogFactory.getLog(ComposableRequestProcessor.class);
    94  
    95      /**
    96       * <p>The {@link CatalogFactory} from which catalog containing the the
    97       * base request-processing {@link Command} will be retrieved.</p>
    98       */
    99      protected CatalogFactory catalogFactory = null;
    100 
    101     /**
    102      * <p>The {@link Catalog} containing all of the available command chains
    103      * for this module.
    104      */
    105     protected Catalog catalog = null;
    106 
    107     /**
    108      * <p>The {@link Command} to be executed for each request.</p>
    109      */
    110     protected Command command = null;
    111 
    112     /**
    113      * <p> ActionContext class as cached by createActionContextInstance
    114      * method. </p>
    115      */
    116     private Class actionContextClass;
    117 
    118     /**
    119      * <p> ActionContext constructor as cached by createActionContextInstance
    120      * method. </p>
    121      */
    122     private Constructor servletActionContextConstructor = null;
    123 
    124     // ---------------------------------------------------------- Public Methods
    125 
    126     /**
    127      * <p>Clean up in preparation for a shutdown of this application.</p>
    128      */
    129     public void destroy() {
    130         super.destroy();
    131         catalogFactory = null;
    132         catalog = null;
    133         command = null;
    134         actionContextClass = null;
    135         servletActionContextConstructor = null;
    136     }
    137 
    138     /**
    139      * <p>Initialize this request processor instance.</p>
    140      *
    141      * @param servlet      The ActionServlet we are associated with
    142      * @param moduleConfig The ModuleConfig we are associated with.
    143      * @throws ServletException If an error occurs during initialization
    144      */
    145     public void init(ActionServlet servlet, ModuleConfig moduleConfig)
    146         throws ServletException {
    147         LOG.info(
    148             "Initializing composable request processor for module prefix '"
    149             + moduleConfig.getPrefix() + "'");
    150         super.init(servlet, moduleConfig);
    151 
    152         initCatalogFactory(servlet, moduleConfig);
    153 
    154         ControllerConfig controllerConfig = moduleConfig.getControllerConfig();
    155 
    156         String catalogName = controllerConfig.getCatalog();
    157 
    158         catalog = this.catalogFactory.getCatalog(catalogName);
    159 
    160         if (catalog == null) {
    161             throw new ServletException("Cannot find catalog '" + catalogName
    162                 + "'");
    163         }
    164 
    165         String commandName = controllerConfig.getCommand();
    166 
    167         command = catalog.getCommand(commandName);
    168 
    169         if (command == null) {
    170             throw new ServletException("Cannot find command '" + commandName
    171                 + "'");
    172         }
    173 
    174         this.setActionContextClassName(controllerConfig.getProperty(
    175                 ACTION_CONTEXT_CLASS));
    176     }
    177 
    178     /**
    179      * <p> Set and cache ActionContext class. </p><p> If there is a custom
    180      * class provided and if it uses our "preferred" constructor, cache a
    181      * reference to that constructor rather than looking it up every time.
    182      * </p>
    183      *
    184      * @param actionContextClass The ActionContext class to process
    185      */
    186     private void setActionContextClass(Class actionContextClass) {
    187         this.actionContextClass = actionContextClass;
    188 
    189         if (actionContextClass != null) {
    190             this.servletActionContextConstructor =
    191                 ConstructorUtils.getAccessibleConstructor(actionContextClass,
    192                     SERVLET_ACTION_CONTEXT_CTOR_SIGNATURE);
    193         } else {
    194             this.servletActionContextConstructor = null;
    195         }
    196     }
    197 
    198     /**
    199      * <p>Make sure that the specified <code>className</code> identfies a
    200      * class which can be found and which implements the
    201      * <code>ActionContext</code> interface.</p>
    202      *
    203      * @param className Fully qualified name of
    204      * @throws ServletException     If an error occurs during initialization
    205      * @throws UnavailableException if class does not implement ActionContext
    206      *                              or is not found
    207      */
    208     private void setActionContextClassName(String className)
    209         throws ServletException {
    210         if ((className != null) && (className.trim().length() > 0)) {
    211             if (LOG.isDebugEnabled()) {
    212                 LOG.debug(
    213                     "setActionContextClassName: requested context class: "
    214                     + className);
    215             }
    216 
    217             try {
    218                 Class actionContextClass =
    219                     RequestUtils.applicationClass(className);
    220 
    221                 if (!ActionContext.class.isAssignableFrom(actionContextClass)) {
    222                     throw new UnavailableException("ActionContextClass " + "["
    223                         + className + "]"
    224                         + " must implement ActionContext interface.");
    225                 }
    226 
    227                 this.setActionContextClass(actionContextClass);
    228             } catch (ClassNotFoundException e) {
    229                 throw new UnavailableException("ActionContextClass "
    230                     + className + " not found.");
    231             }
    232         } else {
    233             if (LOG.isDebugEnabled()) {
    234                 LOG.debug("setActionContextClassName: no className specified");
    235             }
    236 
    237             this.setActionContextClass(null);
    238         }
    239     }
    240 
    241     /**
    242      * <p> Establish the CatalogFactory which will be used to look up the
    243      * catalog which has the request processing command. </p><p> The base
    244      * implementation simply calls CatalogFactory.getInstance(), unless the
    245      * catalogFactory property of this object has already been set, in which
    246      * case it is not changed. </p>
    247      *
    248      * @param servlet      The ActionServlet we are processing
    249      * @param moduleConfig The ModuleConfig we are processing
    250      */
    251     protected void initCatalogFactory(ActionServlet servlet,
    252         ModuleConfig moduleConfig) {
    253         if (this.catalogFactory != null) {
    254             return;
    255         }
    256 
    257         this.catalogFactory = CatalogFactory.getInstance();
    258     }
    259 
    260     /**
    261      * <p>Process an <code>HttpServletRequest</code> and create the
    262      * corresponding <code>HttpServletResponse</code>.</p>
    263      *
    264      * @param request  The servlet request we are processing
    265      * @param response The servlet response we are creating
    266      * @throws IOException      if an input/output error occurs
    267      * @throws ServletException if a processing exception occurs
    268      */
    269     public void process(HttpServletRequest request, HttpServletResponse response)
    270         throws IOException, ServletException {
    271         // Wrap the request in the case of a multipart request
    272         request = processMultipart(request);
    273 
    274         // Create and populate a Context for this request
    275         ActionContext context = contextInstance(request, response);
    276 
    277         // Create and execute the command.
    278         try {
    279             if (LOG.isDebugEnabled()) {
    280                 LOG.debug("Using processing chain for this request");
    281             }
    282 
    283             command.execute(context);
    284         } catch (Exception e) {
    285             // Execute the exception processing chain??
    286             throw new ServletException(e);
    287         }
    288 
    289         // Release the context.
    290         context.release();
    291     }
    292 
    293     /**
    294      * <p>Provide the initialized <code>ActionContext</code> instance which
    295      * will be used by this request. Internally, this simply calls
    296      * <code>createActionContextInstance</code> followed by
    297      * <code>initializeActionContext</code>.</p>
    298      *
    299      * @param request  The servlet request we are processing
    300      * @param response The servlet response we are creating
    301      * @return Initiliazed ActionContext
    302      * @throws ServletException if a processing exception occurs
    303      */
    304     protected ActionContext contextInstance(HttpServletRequest request,
    305         HttpServletResponse response)
    306         throws ServletException {
    307         ActionContext context =
    308             createActionContextInstance(getServletContext(), request, response);
    309 
    310         initializeActionContext(context);
    311 
    312         return context;
    313     }
    314 
    315     /**
    316      * <p>Create a new instance of <code>ActionContext</code> according to
    317      * configuration.  If no alternative was specified at initialization, a
    318      * new instance <code>ServletActionContext</code> is returned.  If an
    319      * alternative was specified using the <code>ACTION_CONTEXT_CLASS</code>
    320      * property, then that value is treated as a classname, and an instance of
    321      * that class is created.  If that class implements the same constructor
    322      * that <code>ServletActionContext</code> does, then that constructor will
    323      * be used: <code>ServletContext, HttpServletRequest,
    324      * HttpServletResponse</code>; otherwise, it is assumed that the class has
    325      * a no-arguments constructor.  If these constraints do not suit you,
    326      * simply override this method in a subclass.</p>
    327      *
    328      * @param servletContext The servlet context we are processing
    329      * @param request        The servlet request we are processing
    330      * @param response       The servlet response we are creating
    331      * @return New instance of ActionContext
    332      * @throws ServletException if a processing exception occurs
    333      */
    334     protected ActionContext createActionContextInstance(
    335         ServletContext servletContext, HttpServletRequest request,
    336         HttpServletResponse response)
    337         throws ServletException {
    338         if (this.actionContextClass == null) {
    339             return new ServletActionContext(servletContext, request, response);
    340         }
    341 
    342         try {
    343             if (this.servletActionContextConstructor == null) {
    344                 return (ActionContext) this.actionContextClass.newInstance();
    345             }
    346 
    347             return (ActionContext) this.servletActionContextConstructor
    348             .newInstance(new Object[] { servletContext, request, response });
    349         } catch (Exception e) {
    350             throw new ServletException(
    351                 "Error creating ActionContext instance of type "
    352                 + this.actionContextClass, e);
    353         }
    354     }
    355 
    356     /**
    357      * <p>Set common properties on the given <code>ActionContext</code>
    358      * instance so that commands in the chain can count on their presence.
    359      * Note that while this method does not require that its argument be an
    360      * instance of <code>ServletActionContext</code>, at this time many common
    361      * Struts commands will be expecting to receive an <code>ActionContext</code>
    362      * which is also a <code>ServletActionContext</code>.</p>
    363      *
    364      * @param context The ActionContext we are processing
    365      */
    366     protected void initializeActionContext(ActionContext context) {
    367         if (context instanceof ServletActionContext) {
    368             ((ServletActionContext) context).setActionServlet(this.servlet);
    369         }
    370 
    371         context.setModuleConfig(this.moduleConfig);
    372     }
    373 
    374     /**
    375      * <p>If this is a multipart request, wrap it with a special wrapper.
    376      * Otherwise, return the request unchanged.</p>
    377      *
    378      * @param request The HttpServletRequest we are processing
    379      * @return Original or wrapped request as appropriate
    380      */
    381     protected HttpServletRequest processMultipart(HttpServletRequest request) {
    382         if (!"POST".equalsIgnoreCase(request.getMethod())) {
    383             return (request);
    384         }
    385 
    386         String contentType = request.getContentType();
    387 
    388         if ((contentType != null)
    389             && contentType.startsWith("multipart/form-data")) {
    390             return (new MultipartRequestWrapper(request));
    391         } else {
    392             return (request);
    393         }
    394     }
    395 
    396     /**
    397      * <p>Set the <code>CatalogFactory</code> instance which should be used to
    398      * find the request-processing command.  In the base implementation, if
    399      * this value is not already set, then it will be initialized when {@link
    400      * #initCatalogFactory} is called. </p>
    401      *
    402      * @param catalogFactory Our CatalogFactory instance
    403      */
    404     public void setCatalogFactory(CatalogFactory catalogFactory) {
    405         this.catalogFactory = catalogFactory;
    406     }
    407 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
