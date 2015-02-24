[View Javadoc](../../../../../apidocs/org/apache/struts/taglib/TagUtils.html.md)


    1   /*
    2    * $Id: TagUtils.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib;
    22  
    23  import org.apache.commons.beanutils.PropertyUtils;
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.struts.Globals;
    27  import org.apache.struts.action.ActionErrors;
    28  import org.apache.struts.action.ActionMessage;
    29  import org.apache.struts.action.ActionMessages;
    30  import org.apache.struts.action.ActionServlet;
    31  import org.apache.struts.config.ForwardConfig;
    32  import org.apache.struts.config.ModuleConfig;
    33  import org.apache.struts.taglib.html.md.Constants;
    34  import org.apache.struts.util.MessageResources;
    35  import org.apache.struts.util.ModuleUtils;
    36  import org.apache.struts.util.RequestUtils;
    37  import org.apache.struts.util.ResponseUtils;
    38  
    39  import javax.servlet.http.HttpServletRequest;
    40  import javax.servlet.http.HttpServletResponse;
    41  import javax.servlet.http.HttpSession;
    42  import javax.servlet.jsp.JspException;
    43  import javax.servlet.jsp.JspWriter;
    44  import javax.servlet.jsp.PageContext;
    45  import javax.servlet.jsp.tagext.BodyContent;
    46  
    47  import java.io.IOException;
    48  
    49  import java.lang.reflect.InvocationTargetException;
    50  
    51  import java.net.MalformedURLException;
    52  
    53  import java.util.HashMap;
    54  import java.util.Iterator;
    55  import java.util.Locale;
    56  import java.util.Map;
    57  
    58  /**
    59   * Provides helper methods for JSP tags.
    60   *
    61   * @version $Rev: 471754 $
    62   * @since Struts 1.2
    63   */
    64  public class TagUtils {
    65      /**
    66       * The Singleton instance.
    67       * @since 1.3.5 Changed to non-final so it may be overridden, use at your own risk (you've been warned!!)
    68       */
    69      private static TagUtils instance = new TagUtils();
    70  
    71      /**
    72       * Commons logging instance.
    73       */
    74      private static final Log log = LogFactory.getLog(TagUtils.class);
    75  
    76      /**
    77       * The message resources for this package. TODO We need to move the
    78       * relevant messages out of this properties file.
    79       */
    80      private static final MessageResources messages =
    81          MessageResources.getMessageResources(
    82              "org.apache.struts.taglib.LocalStrings");
    83  
    84      /**
    85       * Maps lowercase JSP scope names to their PageContext integer constant
    86       * values.
    87       */
    88      private static final Map scopes = new HashMap();
    89  
    90      /**
    91       * Initialize the scope names map and the encode variable with the
    92       * Java 1.4 method if available.
    93       */
    94      static {
    95          scopes.put("page", new Integer(PageContext.PAGE_SCOPE));
    96          scopes.put("request", new Integer(PageContext.REQUEST_SCOPE));
    97          scopes.put("session", new Integer(PageContext.SESSION_SCOPE));
    98          scopes.put("application", new Integer(PageContext.APPLICATION_SCOPE));
    99      }
    100 
    101     /**
    102      * Constructor for TagUtils.
    103      */
    104     protected TagUtils() {
    105         super();
    106     }
    107 
    108     /**
    109      * Returns the Singleton instance of TagUtils.
    110      */
    111     public static TagUtils getInstance() {
    112         return instance;
    113     }
    114 
    115     /**
    116      * Set the instance.
    117      * This blatently violates the Singleton pattern, but then some say Singletons are an anti-pattern.
    118      * @since 1.3.5 Changed to non-final and added setInstance() so TagUtils may be overridden, use at your own risk (you've been warned!!)
    119      * @param instance The instance to set.
    120      */
    121     public static void setInstance(TagUtils instance){
    122       TagUtils.instance = instance;
    123     }
    124 
    125     /**
    126      * Compute a set of query parameters that will be dynamically added to a
    127      * generated URL.  The returned Map is keyed by parameter name, and the
    128      * values are either null (no value specified), a String (single value
    129      * specified), or a String[] array (multiple values specified).  Parameter
    130      * names correspond to the corresponding attributes of the
    131      * <code>&lt.html.md:link&gt;</code> tag.  If no query parameters are
    132      * identified, return <code>null</code>.
    133      *
    134      * @param pageContext   PageContext we are operating in
    135      * @param paramId       Single-value request parameter name (if any)
    136      * @param paramName     Bean containing single-value parameter value
    137      * @param paramProperty Property (of bean named by <code>paramName</code>
    138      *                      containing single-value parameter value
    139      * @param paramScope    Scope containing bean named by <code>paramName</code>
    140      * @param name          Bean containing multi-value parameters Map (if
    141      *                      any)
    142      * @param property      Property (of bean named by <code>name</code>
    143      *                      containing multi-value parameters Map
    144      * @param scope         Scope containing bean named by <code>name</code>
    145      * @param transaction   Should we add our transaction control token?
    146      * @return Map of query parameters
    147      * @throws JspException if we cannot look up the required beans
    148      * @throws JspException if a class cast exception occurs on a looked-up
    149      *                      bean or property
    150      */
    151     public Map computeParameters(PageContext pageContext, String paramId,
    152         String paramName, String paramProperty, String paramScope, String name,
    153         String property, String scope, boolean transaction)
    154         throws JspException {
    155         // Short circuit if no parameters are specified
    156         if ((paramId == null) && (name == null) && !transaction) {
    157             return (null);
    158         }
    159 
    160         // Locate the Map containing our multi-value parameters map
    161         Map map = null;
    162 
    163         try {
    164             if (name != null) {
    165                 map = (Map) getInstance().lookup(pageContext, name, property,
    166                         scope);
    167             }
    168 
    169             // @TODO - remove this - it is never thrown
    170             //        } catch (ClassCastException e) {
    171             //            saveException(pageContext, e);
    172             //            throw new JspException(
    173             //                    messages.getMessage("parameters.multi", name, property, scope));
    174         } catch (JspException e) {
    175             saveException(pageContext, e);
    176             throw e;
    177         }
    178 
    179         // Create a Map to contain our results from the multi-value parameters
    180         Map results = null;
    181 
    182         if (map != null) {
    183             results = new HashMap(map);
    184         } else {
    185             results = new HashMap();
    186         }
    187 
    188         // Add the single-value parameter (if any)
    189         if ((paramId != null) && (paramName != null)) {
    190             Object paramValue = null;
    191 
    192             try {
    193                 paramValue =
    194                     TagUtils.getInstance().lookup(pageContext, paramName,
    195                         paramProperty, paramScope);
    196             } catch (JspException e) {
    197                 saveException(pageContext, e);
    198                 throw e;
    199             }
    200 
    201             if (paramValue != null) {
    202                 String paramString = null;
    203 
    204                 if (paramValue instanceof String) {
    205                     paramString = (String) paramValue;
    206                 } else {
    207                     paramString = paramValue.toString();
    208                 }
    209 
    210                 Object mapValue = results.get(paramId);
    211 
    212                 if (mapValue == null) {
    213                     results.put(paramId, paramString);
    214                 } else if (mapValue instanceof String[]) {
    215                     String[] oldValues = (String[]) mapValue;
    216                     String[] newValues = new String[oldValues.length + 1];
    217 
    218                     System.arraycopy(oldValues, 0, newValues, 0,
    219                         oldValues.length);
    220                     newValues[oldValues.length] = paramString;
    221                     results.put(paramId, newValues);
    222                 } else {
    223                     String[] newValues = new String[2];
    224 
    225                     newValues[0] = mapValue.toString();
    226                     newValues[1] = paramString;
    227                     results.put(paramId, newValues);
    228                 }
    229             }
    230         }
    231 
    232         // Add our transaction control token (if requested)
    233         if (transaction) {
    234             HttpSession session = pageContext.getSession();
    235             String token = null;
    236 
    237             if (session != null) {
    238                 token =
    239                     (String) session.getAttribute(Globals.TRANSACTION_TOKEN_KEY);
    240             }
    241 
    242             if (token != null) {
    243                 results.put(Constants.TOKEN_KEY, token);
    244             }
    245         }
    246 
    247         // Return the completed Map
    248         return (results);
    249     }
    250 
    251     public String computeURL(PageContext pageContext, String forward,
    252         String href, String page, String action, String module, Map params,
    253         String anchor, boolean redirect)
    254         throws MalformedURLException {
    255         return this.computeURLWithCharEncoding(pageContext, forward, href,
    256             page, action, module, params, anchor, redirect, false);
    257     }
    258 
    259     /**
    260      * Compute a hyperlink URL based on the <code>forward</code>,
    261      * <code>href</code>, <code>action</code> or <code>page</code> parameter
    262      * that is not null. The returned URL will have already been passed to
    263      * <code>response.encodeURL()</code> for adding a session identifier.
    264      *
    265      * @param pageContext PageContext for the tag making this call
    266      * @param forward     Logical forward name for which to look up the
    267      *                    context-relative URI (if specified)
    268      * @param href        URL to be utilized unmodified (if specified)
    269      * @param page        Module-relative page for which a URL should be
    270      *                    created (if specified)
    271      * @param action      Logical action name for which to look up the
    272      *                    context-relative URI (if specified)
    273      * @param params      Map of parameters to be dynamically included (if
    274      *                    any)
    275      * @param anchor      Anchor to be dynamically included (if any)
    276      * @param redirect    Is this URL for a <code>response.sendRedirect()</code>?
    277      * @return URL with session identifier
    278      * @throws java.net.MalformedURLException if a URL cannot be created for
    279      *                                        the specified parameters
    280      */
    281     public String computeURLWithCharEncoding(PageContext pageContext,
    282         String forward, String href, String page, String action, String module,
    283         Map params, String anchor, boolean redirect, boolean useLocalEncoding)
    284         throws MalformedURLException {
    285         return computeURLWithCharEncoding(pageContext, forward, href, page,
    286             action, module, params, anchor, redirect, true, useLocalEncoding);
    287     }
    288 
    289     public String computeURL(PageContext pageContext, String forward,
    290         String href, String page, String action, String module, Map params,
    291         String anchor, boolean redirect, boolean encodeSeparator)
    292         throws MalformedURLException {
    293         return computeURLWithCharEncoding(pageContext, forward, href, page,
    294             action, module, params, anchor, redirect, encodeSeparator, false);
    295     }
    296 
    297     /**
    298      * Compute a hyperlink URL based on the <code>forward</code>,
    299      * <code>href</code>, <code>action</code> or <code>page</code> parameter
    300      * that is not null. The returned URL will have already been passed to
    301      * <code>response.encodeURL()</code> for adding a session identifier.
    302      *
    303      * @param pageContext      PageContext for the tag making this call
    304      * @param forward          Logical forward name for which to look up the
    305      *                         context-relative URI (if specified)
    306      * @param href             URL to be utilized unmodified (if specified)
    307      * @param page             Module-relative page for which a URL should be
    308      *                         created (if specified)
    309      * @param action           Logical action name for which to look up the
    310      *                         context-relative URI (if specified)
    311      * @param params           Map of parameters to be dynamically included
    312      *                         (if any)
    313      * @param anchor           Anchor to be dynamically included (if any)
    314      * @param redirect         Is this URL for a <code>response.sendRedirect()</code>?
    315      * @param encodeSeparator  This is only checked if redirect is set to
    316      *                         false (never encoded for a redirect).  If true,
    317      *                         query string parameter separators are encoded
    318      *                         as &gt;amp;, else &amp; is used.
    319      * @param useLocalEncoding If set to true, urlencoding is done on the
    320      *                         bytes of character encoding from
    321      *                         ServletResponse#getCharacterEncoding. Use UTF-8
    322      *                         otherwise.
    323      * @return URL with session identifier
    324      * @throws java.net.MalformedURLException if a URL cannot be created for
    325      *                                        the specified parameters
    326      */
    327     public String computeURLWithCharEncoding(PageContext pageContext,
    328         String forward, String href, String page, String action, String module,
    329         Map params, String anchor, boolean redirect, boolean encodeSeparator,
    330         boolean useLocalEncoding)
    331         throws MalformedURLException {
    332         String charEncoding = "UTF-8";
    333 
    334         if (useLocalEncoding) {
    335             charEncoding = pageContext.getResponse().getCharacterEncoding();
    336         }
    337 
    338         // TODO All the computeURL() methods need refactoring!
    339         // Validate that exactly one specifier was included
    340         int n = 0;
    341 
    342         if (forward != null) {
    343             n++;
    344         }
    345 
    346         if (href != null) {
    347             n++;
    348         }
    349 
    350         if (page != null) {
    351             n++;
    352         }
    353 
    354         if (action != null) {
    355             n++;
    356         }
    357 
    358         if (n != 1) {
    359             throw new MalformedURLException(messages.getMessage(
    360                     "computeURL.specifier"));
    361         }
    362 
    363         // Look up the module configuration for this request
    364         ModuleConfig moduleConfig = getModuleConfig(module, pageContext);
    365 
    366         // Calculate the appropriate URL
    367         StringBuffer url = new StringBuffer();
    368         HttpServletRequest request =
    369             (HttpServletRequest) pageContext.getRequest();
    370 
    371         if (forward != null) {
    372             ForwardConfig forwardConfig =
    373                 moduleConfig.findForwardConfig(forward);
    374 
    375             if (forwardConfig == null) {
    376                 throw new MalformedURLException(messages.getMessage(
    377                         "computeURL.forward", forward));
    378             }
    379 
    380             // **** removed - see bug 37817 ****
    381             //  if (forwardConfig.getRedirect()) {
    382             //      redirect = true;
    383             //  }
    384 
    385             if (forwardConfig.getPath().startsWith("/")) {
    386                 url.append(request.getContextPath());
    387                 url.append(RequestUtils.forwardURL(request, forwardConfig,
    388                         moduleConfig));
    389             } else {
    390                 url.append(forwardConfig.getPath());
    391             }
    392         } else if (href != null) {
    393             url.append(href);
    394         } else if (action != null) {
    395             ActionServlet servlet = (ActionServlet) pageContext.getServletContext().getAttribute(Globals.ACTION_SERVLET_KEY);
    396             String actionIdPath = RequestUtils.actionIdURL(action, moduleConfig, servlet);
    397             if (actionIdPath != null) {
    398                 action = actionIdPath;
    399                 url.append(request.getContextPath());
    400                 url.append(actionIdPath);
    401             } else {
    402                 url.append(instance.getActionMappingURL(action, module,
    403                         pageContext, false));
    404             }
    405         } else /* if (page != null) */
    406          {
    407             url.append(request.getContextPath());
    408             url.append(this.pageURL(request, page, moduleConfig));
    409         }
    410 
    411         // Add anchor if requested (replacing any existing anchor)
    412         if (anchor != null) {
    413             String temp = url.toString();
    414             int hash = temp.indexOf('#');
    415 
    416             if (hash >= 0) {
    417                 url.setLength(hash);
    418             }
    419 
    420             url.append('#');
    421             url.append(this.encodeURL(anchor, charEncoding));
    422         }
    423 
    424         // Add dynamic parameters if requested
    425         if ((params != null) && (params.size() > 0)) {
    426             // Save any existing anchor
    427             String temp = url.toString();
    428             int hash = temp.indexOf('#');
    429 
    430             if (hash >= 0) {
    431                 anchor = temp.substring(hash + 1);
    432                 url.setLength(hash);
    433                 temp = url.toString();
    434             } else {
    435                 anchor = null;
    436             }
    437 
    438             // Define the parameter separator
    439             String separator = null;
    440 
    441             if (redirect) {
    442                 separator = "&";
    443             } else if (encodeSeparator) {
    444                 separator = "&amp;";
    445             } else {
    446                 separator = "&";
    447             }
    448 
    449             // Add the required request parameters
    450             boolean question = temp.indexOf('?') >= 0;
    451             Iterator keys = params.keySet().iterator();
    452 
    453             while (keys.hasNext()) {
    454                 String key = (String) keys.next();
    455                 Object value = params.get(key);
    456 
    457                 if (value == null) {
    458                     if (!question) {
    459                         url.append('?');
    460                         question = true;
    461                     } else {
    462                         url.append(separator);
    463                     }
    464 
    465                     url.append(this.encodeURL(key, charEncoding));
    466                     url.append('='); // Interpret null as "no value"
    467                 } else if (value instanceof String) {
    468                     if (!question) {
    469                         url.append('?');
    470                         question = true;
    471                     } else {
    472                         url.append(separator);
    473                     }
    474 
    475                     url.append(this.encodeURL(key, charEncoding));
    476                     url.append('=');
    477                     url.append(this.encodeURL((String) value, charEncoding));
    478                 } else if (value instanceof String[]) {
    479                     String[] values = (String[]) value;
    480 
    481                     for (int i = 0; i < values.length; i++) {
    482                         if (!question) {
    483                             url.append('?');
    484                             question = true;
    485                         } else {
    486                             url.append(separator);
    487                         }
    488 
    489                         url.append(this.encodeURL(key, charEncoding));
    490                         url.append('=');
    491                         url.append(this.encodeURL(values[i], charEncoding));
    492                     }
    493                 } else /* Convert other objects to a string */
    494                  {
    495                     if (!question) {
    496                         url.append('?');
    497                         question = true;
    498                     } else {
    499                         url.append(separator);
    500                     }
    501 
    502                     url.append(this.encodeURL(key, charEncoding));
    503                     url.append('=');
    504                     url.append(this.encodeURL(value.toString(), charEncoding));
    505                 }
    506             }
    507 
    508             // Re-add the saved anchor (if any)
    509             if (anchor != null) {
    510                 url.append('#');
    511                 url.append(this.encodeURL(anchor, charEncoding));
    512             }
    513         }
    514 
    515         // Perform URL rewriting to include our session ID (if any)
    516         // but only if url is not an external URL
    517         if ((href == null) && (pageContext.getSession() != null)) {
    518             HttpServletResponse response =
    519                 (HttpServletResponse) pageContext.getResponse();
    520 
    521             if (redirect) {
    522                 return (response.encodeRedirectURL(url.toString()));
    523             }
    524 
    525             return (response.encodeURL(url.toString()));
    526         }
    527 
    528         return (url.toString());
    529     }
    530 
    531     /**
    532      * URLencodes a string assuming the character encoding is UTF-8.
    533      *
    534      * @param url
    535      * @return String The encoded url in UTF-8
    536      */
    537     public String encodeURL(String url) {
    538         return encodeURL(url, "UTF-8");
    539     }
    540 
    541     /**
    542      * Use the new URLEncoder.encode() method from Java 1.4 if available, else
    543      * use the old deprecated version.  This method uses reflection to find
    544      * the appropriate method; if the reflection operations throw exceptions,
    545      * this will return the url encoded with the old URLEncoder.encode()
    546      * method.
    547      *
    548      * @param enc The character encoding the urlencode is performed on.
    549      * @return String The encoded url.
    550      */
    551     public String encodeURL(String url, String enc) {
    552         return ResponseUtils.encodeURL(url, enc);
    553     }
    554 
    555     /**
    556      * Filter the specified string for characters that are senstive to HTML
    557      * interpreters, returning the string with these characters replaced by
    558      * the corresponding character entities.
    559      *
    560      * @param value The string to be filtered and returned
    561      */
    562     public String filter(String value) {
    563         return ResponseUtils.filter(value);
    564     }
    565 
    566     /**
    567      * Return the form action converted into an action mapping path.  The
    568      * value of the <code>action</code> property is manipulated as follows in
    569      * computing the name of the requested mapping:
    570      *
    571      * <ul>
    572      *
    573      * <li>Any filename extension is removed (on the theory that extension
    574      * mapping is being used to select the controller servlet).</li>
    575      *
    576      * <li>If the resulting value does not start with a slash, then a slash is
    577      * prepended.</li>
    578      *
    579      * </ul>
    580      */
    581     public String getActionMappingName(String action) {
    582         String value = action;
    583         int question = action.indexOf("?");
    584 
    585         if (question >= 0) {
    586             value = value.substring(0, question);
    587         }
    588 
    589         int pound = value.indexOf("#");
    590 
    591         if (pound >= 0) {
    592             value = value.substring(0, pound);
    593         }
    594 
    595         int slash = value.lastIndexOf("/");
    596         int period = value.lastIndexOf(".");
    597 
    598         if ((period >= 0) && (period > slash)) {
    599             value = value.substring(0, period);
    600         }
    601 
    602         return value.startsWith("/") ? value : ("/" + value);
    603     }
    604 
    605     /**
    606      * Return the form action converted into a server-relative URL.
    607      */
    608     public String getActionMappingURL(String action, PageContext pageContext) {
    609         return getActionMappingURL(action, null, pageContext, false);
    610     }
    611 
    612     /**
    613      * Return the form action converted into a server-relative URL.
    614      */
    615     public String getActionMappingURL(String action, String module,
    616         PageContext pageContext, boolean contextRelative) {
    617         HttpServletRequest request =
    618             (HttpServletRequest) pageContext.getRequest();
    619 
    620         String contextPath = request.getContextPath();
    621         StringBuffer value = new StringBuffer();
    622 
    623         // Avoid setting two slashes at the beginning of an action:
    624         //  the length of contextPath should be more than 1
    625         //  in case of non-root context, otherwise length==1 (the slash)
    626         if (contextPath.length() > 1) {
    627             value.append(contextPath);
    628         }
    629 
    630         ModuleConfig moduleConfig = getModuleConfig(module, pageContext);
    631 
    632         if ((moduleConfig != null) && (!contextRelative)) {
    633             value.append(moduleConfig.getPrefix());
    634         }
    635 
    636         // Use our servlet mapping, if one is specified
    637         String servletMapping =
    638             (String) pageContext.getAttribute(Globals.SERVLET_KEY,
    639                 PageContext.APPLICATION_SCOPE);
    640 
    641         if (servletMapping != null) {
    642             String queryString = null;
    643             int question = action.indexOf("?");
    644 
    645             if (question >= 0) {
    646                 queryString = action.substring(question);
    647             }
    648 
    649             String actionMapping = getActionMappingName(action);
    650 
    651             if (servletMapping.startsWith("*.")) {
    652                 value.append(actionMapping);
    653                 value.append(servletMapping.substring(1));
    654             } else if (servletMapping.endsWith("/*")) {
    655                 value.append(servletMapping.substring(0,
    656                         servletMapping.length() - 2));
    657                 value.append(actionMapping);
    658             } else if (servletMapping.equals("/")) {
    659                 value.append(actionMapping);
    660             }
    661 
    662             if (queryString != null) {
    663                 value.append(queryString);
    664             }
    665         }
    666         // Otherwise, assume extension mapping is in use and extension is
    667         // already included in the action property
    668         else {
    669             if (!action.startsWith("/")) {
    670                 value.append("/");
    671             }
    672 
    673             value.append(action);
    674         }
    675 
    676         return value.toString();
    677     }
    678 
    679     /**
    680      * Retrieves the value from request scope and if it isn't already an
    681      * <code>ActionMessages</code>, some classes are converted to one.
    682      *
    683      * @param pageContext The PageContext for the current page
    684      * @param paramName   Key for parameter value
    685      * @return ActionErrors in page context.
    686      * @throws JspException
    687      */
    688     public ActionMessages getActionMessages(PageContext pageContext,
    689         String paramName) throws JspException {
    690         ActionMessages am = new ActionMessages();
    691 
    692         Object value = pageContext.findAttribute(paramName);
    693 
    694         if (value != null) {
    695             try {
    696                 if (value instanceof String) {
    697                     am.add(ActionMessages.GLOBAL_MESSAGE,
    698                         new ActionMessage((String) value));
    699                 } else if (value instanceof String[]) {
    700                     String[] keys = (String[]) value;
    701 
    702                     for (int i = 0; i < keys.length; i++) {
    703                         am.add(ActionMessages.GLOBAL_MESSAGE,
    704                             new ActionMessage(keys[i]));
    705                     }
    706                 } else if (value instanceof ActionErrors) {
    707                     ActionMessages m = (ActionMessages) value;
    708 
    709                     am.add(m);
    710                 } else if (value instanceof ActionMessages) {
    711                     am = (ActionMessages) value;
    712                 } else {
    713                     throw new JspException(messages.getMessage(
    714                             "actionMessages.errors", value.getClass().getName()));
    715                 }
    716             } catch (JspException e) {
    717                 throw e;
    718             } catch (Exception e) {
    719                 log.warn("Unable to retieve ActionMessage for paramName : "
    720                     + paramName, e);
    721             }
    722         }
    723 
    724         return am;
    725     }
    726 
    727     /**
    728      * Return the default ModuleConfig object if it exists, null if
    729      * otherwise.
    730      *
    731      * @param pageContext The page context.
    732      * @return the ModuleConfig object
    733      */
    734     public ModuleConfig getModuleConfig(PageContext pageContext) {
    735         return getModuleConfig(null, pageContext);
    736     }
    737 
    738     /**
    739      * Return the specified ModuleConfig object for the given prefix if it
    740      * exists, otherwise a NullPointerException will be thrown.
    741      *
    742      * @param module      The module prefix
    743      * @param pageContext The page context.
    744      * @return the ModuleConfig object
    745      * @throws NullPointerException Thrown when module cannot be found
    746      */
    747     public ModuleConfig getModuleConfig(String module, PageContext pageContext) {
    748         ModuleConfig config =
    749             ModuleUtils.getInstance().getModuleConfig(module,
    750                 (HttpServletRequest) pageContext.getRequest(),
    751                 pageContext.getServletContext());
    752 
    753         // ModuleConfig not found
    754         if (config == null) {
    755             throw new NullPointerException("Module '" + module + "' not found.");
    756         }
    757 
    758         return config;
    759     }
    760 
    761     /**
    762      * Converts the scope name into its corresponding PageContext constant
    763      * value.
    764      *
    765      * @param scopeName Can be "page", "request", "session", or "application"
    766      *                  in any case.
    767      * @return The constant representing the scope (ie. PageContext.REQUEST_SCOPE).
    768      * @throws JspException if the scopeName is not a valid name.
    769      */
    770     public int getScope(String scopeName)
    771         throws JspException {
    772         Integer scope = (Integer) scopes.get(scopeName.toLowerCase());
    773 
    774         if (scope == null) {
    775             throw new JspException(messages.getMessage("lookup.scope", scope));
    776         }
    777 
    778         return scope.intValue();
    779     }
    780 
    781     /**
    782      * Look up and return current user locale, based on the specified
    783      * parameters.
    784      *
    785      * @param pageContext The PageContext associated with this request
    786      * @param locale      Name of the session attribute for our user's Locale.
    787      *                    If this is <code>null</code>, the default locale key
    788      *                    is used for the lookup.
    789      * @return current user locale
    790      */
    791     public Locale getUserLocale(PageContext pageContext, String locale) {
    792         return RequestUtils.getUserLocale((HttpServletRequest) pageContext
    793             .getRequest(), locale);
    794     }
    795 
    796     /**
    797      * Returns true if the custom tags are in XHTML mode.
    798      */
    799     public boolean is.html.md(PageContext pageContext) {
    800         String .html.md =
    801             (String) pageContext.getAttribute(Globals.XHTML_KEY,
    802                 PageContext.PAGE_SCOPE);
    803 
    804         return "true".equalsIgnoreCase(.html.md);
    805     }
    806 
    807     /**
    808      * Locate and return the specified bean, from an optionally specified
    809      * scope, in the specified page context.  If no such bean is found, return
    810      * <code>null</code> instead.  If an exception is thrown, it will have
    811      * already been saved via a call to <code>saveException()</code>.
    812      *
    813      * @param pageContext Page context to be searched
    814      * @param name        Name of the bean to be retrieved
    815      * @param scopeName   Scope to be searched (page, request, session,
    816      *                    application) or <code>null</code> to use
    817      *                    <code>findAttribute()</code> instead
    818      * @return JavaBean in the specified page context
    819      * @throws JspException if an invalid scope name is requested
    820      */
    821     public Object lookup(PageContext pageContext, String name, String scopeName)
    822         throws JspException {
    823         if (scopeName == null) {
    824             return pageContext.findAttribute(name);
    825         }
    826 
    827         try {
    828             return pageContext.getAttribute(name, instance.getScope(scopeName));
    829         } catch (JspException e) {
    830             saveException(pageContext, e);
    831             throw e;
    832         }
    833     }
    834 
    835     /**
    836      * Locate and return the specified property of the specified bean, from an
    837      * optionally specified scope, in the specified page context.  If an
    838      * exception is thrown, it will have already been saved via a call to
    839      * <code>saveException()</code>.
    840      *
    841      * @param pageContext Page context to be searched
    842      * @param name        Name of the bean to be retrieved
    843      * @param property    Name of the property to be retrieved, or
    844      *                    <code>null</code> to retrieve the bean itself
    845      * @param scope       Scope to be searched (page, request, session,
    846      *                    application) or <code>null</code> to use
    847      *                    <code>findAttribute()</code> instead
    848      * @return property of specified JavaBean
    849      * @throws JspException if an invalid scope name is requested
    850      * @throws JspException if the specified bean is not found
    851      * @throws JspException if accessing this property causes an
    852      *                      IllegalAccessException, IllegalArgumentException,
    853      *                      InvocationTargetException, or NoSuchMethodException
    854      */
    855     public Object lookup(PageContext pageContext, String name, String property,
    856         String scope) throws JspException {
    857         // Look up the requested bean, and return if requested
    858         Object bean = lookup(pageContext, name, scope);
    859 
    860         if (bean == null) {
    861             JspException e = null;
    862 
    863             if (scope == null) {
    864                 e = new JspException(messages.getMessage("lookup.bean.any", name));
    865             } else {
    866                 e = new JspException(messages.getMessage("lookup.bean", name,
    867                             scope));
    868             }
    869 
    870             saveException(pageContext, e);
    871             throw e;
    872         }
    873 
    874         if (property == null) {
    875             return bean;
    876         }
    877 
    878         // Locate and return the specified property
    879         try {
    880             return PropertyUtils.getProperty(bean, property);
    881         } catch (IllegalAccessException e) {
    882             saveException(pageContext, e);
    883             throw new JspException(messages.getMessage("lookup.access",
    884                     property, name));
    885         } catch (IllegalArgumentException e) {
    886             saveException(pageContext, e);
    887             throw new JspException(messages.getMessage("lookup.argument",
    888                     property, name));
    889         } catch (InvocationTargetException e) {
    890             Throwable t = e.getTargetException();
    891 
    892             if (t == null) {
    893                 t = e;
    894             }
    895 
    896             saveException(pageContext, t);
    897             throw new JspException(messages.getMessage("lookup.target",
    898                     property, name));
    899         } catch (NoSuchMethodException e) {
    900             saveException(pageContext, e);
    901 
    902             String beanName = name;
    903 
    904             // Name defaults to Contants.BEAN_KEY if no name is specified by
    905             // an input tag. Thus lookup the bean under the key and use
    906             // its class name for the exception message.
    907             if (Constants.BEAN_KEY.equals(name)) {
    908                 Object obj = pageContext.findAttribute(Constants.BEAN_KEY);
    909 
    910                 if (obj != null) {
    911                     beanName = obj.getClass().getName();
    912                 }
    913             }
    914 
    915             throw new JspException(messages.getMessage("lookup.method",
    916                     property, beanName));
    917         }
    918     }
    919 
    920     /**
    921      * Look up and return a message string, based on the specified
    922      * parameters.
    923      *
    924      * @param pageContext The PageContext associated with this request
    925      * @param bundle      Name of the servlet context attribute for our
    926      *                    message resources bundle
    927      * @param locale      Name of the session attribute for our user's Locale
    928      * @param key         Message key to be looked up and returned
    929      * @return message string
    930      * @throws JspException if a lookup error occurs (will have been saved in
    931      *                      the request already)
    932      */
    933     public String message(PageContext pageContext, String bundle,
    934         String locale, String key)
    935         throws JspException {
    936         return message(pageContext, bundle, locale, key, null);
    937     }
    938 
    939     /**
    940      * Look up and return a message string, based on the specified
    941      * parameters.
    942      *
    943      * @param pageContext The PageContext associated with this request
    944      * @param bundle      Name of the servlet context attribute for our
    945      *                    message resources bundle
    946      * @param locale      Name of the session attribute for our user's Locale
    947      * @param key         Message key to be looked up and returned
    948      * @param args        Replacement parameters for this message
    949      * @return message string
    950      * @throws JspException if a lookup error occurs (will have been saved in
    951      *                      the request already)
    952      */
    953     public String message(PageContext pageContext, String bundle,
    954         String locale, String key, Object[] args)
    955         throws JspException {
    956         MessageResources resources =
    957             retrieveMessageResources(pageContext, bundle, false);
    958 
    959         Locale userLocale = getUserLocale(pageContext, locale);
    960         String message = null;
    961 
    962         if (args == null) {
    963             message = resources.getMessage(userLocale, key);
    964         } else {
    965             message = resources.getMessage(userLocale, key, args);
    966         }
    967 
    968         if ((message == null) && log.isDebugEnabled()) {
    969             // log missing key to ease debugging
    970             log.debug(resources.getMessage("message.resources", key, bundle,
    971                     locale));
    972         }
    973 
    974         return message;
    975     }
    976 
    977     /**
    978      * <p>Return the context-relative URL that corresponds to the specified
    979      * <code>page</code> attribute value, calculated based on the
    980      * <code>pagePattern</code> property of the current module's {@link
    981      * ModuleConfig}.</p>
    982      *
    983      * @param request The servlet request we are processing
    984      * @param page    The module-relative URL to be substituted in to the
    985      *                <code>pagePattern</code> pattern for the current module
    986      *                (<strong>MUST</strong> start with a slash)
    987      * @return context-relative URL
    988      */
    989     public String pageURL(HttpServletRequest request, String page,
    990         ModuleConfig moduleConfig) {
    991         StringBuffer sb = new StringBuffer();
    992         String pagePattern =
    993             moduleConfig.getControllerConfig().getPagePattern();
    994 
    995         if (pagePattern == null) {
    996             sb.append(moduleConfig.getPrefix());
    997             sb.append(page);
    998         } else {
    999             boolean dollar = false;
    1000 
    1001             for (int i = 0; i < pagePattern.length(); i++) {
    1002                 char ch = pagePattern.charAt(i);
    1003 
    1004                 if (dollar) {
    1005                     switch (ch) {
    1006                     case 'M':
    1007                         sb.append(moduleConfig.getPrefix());
    1008 
    1009                         break;
    1010 
    1011                     case 'P':
    1012                         sb.append(page);
    1013 
    1014                         break;
    1015 
    1016                     case '$':
    1017                         sb.append('$');
    1018 
    1019                         break;
    1020 
    1021                     default:
    1022                         ; // Silently swallow
    1023                     }
    1024 
    1025                     dollar = false;
    1026 
    1027                     continue;
    1028                 } else if (ch == '$') {
    1029                     dollar = true;
    1030                 } else {
    1031                     sb.append(ch);
    1032                 }
    1033             }
    1034         }
    1035 
    1036         return sb.toString();
    1037     }
    1038 
    1039     /**
    1040      * Return true if a message string for the specified message key is
    1041      * present for the specified <code>Locale</code> and bundle.
    1042      *
    1043      * @param pageContext The PageContext associated with this request
    1044      * @param bundle      Name of the servlet context attribute for our
    1045      *                    message resources bundle
    1046      * @param locale      Name of the session attribute for our user's Locale
    1047      * @param key         Message key to be looked up and returned
    1048      * @return true if a message string for message key exists
    1049      * @throws JspException if a lookup error occurs (will have been saved in
    1050      *                      the request already)
    1051      */
    1052     public boolean present(PageContext pageContext, String bundle,
    1053         String locale, String key)
    1054         throws JspException {
    1055         MessageResources resources =
    1056             retrieveMessageResources(pageContext, bundle, true);
    1057 
    1058         Locale userLocale = getUserLocale(pageContext, locale);
    1059 
    1060         return resources.isPresent(userLocale, key);
    1061     }
    1062 
    1063     /**
    1064      * Returns the appropriate MessageResources object for the current module
    1065      * and the given bundle.
    1066      *
    1067      * @param pageContext    Search the context's scopes for the resources.
    1068      * @param bundle         The bundle name to look for.  If this is
    1069      *                       <code>null</code>, the default bundle name is
    1070      *                       used.
    1071      * @param checkPageScope Whether to check page scope
    1072      * @return MessageResources The bundle's resources stored in some scope.
    1073      * @throws JspException if the MessageResources object could not be
    1074      *                      found.
    1075      */
    1076     public MessageResources retrieveMessageResources(PageContext pageContext,
    1077         String bundle, boolean checkPageScope)
    1078         throws JspException {
    1079         MessageResources resources = null;
    1080 
    1081         if (bundle == null) {
    1082             bundle = Globals.MESSAGES_KEY;
    1083         }
    1084 
    1085         if (checkPageScope) {
    1086             resources =
    1087                 (MessageResources) pageContext.getAttribute(bundle,
    1088                     PageContext.PAGE_SCOPE);
    1089         }
    1090 
    1091         if (resources == null) {
    1092             resources =
    1093                 (MessageResources) pageContext.getAttribute(bundle,
    1094                     PageContext.REQUEST_SCOPE);
    1095         }
    1096 
    1097         if (resources == null) {
    1098             ModuleConfig moduleConfig = getModuleConfig(pageContext);
    1099 
    1100             resources =
    1101                 (MessageResources) pageContext.getAttribute(bundle
    1102                     + moduleConfig.getPrefix(), PageContext.APPLICATION_SCOPE);
    1103         }
    1104 
    1105         if (resources == null) {
    1106             resources =
    1107                 (MessageResources) pageContext.getAttribute(bundle,
    1108                     PageContext.APPLICATION_SCOPE);
    1109         }
    1110 
    1111         if (resources == null) {
    1112             JspException e =
    1113                 new JspException(messages.getMessage("message.bundle", bundle));
    1114 
    1115             saveException(pageContext, e);
    1116             throw e;
    1117         }
    1118 
    1119         return resources;
    1120     }
    1121 
    1122     /**
    1123      * Save the specified exception as a request attribute for later use.
    1124      *
    1125      * @param pageContext The PageContext for the current page
    1126      * @param exception   The exception to be saved
    1127      */
    1128     public void saveException(PageContext pageContext, Throwable exception) {
    1129         pageContext.setAttribute(Globals.EXCEPTION_KEY, exception,
    1130             PageContext.REQUEST_SCOPE);
    1131     }
    1132 
    1133     /**
    1134      * Write the specified text as the response to the writer associated with
    1135      * this page.  <strong>WARNING</strong> - If you are writing body content
    1136      * from the <code>doAfterBody()</code> method of a custom tag class that
    1137      * implements <code>BodyTag</code>, you should be calling
    1138      * <code>writePrevious()</code> instead.
    1139      *
    1140      * @param pageContext The PageContext object for this page
    1141      * @param text        The text to be written
    1142      * @throws JspException if an input/output error occurs (already saved)
    1143      */
    1144     public void write(PageContext pageContext, String text)
    1145         throws JspException {
    1146         JspWriter writer = pageContext.getOut();
    1147 
    1148         try {
    1149             writer.print(text);
    1150         } catch (IOException e) {
    1151             saveException(pageContext, e);
    1152             throw new JspException(messages.getMessage("write.io", e.toString()));
    1153         }
    1154     }
    1155 
    1156     /**
    1157      * Write the specified text as the response to the writer associated with
    1158      * the body content for the tag within which we are currently nested.
    1159      *
    1160      * @param pageContext The PageContext object for this page
    1161      * @param text        The text to be written
    1162      * @throws JspException if an input/output error occurs (already saved)
    1163      */
    1164     public void writePrevious(PageContext pageContext, String text)
    1165         throws JspException {
    1166         JspWriter writer = pageContext.getOut();
    1167 
    1168         if (writer instanceof BodyContent) {
    1169             writer = ((BodyContent) writer).getEnclosingWriter();
    1170         }
    1171 
    1172         try {
    1173             writer.print(text);
    1174         } catch (IOException e) {
    1175             saveException(pageContext, e);
    1176             throw new JspException(messages.getMessage("write.io", e.toString()));
    1177         }
    1178     }
    1179 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
