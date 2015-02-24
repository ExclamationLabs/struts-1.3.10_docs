[View Javadoc](../../../../../apidocs/org/apache/struts/actions/ActionDispatcher.html.md)


    1   /*
    2    * $Id: ActionDispatcher.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import org.apache.struts.action.Action;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionForward;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.util.MessageResources;
    31  
    32  import javax.servlet.ServletException;
    33  import javax.servlet.http.HttpServletRequest;
    34  import javax.servlet.http.HttpServletResponse;
    35  
    36  import java.lang.reflect.InvocationTargetException;
    37  import java.lang.reflect.Method;
    38  
    39  import java.util.HashMap;
    40  
    41  /**
    42   * <p>Action <i>helper</i> class that dispatches to a public method in an
    43   * Action.</p> <p/> <p>This class is provided as an alternative mechanism to
    44   * using DispatchAction and its various flavours and means <i>Dispatch</i>
    45   * behaviour can be easily implemented into any <code>Action</code> without
    46   * having to inherit from a particular super <code>Action</code>.</p> <p/>
    47   * <p>To implement <i>dispatch</i> behaviour in an <code>Action</code> class,
    48   * create your custom Action as follows, along with the methods you require
    49   * (and optionally "cancelled" and "unspecified" methods):</p> <p/>
    50   * <pre>
    51   *   public class MyCustomAction extends Action {
    52   *
    53   *       protected ActionDispatcher dispatcher
    54   *                = new ActionDispatcher(this, ActionDispatcher.MAPPING_FLAVOR);
    55   *
    56   *       public ActionForward execute(ActionMapping mapping,
    57   *                                    ActionForm form,
    58   *                                    HttpServletRequest request,
    59   *                                    HttpServletResponse response)
    60   *                           throws Exception {
    61   *           return dispatcher.execute(mapping, form, request, response);
    62   *       }
    63   *   }
    64   * </pre>
    65   * <p/>
    66   *
    67   * <p>It provides three flavours of determing the name of the method:</p>
    68   *
    69   * <ul>
    70   *
    71   * <li><strong>{@link #DEFAULT_FLAVOR}</strong> - uses the parameter
    72   * specified in the struts-config.xml to get the method name from the Request
    73   * (equivalent to <code>DispatchAction</code> <b>except</b> uses "method" as a
    74   * default if the <code>parameter</code> is not specified in the
    75   * struts-config.xml).</li>
    76   *
    77   * <li><strong>{@link #DISPATCH_FLAVOR}</strong>
    78   * - uses the parameter specified in the struts-config.xml to get the method
    79   * name from the Request (equivalent to <code>DispatchAction</code>).</li>
    80   *
    81   * <li><strong>{@link #MAPPING_FLAVOR}</strong> - uses the parameter
    82   * specified in the struts-config.xml as the method name (equivalent to
    83   * <code>MappingDispatchAction</code>).</li>
    84  
    85   * </ul>
    86   *
    87   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    88   * @since Struts 1.2.7
    89   */
    90  public class ActionDispatcher {
    91      // ----------------------------------------------------- Instance Variables
    92  
    93      /**
    94       * Indicates "default" dispatch flavor.
    95       */
    96      public static final int DEFAULT_FLAVOR = 0;
    97  
    98      /**
    99       * Indicates "mapping" dispatch flavor.
    100      */
    101     public static final int MAPPING_FLAVOR = 1;
    102 
    103     /**
    104      * Indicates flavor compatible with DispatchAction.
    105      */
    106     public static final int DISPATCH_FLAVOR = 2;
    107 
    108     /**
    109      * Commons Logging instance.
    110      */
    111     protected static Log log = LogFactory.getLog(ActionDispatcher.class);
    112 
    113     /**
    114      * The message resources for this package.
    115      */
    116     protected static MessageResources messages =
    117         MessageResources.getMessageResources(
    118             "org.apache.struts.actions.LocalStrings");
    119 
    120     /**
    121      * The associated Action to dispatch to.
    122      */
    123     protected Action actionInstance;
    124 
    125     /**
    126      * Indicates dispatch <i>flavor</i>.
    127      */
    128     protected int flavor;
    129 
    130     /**
    131      * The Class instance of this <code>DispatchAction</code> class.
    132      */
    133     protected Class clazz;
    134 
    135     /**
    136      * The set of Method objects we have introspected for this class, keyed by
    137      * method name.  This collection is populated as different methods are
    138      * called, so that introspection needs to occur only once per method
    139      * name.
    140      */
    141     protected HashMap methods = new HashMap();
    142 
    143     /**
    144      * The set of argument type classes for the reflected method call.  These
    145      * are the same for all calls, so calculate them only once.
    146      */
    147     protected Class[] types =
    148         {
    149             ActionMapping.class, ActionForm.class, HttpServletRequest.class,
    150             HttpServletResponse.class
    151         };
    152 
    153     // ----------------------------------------------------- Constructors
    154 
    155     /**
    156      * Construct an instance of this class from the supplied parameters.
    157      *
    158      * @param actionInstance The action instance to be invoked.
    159      */
    160     public ActionDispatcher(Action actionInstance) {
    161         this(actionInstance, DEFAULT_FLAVOR);
    162     }
    163 
    164     /**
    165      * Construct an instance of this class from the supplied parameters.
    166      *
    167      * @param actionInstance The action instance to be invoked.
    168      * @param flavor         The flavor of dispatch to use.
    169      */
    170     public ActionDispatcher(Action actionInstance, int flavor) {
    171         this.actionInstance = actionInstance;
    172         this.flavor = flavor;
    173 
    174         clazz = actionInstance.getClass();
    175     }
    176 
    177     // --------------------------------------------------------- Public Methods
    178 
    179     /**
    180      * Process the specified HTTP request, and create the corresponding HTTP
    181      * response (or forward to another web component that will create it).
    182      * Return an <code>ActionForward</code> instance describing where and how
    183      * control should be forwarded, or <code>null</code> if the response has
    184      * already been completed.
    185      *
    186      * @param mapping  The ActionMapping used to select this instance
    187      * @param form     The optional ActionForm bean for this request (if any)
    188      * @param request  The HTTP request we are processing
    189      * @param response The HTTP response we are creating
    190      * @return The forward to which control should be transferred, or
    191      *         <code>null</code> if the response has been completed.
    192      * @throws Exception if an exception occurs
    193      */
    194     public ActionForward execute(ActionMapping mapping, ActionForm form,
    195         HttpServletRequest request, HttpServletResponse response)
    196         throws Exception {
    197         // Process "cancelled"
    198         if (isCancelled(request)) {
    199             ActionForward af = cancelled(mapping, form, request, response);
    200 
    201             if (af != null) {
    202                 return af;
    203             }
    204         }
    205 
    206         // Identify the request parameter containing the method name
    207         String parameter = getParameter(mapping, form, request, response);
    208 
    209         // Get the method's name. This could be overridden in subclasses.
    210         String name =
    211             getMethodName(mapping, form, request, response, parameter);
    212 
    213         // Prevent recursive calls
    214         if ("execute".equals(name) || "perform".equals(name)) {
    215             String message =
    216                 messages.getMessage("dispatch.recursive", mapping.getPath());
    217 
    218             log.error(message);
    219             throw new ServletException(message);
    220         }
    221 
    222         // Invoke the named method, and return the result
    223         return dispatchMethod(mapping, form, request, response, name);
    224     }
    225 
    226     /**
    227      * <p>Dispatches to the target class' <code>unspecified</code> method, if
    228      * present, otherwise throws a ServletException. Classes utilizing
    229      * <code>ActionDispatcher</code> should provide an <code>unspecified</code>
    230      * method if they wish to provide behavior different than throwing a
    231      * ServletException.</p>
    232      *
    233      * @param mapping  The ActionMapping used to select this instance
    234      * @param form     The optional ActionForm bean for this request (if any)
    235      * @param request  The non-HTTP request we are processing
    236      * @param response The non-HTTP response we are creating
    237      * @return The forward to which control should be transferred, or
    238      *         <code>null</code> if the response has been completed.
    239      * @throws Exception if the application business logic throws an
    240      *                   exception.
    241      */
    242     protected ActionForward unspecified(ActionMapping mapping, ActionForm form,
    243         HttpServletRequest request, HttpServletResponse response)
    244         throws Exception {
    245         // Identify if there is an "unspecified" method to be dispatched to
    246         String name = "unspecified";
    247         Method method = null;
    248 
    249         try {
    250             method = getMethod(name);
    251         } catch (NoSuchMethodException e) {
    252             String message =
    253                 messages.getMessage("dispatch.parameter", mapping.getPath(),
    254                     mapping.getParameter());
    255 
    256             log.error(message);
    257 
    258             throw new ServletException(message);
    259         }
    260 
    261         return dispatchMethod(mapping, form, request, response, name, method);
    262     }
    263 
    264     /**
    265      * <p>Dispatches to the target class' cancelled method, if present,
    266      * otherwise returns null. Classes utilizing <code>ActionDispatcher</code>
    267      * should provide a <code>cancelled</code> method if they wish to provide
    268      * behavior different than returning null.</p>
    269      *
    270      * @param mapping  The ActionMapping used to select this instance
    271      * @param form     The optional ActionForm bean for this request (if any)
    272      * @param request  The non-HTTP request we are processing
    273      * @param response The non-HTTP response we are creating
    274      * @return The forward to which control should be transferred, or
    275      *         <code>null</code> if the response has been completed.
    276      * @throws Exception if the application business logic throws an
    277      *                   exception.
    278      */
    279     protected ActionForward cancelled(ActionMapping mapping, ActionForm form,
    280         HttpServletRequest request, HttpServletResponse response)
    281         throws Exception {
    282         // Identify if there is an "cancelled" method to be dispatched to
    283         String name = "cancelled";
    284         Method method = null;
    285 
    286         try {
    287             method = getMethod(name);
    288         } catch (NoSuchMethodException e) {
    289             return null;
    290         }
    291 
    292         return dispatchMethod(mapping, form, request, response, name, method);
    293     }
    294 
    295     // ----------------------------------------------------- Protected Methods
    296 
    297     /**
    298      * Dispatch to the specified method.
    299      *
    300      * @param mapping  The ActionMapping used to select this instance
    301      * @param form     The optional ActionForm bean for this request (if any)
    302      * @param request  The non-HTTP request we are processing
    303      * @param response The non-HTTP response we are creating
    304      * @param name     The name of the method to invoke
    305      * @return The forward to which control should be transferred, or
    306      *         <code>null</code> if the response has been completed.
    307      * @throws Exception if the application business logic throws an
    308      *                   exception.
    309      */
    310     protected ActionForward dispatchMethod(ActionMapping mapping,
    311         ActionForm form, HttpServletRequest request,
    312         HttpServletResponse response, String name)
    313         throws Exception {
    314         // Make sure we have a valid method name to call.
    315         // This may be null if the user hacks the query string.
    316         if (name == null) {
    317             return this.unspecified(mapping, form, request, response);
    318         }
    319 
    320         // Identify the method object to be dispatched to
    321         Method method = null;
    322 
    323         try {
    324             method = getMethod(name);
    325         } catch (NoSuchMethodException e) {
    326             String message =
    327                 messages.getMessage("dispatch.method", mapping.getPath(), name);
    328 
    329             log.error(message, e);
    330 
    331             String userMsg =
    332                 messages.getMessage("dispatch.method.user", mapping.getPath());
    333             throw new NoSuchMethodException(userMsg);
    334         }
    335 
    336         return dispatchMethod(mapping, form, request, response, name, method);
    337     }
    338 
    339     /**
    340      * Dispatch to the specified method.
    341      *
    342      * @param mapping  The ActionMapping used to select this instance
    343      * @param form     The optional ActionForm bean for this request (if any)
    344      * @param request  The non-HTTP request we are processing
    345      * @param response The non-HTTP response we are creating
    346      * @param name     The name of the method to invoke
    347      * @param method   The method to invoke
    348      * @return The forward to which control should be transferred, or
    349      *         <code>null</code> if the response has been completed.
    350      * @throws Exception if the application business logic throws an
    351      *                   exception.
    352      */
    353     protected ActionForward dispatchMethod(ActionMapping mapping,
    354         ActionForm form, HttpServletRequest request,
    355         HttpServletResponse response, String name, Method method)
    356         throws Exception {
    357         ActionForward forward = null;
    358 
    359         try {
    360             Object[] args = { mapping, form, request, response };
    361 
    362             forward = (ActionForward) method.invoke(actionInstance, args);
    363         } catch (ClassCastException e) {
    364             String message =
    365                 messages.getMessage("dispatch.return", mapping.getPath(), name);
    366 
    367             log.error(message, e);
    368             throw e;
    369         } catch (IllegalAccessException e) {
    370             String message =
    371                 messages.getMessage("dispatch.error", mapping.getPath(), name);
    372 
    373             log.error(message, e);
    374             throw e;
    375         } catch (InvocationTargetException e) {
    376             // Rethrow the target exception if possible so that the
    377             // exception handling machinery can deal with it
    378             Throwable t = e.getTargetException();
    379 
    380             if (t instanceof Exception) {
    381                 throw ((Exception) t);
    382             } else {
    383                 String message =
    384                     messages.getMessage("dispatch.error", mapping.getPath(),
    385                         name);
    386 
    387                 log.error(message, e);
    388                 throw new ServletException(t);
    389             }
    390         }
    391 
    392         // Return the returned ActionForward instance
    393         return (forward);
    394     }
    395 
    396     /**
    397      * Introspect the current class to identify a method of the specified name
    398      * that accepts the same parameter types as the <code>execute</code>
    399      * method does.
    400      *
    401      * @param name Name of the method to be introspected
    402      * @return The method with the specified name.
    403      * @throws NoSuchMethodException if no such method can be found
    404      */
    405     protected Method getMethod(String name)
    406         throws NoSuchMethodException {
    407         synchronized (methods) {
    408             Method method = (Method) methods.get(name);
    409 
    410             if (method == null) {
    411                 method = clazz.getMethod(name, types);
    412                 methods.put(name, method);
    413             }
    414 
    415             return (method);
    416         }
    417     }
    418 
    419     /**
    420      * <p>Returns the parameter value as influenced by the selected {@link
    421      * #flavor} specified for this <code>ActionDispatcher</code>.</p>
    422      *
    423      * @param mapping  The ActionMapping used to select this instance
    424      * @param form     The optional ActionForm bean for this request (if any)
    425      * @param request  The HTTP request we are processing
    426      * @param response The HTTP response we are creating
    427      * @return The <code>ActionMapping</code> parameter's value
    428      * @throws Exception if an error occurs.
    429      */
    430     protected String getParameter(ActionMapping mapping, ActionForm form,
    431         HttpServletRequest request, HttpServletResponse response)
    432         throws Exception {
    433         String parameter = mapping.getParameter();
    434 
    435         if ("".equals(parameter)) {
    436             parameter = null;
    437         }
    438 
    439         if ((parameter == null) && (flavor == DEFAULT_FLAVOR)) {
    440             // use "method" for DEFAULT_FLAVOR if no parameter was provided
    441             return "method";
    442         }
    443 
    444         if ((parameter == null)
    445             && ((flavor == MAPPING_FLAVOR) || (flavor == DISPATCH_FLAVOR))) {
    446             String message =
    447                 messages.getMessage("dispatch.handler", mapping.getPath());
    448 
    449             log.error(message);
    450 
    451             throw new ServletException(message);
    452         }
    453 
    454         return parameter;
    455     }
    456 
    457     /**
    458      * Returns the method name, given a parameter's value.
    459      *
    460      * @param mapping   The ActionMapping used to select this instance
    461      * @param form      The optional ActionForm bean for this request (if
    462      *                  any)
    463      * @param request   The HTTP request we are processing
    464      * @param response  The HTTP response we are creating
    465      * @param parameter The <code>ActionMapping</code> parameter's name
    466      * @return The method's name.
    467      * @throws Exception if an error occurs.
    468      */
    469     protected String getMethodName(ActionMapping mapping, ActionForm form,
    470         HttpServletRequest request, HttpServletResponse response,
    471         String parameter) throws Exception {
    472         // "Mapping" flavor, defaults to "method"
    473         if (flavor == MAPPING_FLAVOR) {
    474             return parameter;
    475         }
    476 
    477         // default behaviour
    478         return request.getParameter(parameter);
    479     }
    480 
    481     /**
    482      * <p>Returns <code>true</code> if the current form's cancel button was
    483      * pressed.  This method will check if the <code>Globals.CANCEL_KEY</code>
    484      * request attribute has been set, which normally occurs if the cancel
    485      * button generated by <strong>CancelTag</strong> was pressed by the user
    486      * in the current request.  If <code>true</code>, validation performed by
    487      * an <strong>ActionForm</strong>'s <code>validate()</code> method will
    488      * have been skipped by the controller servlet.</p>
    489      *
    490      * @param request The servlet request we are processing
    491      * @return <code>true</code> if the current form's cancel button was
    492      *         pressed; <code>false</code> otherwise.
    493      * @see org.apache.struts.taglib.html.md.CancelTag
    494      */
    495     protected boolean isCancelled(HttpServletRequest request) {
    496         return (request.getAttribute(Globals.CANCEL_KEY) != null);
    497     }
    498 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
