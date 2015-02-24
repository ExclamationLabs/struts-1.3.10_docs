[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/application/ActionListenerImpl.html.md)


    1   /*
    2    * $Id: ActionListenerImpl.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.application;
    23  
    24  
    25  import javax.faces.component.ActionSource;
    26  import javax.faces.component.UIComponent;
    27  import javax.faces.component.UIForm;
    28  import javax.faces.context.FacesContext;
    29  import javax.faces.event.AbortProcessingException;
    30  import javax.faces.event.ActionEvent;
    31  import javax.faces.event.ActionListener;
    32  import javax.servlet.ServletContext;
    33  import javax.servlet.http.HttpServletRequest;
    34  import javax.servlet.http.HttpServletResponse;
    35  import org.apache.commons.logging.Log;
    36  import org.apache.commons.logging.LogFactory;
    37  import org.apache.struts.Globals;
    38  import org.apache.struts.action.ActionServlet;
    39  import org.apache.struts.action.RequestProcessor;
    40  import org.apache.struts.config.ModuleConfig;
    41  import org.apache.struts.faces.Constants;
    42  import org.apache.struts.faces.component.FormComponent;
    43  import org.apache.struts.util.RequestUtils;
    44  import org.apache.struts.util.ModuleUtils;
    45  
    46  
    47  /**
    48   * <p>Concrete implementation of <code>ActionListener</code> that replaces
    49   * the default provided implementation.  It converts application-level events
    50   * into execution of the corresponding Struts request processing lifecycle.
    51   * </p>
    52   *
    53   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    54   */
    55  
    56  public final class ActionListenerImpl implements ActionListener {
    57  
    58  
    59      // ------------------------------------------------------------ Constructors
    60  
    61  
    62      /**
    63       * <p>Construct a new default <code>ActionListener</code> instance,
    64       * passing it the previously configured one.</p>
    65       *
    66       * @param original Original default <code>ActionListener</code>
    67       *
    68       * @exception NullPointerException if <code>original</code>
    69       *  is <code>null</code>
    70       */
    71      public ActionListenerImpl(ActionListener original) {
    72  
    73          if (original == null) {
    74              throw new NullPointerException();
    75          }
    76          this.original = original;
    77          if (log.isInfoEnabled()) {
    78              log.info("Create ActionListener wrapping instance of type '" +
    79                       original.getClass().getName() + "'");
    80          }
    81  
    82      }
    83  
    84  
    85  
    86      // ------------------------------------------------------ Instance Variables
    87  
    88  
    89      /**
    90       * <p>The logger for this instance.</p>
    91       */
    92      private static final Log log = LogFactory.getLog(ActionListenerImpl.class);
    93  
    94  
    95      /**
    96       * <p>The previously configured <code>ActionListener</code> instance.</p>
    97       */
    98      private ActionListener original;
    99  
    100 
    101     // ---------------------------------------------------------- Public Methods
    102 
    103 
    104     /**
    105      * <p>Process the specified <code>ActionEvent</code>.</p>
    106      *
    107      * @param event The <code>ActionEvent</code> to be processed
    108      *
    109      * @exception AbortProcessingException to signal that no further
    110      *  event processing should be performed
    111      */
    112     public void processAction(ActionEvent event)
    113         throws AbortProcessingException {
    114 
    115         // If this is an immediate action, or we are NOT nested in a
    116         // Struts form, perform the standard processing
    117         UIComponent component = event.getComponent();
    118         ActionSource source = (ActionSource) component;
    119         boolean standard = source.isImmediate();
    120         if (!standard) {
    121             UIComponent parent = component.getParent();
    122             while (parent != null) {
    123                 if (parent instanceof UIForm) {
    124                     if (!(parent instanceof FormComponent)) {
    125                         standard = true;
    126                     }
    127                     break;
    128                 }
    129                 parent = parent.getParent();
    130             }
    131         }
    132         if (standard) {
    133             if (log.isDebugEnabled()) {
    134                 log.debug("Performing standard handling for event " +
    135                           "from source component '" + component.getId() + "'");
    136             }
    137             original.processAction(event);
    138             return;
    139         }
    140 
    141 
    142         // Acquire Servlet API Object References
    143         FacesContext context = FacesContext.getCurrentInstance();
    144         ServletContext servletContext = (ServletContext)
    145             context.getExternalContext().getContext();
    146         HttpServletRequest request = (HttpServletRequest)
    147             context.getExternalContext().getRequest();
    148         HttpServletResponse response = (HttpServletResponse)
    149             context.getExternalContext().getResponse();
    150 
    151         // Log this event if requested
    152         if (log.isDebugEnabled()) {
    153             log.debug("Performing Struts form submit for event " +
    154                       " from source component '" +
    155                       component.getId() + "'");
    156         }
    157 
    158         // Invoke the appropriate request processor for this request
    159         try {
    160             request.setAttribute(Constants.ACTION_EVENT_KEY, event);
    161             ModuleUtils.getInstance().selectModule(request, servletContext);
    162             ModuleConfig moduleConfig = (ModuleConfig)
    163                 request.getAttribute(Globals.MODULE_KEY);
    164             if (log.isTraceEnabled()) {
    165                 log.trace("Assigned to module with prefix '" +
    166                           moduleConfig.getPrefix() + "'");
    167             }
    168             RequestProcessor processor =
    169                 getRequestProcessor(moduleConfig, servletContext);
    170             if (log.isTraceEnabled()) {
    171                 log.trace("Invoking request processor instance " + processor);
    172             }
    173             processor.process(request, response);
    174             context.responseComplete();
    175         } catch (Exception e) {
    176             log.error("Exception processing action event " + event, e);
    177         } finally {
    178             request.removeAttribute(Constants.ACTION_EVENT_KEY);
    179         }
    180 
    181     }
    182 
    183 
    184     // ------------------------------------------------------ Protected Methods
    185 
    186 
    187     /**
    188      * <p>Look up and return the <code>RequestProcessor</code> responsible for
    189      * the specified module, creating a new one if necessary.  This method is
    190      * based on the corresponding code in <code>ActionServlet</code>, which
    191      * cannot be used directly because it is a protected method.</p>
    192      *
    193      * @param config The module configuration for which to
    194      *  acquire and return a RequestProcessor
    195      * @param context The <code>ServletContext</code> instance
    196      *  for this web application
    197      *
    198      * @exception IllegalStateException if we cannot instantiate a
    199      *  RequestProcessor instance
    200      */
    201     protected RequestProcessor getRequestProcessor(ModuleConfig config,
    202                                                    ServletContext context) {
    203 
    204         String key = Globals.REQUEST_PROCESSOR_KEY + config.getPrefix();
    205         RequestProcessor processor =
    206             (RequestProcessor) context.getAttribute(key);
    207 
    208         if (processor == null) {
    209             try {
    210                 if (log.isDebugEnabled()) {
    211                     log.debug("Instantiating RequestProcessor of class " +
    212                               config.getControllerConfig().getProcessorClass());
    213                 }
    214                 ActionServlet servlet = (ActionServlet)
    215                 context.getAttribute(Globals.ACTION_SERVLET_KEY);
    216                 processor =
    217                     (RequestProcessor) RequestUtils.applicationInstance(
    218                         config.getControllerConfig().getProcessorClass());
    219                 processor.init(servlet, config);
    220                 context.setAttribute(key, processor);
    221             } catch (Exception e) {
    222                 log.error("Cannot instantiate RequestProcessor of class "
    223                           + config.getControllerConfig().getProcessorClass(),
    224                           e);
    225                 throw new IllegalStateException(
    226                     "Cannot initialize RequestProcessor of class "
    227                         + config.getControllerConfig().getProcessorClass()
    228                         + ": "
    229                         + e);
    230             }
    231 
    232         }
    233         return (processor);
    234 
    235     }
    236 
    237 
    238 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
