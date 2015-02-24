[View Javadoc](../../../../../apidocs/org/apache/struts/actions/MappingDispatchAction.html.md)


    1   /*
    2    * $Id: MappingDispatchAction.java 480570 2006-11-29 13:39:37Z niallp $
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
    33  /**
    34   * <p>An abstract <strong>Action</strong> that dispatches to a public method
    35   * that is named by the <code>parameter</code> attribute of the corresponding
    36   * ActionMapping.  This is useful for developers who prefer to combine many
    37   * related actions into a single Action class.</p>
    38   *
    39   * <p>To configure the use of this action in your <code>struts-config.xml</code>
    40   * file, create an entry like this:</p>
    41   *
    42   * <pre><code>
    43   *   &lt;action path="/saveSubscription"
    44   *           type="org.example.SubscriptionAction"
    45   *           name="subscriptionForm"
    46   *          scope="request"
    47   *          input="/subscription.jsp"
    48   *      parameter="method"/&gt;
    49   * </code></pre>
    50   *
    51   * <p>where 'method' is the name of a method in your subclass of
    52   * MappingDispatchAction that has the same signature (other than method name)
    53   * of the standard Action.execute method.  For example, you might combine the
    54   * methods for managing a subscription into a  single MappingDispatchAction
    55   * class using the following methods:</p>
    56   *
    57   * <ul>
    58   *
    59   * <li>public ActionForward create(ActionMapping mapping, ActionForm form,
    60   * HttpServletRequest request, HttpServletResponse response) throws
    61   * Exception</li>
    62   *
    63   * <li>public ActionForward edit(ActionMapping mapping, ActionForm form,
    64   * HttpServletRequest request, HttpServletResponse response) throws
    65   * Exception</li>
    66   *
    67   * <li>public ActionForward save(ActionMapping mapping, ActionForm form,
    68   * HttpServletRequest request, HttpServletResponse response) throws
    69   * Exception</li>
    70   *
    71   * <li>public ActionForward delete(ActionMapping mapping, ActionForm form,
    72   * HttpServletRequest request, HttpServletResponse response) throws
    73   * Exception</li>
    74   *
    75   * <li>public ActionForward list(ActionMapping mapping, ActionForm form,
    76   * HttpServletRequest request, HttpServletResponse response) throws
    77   * Exception</li>
    78   *
    79   * </ul>
    80   *
    81   * <p>for which you would create corresponding &lt;action&gt; configurations
    82   * that reference this class:</p>
    83   *
    84   * <pre><code>
    85   *  &lt;action path="/createSubscription"
    86   *          type="org.example.SubscriptionAction"
    87   *          parameter="create"&gt;
    88   *      &lt;forward name="success" path="/editSubscription.jsp"/&gt;
    89   *  &lt;/action&gt;
    90   *
    91   *  &lt;action path="/editSubscription"
    92   *          type="org.example.SubscriptionAction"
    93   *          parameter="edit"&gt;
    94   *      &lt;forward name="success" path="/editSubscription.jsp"/&gt;
    95   *  &lt;/action&gt;
    96   *
    97   *  &lt;action path="/saveSubscription"
    98   *          type="org.example.SubscriptionAction"
    99   *          parameter="save"
    100  *          name="subscriptionForm"
    101  *          validate="true"
    102  *          input="/editSubscription.jsp"
    103  *          scope="request"&gt;
    104  *      &lt;forward name="success" path="/savedSubscription.jsp"/&gt;
    105  *  &lt;/action&gt;
    106  *
    107  *  &lt;action path="/deleteSubscription"
    108  *          type="org.example.SubscriptionAction"
    109  *          name="subscriptionForm"
    110  *          scope="request"
    111  *          input="/subscription.jsp"
    112  *          parameter="delete"&gt;
    113  *      &lt;forward name="success" path="/deletedSubscription.jsp"/&gt;
    114  *  &lt;/action&gt;
    115  *
    116  *  &lt;action path="/listSubscriptions"
    117  *          type="org.example.SubscriptionAction"
    118  *          parameter="list"&gt;
    119  *      &lt;forward name="success" path="/subscriptionList.jsp"/&gt;
    120  *  &lt;/action&gt;
    121  * </code></pre>
    122  *
    123  * <p><strong>NOTE</strong> - Unlike DispatchAction, mapping characteristics
    124  * may differ between the various handlers, so you can combine actions in the
    125  * same class that, for example, differ in their use of forms or validation.
    126  * Also, a request parameter, which would be visible to the application user,
    127  * is not required to enable selection of the handler method. </p>
    128  *
    129  * @version $Rev: 480570 $ $Date: 2006-11-29 07:39:37 -0600 (Wed, 29 Nov 2006) $
    130  * @since Struts 1.2
    131  */
    132 public class MappingDispatchAction extends DispatchAction {
    133     // -------------------------------------------------------- Class Variables
    134 
    135     /**
    136      * Commons Logging instance.
    137      */
    138     private static Log log = LogFactory.getLog(MappingDispatchAction.class);
    139 
    140     // --------------------------------------------------------- Public Methods
    141 
    142     /**
    143      * Process the specified HTTP request, and create the corresponding HTTP
    144      * response (or forward to another web component that will create it).
    145      * Return an <code>ActionForward</code> instance describing where and how
    146      * control should be forwarded, or <code>null</code> if the response has
    147      * already been completed.
    148      *
    149      * This method dispatches the request to other methods of
    150      * <code>MappingDispatchAction</code> using the 'parameter' attribute of
    151      * <code>ActionMapping</code> and Java Introspection.
    152      *
    153      * @param mapping  The ActionMapping used to select this instance
    154      * @param form     The optional ActionForm bean for this request (if any)
    155      * @param request  The HTTP request we are processing
    156      * @param response The HTTP response we are creating
    157      * @return Return an <code>ActionForward</code> instance describing where
    158      *         and how control should be forwarded, or <code>null</code> if
    159      *         the response has already been completed.
    160      * @throws Exception if an exception occurs
    161      */
    162     public ActionForward execute(ActionMapping mapping, ActionForm form,
    163         HttpServletRequest request, HttpServletResponse response)
    164         throws Exception {
    165         // Use the overridden getMethodName.
    166         return super.execute(mapping, form, request, response);
    167     }
    168 
    169     /**
    170      * Method which is dispatched to when there is no value for the parameter
    171      * in the ActionMapping.  Subclasses of <code>MappingDispatchAction</code>
    172      * should override this method if they wish to provide default behavior
    173      * different than throwing a ServletException.
    174      *
    175      * @param mapping  The ActionMapping used to select this instance
    176      * @param form     The optional ActionForm bean for this request (if any)
    177      * @param request  The HTTP request we are processing
    178      * @param response The HTTP response we are creating
    179      * @return Return an <code>ActionForward</code> instance describing where
    180      *         and how control should be forwarded, or <code>null</code> if
    181      *         the response has already been completed.
    182      * @throws Exception if an exception occurs
    183      */
    184     protected ActionForward unspecified(ActionMapping mapping, ActionForm form,
    185         HttpServletRequest request, HttpServletResponse response)
    186         throws Exception {
    187         String message =
    188             messages.getMessage("mapping.parameter", mapping.getPath());
    189 
    190         log.error(message);
    191 
    192         throw new ServletException(message);
    193     }
    194 
    195     /**
    196      * <p>Returns the parameter value.</p>
    197      *
    198      * @param mapping  The ActionMapping used to select this instance
    199      * @param form     The optional ActionForm bean for this request (if any)
    200      * @param request  The HTTP request we are processing
    201      * @param response The HTTP response we are creating
    202      * @return The <code>ActionMapping</code> parameter's value
    203      */
    204     protected String getParameter(ActionMapping mapping, ActionForm form,
    205         HttpServletRequest request, HttpServletResponse response)
    206         throws Exception {
    207 
    208         return mapping.getParameter();
    209 
    210     }
    211 
    212     /**
    213      * Returns the method name, given a parameter's value.
    214      *
    215      * @param mapping   The ActionMapping used to select this instance
    216      * @param form      The optional ActionForm bean for this request (if
    217      *                  any)
    218      * @param request   The HTTP request we are processing
    219      * @param response  The HTTP response we are creating
    220      * @param parameter The <code>ActionMapping</code> parameter's name
    221      * @return The method's name.
    222      * @throws Exception if an error occurs
    223      * @since Struts 1.2.0
    224      */
    225     protected String getMethodName(ActionMapping mapping, ActionForm form,
    226         HttpServletRequest request, HttpServletResponse response,
    227         String parameter) throws Exception {
    228         // Return the unresolved mapping parameter.
    229         return parameter;
    230     }
    231 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
