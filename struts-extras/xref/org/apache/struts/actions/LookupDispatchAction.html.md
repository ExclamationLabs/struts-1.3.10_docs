[View Javadoc](../../../../../apidocs/org/apache/struts/actions/LookupDispatchAction.html.md)


    1   /*
    2    * $Id: LookupDispatchAction.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.actions;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.Globals;
    26  import org.apache.struts.action.ActionForm;
    27  import org.apache.struts.action.ActionForward;
    28  import org.apache.struts.action.ActionMapping;
    29  import org.apache.struts.config.MessageResourcesConfig;
    30  import org.apache.struts.config.ModuleConfig;
    31  import org.apache.struts.util.MessageResources;
    32  
    33  import javax.servlet.ServletException;
    34  import javax.servlet.http.HttpServletRequest;
    35  import javax.servlet.http.HttpServletResponse;
    36  
    37  import java.util.HashMap;
    38  import java.util.Iterator;
    39  import java.util.Locale;
    40  import java.util.Map;
    41  
    42  /**
    43   * <p> An abstract <strong>Action</strong> that dispatches to the subclass
    44   * mapped <code>execute</code> method. This is useful in cases where an HTML
    45   * form has multiple submit buttons with the same name. The button name is
    46   * specified by the <code>parameter</code> property of the corresponding
    47   * ActionMapping. To configure the use of this action in your
    48   * <code>struts-config.xml</code> file, create an entry like this:</p> <pre>
    49   *   &lt;action path="/test"
    50   *           type="org.example.MyAction"
    51   *           name="MyForm"
    52   *          scope="request"
    53   *          input="/test.jsp"
    54   *      parameter="method"/&gt;
    55   * </pre> <p>
    56   *
    57   * which will use the value of the request parameter named "method" to locate
    58   * the corresponding key in ApplicationResources. For example, you might have
    59   * the following ApplicationResources.properties:</p> <pre>
    60   *    button.add=Add Record
    61   *    button.delete=Delete Record
    62   *  </pre><p>
    63   *
    64   * And your JSP would have the following format for submit buttons:</p> <pre>
    65   *   &lt.html.md:form action="/test"&gt;
    66   *    &lt.html.md:submit property="method"&gt;
    67   *      &lt;bean:message key="button.add"/&gt;
    68   *    &lt;.html.md:submit&gt;
    69   *    &lt.html.md:submit property="method"&gt;
    70   *      &lt;bean:message key="button.delete"/&gt;
    71   *    &lt;.html.md:submit&gt;
    72   *  &lt;.html.md:form&gt;
    73   *  </pre> <p>
    74   *
    75   * Your subclass must implement both getKeyMethodMap and the methods defined
    76   * in the map. An example of such implementations are:</p>
    77   * <pre>
    78   *  protected Map getKeyMethodMap() {
    79   *      Map map = new HashMap();
    80   *      map.put("button.add", "add");
    81   *      map.put("button.delete", "delete");
    82   *      return map;
    83   *  }
    84   *
    85   *  public ActionForward add(ActionMapping mapping,
    86   *          ActionForm form,
    87   *          HttpServletRequest request,
    88   *          HttpServletResponse response)
    89   *          throws IOException, ServletException {
    90   *      // do add
    91   *      return mapping.findForward("success");
    92   *  }
    93   *
    94   *  public ActionForward delete(ActionMapping mapping,
    95   *          ActionForm form,
    96   *          HttpServletRequest request,
    97   *          HttpServletResponse response)
    98   *          throws IOException, ServletException {
    99   *      // do delete
    100  *      return mapping.findForward("success");
    101  *  }
    102  * </pre>
    103  * <p> <strong>Notes</strong> - If duplicate values exist for the keys
    104  * returned by getKeys, only the first one found will be returned. If no
    105  * corresponding key is found then an exception will be thrown. You can
    106  * override the method <code>unspecified</code> to provide a custom handler.
    107  * If the submit was cancelled (a <code.html.md:cancel</code> button was
    108  * pressed), the custom handler <code>cancelled</code> will be used instead.
    109  */
    110 public abstract class LookupDispatchAction extends DispatchAction {
    111 
    112     /**
    113      * Commons Logging instance.
    114      */
    115     private static final Log LOG = LogFactory.getLog(LookupDispatchAction.class);
    116 
    117     /**
    118      * Reverse lookup map from resource value to resource key.
    119      */
    120     protected Map localeMap = new HashMap();
    121 
    122     /**
    123      * Resource key to method name lookup.
    124      */
    125     protected Map keyMethodMap = null;
    126 
    127     // ---------------------------------------------------------- Public Methods
    128 
    129     /**
    130      * Process the specified HTTP request, and create the corresponding HTTP
    131      * response (or forward to another web component that will create it).
    132      * Return an <code>ActionForward</code> instance describing where and how
    133      * control should be forwarded, or <code>null</code> if the response has
    134      * already been completed.
    135      *
    136      * @param mapping  The ActionMapping used to select this instance
    137      * @param request  The HTTP request we are processing
    138      * @param response The HTTP response we are creating
    139      * @param form     The optional ActionForm bean for this request (if any)
    140      * @return Describes where and how control should be forwarded.
    141      * @throws Exception if an error occurs
    142      */
    143     public ActionForward execute(ActionMapping mapping, ActionForm form,
    144         HttpServletRequest request, HttpServletResponse response)
    145         throws Exception {
    146         return super.execute(mapping, form, request, response);
    147     }
    148 
    149     /**
    150      * This is the first time this Locale is used so build the reverse lookup
    151      * Map. Search for message keys in all configured MessageResources for the
    152      * current module.
    153      *
    154      * @param request    The HTTP request we are processing
    155      * @param userLocale The locale for this request
    156      * @return The reverse lookup map for the specified locale.
    157      */
    158     private Map initLookupMap(HttpServletRequest request, Locale userLocale) {
    159         Map lookupMap = new HashMap();
    160 
    161         this.keyMethodMap = this.getKeyMethodMap();
    162 
    163         ModuleConfig moduleConfig =
    164             (ModuleConfig) request.getAttribute(Globals.MODULE_KEY);
    165 
    166         MessageResourcesConfig[] mrc =
    167             moduleConfig.findMessageResourcesConfigs();
    168 
    169         // Look through all module's MessageResources
    170         for (int i = 0; i < mrc.length; i++) {
    171             MessageResources resources =
    172                 this.getResources(request, mrc[i].getKey());
    173 
    174             // Look for key in MessageResources
    175             Iterator iter = this.keyMethodMap.keySet().iterator();
    176 
    177             while (iter.hasNext()) {
    178                 String key = (String) iter.next();
    179                 String text = resources.getMessage(userLocale, key);
    180 
    181                 // Found key and haven't added to Map yet, so add the text
    182                 if ((text != null) && !lookupMap.containsKey(text)) {
    183                     lookupMap.put(text, key);
    184                 }
    185             }
    186         }
    187 
    188         return lookupMap;
    189     }
    190 
    191     /**
    192      * Provides the mapping from resource key to method name.
    193      *
    194      * @return Resource key / method name map.
    195      */
    196     protected abstract Map getKeyMethodMap();
    197 
    198     /**
    199      * Lookup the method name corresponding to the client request's locale.
    200      *
    201      * @param request The HTTP request we are processing
    202      * @param keyName The parameter name to use as the properties key
    203      * @param mapping The ActionMapping used to select this instance
    204      * @return The method's localized name.
    205      * @throws ServletException if keyName cannot be resolved
    206      * @since Struts 1.2.0
    207      */
    208     protected String getLookupMapName(HttpServletRequest request,
    209         String keyName, ActionMapping mapping)
    210         throws ServletException {
    211         // Based on this request's Locale get the lookupMap
    212         Map lookupMap = null;
    213 
    214         synchronized (localeMap) {
    215             Locale userLocale = this.getLocale(request);
    216 
    217             lookupMap = (Map) this.localeMap.get(userLocale);
    218 
    219             if (lookupMap == null) {
    220                 lookupMap = this.initLookupMap(request, userLocale);
    221                 this.localeMap.put(userLocale, lookupMap);
    222             }
    223         }
    224 
    225         // Find the key for the resource
    226         String key = (String) lookupMap.get(keyName);
    227 
    228         if (key == null) {
    229             String message =
    230                 messages.getMessage("dispatch.resource", mapping.getPath());
    231             LOG.error(message + " '" + keyName + "'");
    232             throw new ServletException(message);
    233         }
    234 
    235         // Find the method name
    236         String methodName = (String) keyMethodMap.get(key);
    237 
    238         if (methodName == null) {
    239             String message =
    240                 messages.getMessage("dispatch.lookup", mapping.getPath(), key);
    241 
    242             throw new ServletException(message);
    243         }
    244 
    245         return methodName;
    246     }
    247 
    248     /**
    249      * Returns the method name, given a parameter's value.
    250      *
    251      * @param mapping   The ActionMapping used to select this instance
    252      * @param form      The optional ActionForm bean for this request (if
    253      *                  any)
    254      * @param request   The HTTP request we are processing
    255      * @param response  The HTTP response we are creating
    256      * @param parameter The <code>ActionMapping</code> parameter's name
    257      * @return The method's name.
    258      * @throws Exception if an error occurs
    259      * @since Struts 1.2.0
    260      */
    261     protected String getMethodName(ActionMapping mapping, ActionForm form,
    262         HttpServletRequest request, HttpServletResponse response,
    263         String parameter) throws Exception {
    264         // Identify the method name to be dispatched to.
    265         // dispatchMethod() will call unspecified() if name is null
    266         String keyName = request.getParameter(parameter);
    267 
    268         if ((keyName == null) || (keyName.length() == 0)) {
    269             return null;
    270         }
    271 
    272         String methodName = getLookupMapName(request, keyName, mapping);
    273 
    274         return methodName;
    275     }
    276 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
