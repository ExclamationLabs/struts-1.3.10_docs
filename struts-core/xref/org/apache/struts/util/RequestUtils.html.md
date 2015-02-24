[View Javadoc](../../../../../apidocs/org/apache/struts/util/RequestUtils.html.md)


    1   /*
    2    * $Id: RequestUtils.java 560654 2007-07-29 01:54:02Z niallp $
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
    21  package org.apache.struts.util;
    22  
    23  import org.apache.commons.beanutils.BeanUtils;
    24  import org.apache.commons.beanutils.PropertyUtils;
    25  import org.apache.commons.logging.Log;
    26  import org.apache.commons.logging.LogFactory;
    27  import org.apache.struts.Globals;
    28  import org.apache.struts.action.ActionForm;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.action.ActionServlet;
    31  import org.apache.struts.action.ActionServletWrapper;
    32  import org.apache.struts.config.ActionConfig;
    33  import org.apache.struts.config.FormBeanConfig;
    34  import org.apache.struts.config.ForwardConfig;
    35  import org.apache.struts.config.ModuleConfig;
    36  import org.apache.struts.upload.FormFile;
    37  import org.apache.struts.upload.MultipartRequestHandler;
    38  import org.apache.struts.upload.MultipartRequestWrapper;
    39  
    40  import javax.servlet.ServletContext;
    41  import javax.servlet.ServletException;
    42  import javax.servlet.http.HttpServletRequest;
    43  import javax.servlet.http.HttpSession;
    44  
    45  import java.lang.reflect.InvocationTargetException;
    46  import java.net.MalformedURLException;
    47  import java.net.URL;
    48  
    49  import java.util.ArrayList;
    50  import java.util.Collections;
    51  import java.util.Enumeration;
    52  import java.util.HashMap;
    53  import java.util.Hashtable;
    54  import java.util.List;
    55  import java.util.Locale;
    56  import java.util.Map;
    57  
    58  /**
    59   * <p>General purpose utility methods related to processing a servlet request
    60   * in the Struts controller framework.</p>
    61   *
    62   * @version $Rev: 560654 $ $Date: 2007-07-28 20:54:02 -0500 (Sat, 28 Jul 2007) $
    63   */
    64  public class RequestUtils {
    65      // ------------------------------------------------------- Static Variables
    66  
    67      /**
    68       * <p>Commons Logging instance.</p>
    69       */
    70      protected static Log log = LogFactory.getLog(RequestUtils.class);
    71  
    72      // --------------------------------------------------------- Public Methods
    73  
    74      /**
    75       * <p>Create and return an absolute URL for the specified context-relative
    76       * path, based on the server and context information in the specified
    77       * request.</p>
    78       *
    79       * @param request The servlet request we are processing
    80       * @param path    The context-relative path (must start with '/')
    81       * @return absolute URL based on context-relative path
    82       * @throws MalformedURLException if we cannot create an absolute URL
    83       */
    84      public static URL absoluteURL(HttpServletRequest request, String path)
    85          throws MalformedURLException {
    86          return (new URL(serverURL(request), request.getContextPath() + path));
    87      }
    88  
    89      /**
    90       * <p>Return the <code>Class</code> object for the specified fully
    91       * qualified class name, from this web application's class loader.</p>
    92       *
    93       * @param className Fully qualified class name to be loaded
    94       * @return Class object
    95       * @throws ClassNotFoundException if the class cannot be found
    96       */
    97      public static Class applicationClass(String className)
    98          throws ClassNotFoundException {
    99          return applicationClass(className, null);
    100     }
    101 
    102     /**
    103      * <p>Return the <code>Class</code> object for the specified fully
    104      * qualified class name, from this web application's class loader.</p>
    105      *
    106      * @param className   Fully qualified class name to be loaded
    107      * @param classLoader The desired classloader to use
    108      * @return Class object
    109      * @throws ClassNotFoundException if the class cannot be found
    110      */
    111     public static Class applicationClass(String className,
    112         ClassLoader classLoader)
    113         throws ClassNotFoundException {
    114         if (classLoader == null) {
    115             // Look up the class loader to be used
    116             classLoader = Thread.currentThread().getContextClassLoader();
    117 
    118             if (classLoader == null) {
    119                 classLoader = RequestUtils.class.getClassLoader();
    120             }
    121         }
    122 
    123         // Attempt to load the specified class
    124         return (classLoader.loadClass(className));
    125     }
    126 
    127     /**
    128      * <p>Return a new instance of the specified fully qualified class name,
    129      * after loading the class from this web application's class loader. The
    130      * specified class <strong>MUST</strong> have a public zero-arguments
    131      * constructor.</p>
    132      *
    133      * @param className Fully qualified class name to use
    134      * @return new instance of class
    135      * @throws ClassNotFoundException if the class cannot be found
    136      * @throws IllegalAccessException if the class or its constructor is not
    137      *                                accessible
    138      * @throws InstantiationException if this class represents an abstract
    139      *                                class, an interface, an array class, a
    140      *                                primitive type, or void
    141      * @throws InstantiationException if this class has no zero-arguments
    142      *                                constructor
    143      */
    144     public static Object applicationInstance(String className)
    145         throws ClassNotFoundException, IllegalAccessException,
    146             InstantiationException {
    147         return applicationInstance(className, null);
    148     }
    149 
    150     /**
    151      * <p>Return a new instance of the specified fully qualified class name,
    152      * after loading the class from this web application's class loader. The
    153      * specified class <strong>MUST</strong> have a public zero-arguments
    154      * constructor.</p>
    155      *
    156      * @param className   Fully qualified class name to use
    157      * @param classLoader The desired classloader to use
    158      * @return new instance of class
    159      * @throws ClassNotFoundException if the class cannot be found
    160      * @throws IllegalAccessException if the class or its constructor is not
    161      *                                accessible
    162      * @throws InstantiationException if this class represents an abstract
    163      *                                class, an interface, an array class, a
    164      *                                primitive type, or void
    165      * @throws InstantiationException if this class has no zero-arguments
    166      *                                constructor
    167      */
    168     public static Object applicationInstance(String className,
    169         ClassLoader classLoader)
    170         throws ClassNotFoundException, IllegalAccessException,
    171             InstantiationException {
    172         return (applicationClass(className, classLoader).newInstance());
    173     }
    174 
    175     /**
    176      * <p>Create (if necessary) and return an <code>ActionForm</code> instance
    177      * appropriate for this request.  If no <code>ActionForm</code> instance
    178      * is required, return <code>null</code>.</p>
    179      *
    180      * @param request      The servlet request we are processing
    181      * @param mapping      The action mapping for this request
    182      * @param moduleConfig The configuration for this module
    183      * @param servlet      The action servlet
    184      * @return ActionForm instance associated with this request
    185      */
    186     public static ActionForm createActionForm(HttpServletRequest request,
    187         ActionMapping mapping, ModuleConfig moduleConfig, ActionServlet servlet) {
    188         // Is there a form bean associated with this mapping?
    189         String attribute = mapping.getAttribute();
    190 
    191         if (attribute == null) {
    192             return (null);
    193         }
    194 
    195         // Look up the form bean configuration information to use
    196         String name = mapping.getName();
    197         FormBeanConfig config = moduleConfig.findFormBeanConfig(name);
    198 
    199         if (config == null) {
    200             log.warn("No FormBeanConfig found under '" + name + "'");
    201 
    202             return (null);
    203         }
    204 
    205         ActionForm instance =
    206             lookupActionForm(request, attribute, mapping.getScope());
    207 
    208         // Can we recycle the existing form bean instance (if there is one)?
    209         if ((instance != null) && config.canReuse(instance)) {
    210             return (instance);
    211         }
    212 
    213         return createActionForm(config, servlet);
    214     }
    215 
    216     private static ActionForm lookupActionForm(HttpServletRequest request,
    217         String attribute, String scope) {
    218         // Look up any existing form bean instance
    219         if (log.isDebugEnabled()) {
    220             log.debug(" Looking for ActionForm bean instance in scope '"
    221                 + scope + "' under attribute key '" + attribute + "'");
    222         }
    223 
    224         ActionForm instance = null;
    225         HttpSession session = null;
    226 
    227         if ("request".equals(scope)) {
    228             instance = (ActionForm) request.getAttribute(attribute);
    229         } else {
    230             session = request.getSession();
    231             instance = (ActionForm) session.getAttribute(attribute);
    232         }
    233 
    234         return (instance);
    235     }
    236 
    237     /**
    238      * <p>Create and return an <code>ActionForm</code> instance appropriate to
    239      * the information in <code>config</code>.</p>
    240      *
    241      * <p>Does not perform any checks to see if an existing ActionForm exists
    242      * which could be reused.</p>
    243      *
    244      * @param config  The configuration for the Form bean which is to be
    245      *                created.
    246      * @param servlet The action servlet
    247      * @return ActionForm instance associated with this request
    248      */
    249     public static ActionForm createActionForm(FormBeanConfig config,
    250         ActionServlet servlet) {
    251         if (config == null) {
    252             return (null);
    253         }
    254 
    255         ActionForm instance = null;
    256 
    257         // Create and return a new form bean instance
    258         try {
    259             instance = config.createActionForm(servlet);
    260 
    261             if (log.isDebugEnabled()) {
    262                 log.debug(" Creating new "
    263                     + (config.getDynamic() ? "DynaActionForm" : "ActionForm")
    264                     + " instance of type '" + config.getType() + "'");
    265                 log.trace(" --> " + instance);
    266             }
    267         } catch (Throwable t) {
    268             log.error(servlet.getInternal().getMessage("formBean",
    269                     config.getType()), t);
    270         }
    271 
    272         return (instance);
    273     }
    274 
    275     /**
    276      * <p>Retrieves the servlet mapping pattern for the specified {@link ActionServlet}.</p>
    277      *
    278      * @return the servlet mapping
    279      * @see Globals#SERVLET_KEY
    280      * @since Struts 1.3.6
    281      */
    282     public static String getServletMapping(ActionServlet servlet) {
    283         ServletContext servletContext = servlet.getServletConfig().getServletContext();
    284         return (String)servletContext.getAttribute(Globals.SERVLET_KEY);
    285     }
    286 
    287     /**
    288      * <p>Look up and return current user locale, based on the specified
    289      * parameters.</p>
    290      *
    291      * @param request The request used to lookup the Locale
    292      * @param locale  Name of the session attribute for our user's Locale.  If
    293      *                this is <code>null</code>, the default locale key is
    294      *                used for the lookup.
    295      * @return current user locale
    296      * @since Struts 1.2
    297      */
    298     public static Locale getUserLocale(HttpServletRequest request, String locale) {
    299         Locale userLocale = null;
    300         HttpSession session = request.getSession(false);
    301 
    302         if (locale == null) {
    303             locale = Globals.LOCALE_KEY;
    304         }
    305 
    306         // Only check session if sessions are enabled
    307         if (session != null) {
    308             userLocale = (Locale) session.getAttribute(locale);
    309         }
    310 
    311         if (userLocale == null) {
    312             // Returns Locale based on Accept-Language header or the server default
    313             userLocale = request.getLocale();
    314         }
    315 
    316         return userLocale;
    317     }
    318 
    319     /**
    320      * <p>Populate the properties of the specified JavaBean from the specified
    321      * HTTP request, based on matching each parameter name against the
    322      * corresponding JavaBeans "property setter" methods in the bean's class.
    323      * Suitable conversion is done for argument types as described under
    324      * <code>convert()</code>.</p>
    325      *
    326      * @param bean    The JavaBean whose properties are to be set
    327      * @param request The HTTP request whose parameters are to be used to
    328      *                populate bean properties
    329      * @throws ServletException if an exception is thrown while setting
    330      *                          property values
    331      */
    332     public static void populate(Object bean, HttpServletRequest request)
    333         throws ServletException {
    334         populate(bean, null, null, request);
    335     }
    336 
    337     /**
    338      * <p>Populate the properties of the specified JavaBean from the specified
    339      * HTTP request, based on matching each parameter name (plus an optional
    340      * prefix and/or suffix) against the corresponding JavaBeans "property
    341      * setter" methods in the bean's class. Suitable conversion is done for
    342      * argument types as described under <code>setProperties</code>.</p>
    343      *
    344      * <p>If you specify a non-null <code>prefix</code> and a non-null
    345      * <code>suffix</code>, the parameter name must match
    346      * <strong>both</strong> conditions for its value(s) to be used in
    347      * populating bean properties. If the request's content type is
    348      * "multipart/form-data" and the method is "POST", the
    349      * <code>HttpServletRequest</code> object will be wrapped in a
    350      * <code>MultipartRequestWrapper</code object.</p>
    351      *
    352      * @param bean    The JavaBean whose properties are to be set
    353      * @param prefix  The prefix (if any) to be prepend to bean property names
    354      *                when looking for matching parameters
    355      * @param suffix  The suffix (if any) to be appended to bean property
    356      *                names when looking for matching parameters
    357      * @param request The HTTP request whose parameters are to be used to
    358      *                populate bean properties
    359      * @throws ServletException if an exception is thrown while setting
    360      *                          property values
    361      */
    362     public static void populate(Object bean, String prefix, String suffix,
    363         HttpServletRequest request)
    364         throws ServletException {
    365         // Build a list of relevant request parameters from this request
    366         HashMap properties = new HashMap();
    367 
    368         // Iterator of parameter names
    369         Enumeration names = null;
    370 
    371         // Map for multipart parameters
    372         Map multipartParameters = null;
    373 
    374         String contentType = request.getContentType();
    375         String method = request.getMethod();
    376         boolean isMultipart = false;
    377 
    378         if (bean instanceof ActionForm) {
    379             ((ActionForm) bean).setMultipartRequestHandler(null);
    380         }
    381 
    382         MultipartRequestHandler multipartHandler = null;
    383         if ((contentType != null)
    384             && (contentType.startsWith("multipart/form-data"))
    385             && (method.equalsIgnoreCase("POST"))) {
    386             // Get the ActionServletWrapper from the form bean
    387             ActionServletWrapper servlet;
    388 
    389             if (bean instanceof ActionForm) {
    390                 servlet = ((ActionForm) bean).getServletWrapper();
    391             } else {
    392                 throw new ServletException("bean that's supposed to be "
    393                     + "populated from a multipart request is not of type "
    394                     + "\"org.apache.struts.action.ActionForm\", but type "
    395                     + "\"" + bean.getClass().getName() + "\"");
    396             }
    397 
    398             // Obtain a MultipartRequestHandler
    399             multipartHandler = getMultipartHandler(request);
    400 
    401             if (multipartHandler != null) {
    402                 isMultipart = true;
    403 
    404                 // Set servlet and mapping info
    405                 servlet.setServletFor(multipartHandler);
    406                 multipartHandler.setMapping((ActionMapping) request
    407                     .getAttribute(Globals.MAPPING_KEY));
    408 
    409                 // Initialize multipart request class handler
    410                 multipartHandler.handleRequest(request);
    411 
    412                 //stop here if the maximum length has been exceeded
    413                 Boolean maxLengthExceeded =
    414                     (Boolean) request.getAttribute(MultipartRequestHandler.ATTRIBUTE_MAX_LENGTH_EXCEEDED);
    415 
    416                 if ((maxLengthExceeded != null)
    417                     && (maxLengthExceeded.booleanValue())) {
    418                     ((ActionForm) bean).setMultipartRequestHandler(multipartHandler);
    419                     return;
    420                 }
    421 
    422                 //retrieve form values and put into properties
    423                 multipartParameters =
    424                     getAllParametersForMultipartRequest(request,
    425                         multipartHandler);
    426                 names = Collections.enumeration(multipartParameters.keySet());
    427             }
    428         }
    429 
    430         if (!isMultipart) {
    431             names = request.getParameterNames();
    432         }
    433 
    434         while (names.hasMoreElements()) {
    435             String name = (String) names.nextElement();
    436             String stripped = name;
    437 
    438             if (prefix != null) {
    439                 if (!stripped.startsWith(prefix)) {
    440                     continue;
    441                 }
    442 
    443                 stripped = stripped.substring(prefix.length());
    444             }
    445 
    446             if (suffix != null) {
    447                 if (!stripped.endsWith(suffix)) {
    448                     continue;
    449                 }
    450 
    451                 stripped =
    452                     stripped.substring(0, stripped.length() - suffix.length());
    453             }
    454 
    455             Object parameterValue = null;
    456 
    457             if (isMultipart) {
    458                 parameterValue = multipartParameters.get(name);
    459                 parameterValue = rationalizeMultipleFileProperty(bean, name, parameterValue);
    460             } else {
    461                 parameterValue = request.getParameterValues(name);
    462             }
    463 
    464             // Populate parameters, except "standard" struts attributes
    465             // such as 'org.apache.struts.action.CANCEL'
    466             if (!(stripped.startsWith("org.apache.struts."))) {
    467                 properties.put(stripped, parameterValue);
    468             }
    469         }
    470 
    471         // Set the corresponding properties of our bean
    472         try {
    473             BeanUtils.populate(bean, properties);
    474         } catch (Exception e) {
    475             throw new ServletException("BeanUtils.populate", e);
    476         } finally {
    477             if (multipartHandler != null) {
    478                 // Set the multipart request handler for our ActionForm.
    479                 // If the bean isn't an ActionForm, an exception would have been
    480                 // thrown earlier, so it's safe to assume that our bean is
    481                 // in fact an ActionForm.
    482                 ((ActionForm) bean).setMultipartRequestHandler(multipartHandler);
    483             }
    484         }
    485     }
    486 
    487     /**
    488      * <p>If the given form bean can accept multiple FormFile objects but the user only uploaded a single, then 
    489      * the property will not match the form bean type.  This method performs some simple checks to try to accommodate
    490      * that situation.</p>
    491      * @param bean
    492      * @param name
    493      * @param parameterValue
    494      * @return 
    495      * @throws ServletException if the introspection has any errors.
    496      */
    497     private static Object rationalizeMultipleFileProperty(Object bean, String name, Object parameterValue) throws ServletException {
    498         if (!(parameterValue instanceof FormFile)) {
    499             return parameterValue;
    500         }
    501 
    502         FormFile formFileValue = (FormFile) parameterValue;
    503         try {
    504             Class propertyType = PropertyUtils.getPropertyType(bean, name);
    505 
    506             if (List.class.isAssignableFrom(propertyType)) {
    507                 ArrayList list = new ArrayList(1);
    508                 list.add(formFileValue);
    509                 return list;
    510             }
    511 
    512             if (propertyType.isArray() && propertyType.getComponentType().equals(FormFile.class)) {
    513                 return new FormFile[] { formFileValue };
    514             }
    515 
    516         } catch (IllegalAccessException e) {
    517             throw new ServletException(e);
    518         } catch (InvocationTargetException e) {
    519             throw new ServletException(e);
    520         } catch (NoSuchMethodException e) {
    521             throw new ServletException(e);
    522         }
    523 
    524         // no changes
    525         return parameterValue;
    526 
    527     }
    528 
    529     /**
    530      * <p>Try to locate a multipart request handler for this request. First,
    531      * look for a mapping-specific handler stored for us under an attribute.
    532      * If one is not present, use the global multipart handler, if there is
    533      * one.</p>
    534      *
    535      * @param request The HTTP request for which the multipart handler should
    536      *                be found.
    537      * @return the multipart handler to use, or null if none is found.
    538      * @throws ServletException if any exception is thrown while attempting to
    539      *                          locate the multipart handler.
    540      */
    541     private static MultipartRequestHandler getMultipartHandler(
    542         HttpServletRequest request)
    543         throws ServletException {
    544         MultipartRequestHandler multipartHandler = null;
    545         String multipartClass =
    546             (String) request.getAttribute(Globals.MULTIPART_KEY);
    547 
    548         request.removeAttribute(Globals.MULTIPART_KEY);
    549 
    550         // Try to initialize the mapping specific request handler
    551         if (multipartClass != null) {
    552             try {
    553                 multipartHandler =
    554                     (MultipartRequestHandler) applicationInstance(multipartClass);
    555             } catch (ClassNotFoundException cnfe) {
    556                 log.error("MultipartRequestHandler class \"" + multipartClass
    557                     + "\" in mapping class not found, "
    558                     + "defaulting to global multipart class");
    559             } catch (InstantiationException ie) {
    560                 log.error("InstantiationException when instantiating "
    561                     + "MultipartRequestHandler \"" + multipartClass + "\", "
    562                     + "defaulting to global multipart class, exception: "
    563                     + ie.getMessage());
    564             } catch (IllegalAccessException iae) {
    565                 log.error("IllegalAccessException when instantiating "
    566                     + "MultipartRequestHandler \"" + multipartClass + "\", "
    567                     + "defaulting to global multipart class, exception: "
    568                     + iae.getMessage());
    569             }
    570 
    571             if (multipartHandler != null) {
    572                 return multipartHandler;
    573             }
    574         }
    575 
    576         ModuleConfig moduleConfig =
    577             ModuleUtils.getInstance().getModuleConfig(request);
    578 
    579         multipartClass = moduleConfig.getControllerConfig().getMultipartClass();
    580 
    581         // Try to initialize the global request handler
    582         if (multipartClass != null) {
    583             try {
    584                 multipartHandler =
    585                     (MultipartRequestHandler) applicationInstance(multipartClass);
    586             } catch (ClassNotFoundException cnfe) {
    587                 throw new ServletException("Cannot find multipart class \""
    588                     + multipartClass + "\"" + ", exception: "
    589                     + cnfe.getMessage());
    590             } catch (InstantiationException ie) {
    591                 throw new ServletException(
    592                     "InstantiationException when instantiating "
    593                     + "multipart class \"" + multipartClass + "\", exception: "
    594                     + ie.getMessage());
    595             } catch (IllegalAccessException iae) {
    596                 throw new ServletException(
    597                     "IllegalAccessException when instantiating "
    598                     + "multipart class \"" + multipartClass + "\", exception: "
    599                     + iae.getMessage());
    600             }
    601 
    602             if (multipartHandler != null) {
    603                 return multipartHandler;
    604             }
    605         }
    606 
    607         return multipartHandler;
    608     }
    609 
    610     /**
    611      * <p>Create a <code>Map</code> containing all of the parameters supplied
    612      * for a multipart request, keyed by parameter name. In addition to text
    613      * and file elements from the multipart body, query string parameters are
    614      * included as well.</p>
    615      *
    616      * @param request          The (wrapped) HTTP request whose parameters are
    617      *                         to be added to the map.
    618      * @param multipartHandler The multipart handler used to parse the
    619      *                         request.
    620      * @return the map containing all parameters for this multipart request.
    621      */
    622     private static Map getAllParametersForMultipartRequest(
    623         HttpServletRequest request, MultipartRequestHandler multipartHandler) {
    624         Map parameters = new HashMap();
    625         Hashtable elements = multipartHandler.getAllElements();
    626         Enumeration e = elements.keys();
    627 
    628         while (e.hasMoreElements()) {
    629             String key = (String) e.nextElement();
    630 
    631             parameters.put(key, elements.get(key));
    632         }
    633 
    634         if (request instanceof MultipartRequestWrapper) {
    635             request =
    636                 (HttpServletRequest) ((MultipartRequestWrapper) request)
    637                 .getRequest();
    638             e = request.getParameterNames();
    639 
    640             while (e.hasMoreElements()) {
    641                 String key = (String) e.nextElement();
    642 
    643                 parameters.put(key, request.getParameterValues(key));
    644             }
    645         } else {
    646             log.debug("Gathering multipart parameters for unwrapped request");
    647         }
    648 
    649         return parameters;
    650     }
    651 
    652     /**
    653      * <p>Compute the printable representation of a URL, leaving off the
    654      * scheme/host/port part if no host is specified. This will typically be
    655      * the case for URLs that were originally created from relative or
    656      * context-relative URIs.</p>
    657      *
    658      * @param url URL to render in a printable representation
    659      * @return printable representation of a URL
    660      */
    661     public static String printableURL(URL url) {
    662         if (url.getHost() != null) {
    663             return (url.toString());
    664         }
    665 
    666         String file = url.getFile();
    667         String ref = url.getRef();
    668 
    669         if (ref == null) {
    670             return (file);
    671         } else {
    672             StringBuffer sb = new StringBuffer(file);
    673 
    674             sb.append('#');
    675             sb.append(ref);
    676 
    677             return (sb.toString());
    678         }
    679     }
    680 
    681     /**
    682      * <p>Return the context-relative URL that corresponds to the specified
    683      * {@link ActionConfig}, relative to the module associated with the
    684      * current modules's {@link ModuleConfig}.</p>
    685      *
    686      * @param request The servlet request we are processing
    687      * @param action  ActionConfig to be evaluated
    688      * @param pattern URL pattern used to map the controller servlet
    689      * @return context-relative URL relative to the module
    690      * @since Struts 1.1
    691      */
    692     public static String actionURL(HttpServletRequest request,
    693         ActionConfig action, String pattern) {
    694         StringBuffer sb = new StringBuffer();
    695 
    696         if (pattern.endsWith("/*")) {
    697             sb.append(pattern.substring(0, pattern.length() - 2));
    698             sb.append(action.getPath());
    699         } else if (pattern.startsWith("*.")) {
    700             ModuleConfig appConfig =
    701                 ModuleUtils.getInstance().getModuleConfig(request);
    702 
    703             sb.append(appConfig.getPrefix());
    704             sb.append(action.getPath());
    705             sb.append(pattern.substring(1));
    706         } else {
    707             throw new IllegalArgumentException(pattern);
    708         }
    709 
    710         return sb.toString();
    711     }
    712 
    713     /**
    714      * <p>Return the context-relative URL that corresponds to the specified
    715      * <code>ForwardConfig</code>. The URL is calculated based on the
    716      * properties of the {@link ForwardConfig} instance as follows:</p>
    717      *
    718      * <ul>
    719      *
    720      *
    721      * <li>If the <code>contextRelative</code> property is set, it is assumed
    722      * that the <code>path</code> property contains a path that is already
    723      * context-relative:
    724      *
    725      * <ul>
    726      *
    727      * <li>If the <code>path</code> property value starts with a slash, it is
    728      * returned unmodified.</li> <li>If the <code>path</code> property value
    729      * does not start with a slash, a slash is prepended.</li>
    730      *
    731      * </ul></li>
    732      *
    733      * <li>Acquire the <code>forwardPattern</code> property from the
    734      * <code>ControllerConfig</code> for the application module used to
    735      * process this request. If no pattern was configured, default to a
    736      * pattern of <code>$M$P</code>, which is compatible with the hard-coded
    737      * mapping behavior in Struts 1.0.</li>
    738      *
    739      * <li>Process the acquired <code>forwardPattern</code>, performing the
    740      * following substitutions:
    741      *
    742      * <ul>
    743      *
    744      * <li><strong>$M</strong> - Replaced by the module prefix for the
    745      * application module processing this request.</li>
    746      *
    747      * <li><strong>$P</strong> - Replaced by the <code>path</code> property of
    748      * the specified {@link ForwardConfig}, prepended with a slash if it does
    749      * not start with one.</li>
    750      *
    751      * <li><strong>$$</strong> - Replaced by a single dollar sign
    752      * character.</li>
    753      *
    754      * <li><strong>$x</strong> (where "x" is any charater not listed above) -
    755      * Silently omit these two characters from the result value.  (This has
    756      * the side effect of causing all other $+letter combinations to be
    757      * reserved.)</li>
    758      *
    759      * </ul></li>
    760      *
    761      * </ul>
    762      *
    763      * @param request The servlet request we are processing
    764      * @param forward ForwardConfig to be evaluated
    765      * @return context-relative URL
    766      * @since Struts 1.1
    767      */
    768     public static String forwardURL(HttpServletRequest request,
    769         ForwardConfig forward) {
    770         return forwardURL(request, forward, null);
    771     }
    772 
    773     /**
    774      * <p>Return the context-relative URL that corresponds to the specified
    775      * <code>ForwardConfig</code>. The URL is calculated based on the
    776      * properties of the {@link ForwardConfig} instance as follows:</p>
    777      *
    778      * <ul>
    779      *
    780      * <li>If the <code>contextRelative</code> property is set, it is assumed
    781      * that the <code>path</code> property contains a path that is already
    782      * context-relative: <ul>
    783      *
    784      * <li>If the <code>path</code> property value starts with a slash, it is
    785      * returned unmodified.</li> <li>If the <code>path</code> property value
    786      * does not start with a slash, a slash is prepended.</li>
    787      *
    788      * </ul></li>
    789      *
    790      * <li>Acquire the <code>forwardPattern</code> property from the
    791      * <code>ControllerConfig</code> for the application module used to
    792      * process this request. If no pattern was configured, default to a
    793      * pattern of <code>$M$P</code>, which is compatible with the hard-coded
    794      * mapping behavior in Struts 1.0.</li>
    795      *
    796      * <li>Process the acquired <code>forwardPattern</code>, performing the
    797      * following substitutions: <ul> <li><strong>$M</strong> - Replaced by the
    798      * module prefix for the application module processing this request.</li>
    799      *
    800      * <li><strong>$P</strong> - Replaced by the <code>path</code> property of
    801      * the specified {@link ForwardConfig}, prepended with a slash if it does
    802      * not start with one.</li>
    803      *
    804      * <li><strong>$$</strong> - Replaced by a single dollar sign
    805      * character.</li>
    806      *
    807      * <li><strong>$x</strong> (where "x" is any charater not listed above) -
    808      * Silently omit these two characters from the result value.  (This has
    809      * the side effect of causing all other $+letter combinations to be
    810      * reserved.)</li>
    811      *
    812      * </ul></li></ul>
    813      *
    814      * @param request      The servlet request we are processing
    815      * @param forward      ForwardConfig to be evaluated
    816      * @param moduleConfig Base forward on this module config.
    817      * @return context-relative URL
    818      * @since Struts 1.2
    819      */
    820     public static String forwardURL(HttpServletRequest request,
    821         ForwardConfig forward, ModuleConfig moduleConfig) {
    822         //load the current moduleConfig, if null
    823         if (moduleConfig == null) {
    824             moduleConfig = ModuleUtils.getInstance().getModuleConfig(request);
    825         }
    826 
    827         String path = forward.getPath();
    828 
    829         //load default prefix
    830         String prefix = moduleConfig.getPrefix();
    831 
    832         //override prefix if supplied by forward
    833         if (forward.getModule() != null) {
    834             prefix = forward.getModule();
    835 
    836             if ("/".equals(prefix)) {
    837                 prefix = "";
    838             }
    839         }
    840 
    841         StringBuffer sb = new StringBuffer();
    842 
    843         // Calculate a context relative path for this ForwardConfig
    844         String forwardPattern =
    845             moduleConfig.getControllerConfig().getForwardPattern();
    846 
    847         if (forwardPattern == null) {
    848             // Performance optimization for previous default behavior
    849             sb.append(prefix);
    850 
    851             // smoothly insert a '/' if needed
    852             if (!path.startsWith("/")) {
    853                 sb.append("/");
    854             }
    855 
    856             sb.append(path);
    857         } else {
    858             boolean dollar = false;
    859 
    860             for (int i = 0; i < forwardPattern.length(); i++) {
    861                 char ch = forwardPattern.charAt(i);
    862 
    863                 if (dollar) {
    864                     switch (ch) {
    865                     case 'M':
    866                         sb.append(prefix);
    867 
    868                         break;
    869 
    870                     case 'P':
    871 
    872                         // add '/' if needed
    873                         if (!path.startsWith("/")) {
    874                             sb.append("/");
    875                         }
    876 
    877                         sb.append(path);
    878 
    879                         break;
    880 
    881                     case '$':
    882                         sb.append('$');
    883 
    884                         break;
    885 
    886                     default:
    887                         ; // Silently swallow
    888                     }
    889 
    890                     dollar = false;
    891 
    892                     continue;
    893                 } else if (ch == '$') {
    894                     dollar = true;
    895                 } else {
    896                     sb.append(ch);
    897                 }
    898             }
    899         }
    900 
    901         return (sb.toString());
    902     }
    903 
    904     /**
    905      * <p>Return the URL representing the current request. This is equivalent
    906      * to <code>HttpServletRequest.getRequestURL</code> in Servlet 2.3.</p>
    907      *
    908      * @param request The servlet request we are processing
    909      * @return URL representing the current request
    910      * @throws MalformedURLException if a URL cannot be created
    911      */
    912     public static URL requestURL(HttpServletRequest request)
    913         throws MalformedURLException {
    914         StringBuffer url = requestToServerUriStringBuffer(request);
    915 
    916         return (new URL(url.toString()));
    917     }
    918 
    919     /**
    920      * <p>Return the URL representing the scheme, server, and port number of
    921      * the current request. Server-relative URLs can be created by simply
    922      * appending the server-relative path (starting with '/') to this.</p>
    923      *
    924      * @param request The servlet request we are processing
    925      * @return URL representing the scheme, server, and port number of the
    926      *         current request
    927      * @throws MalformedURLException if a URL cannot be created
    928      */
    929     public static URL serverURL(HttpServletRequest request)
    930         throws MalformedURLException {
    931         StringBuffer url = requestToServerStringBuffer(request);
    932 
    933         return (new URL(url.toString()));
    934     }
    935 
    936     /**
    937      * <p>Return the string representing the scheme, server, and port number
    938      * of the current request. Server-relative URLs can be created by simply
    939      * appending the server-relative path (starting with '/') to this.</p>
    940      *
    941      * @param request The servlet request we are processing
    942      * @return URL representing the scheme, server, and port number of the
    943      *         current request
    944      * @since Struts 1.2.0
    945      */
    946     public static StringBuffer requestToServerUriStringBuffer(
    947         HttpServletRequest request) {
    948         StringBuffer serverUri =
    949             createServerUriStringBuffer(request.getScheme(),
    950                 request.getServerName(), request.getServerPort(),
    951                 request.getRequestURI());
    952 
    953         return serverUri;
    954     }
    955 
    956     /**
    957      * <p>Return <code>StringBuffer</code> representing the scheme, server,
    958      * and port number of the current request. Server-relative URLs can be
    959      * created by simply appending the server-relative path (starting with
    960      * '/') to this.</p>
    961      *
    962      * @param request The servlet request we are processing
    963      * @return URL representing the scheme, server, and port number of the
    964      *         current request
    965      * @since Struts 1.2.0
    966      */
    967     public static StringBuffer requestToServerStringBuffer(
    968         HttpServletRequest request) {
    969         return createServerStringBuffer(request.getScheme(),
    970             request.getServerName(), request.getServerPort());
    971     }
    972 
    973     /**
    974      * <p>Return <code>StringBuffer</code> representing the scheme, server,
    975      * and port number of the current request.</p>
    976      *
    977      * @param scheme The scheme name to use
    978      * @param server The server name to use
    979      * @param port   The port value to use
    980      * @return StringBuffer in the form scheme: server: port
    981      * @since Struts 1.2.0
    982      */
    983     public static StringBuffer createServerStringBuffer(String scheme,
    984         String server, int port) {
    985         StringBuffer url = new StringBuffer();
    986 
    987         if (port < 0) {
    988             port = 80; // Work around java.net.URL bug
    989         }
    990 
    991         url.append(scheme);
    992         url.append("://");
    993         url.append(server);
    994 
    995         if ((scheme.equals("http") && (port != 80))
    996             || (scheme.equals("https") && (port != 443))) {
    997             url.append(':');
    998             url.append(port);
    999         }
    1000 
    1001         return url;
    1002     }
    1003 
    1004     /**
    1005      * <p>Return <code>StringBuffer</code> representing the scheme, server,
    1006      * and port number of the current request.</p>
    1007      *
    1008      * @param scheme The scheme name to use
    1009      * @param server The server name to use
    1010      * @param port   The port value to use
    1011      * @param uri    The uri value to use
    1012      * @return StringBuffer in the form scheme: server: port
    1013      * @since Struts 1.2.0
    1014      */
    1015     public static StringBuffer createServerUriStringBuffer(String scheme,
    1016         String server, int port, String uri) {
    1017         StringBuffer serverUri = createServerStringBuffer(scheme, server, port);
    1018 
    1019         serverUri.append(uri);
    1020 
    1021         return serverUri;
    1022     }
    1023 
    1024     /**
    1025      * <p>Returns the true path of the destination action if the specified forward
    1026      * is an action-aliased URL. This method version forms the URL based on
    1027      * the current request; selecting the current module if the forward does not
    1028      * explicitly contain a module path.</p>
    1029      *
    1030      * @param forward the forward config
    1031      * @param request the current request
    1032      * @param servlet the servlet handling the current request
    1033      * @return the context-relative URL of the action if the forward has an action identifier; otherwise <code>null</code>.
    1034      * @since Struts 1.3.6
    1035      */
    1036     public static String actionIdURL(ForwardConfig forward, HttpServletRequest request, ActionServlet servlet) {
    1037         ModuleConfig moduleConfig = null;
    1038         if (forward.getModule() != null) {
    1039             String prefix = forward.getModule();
    1040             moduleConfig = ModuleUtils.getInstance().getModuleConfig(prefix, servlet.getServletContext());
    1041         } else {
    1042             moduleConfig = ModuleUtils.getInstance().getModuleConfig(request);
    1043         }
    1044         return actionIdURL(forward.getPath(), moduleConfig, servlet);
    1045     }
    1046 
    1047     /**
    1048      * <p>Returns the true path of the destination action if the specified forward
    1049      * is an action-aliased URL. This method version forms the URL based on
    1050      * the specified module.
    1051      *
    1052      * @param originalPath the action-aliased path
    1053      * @param moduleConfig the module config for this request
    1054      * @param servlet the servlet handling the current request
    1055      * @return the context-relative URL of the action if the path has an action identifier; otherwise <code>null</code>.
    1056      * @since Struts 1.3.6
    1057      */
    1058     public static String actionIdURL(String originalPath, ModuleConfig moduleConfig, ActionServlet servlet) {
    1059         if (originalPath.startsWith("http") || originalPath.startsWith("/")) {
    1060             return null;
    1061         }
    1062 
    1063         // Split the forward path into the resource and query string;
    1064         // it is possible a forward (or redirect) has added parameters.
    1065         String actionId = null;
    1066         String qs = null;
    1067         int qpos = originalPath.indexOf("?");
    1068         if (qpos == -1) {
    1069             actionId = originalPath;
    1070         } else {
    1071             actionId = originalPath.substring(0, qpos);
    1072             qs = originalPath.substring(qpos);
    1073         }
    1074 
    1075         // Find the action of the given actionId
    1076         ActionConfig actionConfig = moduleConfig.findActionConfigId(actionId);
    1077         if (actionConfig == null) {
    1078             if (log.isDebugEnabled()) {
    1079                 log.debug("No actionId found for " + actionId);
    1080             }
    1081             return null;
    1082         }
    1083 
    1084         String path = actionConfig.getPath();
    1085         String mapping = RequestUtils.getServletMapping(servlet);
    1086         StringBuffer actionIdPath = new StringBuffer();
    1087 
    1088         // Form the path based on the servlet mapping pattern
    1089         if (mapping.startsWith("*")) {
    1090             actionIdPath.append(path);
    1091             actionIdPath.append(mapping.substring(1));
    1092         } else if (mapping.startsWith("/")) {  // implied ends with a *
    1093             mapping = mapping.substring(0, mapping.length() - 1);
    1094             if (mapping.endsWith("/") && path.startsWith("/")) {
    1095                 actionIdPath.append(mapping);
    1096                 actionIdPath.append(path.substring(1));
    1097             } else {
    1098                 actionIdPath.append(mapping);
    1099                 actionIdPath.append(path);
    1100             }
    1101         } else {
    1102             log.warn("Unknown servlet mapping pattern");
    1103             actionIdPath.append(path);
    1104         }
    1105 
    1106         // Lastly add any query parameters (the ? is part of the query string)
    1107         if (qs != null) {
    1108             actionIdPath.append(qs);
    1109         }
    1110 
    1111         // Return the path
    1112         if (log.isDebugEnabled()) {
    1113             log.debug(originalPath + " unaliased to " + actionIdPath.toString());
    1114         }
    1115         return actionIdPath.toString();
    1116     }
    1117 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
