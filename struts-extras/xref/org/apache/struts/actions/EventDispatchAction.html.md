[View Javadoc](../../../../../apidocs/org/apache/struts/actions/EventDispatchAction.html.md)


    1   /*
    2    * $Id: EventDispatchAction.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import java.util.StringTokenizer;
    24  
    25  import javax.servlet.ServletException;
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.http.HttpServletResponse;
    28  
    29  import org.apache.commons.logging.Log;
    30  import org.apache.commons.logging.LogFactory;
    31  import org.apache.struts.action.ActionForm;
    32  import org.apache.struts.action.ActionMapping;
    33  import org.apache.struts.action.ActionForward;
    34  
    35  /**
    36   * <p>An <strong>Action</strong> that dispatches to to one of the public methods
    37   * that are named in the <code>parameter</code> attribute of the corresponding
    38   * ActionMapping and matches a submission parameter. This is useful for
    39   * developers who prefer to use many submit buttons, images, or submit links
    40   * on a single form and whose related actions exist in a single Action class.</p>
    41   *
    42   * <p>The method(s) must have the same signature (other than method name) of the
    43   * standard Action.execute method.</p>
    44   *
    45   * <p>To configure the use of this action in your
    46   * <code>struts-config.xml</code> file, create an entry like this:</p>
    47   *
    48   * <pre><code>
    49   *   &lt;action path="/saveSubscription"
    50   *           type="org.example.SubscriptionAction"
    51   *           name="subscriptionForm"
    52   *          scope="request"
    53   *          input="/subscription.jsp"
    54   *      parameter="save,back,recalc=recalculate,default=save"/&gt;
    55   * </code></pre>
    56   *
    57   * <p>where <code>parameter</code> contains three possible methods and one
    58   * default method if nothing matches (such as the user pressing the enter key).</p>
    59   *
    60   * <p>For utility purposes, you can use the <code>key=value</code> notation to
    61   * alias methods so that they are exposed as different form element names, in the
    62   * event of a naming conflict or otherwise. In this example, the <em>recalc</em>
    63   * button (via a request parameter) will invoke the <code>recalculate</code>
    64   * method. The security-minded person may find this feature valuable to
    65   * obfuscate and not expose the methods.</p>
    66   *
    67   * <p>The <em>default</em> key is purely optional. If this is not specified
    68   * and no parameters match the list of method keys, <code>null</code> is
    69   * returned which means the <code>unspecified</code> method will be invoked.</p>
    70   *
    71   * <p>The order of the parameters are guaranteed to be iterated in the order
    72   * specified. If multiple buttons were accidently submitted, the first match in
    73   * the list will be dispatched.</p>
    74   *
    75   * @since Struts 1.2.9
    76   */
    77  public class EventDispatchAction extends DispatchAction {
    78  
    79      /**
    80       * Commons Logging instance.
    81       */
    82      private static final Log LOG = LogFactory.getLog(EventDispatchAction.class);
    83  
    84      /**
    85       * The method key, if present, to use if other specified method keys
    86       * do not match a request parameter.
    87       */
    88      private static final String DEFAULT_METHOD_KEY = "default";
    89  
    90      // --------------------------------------------------------- Protected Methods
    91  
    92      /**
    93       * Method which is dispatched to when there is no value for specified
    94       * request parameter included in the request.  Subclasses of
    95       * <code>DispatchAction</code> should override this method if they wish to
    96       * provide default behavior different than throwing a ServletException.
    97       *
    98       * @param mapping  The ActionMapping used to select this instance
    99       * @param form     The optional ActionForm bean for this request (if any)
    100      * @param request  The non-HTTP request we are processing
    101      * @param response The non-HTTP response we are creating
    102      * @return The forward to which control should be transferred, or
    103      *         <code>null</code> if the response has been completed.
    104      * @throws Exception if the application business logic throws an
    105      *                   exception.
    106      */
    107     protected ActionForward unspecified(ActionMapping mapping, ActionForm form,
    108         HttpServletRequest request, HttpServletResponse response)
    109         throws Exception {
    110         String message =
    111             messages.getMessage("event.parameter", mapping.getPath(),
    112                 mapping.getParameter());
    113 
    114         LOG.error(message + " " + mapping.getParameter());
    115 
    116         throw new ServletException(message);
    117     }
    118 
    119     /**
    120      * Returns the method name, given a parameter's value.
    121      *
    122      * @param mapping   The ActionMapping used to select this instance
    123      * @param form      The optional ActionForm bean for this request (if
    124      *                  any)
    125      * @param request   The HTTP request we are processing
    126      * @param response  The HTTP response we are creating
    127      * @param parameter The <code>ActionMapping</code> parameter's name
    128      * @return The method's name.
    129      * @throws Exception if an error occurs.
    130      */
    131     protected String getMethodName(ActionMapping mapping, ActionForm form,
    132             HttpServletRequest request, HttpServletResponse response,
    133             String parameter) throws Exception {
    134 
    135         StringTokenizer st = new StringTokenizer(parameter, ",");
    136         String defaultMethodName = null;
    137 
    138         while (st.hasMoreTokens()) {
    139             String methodKey = st.nextToken().trim();
    140             String methodName = methodKey;
    141 
    142             // The key can either be a direct method name or an alias
    143             // to a method as indicated by a "key=value" signature
    144             int equals = methodKey.indexOf('=');
    145             if (equals > -1) {
    146                 methodName = methodKey.substring(equals + 1).trim();
    147                 methodKey = methodKey.substring(0, equals).trim();
    148             }
    149 
    150             // Set the default if it passes by
    151             if (methodKey.equals(DEFAULT_METHOD_KEY)) {
    152                 defaultMethodName = methodName;
    153             }
    154 
    155             // If the method key exists as a standalone parameter or with
    156             // the image suffixes (.x/.y), the method name has been found.
    157             if ((request.getParameter(methodKey) != null)
    158                   || (request.getParameter(methodKey + ".x") != null)) {
    159                 return methodName;
    160             }
    161         }
    162 
    163         return defaultMethodName;
    164     }
    165 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
