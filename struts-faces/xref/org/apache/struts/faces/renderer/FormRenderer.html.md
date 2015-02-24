[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/FormRenderer.html.md)


    1   /*
    2    * $Id: FormRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.renderer;
    23  
    24  
    25  import java.io.IOException;
    26  import java.util.Map;
    27  
    28  import javax.faces.component.NamingContainer;
    29  import javax.faces.component.UIComponent;
    30  import javax.faces.context.FacesContext;
    31  import javax.faces.context.ResponseWriter;
    32  import javax.servlet.http.HttpSession;
    33  
    34  import org.apache.commons.logging.Log;
    35  import org.apache.commons.logging.LogFactory;
    36  import org.apache.struts.Globals;
    37  import org.apache.struts.config.ActionConfig;
    38  import org.apache.struts.config.ModuleConfig;
    39  import org.apache.struts.faces.component.FormComponent;
    40  
    41  
    42  /**
    43   * <p><code>Renderer</code> implementation for the <code>form</code> tag
    44   * from the <em>Struts-Faces Integration Library</em>.</p>
    45   *
    46   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    47   */
    48  
    49  public class FormRenderer extends AbstractRenderer {
    50  
    51  
    52      // -------------------------------------------------------- Static Variables
    53  
    54  
    55      /**
    56       * <p>The <code>Log</code> instance for this class.</p>
    57       */
    58      private static Log log = LogFactory.getLog(FormRenderer.class);
    59  
    60  
    61      // ---------------------------------------------------------- Public Methods
    62  
    63  
    64      /**
    65       * <p>Perform setup processing that will be required for decoding the
    66       * incoming request.</p>
    67       *
    68       * @param context FacesContext for the request we are processing
    69       * @param component UIComponent to be processed
    70       *
    71       * @exception NullPointerException if <code>context</code>
    72       *  or <code>component</code> is null
    73       */
    74      public void decode(FacesContext context, UIComponent component) {
    75  
    76          if ((context == null) || (component == null)) {
    77              throw new NullPointerException();
    78          }
    79          String clientId = component.getClientId(context);
    80          Map map = context.getExternalContext().getRequestParameterMap();
    81          if (log.isDebugEnabled()) {
    82              log.debug("decode(" + clientId + ") --> " +
    83                        map.containsKey(clientId));
    84          }
    85          component.getAttributes().put
    86              ("submitted",
    87               map.containsKey(clientId) ? Boolean.TRUE : Boolean.FALSE);
    88  
    89      }
    90  
    91  
    92      private static String passThrough[] =
    93      { "enctype", "method", "onreset", "onsubmit", "style", "target", };
    94  
    95  
    96      /**
    97       * <p>Render the beginning of an HTML <code>&lt;form&gt;</code>
    98       * control.</p>
    99       *
    100      * @param context FacesContext for the request we are processing
    101      * @param component UIComponent to be rendered
    102      *
    103      * @exception IOException if an input/output error occurs while rendering
    104      * @exception NullPointerException if <code>context</code>
    105      *  or <code>component</code> is null
    106      */
    107     public void encodeBegin(FacesContext context, UIComponent component)
    108         throws IOException {
    109 
    110         if ((context == null) || (component == null)) {
    111             throw new NullPointerException();
    112         }
    113 
    114         // Calculate and cache the form name
    115         FormComponent form = (FormComponent) component;
    116         String action = form.getAction();
    117         ModuleConfig moduleConfig = form.lookupModuleConfig(context);
    118         ActionConfig actionConfig = moduleConfig.findActionConfig(action);
    119         if (actionConfig == null) {
    120             throw new IllegalArgumentException("Cannot find action '" +
    121                                                action + "' configuration");
    122         }
    123         String beanName = actionConfig.getAttribute();
    124         if (beanName != null) {
    125             form.getAttributes().put("beanName", beanName);
    126         }
    127 
    128         // Look up attribute values we need
    129         String clientId = component.getClientId(context);
    130         if (log.isDebugEnabled()) {
    131             log.debug("encodeBegin(" + clientId + ")");
    132         }
    133         String styleClass =
    134             (String) component.getAttributes().get("styleClass");
    135 
    136         // Render the beginning of this form
    137         ResponseWriter writer = context.getResponseWriter();
    138         writer.startElement("form", form);
    139         writer.writeAttribute("id", clientId, "clientId");
    140         if (beanName != null) {
    141             writer.writeAttribute("name", beanName, null);
    142         }
    143         writer.writeAttribute("action", action(context, component), "action");
    144         if (styleClass != null) {
    145             writer.writeAttribute("class", styleClass, "styleClass");
    146         }
    147         if (component.getAttributes().get("method") == null) {
    148             writer.writeAttribute("method", "post", null);
    149         }
    150         renderPassThrough(context, component, writer, passThrough);
    151         writer.writeText("\n", null);
    152 
    153         // Add a marker used by our decode() method to note this form is submitted
    154         writer.startElement("input", form);
    155         writer.writeAttribute("type", "hidden", null);
    156         writer.writeAttribute("name", clientId, null);
    157         writer.writeAttribute("value", clientId, null);
    158         writer.endElement("input");
    159         writer.writeText("\n", null);
    160 
    161         // Add a transaction token if necessary
    162         HttpSession session = (HttpSession)
    163             context.getExternalContext().getSession(false);
    164         if (session != null) {
    165             String token = (String)
    166                 session.getAttribute(Globals.TRANSACTION_TOKEN_KEY);
    167             if (token != null) {
    168                 writer.startElement("input", form);
    169                 writer.writeAttribute("type", "hidden", null);
    170                 writer.writeAttribute
    171                     ("name", "org.apache.struts.taglib.html.md.TOKEN", null);
    172                 writer.writeAttribute("value", token, null);
    173                 writer.endElement("input");
    174                 writer.writeText("\n", null);
    175             }
    176         }
    177 
    178         // Create an instance of the form bean if necessary
    179         if (component instanceof FormComponent) {
    180             ((FormComponent) component).createActionForm(context);
    181         }
    182 
    183     }
    184 
    185 
    186     /**
    187      * <p>Render the ending of an HTML <code>&lt;form&gt;</code>
    188      * control.</p>
    189      *
    190      * @param context FacesContext for the request we are processing
    191      * @param component UIComponent to be rendered
    192      *
    193      * @exception IOException if an input/output error occurs while rendering
    194      * @exception NullPointerException if <code>context</code>
    195      *  or <code>component</code> is null
    196      */
    197     public void encodeEnd(FacesContext context, UIComponent component)
    198         throws IOException {
    199 
    200         if ((context == null) || (component == null)) {
    201             throw new NullPointerException();
    202         }
    203         String clientId = component.getClientId(context);
    204         if (log.isDebugEnabled()) {
    205             log.debug("encodeEnd(" + clientId + ")");
    206         }
    207         ResponseWriter writer = context.getResponseWriter();
    208 
    209         // Render the hidden variable our decode() method uses to detect submits
    210         writer.startElement("input", component);
    211         writer.writeAttribute("type", "hidden", null);
    212         writer.writeAttribute("name", component.getClientId(context), null);
    213         writer.writeAttribute("value", component.getClientId(context), null);
    214         writer.endElement("input");
    215         writer.write("\n");
    216 
    217         // Write our state information (if necessary)
    218         context.getApplication().getViewHandler().writeState(context);
    219 
    220         // Render the ending of this form
    221         writer.endElement("form");
    222         writer.writeText("\n", null);
    223 
    224         // Render focus JavaScript if requested
    225         if (!(component instanceof FormComponent)) {
    226             return;
    227         }
    228         String focus = (String) component.getAttributes().get("focus");
    229         if (focus == null) {
    230             return;
    231         }
    232         String focusIndex =
    233             (String) component.getAttributes().get("focusIndex");
    234         writer.writeText("\n", null);
    235         FormComponent form = (FormComponent) component;
    236         writer.startElement("script", form);
    237         writer.writeAttribute("type", "text/javascript", null);
    238         if (!is.html.md(component)) {
    239             writer.writeAttribute("language", "JavaScript", null);
    240         }
    241         writer.writeText("\n", null);
    242         if (!is.html.md(component)) {
    243             writer.write("<!--\n");
    244         }
    245 
    246         StringBuffer sb = new StringBuffer("document.forms[\"");
    247         sb.append(clientId);
    248         sb.append("\"].elements[\"");
    249         sb.append(component.getClientId(context));
    250         sb.append(NamingContainer.SEPARATOR_CHAR);
    251         sb.append(focus);
    252         sb.append("\"]");
    253         String focusControl = sb.toString();
    254 
    255         writer.write("  var focusControl = ");
    256         writer.write(focusControl);
    257         writer.write(";\n");
    258         writer.write("  if (focusControl.type != \"hidden\") {\n");
    259         writer.write("    ");
    260         writer.write(focusControl);
    261         if (focusIndex != null) {
    262             writer.write("[");
    263             writer.write(focusIndex);
    264             writer.write("]");
    265         }
    266         writer.write(".focus();\n");
    267         writer.write("  }\n");
    268 
    269         if (!is.html.md(component)) {
    270             writer.write("// -->\n");
    271         }
    272         writer.endElement("script");
    273         writer.writeText("\n", null);
    274 
    275     }
    276 
    277 
    278     // ------------------------------------------------------- Protected Methods
    279 
    280 
    281     /**
    282      * <p>Calculate and return the value to be specifed for the
    283      * <code>action</action> attribute on the <code>&lt;form&gt;</code>
    284      * element to be rendered.</p>
    285      *
    286      * @param context FacesContext for the current request
    287      * @param component Component being processed
    288      */
    289     protected String action(FacesContext context, UIComponent component) {
    290 
    291         String actionURL =
    292             context.getApplication().getViewHandler().
    293             getActionURL(context, context.getViewRoot().getViewId());
    294         if (log.isTraceEnabled()) {
    295             log.trace("getActionURL(" + context.getViewRoot().getViewId() +
    296                       ") --> " + actionURL);
    297         }
    298         return (context.getExternalContext().encodeActionURL(actionURL));
    299 
    300     }
    301 
    302 
    303     /**
    304      * <p>Return <code>true</code> if we should render as XHTML.</p>
    305      *
    306      * @param component The component we are rendering
    307      */
    308     protected boolean is.html.md(UIComponent component) {
    309 
    310         return (false); // FIXME -- check up the hierarchy
    311 
    312     }
    313 
    314 
    315 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
