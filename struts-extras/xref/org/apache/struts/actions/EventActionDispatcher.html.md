[View Javadoc](../../../../../apidocs/org/apache/struts/actions/EventActionDispatcher.html.md)


    1   /*
    2    * $Id: EventActionDispatcher.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.actions;
    23  
    24  import java.util.StringTokenizer;
    25  import java.lang.reflect.Method;
    26  
    27  import javax.servlet.ServletException;
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  
    31  import org.apache.commons.logging.Log;
    32  import org.apache.commons.logging.LogFactory;
    33  import org.apache.struts.action.Action;
    34  import org.apache.struts.action.ActionForm;
    35  import org.apache.struts.action.ActionMapping;
    36  import org.apache.struts.action.ActionForward;
    37  
    38  /**
    39   * <p>An Action helper class that dispatches to to one of the public methods
    40   * that are named in the <code>parameter</code> attribute of the corresponding
    41   * ActionMapping and matches a submission parameter. This is useful for
    42   * developers who prefer to use many submit buttons, images, or submit links
    43   * on a single form and whose related actions exist in a single Action class.</p>
    44   *
    45   * <p>The method(s) in the associated <code>Action</code> must have the same
    46   * signature (other than method name) of the standard Action.execute method.</p>
    47   *
    48   * <p>To configure the use of this action in your
    49   * <code>struts-config.xml</code> file, create an entry like this:</p>
    50   *
    51   * <pre><code>
    52   *   &lt;action path="/saveSubscription"
    53   *           type="org.example.SubscriptionAction"
    54   *           name="subscriptionForm"
    55   *          scope="request"
    56   *          input="/subscription.jsp"
    57   *      parameter="save,back,recalc=recalculate,default=save"/&gt;
    58   * </code></pre>
    59   *
    60   * <p>where <code>parameter</code> contains three possible methods and one
    61   * default method if nothing matches (such as the user pressing the enter key).</p>
    62   *
    63   * <p>For utility purposes, you can use the <code>key=value</code> notation to
    64   * alias methods so that they are exposed as different form element names, in the
    65   * event of a naming conflict or otherwise. In this example, the <em>recalc</em>
    66   * button (via a request parameter) will invoke the <code>recalculate</code>
    67   * method. The security-minded person may find this feature valuable to
    68   * obfuscate and not expose the methods.</p>
    69   *
    70   * <p>The <em>default</em> key is purely optional. If this is not specified
    71   * and no parameters match the list of method keys, <code>null</code> is
    72   * returned which means the <code>unspecified</code> method will be invoked.</p>
    73   *
    74   * <p>The order of the parameters are guaranteed to be iterated in the order
    75   * specified. If multiple buttons were accidently submitted, the first match in
    76   * the list will be dispatched.</p>
    77   *
    78   * <p>To implement this <i>dispatch</i> behaviour in an <code>Action</code>,
    79   * class create your custom Action as follows, along with the methods you require
    80   * (and optionally "cancelled" and "unspecified" methods):</p> <p/>
    81   * <pre>
    82   *   public class MyCustomAction extends Action {
    83   *
    84   *       protected ActionDispatcher dispatcher = new EventActionDispatcher(this);
    85   *
    86   *       public ActionForward execute(ActionMapping mapping,
    87   *                                    ActionForm form,
    88   *                                    HttpServletRequest request,
    89   *                                    HttpServletResponse response)
    90   *                           throws Exception {
    91   *           return dispatcher.execute(mapping, form, request, response);
    92   *       }
    93   *   }
    94   * </pre>
    95   * <p/>
    96   *
    97   * @since Struts 1.2.9
    98   */
    99  public class EventActionDispatcher extends ActionDispatcher {
    100 
    101     /**
    102      * Commons Logging instance.
    103      */
    104     private static final Log LOG = LogFactory.getLog(EventActionDispatcher.class);
    105 
    106     /**
    107      * The method key, if present, to use if other specified method keys
    108      * do not match a request parameter.
    109      */
    110     private static final String DEFAULT_METHOD_KEY = "default";
    111 
    112     /**
    113      * Constructs a new object for the specified action.
    114      * @param action the action
    115      */
    116     public EventActionDispatcher(Action action) {
    117         // N.B. MAPPING_FLAVOR causes the getParameter() method
    118         //      in ActionDispatcher to throw an exception if the
    119         //      parameter is missing
    120         super(action, ActionDispatcher.MAPPING_FLAVOR);
    121     }
    122 
    123     /**
    124      * <p>Dispatches to the target class' <code>unspecified</code> method, if
    125      * present, otherwise throws a ServletException. Classes utilizing
    126      * <code>EventActionDispatcher</code> should provide an <code>unspecified</code>
    127      * method if they wish to provide behavior different than throwing a
    128      * ServletException.</p>
    129      *
    130      * @param mapping  The ActionMapping used to select this instance
    131      * @param form     The optional ActionForm bean for this request (if any)
    132      * @param request  The non-HTTP request we are processing
    133      * @param response The non-HTTP response we are creating
    134      * @return The forward to which control should be transferred, or
    135      *         <code>null</code> if the response has been completed.
    136      * @throws Exception if the application business logic throws an
    137      *                   exception.
    138      */
    139     protected ActionForward unspecified(ActionMapping mapping, ActionForm form,
    140         HttpServletRequest request, HttpServletResponse response)
    141         throws Exception {
    142         // Identify if there is an "unspecified" method to be dispatched to
    143         String name = "unspecified";
    144         Method method = null;
    145 
    146         try {
    147             method = getMethod(name);
    148         } catch (NoSuchMethodException e) {
    149             String message =
    150                 messages.getMessage("event.parameter", mapping.getPath());
    151 
    152             LOG.error(message + " " + mapping.getParameter());
    153 
    154             throw new ServletException(message);
    155         }
    156 
    157         return dispatchMethod(mapping, form, request, response, name, method);
    158     }
    159 
    160     /**
    161      * Returns the method name, given a parameter's value.
    162      *
    163      * @param mapping   The ActionMapping used to select this instance
    164      * @param form      The optional ActionForm bean for this request (if
    165      *                  any)
    166      * @param request   The HTTP request we are processing
    167      * @param response  The HTTP response we are creating
    168      * @param parameter The <code>ActionMapping</code> parameter's name
    169      * @return The method's name.
    170      * @throws Exception if an error occurs.
    171      */
    172     protected String getMethodName(ActionMapping mapping, ActionForm form,
    173             HttpServletRequest request, HttpServletResponse response,
    174             String parameter) throws Exception {
    175 
    176         StringTokenizer st = new StringTokenizer(parameter, ",");
    177         String defaultMethodName = null;
    178 
    179         while (st.hasMoreTokens()) {
    180             String methodKey = st.nextToken().trim();
    181             String methodName = methodKey;
    182 
    183             // The key can either be a direct method name or an alias
    184             // to a method as indicated by a "key=value" signature
    185             int equals = methodKey.indexOf('=');
    186             if (equals > -1) {
    187                 methodName = methodKey.substring(equals + 1).trim();
    188                 methodKey = methodKey.substring(0, equals).trim();
    189             }
    190 
    191             // Set the default if it passes by
    192             if (methodKey.equals(DEFAULT_METHOD_KEY)) {
    193                 defaultMethodName = methodName;
    194             }
    195 
    196             // If the method key exists as a standalone parameter or with
    197             // the image suffixes (.x/.y), the method name has been found.
    198             if ((request.getParameter(methodKey) != null)
    199                   || (request.getParameter(methodKey + ".x") != null)) {
    200                 return methodName;
    201             }
    202         }
    203 
    204         return defaultMethodName;
    205     }
    206 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
