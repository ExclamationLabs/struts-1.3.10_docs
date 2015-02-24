[View Javadoc](../../../../../apidocs/org/apache/struts/actions/DispatchAction.html.md)


    1   /*
    2    * $Id: DispatchAction.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import org.apache.struts.action.ActionForm;
    26  import org.apache.struts.action.ActionForward;
    27  import org.apache.struts.action.ActionMapping;
    28  
    29  import javax.servlet.ServletException;
    30  import javax.servlet.http.HttpServletRequest;
    31  import javax.servlet.http.HttpServletResponse;
    32  
    33  import java.lang.reflect.InvocationTargetException;
    34  import java.lang.reflect.Method;
    35  
    36  import java.util.HashMap;
    37  
    38  /**
    39   * <p>An abstract <strong>Action</strong> that dispatches to a public method
    40   * that is named by the request parameter whose name is specified by the
    41   * <code>parameter</code> property of the corresponding ActionMapping.  This
    42   * Action is useful for developers who prefer to combine many similar actions
    43   * into a single Action class, in order to simplify their application
    44   * design.</p>
    45   *
    46   * <p>To configure the use of this action in your <code>struts-config.xml</code>
    47   * file, create an entry like this:</p>
    48   *
    49   * <code> &lt;action path="/saveSubscription" type="org.apache.struts.actions.DispatchAction"
    50   * name="subscriptionForm" scope="request" input="/subscription.jsp"
    51   * parameter="method"/&gt; </code>
    52   *
    53   * <p>which will use the value of the request parameter named "method" to pick
    54   * the appropriate "execute" method, which must have the same signature (other
    55   * than method name) of the standard Action.execute method.  For example, you
    56   * might have the following three methods in the same action:</p>
    57   *
    58   * <ul>
    59   *
    60   * <li>public ActionForward delete(ActionMapping mapping, ActionForm form,
    61   * HttpServletRequest request, HttpServletResponse response) throws
    62   * Exception</li>
    63   *
    64   * <li>public ActionForward insert(ActionMapping mapping, ActionForm form,
    65   * HttpServletRequest request, HttpServletResponse response) throws
    66   * Exception</li>
    67   *
    68   * <li>public ActionForward update(ActionMapping mapping, ActionForm form,
    69   * HttpServletRequest request, HttpServletResponse response) throws
    70   * Exception</li>
    71   *
    72   * </ul>
    73   *
    74   * <p>and call one of the methods with a URL like this:</p>
    75   *
    76   * <p> <code> http://localhost:8080/myapp/saveSubscription.do?method=update
    77   * </code></p>
    78   *
    79   * <p><strong>NOTE</strong> - All of the other mapping characteristics of this
    80   * action must be shared by the various handlers.  This places some
    81   * constraints over what types of handlers may reasonably be packaged into the
    82   * same <code>DispatchAction</code> subclass.</p>
    83   *
    84   * <p><strong>NOTE</strong> - If the value of the request parameter is empty,
    85   * a method named <code>unspecified</code> is called. The default action is to
    86   * throw an exception. If the request was cancelled (a
    87   * <code.html.md:cancel</code> button was pressed), the custom handler
    88   * <code>cancelled</code> will be used instead. You can also override the
    89   * <code>getMethodName</code> method to override the action's default handler
    90   * selection.</p>
    91   *
    92   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    93   */
    94  public abstract class DispatchAction extends BaseAction {
    95      /**
    96       * Commons Logging instance.
    97       */
    98      protected static Log log = LogFactory.getLog(DispatchAction.class);
    99  
    100     // ----------------------------------------------------- Instance Variables
    101 
    102     /**
    103      * The Class instance of this <code>DispatchAction</code> class.
    104      */
    105     protected Class clazz = this.getClass();
    106 
    107     /**
    108      * The set of Method objects we have introspected for this class, keyed by
    109      * method name.  This collection is populated as different methods are
    110      * called, so that introspection needs to occur only once per method
    111      * name.
    112      */
    113     protected HashMap methods = new HashMap();
    114 
    115     /**
    116      * The set of argument type classes for the reflected method call.  These
    117      * are the same for all calls, so calculate them only once.
    118      */
    119     protected Class[] types =
    120         {
    121             ActionMapping.class, ActionForm.class, HttpServletRequest.class,
    122             HttpServletResponse.class
    123         };
    124 
    125     // --------------------------------------------------------- Public Methods
    126 
    127     /**
    128      * Process the specified HTTP request, and create the corresponding HTTP
    129      * response (or forward to another web component that will create it).
    130      * Return an <code>ActionForward</code> instance describing where and how
    131      * control should be forwarded, or <code>null</code> if the response has
    132      * already been completed.
    133      *
    134      * @param mapping  The ActionMapping used to select this instance
    135      * @param form     The optional ActionForm bean for this request (if any)
    136      * @param request  The HTTP request we are processing
    137      * @param response The HTTP response we are creating
    138      * @return The forward to which control should be transferred, or
    139      *         <code>null</code> if the response has been completed.
    140      * @throws Exception if an exception occurs
    141      */
    142     public ActionForward execute(ActionMapping mapping, ActionForm form,
    143         HttpServletRequest request, HttpServletResponse response)
    144         throws Exception {
    145         if (isCancelled(request)) {
    146             ActionForward af = cancelled(mapping, form, request, response);
    147 
    148             if (af != null) {
    149                 return af;
    150             }
    151         }
    152 
    153         // Get the parameter. This could be overridden in subclasses.
    154         String parameter = getParameter(mapping, form, request, response);
    155 
    156         // Get the method's name. This could be overridden in subclasses.
    157         String name =
    158             getMethodName(mapping, form, request, response, parameter);
    159 
    160         // Prevent recursive calls
    161         if ("execute".equals(name) || "perform".equals(name)) {
    162             String message =
    163                 messages.getMessage("dispatch.recursive", mapping.getPath());
    164 
    165             log.error(message);
    166             throw new ServletException(message);
    167         }
    168 
    169         // Invoke the named method, and return the result
    170         return dispatchMethod(mapping, form, request, response, name);
    171     }
    172 
    173     /**
    174      * Method which is dispatched to when there is no value for specified
    175      * request parameter included in the request.  Subclasses of
    176      * <code>DispatchAction</code> should override this method if they wish to
    177      * provide default behavior different than throwing a ServletException.
    178      *
    179      * @param mapping  The ActionMapping used to select this instance
    180      * @param form     The optional ActionForm bean for this request (if any)
    181      * @param request  The non-HTTP request we are processing
    182      * @param response The non-HTTP response we are creating
    183      * @return The forward to which control should be transferred, or
    184      *         <code>null</code> if the response has been completed.
    185      * @throws Exception if the application business logic throws an
    186      *                   exception.
    187      */
    188     protected ActionForward unspecified(ActionMapping mapping, ActionForm form,
    189         HttpServletRequest request, HttpServletResponse response)
    190         throws Exception {
    191         String message =
    192             messages.getMessage("dispatch.parameter", mapping.getPath(),
    193                 mapping.getParameter());
    194 
    195         log.error(message);
    196 
    197         throw new ServletException(message);
    198     }
    199 
    200     /**
    201      * Method which is dispatched to when the request is a cancel button
    202      * submit. Subclasses of <code>DispatchAction</code> should override this
    203      * method if they wish to provide default behavior different than
    204      * returning null.
    205      *
    206      * @param mapping  The ActionMapping used to select this instance
    207      * @param form     The optional ActionForm bean for this request (if any)
    208      * @param request  The non-HTTP request we are processing
    209      * @param response The non-HTTP response we are creating
    210      * @return The forward to which control should be transferred, or
    211      *         <code>null</code> if the response has been completed.
    212      * @throws Exception if the application business logic throws an
    213      *                   exception.
    214      * @since Struts 1.2.0
    215      */
    216     protected ActionForward cancelled(ActionMapping mapping, ActionForm form,
    217         HttpServletRequest request, HttpServletResponse response)
    218         throws Exception {
    219         return null;
    220     }
    221 
    222     // ----------------------------------------------------- Protected Methods
    223 
    224     /**
    225      * Dispatch to the specified method.
    226      *
    227      * @param mapping  The ActionMapping used to select this instance
    228      * @param form     The optional ActionForm bean for this request (if any)
    229      * @param request  The non-HTTP request we are processing
    230      * @param response The non-HTTP response we are creating
    231      * @param name     The name of the method to invoke
    232      * @return The forward to which control should be transferred, or
    233      *         <code>null</code> if the response has been completed.
    234      * @throws Exception if the application business logic throws an
    235      *                   exception.
    236      * @since Struts 1.1
    237      */
    238     protected ActionForward dispatchMethod(ActionMapping mapping,
    239         ActionForm form, HttpServletRequest request,
    240         HttpServletResponse response, String name)
    241         throws Exception {
    242         // Make sure we have a valid method name to call.
    243         // This may be null if the user hacks the query string.
    244         if (name == null) {
    245             return this.unspecified(mapping, form, request, response);
    246         }
    247 
    248         // Identify the method object to be dispatched to
    249         Method method = null;
    250 
    251         try {
    252             method = getMethod(name);
    253         } catch (NoSuchMethodException e) {
    254             String message =
    255                 messages.getMessage("dispatch.method", mapping.getPath(), name);
    256 
    257             log.error(message, e);
    258 
    259             String userMsg =
    260                 messages.getMessage("dispatch.method.user", mapping.getPath());
    261             throw new NoSuchMethodException(userMsg);
    262         }
    263 
    264         ActionForward forward = null;
    265 
    266         try {
    267             Object[] args = { mapping, form, request, response };
    268 
    269             forward = (ActionForward) method.invoke(this, args);
    270         } catch (ClassCastException e) {
    271             String message =
    272                 messages.getMessage("dispatch.return", mapping.getPath(), name);
    273 
    274             log.error(message, e);
    275             throw e;
    276         } catch (IllegalAccessException e) {
    277             String message =
    278                 messages.getMessage("dispatch.error", mapping.getPath(), name);
    279 
    280             log.error(message, e);
    281             throw e;
    282         } catch (InvocationTargetException e) {
    283             // Rethrow the target exception if possible so that the
    284             // exception handling machinery can deal with it
    285             Throwable t = e.getTargetException();
    286 
    287             if (t instanceof Exception) {
    288                 throw ((Exception) t);
    289             } else {
    290                 String message =
    291                     messages.getMessage("dispatch.error", mapping.getPath(),
    292                         name);
    293 
    294                 log.error(message, e);
    295                 throw new ServletException(t);
    296             }
    297         }
    298 
    299         // Return the returned ActionForward instance
    300         return (forward);
    301     }
    302 
    303     /**
    304      * <p>Returns the parameter value.</p>
    305      *
    306      * @param mapping  The ActionMapping used to select this instance
    307      * @param form     The optional ActionForm bean for this request (if any)
    308      * @param request  The HTTP request we are processing
    309      * @param response The HTTP response we are creating
    310      * @return The <code>ActionMapping</code> parameter's value
    311      * @throws Exception if the parameter is missing.
    312      */
    313     protected String getParameter(ActionMapping mapping, ActionForm form,
    314         HttpServletRequest request, HttpServletResponse response)
    315         throws Exception {
    316 
    317         // Identify the request parameter containing the method name
    318         String parameter = mapping.getParameter();
    319 
    320         if (parameter == null) {
    321             String message =
    322                 messages.getMessage("dispatch.handler", mapping.getPath());
    323 
    324             log.error(message);
    325 
    326             throw new ServletException(message);
    327         }
    328 
    329 
    330         return parameter;
    331     }
    332 
    333     /**
    334      * Introspect the current class to identify a method of the specified name
    335      * that accepts the same parameter types as the <code>execute</code>
    336      * method does.
    337      *
    338      * @param name Name of the method to be introspected
    339      * @return The method with the specified name.
    340      * @throws NoSuchMethodException if no such method can be found
    341      */
    342     protected Method getMethod(String name)
    343         throws NoSuchMethodException {
    344         synchronized (methods) {
    345             Method method = (Method) methods.get(name);
    346 
    347             if (method == null) {
    348                 method = clazz.getMethod(name, types);
    349                 methods.put(name, method);
    350             }
    351 
    352             return (method);
    353         }
    354     }
    355 
    356     /**
    357      * Returns the method name, given a parameter's value.
    358      *
    359      * @param mapping   The ActionMapping used to select this instance
    360      * @param form      The optional ActionForm bean for this request (if
    361      *                  any)
    362      * @param request   The HTTP request we are processing
    363      * @param response  The HTTP response we are creating
    364      * @param parameter The <code>ActionMapping</code> parameter's name
    365      * @return The method's name.
    366      * @throws Exception if an error occurs.
    367      * @since Struts 1.2.0
    368      */
    369     protected String getMethodName(ActionMapping mapping, ActionForm form,
    370         HttpServletRequest request, HttpServletResponse response,
    371         String parameter) throws Exception {
    372         // Identify the method name to be dispatched to.
    373         // dispatchMethod() will call unspecified() if name is null
    374         return request.getParameter(parameter);
    375     }
    376 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
