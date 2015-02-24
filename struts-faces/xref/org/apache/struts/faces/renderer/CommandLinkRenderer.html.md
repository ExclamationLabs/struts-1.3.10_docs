[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/CommandLinkRenderer.html.md)


    1   /*
    2    * $Id: CommandLinkRenderer.java 473327 2006-11-10 12:59:22Z niallp $
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
    26  import java.util.Iterator;
    27  
    28  import javax.faces.component.NamingContainer;
    29  import javax.faces.component.UICommand;
    30  import javax.faces.component.UIComponent;
    31  import javax.faces.component.UIForm;
    32  import javax.faces.component.UIParameter;
    33  import javax.faces.context.FacesContext;
    34  import javax.faces.context.ResponseWriter;
    35  import javax.faces.event.ActionEvent;
    36  
    37  import org.apache.commons.logging.Log;
    38  import org.apache.commons.logging.LogFactory;
    39  import org.apache.struts.Globals;
    40  import org.apache.struts.config.ActionConfig;
    41  import org.apache.struts.config.ModuleConfig;
    42  
    43  
    44  /**
    45   * <p><code>Renderer</code> implementation for the <code>commandLink</code>
    46   * tag from the <em>Struts-Faces Integration Library</em>.</p>
    47   *
    48   * @version $Rev: 473327 $ $Date: 2006-11-10 06:59:22 -0600 (Fri, 10 Nov 2006) $
    49   */
    50  
    51  public class CommandLinkRenderer extends AbstractRenderer {
    52  
    53  
    54      // -------------------------------------------------------- Static Variables
    55  
    56  
    57      /**
    58       * <p>Token for private names.</p>
    59       */
    60      private static final String TOKEN =
    61          "org_apache_struts_faces_renderer_CommandLinkRenderer";
    62  
    63  
    64      /**
    65       * <p>The <code>Log</code> instance for this class.</p>
    66       */
    67      private static Log log = LogFactory.getLog(CommandLinkRenderer.class);
    68  
    69  
    70      // ---------------------------------------------------------- Public Methods
    71  
    72  
    73      /**
    74       * <p>Perform setup processing that will be required for decoding the
    75       * incoming request.</p>
    76       *
    77       * @param context FacesContext for the request we are processing
    78       * @param component UIComponent to be processed
    79       *
    80       * @exception NullPointerException if <code>context</code>
    81       *  or <code>component</code> is null
    82       */
    83      public void decode(FacesContext context, UIComponent component) {
    84  
    85          // Implement spec requirements on NullPointerException
    86          if ((context == null) || (component == null)) {
    87              throw new NullPointerException();
    88          }
    89  
    90          // Skip this component if it is not relevant
    91          if (!component.isRendered() || isDisabled(component) ||
    92              isReadOnly(component)) {
    93              return;
    94          }
    95  
    96          // Set up variables we will need
    97          UIForm form = null;
    98          UIComponent parent = component.getParent();
    99          while (parent != null) {
    100             if (parent instanceof UIForm) {
    101                 form = (UIForm) parent;
    102                 break;
    103             }
    104             parent = parent.getParent();
    105         }
    106         if (form == null) {
    107             log.warn("CommandLinkComponent not nested inside UIForm, ignored");
    108             return;
    109         }
    110 
    111         // Was this the component that submitted this form?
    112         String paramId = TOKEN;
    113         String value = (String)
    114             context.getExternalContext().getRequestParameterMap().get(paramId);
    115         if ((value == null) || !value.equals(component.getClientId(context))) {
    116             if (log.isTraceEnabled()) {
    117                 log.trace("decode(" + component.getId() + ") --> not active");
    118             }
    119             return;
    120         }
    121 
    122         // Queue an ActionEvent from this component
    123         if (log.isTraceEnabled()) {
    124             log.trace("decode(" + component.getId() + ") --> queueEvent()");
    125         }
    126         component.queueEvent(new ActionEvent(component));
    127 
    128     }
    129 
    130 
    131     private static String passThrough[] =
    132     { "accesskey", "charset", "dir", "hreflang", "lang", "onblur",
    133       /* "onclick", */ "ondblclick", "onfocus", "onkeydown",
    134       "onkeypress", "onkeyup", "onmousedown", "onmousemove",
    135       "onmouseout", "onmouseover", "onmouseup", "rel", "rev",
    136       "style", "tabindex", "target", "title", "type" };
    137 
    138 
    139     /**
    140      * <p>Render the beginning of a hyperlink to submit this form.</p>
    141      *
    142      * @param context FacesContext for the request we are processing
    143      * @param component UIComponent to be rendered
    144      * @param writer ResponseWriter we are rendering to
    145      *
    146      * @exception IOException if an input/output error occurs while rendering
    147      * @exception NullPointerException if <code>context</code>
    148      *  or <code>component</code> is null
    149      */
    150     public void renderStart(FacesContext context, UIComponent component,
    151                             ResponseWriter writer)
    152         throws IOException {
    153 
    154         // Skip this component if it is not relevant
    155         if (!component.isRendered() || isDisabled(component) ||
    156             isReadOnly(component)) {
    157             return;
    158         }
    159 
    160         // Set up variables we will need
    161         UIForm form = null;
    162         UIComponent parent = component.getParent();
    163         while (parent != null) {
    164             if (parent instanceof UIForm) {
    165                 form = (UIForm) parent;
    166                 break;
    167             }
    168             parent = parent.getParent();
    169         }
    170         if (form == null) {
    171             log.warn("CommandLinkComponent not nested inside UIForm, ignored");
    172             return;
    173         }
    174         String formClientId = form.getClientId(context);
    175 
    176         // If this is the first nested command link inside this form,
    177         // render a hidden variable to identify which link did the submit
    178         String key = formClientId + NamingContainer.SEPARATOR_CHAR + TOKEN;
    179         if (context.getExternalContext().getRequestMap().get(key) == null) {
    180             writer.startElement("input", null);
    181             writer.writeAttribute("name", TOKEN, null);
    182             writer.writeAttribute("type", "hidden", null);
    183             writer.writeAttribute("value", "", null);
    184             writer.endElement("input");
    185             context.getExternalContext().getRequestMap().put
    186                 (key, Boolean.TRUE);
    187         }
    188 
    189 
    190         // Render the beginning of this hyperlink
    191         writer.startElement("a", component);
    192 
    193     }
    194 
    195 
    196     /**
    197      * <p>Render the attributes of a hyperlink to submit this form.</p>
    198      *
    199      * @param context FacesContext for the request we are processing
    200      * @param component UIComponent to be rendered
    201      * @param writer ResponseWriter we are rendering to
    202      *
    203      * @exception IOException if an input/output error occurs while rendering
    204      * @exception NullPointerException if <code>context</code>
    205      *  or <code>component</code> is null
    206      */
    207     public void renderAttributes(FacesContext context, UIComponent component,
    208                                  ResponseWriter writer)
    209         throws IOException {
    210 
    211         // Skip this component if it is not relevant
    212         if (!component.isRendered() || isDisabled(component) ||
    213             isReadOnly(component)) {
    214             return;
    215         }
    216 
    217         // Set up variables we will need
    218         UIComponent form = null;
    219         UIComponent parent = component.getParent();
    220         while (parent != null) {
    221             if (parent instanceof UIForm || 
    222                 "org.apache.myfaces.trinidad.Form".equals(parent.getFamily()) ||
    223                 "oracle.adf.Form".equals(parent.getFamily())) {
    224                 form = parent;
    225                 break;
    226             }
    227             parent = parent.getParent();
    228         }
    229         if (form == null) {
    230             log.warn("CommandLinkComponent not nested inside UIForm, ignored");
    231             return;
    232         }
    233         String formClientId = form.getClientId(context);
    234 
    235         // Render the attributes of this hyperlink
    236         if (component.getId() != null) {
    237             writer.writeAttribute("id", component.getClientId(context), "id");
    238         }
    239         writer.writeAttribute("href", "#", null);
    240         String styleClass = (String)
    241             component.getAttributes().get("styleClass");
    242         if (styleClass != null) {
    243             writer.writeAttribute("class", styleClass, "styleClass");
    244         }
    245         renderPassThrough(context, component, writer, passThrough);
    246 
    247         // Render the JavaScript content of the "onclick" element
    248         StringBuffer sb = new StringBuffer();
    249         sb.append("document.forms['");
    250         sb.append(formClientId);
    251         sb.append("']['");
    252         sb.append(TOKEN);
    253         sb.append("'].value='");
    254         sb.append(component.getClientId(context));
    255         sb.append("';");
    256         Iterator kids = component.getChildren().iterator();
    257         while (kids.hasNext()) {
    258             UIComponent kid = (UIComponent) kids.next();
    259             if (!(kid instanceof UIParameter)) {
    260                 continue;
    261             }
    262             sb.append("document.forms['");
    263             sb.append(formClientId);
    264             sb.append("']['");
    265             sb.append((String) kid.getAttributes().get("name"));
    266             sb.append("'].value='");
    267             sb.append((String) kid.getAttributes().get("value"));
    268             sb.append("';");
    269         }
    270         sb.append("document.forms['");
    271         sb.append(formClientId);
    272         sb.append("'].submit(); return false;");
    273         writer.writeAttribute("onclick", sb.toString(), null);
    274 
    275         // Render the component value as the hyperlink text
    276         Object value = component.getAttributes().get("value");
    277         if (value != null) {
    278             if (value instanceof String) {
    279                 writer.write((String) value);
    280             } else {
    281                 writer.write(value.toString());
    282             }
    283         }
    284 
    285     }
    286 
    287 
    288     /**
    289      * <p>Render the end of a hyperlink to submit this form.</p>
    290      *
    291      * @param context FacesContext for the request we are processing
    292      * @param component UIComponent to be rendered
    293      * @param writer ResponseWriter we are rendering to
    294      *
    295      * @exception IOException if an input/output error occurs while rendering
    296      * @exception NullPointerException if <code>context</code>
    297      *  or <code>component</code> is null
    298      */
    299     public void renderEnd(FacesContext context, UIComponent component,
    300                           ResponseWriter writer)
    301         throws IOException {
    302 
    303         // Skip this component if it is not relevant
    304         if (!component.isRendered() || isDisabled(component) ||
    305             isReadOnly(component)) {
    306             return;
    307         }
    308 
    309         // Render the beginning of this hyperlink
    310         writer.endElement("a");
    311 
    312     }
    313 
    314 
    315 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
