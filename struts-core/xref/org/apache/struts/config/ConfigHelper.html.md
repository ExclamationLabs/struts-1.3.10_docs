[View Javadoc](../../../../../apidocs/org/apache/struts/config/ConfigHelper.html.md)


    1   /*
    2    * $Id: ConfigHelper.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.config;
    22  
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.action.ActionForm;
    25  import org.apache.struts.action.ActionFormBean;
    26  import org.apache.struts.action.ActionForward;
    27  import org.apache.struts.action.ActionMapping;
    28  import org.apache.struts.action.ActionMessages;
    29  import org.apache.struts.upload.MultipartRequestWrapper;
    30  import org.apache.struts.util.MessageResources;
    31  import org.apache.struts.util.RequestUtils;
    32  
    33  import javax.servlet.ServletContext;
    34  import javax.servlet.http.HttpServletRequest;
    35  import javax.servlet.http.HttpServletResponse;
    36  import javax.servlet.http.HttpSession;
    37  
    38  /**
    39   * <p> NOTE: THIS CLASS IS UNDER ACTIVE DEVELOPMENT. THE CURRENT CODE IS
    40   * WRITTEN FOR CLARITY NOT EFFICIENCY. NOT EVERY API FUNCTION HAS BEEN
    41   * IMPLEMENTED YET. </p><p> A helper object to expose the Struts shared
    42   * resources, which are be stored in the application, session, or request
    43   * contexts, as appropriate. </p><p> An instance should be created for each
    44   * request processed. The  methods which return resources from the request or
    45   * session contexts are not thread-safe. </p><p> Provided for use by other
    46   * servlets in the application so they can easily access the Struts shared
    47   * resources. </p><p> The resources are stored under attributes in the
    48   * application, session, or request contexts. </p><p> The ActionConfig methods
    49   * simply return the resources from under the context and key used by the
    50   * Struts ActionServlet when the resources are created. </p>
    51   *
    52   * @version $Rev: 471754 $ $Date: 2005-05-14 02:09:06 -0400 (Sat, 14 May 2005)
    53   *          $
    54   * @since Struts 1.1
    55   */
    56  public class ConfigHelper implements ConfigHelperInterface {
    57      // --------------------------------------------------------  Properites
    58  
    59      /**
    60       * <p> The application associated with this instance. </p>
    61       */
    62      private ServletContext application = null;
    63  
    64      /**
    65       * <p> The session associated with this instance. </p>
    66       */
    67      private HttpSession session = null;
    68  
    69      /**
    70       * <p> The request associated with this instance. </p>
    71       */
    72      private HttpServletRequest request = null;
    73  
    74      /**
    75       * <p> The response associated with this instance. </p>
    76       */
    77      private HttpServletResponse response = null;
    78  
    79      /**
    80       * <p> The forward associated with this instance. </p>
    81       */
    82      private ActionForward forward = null;
    83  
    84      public ConfigHelper() {
    85          super();
    86      }
    87  
    88      public ConfigHelper(ServletContext application, HttpServletRequest request,
    89          HttpServletResponse response) {
    90          super();
    91          this.setResources(application, request, response);
    92      }
    93  
    94      /**
    95       * <p> Set the application associated with this instance.
    96       * [servlet.getServletContext()] </p>
    97       */
    98      public void setApplication(ServletContext application) {
    99          this.application = application;
    100     }
    101 
    102     /**
    103      * <p> Set the session associated with this instance. </p>
    104      */
    105     public void setSession(HttpSession session) {
    106         this.session = session;
    107     }
    108 
    109     /**
    110      * <p> Set the request associated with this object. Session object is also
    111      * set or cleared. </p>
    112      */
    113     public void setRequest(HttpServletRequest request) {
    114         this.request = request;
    115 
    116         if (this.request == null) {
    117             setSession(null);
    118         } else {
    119             setSession(this.request.getSession());
    120         }
    121     }
    122 
    123     /**
    124      * <p> Set the response associated with this isntance. Session object is
    125      * also set or cleared. </p>
    126      */
    127     public void setResponse(HttpServletResponse response) {
    128         this.response = response;
    129     }
    130 
    131     /**
    132      * Set the forward associated with this instance.
    133      */
    134     public void setForward(ActionForward forward) {
    135         this.forward = forward;
    136     }
    137 
    138     /**
    139      * <p> Set the application and request for this object instance. The
    140      * ServletContext can be set by any servlet in the application. The
    141      * request should be the instant request. Most of the other methods
    142      * retrieve their own objects by reference to the application, request, or
    143      * session attributes. Do not call other methods without setting these
    144      * first! This is also called by the convenience constructor. </p>
    145      *
    146      * @param application - The associated ServletContext.
    147      * @param request     - The associated HTTP request.
    148      * @param response    - The associated HTTP response.
    149      */
    150     public void setResources(ServletContext application,
    151         HttpServletRequest request, HttpServletResponse response) {
    152         setApplication(application);
    153         setRequest(request);
    154         setResponse(response);
    155     }
    156 
    157     // ------------------------------------------------ Application Context
    158     public ActionMessages getActionMessages() {
    159         if (this.application == null) {
    160             return null;
    161         }
    162 
    163         return (ActionMessages) this.application.getAttribute(Globals.MESSAGE_KEY);
    164     }
    165 
    166     /**
    167      * <p> The application resources for this application. </p>
    168      */
    169     public MessageResources getMessageResources() {
    170         if (this.application == null) {
    171             return null;
    172         }
    173 
    174         return (MessageResources) this.application.getAttribute(Globals.MESSAGES_KEY);
    175     }
    176 
    177     /**
    178      * <p> The path-mapped pattern (<code>/action/*</code>) or extension
    179      * mapped pattern ((<code>*.do</code>) used to determine our Action URIs
    180      * in this application. </p>
    181      */
    182     public String getServletMapping() {
    183         if (this.application == null) {
    184             return null;
    185         }
    186 
    187         return (String) this.application.getAttribute(Globals.SERVLET_KEY);
    188     }
    189 
    190     // ---------------------------------------------------- Session Context
    191 
    192     /**
    193      * <p> The transaction token stored in this session, if it is used. </p>
    194      */
    195     public String getToken() {
    196         if (this.session == null) {
    197             return null;
    198         }
    199 
    200         return (String) session.getAttribute(Globals.TRANSACTION_TOKEN_KEY);
    201     }
    202 
    203     // ---------------------------------------------------- Request Context
    204 
    205     /**
    206      * <p> The runtime JspException that may be been thrown by a Struts tag
    207      * extension, or compatible presentation extension, and placed in the
    208      * request. </p>
    209      */
    210     public Throwable getException() {
    211         if (this.request == null) {
    212             return null;
    213         }
    214 
    215         return (Throwable) this.request.getAttribute(Globals.EXCEPTION_KEY);
    216     }
    217 
    218     /**
    219      * <p> The multipart object for this request. </p>
    220      */
    221     public MultipartRequestWrapper getMultipartRequestWrapper() {
    222         if (this.request == null) {
    223             return null;
    224         }
    225 
    226         return (MultipartRequestWrapper) this.request.getAttribute(Globals.MULTIPART_KEY);
    227     }
    228 
    229     /**
    230      * <p> The <code>org.apache.struts.ActionMapping</code> instance for this
    231      * request. </p>
    232      */
    233     public ActionMapping getMapping() {
    234         if (this.request == null) {
    235             return null;
    236         }
    237 
    238         return (ActionMapping) this.request.getAttribute(Globals.MAPPING_KEY);
    239     }
    240 
    241     // ---------------------------------------------------- Utility Methods
    242 
    243     /**
    244      * <p> Return true if a message string for the specified message key is
    245      * present for the user's Locale. </p>
    246      *
    247      * @param key Message key
    248      */
    249     public boolean isMessage(String key) {
    250         // Look up the requested MessageResources
    251         MessageResources resources = getMessageResources();
    252 
    253         if (resources == null) {
    254             return false;
    255         }
    256 
    257         // Return the requested message presence indicator
    258         return resources.isPresent(RequestUtils.getUserLocale(request, null),
    259             key);
    260     }
    261 
    262     /*
    263      * <p>
    264      * Retrieve and return the <code>ActionForm</code> bean associated with
    265      * this mapping, creating and stashing one if necessary.  If there is no
    266      * form bean associated with this mapping, return <code>null</code>.
    267      * </p>
    268      */
    269     public ActionForm getActionForm() {
    270         // Is there a mapping associated with this request?
    271         ActionMapping mapping = getMapping();
    272 
    273         if (mapping == null) {
    274             return (null);
    275         }
    276 
    277         // Is there a form bean associated with this mapping?
    278         String attribute = mapping.getAttribute();
    279 
    280         if (attribute == null) {
    281             return (null);
    282         }
    283 
    284         // Look up the existing form bean, if any
    285         ActionForm instance;
    286 
    287         if ("request".equals(mapping.getScope())) {
    288             instance = (ActionForm) this.request.getAttribute(attribute);
    289         } else {
    290             instance = (ActionForm) this.session.getAttribute(attribute);
    291         }
    292 
    293         return instance;
    294     }
    295 
    296     /**
    297      * <p> Return the form bean definition associated with the specified
    298      * logical name, if any; otherwise return <code>null</code>. </p>
    299      *
    300      * @param name Logical name of the requested form bean definition
    301      */
    302     public ActionFormBean getFormBean(String name) {
    303         return null;
    304     }
    305 
    306     /**
    307      * <p> Return the forwarding associated with the specified logical name,
    308      * if any; otherwise return <code>null</code>. </p>
    309      *
    310      * @param name Logical name of the requested forwarding
    311      */
    312     public ActionForward getActionForward(String name) {
    313         return null;
    314     }
    315 
    316     /**
    317      * <p> Return the mapping associated with the specified request path, if
    318      * any; otherwise return <code>null</code>. </p>
    319      *
    320      * @param path Request path for which a mapping is requested
    321      */
    322     public ActionMapping getActionMapping(String path) {
    323         return null;
    324     }
    325 
    326     /**
    327      * <p> Return the form action converted into an action mapping path.  The
    328      * value of the <code>action</code> property is manipulated as follows in
    329      * computing the name of the requested mapping:</p>
    330      *
    331      * <ul>
    332      *
    333      * <li>Any filename extension is removed (on the theory that extension
    334      * mapping is being used to select the controller servlet).</li>
    335      *
    336      * <li>If the resulting value does not start with a slash, then a slash is
    337      * prepended.</li>
    338      *
    339      * </ul>
    340      */
    341     public String getActionMappingName(String action) {
    342         String value = action;
    343         int question = action.indexOf("?");
    344 
    345         if (question >= 0) {
    346             value = value.substring(0, question);
    347         }
    348 
    349         int slash = value.lastIndexOf("/");
    350         int period = value.lastIndexOf(".");
    351 
    352         if ((period >= 0) && (period > slash)) {
    353             value = value.substring(0, period);
    354         }
    355 
    356         if (value.startsWith("/")) {
    357             return (value);
    358         } else {
    359             return ("/" + value);
    360         }
    361     }
    362 
    363     /**
    364      * <p> Return the form action converted into a server-relative URL. </p>
    365      */
    366     public String getActionMappingURL(String action) {
    367         StringBuffer value = new StringBuffer(this.request.getContextPath());
    368 
    369         // Use our servlet mapping, if one is specified
    370         String servletMapping = getServletMapping();
    371 
    372         if (servletMapping != null) {
    373             String queryString = null;
    374             int question = action.indexOf("?");
    375 
    376             if (question >= 0) {
    377                 queryString = action.substring(question);
    378             }
    379 
    380             String actionMapping = getActionMappingName(action);
    381 
    382             if (servletMapping.startsWith("*.")) {
    383                 value.append(actionMapping);
    384                 value.append(servletMapping.substring(1));
    385             } else if (servletMapping.endsWith("/*")) {
    386                 value.append(servletMapping.substring(0,
    387                         servletMapping.length() - 2));
    388                 value.append(actionMapping);
    389             }
    390 
    391             if (queryString != null) {
    392                 value.append(queryString);
    393             }
    394         }
    395         // Otherwise, assume extension mapping is in use and extension is
    396         // already included in the action property
    397         else {
    398             if (!action.startsWith("/")) {
    399                 value.append("/");
    400             }
    401 
    402             value.append(action);
    403         }
    404 
    405         // Return the completed value
    406         return (value.toString());
    407     }
    408 
    409     /**
    410      * <p> Return the url encoded to maintain the user session, if any. </p>
    411      */
    412     public String getEncodeURL(String url) {
    413         if ((session != null) && (response != null)) {
    414             boolean redirect = false;
    415 
    416             if (forward != null) {
    417                 redirect = forward.getRedirect();
    418             }
    419 
    420             if (redirect) {
    421                 return response.encodeRedirectURL(url);
    422             } else {
    423                 return response.encodeURL(url);
    424             }
    425         } else {
    426             return (url);
    427         }
    428     }
    429 
    430     // ------------------------------------------------ Presentation API
    431 
    432     /**
    433      * <p> Renders the reference for a HTML <base> element </p>
    434      */
    435     public String getOrigRef() {
    436         // HttpServletRequest request = (HttpServletRequest)pageContext.getRequest();
    437         if (request == null) {
    438             return null;
    439         }
    440 
    441         StringBuffer result =
    442             RequestUtils.requestToServerUriStringBuffer(request);
    443 
    444         return result.toString();
    445     }
    446 
    447     /**
    448      * <p> Renders the reference for a HTML <base> element. </p>
    449      */
    450     public String getBaseRef() {
    451         if (request == null) {
    452             return null;
    453         }
    454 
    455         StringBuffer result = RequestUtils.requestToServerStringBuffer(request);
    456         String path;
    457 
    458         if (forward == null) {
    459             path = request.getRequestURI();
    460         } else {
    461             path = request.getContextPath() + forward.getPath();
    462         }
    463 
    464         result.append(path);
    465 
    466         return result.toString();
    467     }
    468 
    469     /**
    470      * <p> Return the path for the specified forward, otherwise return
    471      * <code>null</code>. </p>
    472      *
    473      * @param name Name given to local or global forward.
    474      */
    475     public String getLink(String name) {
    476         ActionForward forward = getActionForward(name);
    477 
    478         if (forward == null) {
    479             return null;
    480         }
    481 
    482         StringBuffer path = new StringBuffer(this.request.getContextPath());
    483 
    484         path.append(forward.getPath());
    485 
    486         // :TODO: What about runtime parameters?
    487         return getEncodeURL(path.toString());
    488     }
    489 
    490     /**
    491      * <p> Return the localized message for the specified key, otherwise
    492      * return <code>null</code>. </p>
    493      *
    494      * @param key Message key
    495      */
    496     public String getMessage(String key) {
    497         MessageResources resources = getMessageResources();
    498 
    499         if (resources == null) {
    500             return null;
    501         }
    502 
    503         return resources.getMessage(RequestUtils.getUserLocale(request, null),
    504             key);
    505     }
    506 
    507     /**
    508      * <p> Look up and return a message string, based on the specified
    509      * parameters. </p>
    510      *
    511      * @param key  Message key to be looked up and returned
    512      * @param args Replacement parameters for this message
    513      */
    514     public String getMessage(String key, Object[] args) {
    515         MessageResources resources = getMessageResources();
    516 
    517         if (resources == null) {
    518             return null;
    519         }
    520 
    521         // Return the requested message
    522         if (args == null) {
    523             return resources.getMessage(RequestUtils.getUserLocale(request, null),
    524                 key);
    525         } else {
    526             return resources.getMessage(RequestUtils.getUserLocale(request, null),
    527                 key, args);
    528         }
    529     }
    530 
    531     /**
    532      * <p> Return the URL for the specified ActionMapping, otherwise return
    533      * <code>null</code>. </p>
    534      *
    535      * @param path Name given to local or global forward.
    536      */
    537     public String getAction(String path) {
    538         return getEncodeURL(getActionMappingURL(path));
    539     }
    540 
    541     // --------------------------------------------- Presentation Wrappers
    542 
    543     /**
    544      * <p> Wrapper for getLink(String) </p>
    545      *
    546      * @param name Name given to local or global forward.
    547      */
    548     public String link(String name) {
    549         return getLink(name);
    550     }
    551 
    552     /**
    553      * <p> Wrapper for getMessage(String) </p>
    554      *
    555      * @param key Message key
    556      */
    557     public String message(String key) {
    558         return getMessage(key);
    559     }
    560 
    561     /**
    562      * <p> Wrapper for getMessage(String,Object[]) </p>
    563      *
    564      * @param key  Message key to be looked up and returned
    565      * @param args Replacement parameters for this message
    566      */
    567     public String message(String key, Object[] args) {
    568         return getMessage(key, args);
    569     }
    570 
    571     /**
    572      * <p> Wrapper for getAction(String) </p>
    573      *
    574      * @param path Name given to local or global forward.
    575      */
    576     public String action(String path) {
    577         return getAction(path);
    578     }
    579 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
