[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/AbstractRenderer.html.md)


    1   /*
    2    * $Id: AbstractRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import java.util.Map;
    28  
    29  import javax.faces.application.FacesMessage;
    30  import javax.faces.component.EditableValueHolder;
    31  import javax.faces.component.UIComponent;
    32  import javax.faces.component.ValueHolder;
    33  import javax.faces.context.FacesContext;
    34  import javax.faces.context.ResponseWriter;
    35  import javax.faces.convert.Converter;
    36  import javax.faces.convert.ConverterException;
    37  import javax.faces.el.ValueBinding;
    38  import javax.faces.render.Renderer;
    39  
    40  import org.apache.commons.logging.Log;
    41  import org.apache.commons.logging.LogFactory;
    42  
    43  
    44  /**
    45   * <p>Abstract base class for concrete implementations of
    46   * <code>javax.faces.render.Renderer</code> for the
    47   * <em>Struts-Faces Integration Library</em>.</p>
    48   *
    49   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    50   */
    51  
    52  public abstract class AbstractRenderer extends Renderer {
    53  
    54  
    55      // -------------------------------------------------------- Static Variables
    56  
    57  
    58      private static final Log log =
    59    LogFactory.getLog(AbstractRenderer.class);
    60  
    61  
    62      // -------------------------------------------------------- Renderer Methods
    63  
    64  
    65      /**
    66       * <p>Decode any new state of the specified <code>UIComponent</code>
    67       * from the request contained in the specified <code>FacesContext</code>,
    68       * and store that state on the <code>UIComponent</code>.</p>
    69       *
    70       * <p>The default implementation calls <code>setSubmittedValue()</code>
    71       * unless this component has a boolean <code>disabled</code> or
    72       * <code>readonly</code> attribute that is set to <code>true</code>.</p>
    73       *
    74       * @param context <code>FacesContext</code> for the current request
    75       * @param component <code>UIComponent</code> to be decoded
    76       *
    77       * @exception NullPointerException if <code>context</code> or
    78       *  <code>component</code> is <code>null</code>
    79       */
    80      public void decode(FacesContext context, UIComponent component) {
    81  
    82          // Enforce NPE requirements in the Javadocs
    83          if ((context == null) || (component == null)) {
    84              throw new NullPointerException();
    85          }
    86  
    87          // Disabled or readonly components are not decoded
    88          if (isDisabled(component) || isReadOnly(component)) {
    89              return;
    90          }
    91  
    92          // Save submitted value on EditableValueHolder components
    93          if (component instanceof EditableValueHolder) {
    94              setSubmittedValue(context, component);
    95          }
    96  
    97      }
    98  
    99  
    100     /**
    101      * <p>Render the beginning of the specified <code>UIComponent</code>
    102      * to the output stream or writer associated with the response we are
    103      * creating.</p>
    104      *
    105      * <p>The default implementation calls <code>renderStart()</code> and
    106      * <code>renderAttributes()</code>.</p>
    107      *
    108      * @param context <code>FacesContext</code> for the current request
    109      * @param component <code>UIComponent</code> to be decoded
    110      *
    111      * @exception NullPointerException if <code>context</code> or
    112      *  <code>component</code> is <code>null</code>
    113      *
    114      * @exception IOException if an input/output error occurs
    115      */
    116     public void encodeBegin(FacesContext context, UIComponent component)
    117         throws IOException {
    118 
    119         // Enforce NPE requirements in the Javadocs
    120         if ((context == null) || (component == null)) {
    121             throw new NullPointerException();
    122         }
    123 
    124         if (log.isTraceEnabled()) {
    125             log.trace("encodeBegin(id=" + component.getId() +
    126                 ", family=" + component.getFamily() +
    127                 ", rendererType=" + component.getRendererType() + ")");
    128         }
    129 
    130         // Render the element and attributes for this component
    131         ResponseWriter writer = context.getResponseWriter();
    132         renderStart(context, component, writer);
    133         renderAttributes(context, component, writer);
    134 
    135     }
    136 
    137 
    138     /**
    139      * <p>Render the children of the specified <code>UIComponent</code>
    140      * to the output stream or writer associated with the response we are
    141      * creating.</p>
    142      *
    143      * <p>The default implementation iterates through the children of
    144      * this component and renders them.</p>
    145      *
    146      * @param context <code>FacesContext</code> for the current request
    147      * @param component <code>UIComponent</code> to be decoded
    148      *
    149      * @exception NullPointerException if <code>context</code> or
    150      *  <code>component</code> is <code>null</code>
    151      *
    152      * @exception IOException if an input/output error occurs
    153      */
    154     public void encodeChildren(FacesContext context, UIComponent component)
    155         throws IOException {
    156 
    157         if (context == null || component == null) {
    158             throw new NullPointerException();
    159         }
    160 
    161         if (log.isTraceEnabled()) {
    162             log.trace("encodeChildren(id=" + component.getId() +
    163                     ", family=" + component.getFamily() +
    164                     ", rendererType=" + component.getRendererType() + ")");
    165         }
    166         Iterator kids = component.getChildren().iterator();
    167         while (kids.hasNext()) {
    168             UIComponent kid = (UIComponent) kids.next();
    169             kid.encodeBegin(context);
    170             if (kid.getRendersChildren()) {
    171                 kid.encodeChildren(context);
    172             }
    173             kid.encodeEnd(context);
    174         }
    175         if (log.isTraceEnabled()) {
    176             log.trace("encodeChildren(id=" + component.getId() + ") end");
    177         }
    178 
    179     }
    180 
    181 
    182     /**
    183      * <p>Render the ending of the specified <code>UIComponent</code>
    184      * to the output stream or writer associated with the response we are
    185      * creating.</p>
    186      *
    187      * <p>The default implementation calls <code>renderEnd()</code>.</p>
    188      *
    189      * @param context <code>FacesContext</code> for the current request
    190      * @param component <code>UIComponent</code> to be decoded
    191      *
    192      * @exception NullPointerException if <code>context</code> or
    193      *  <code>component</code> is <code>null</code>
    194      *
    195      * @exception IOException if an input/output error occurs
    196      */
    197     public void encodeEnd(FacesContext context, UIComponent component)
    198         throws IOException {
    199 
    200         // Enforce NPE requirements in the Javadocs
    201         if ((context == null) || (component == null)) {
    202             throw new NullPointerException();
    203         }
    204 
    205         if (log.isTraceEnabled()) {
    206             log.trace("encodeEnd(id=" + component.getId() +
    207                     ", family=" + component.getFamily() +
    208                     ", rendererType=" + component.getRendererType() + ")");
    209         }
    210 
    211         // Render the element closing for this component
    212         ResponseWriter writer = context.getResponseWriter();
    213         renderEnd(context, component, writer);
    214 
    215     }
    216 
    217 
    218     // --------------------------------------------------------- Package Methods
    219 
    220 
    221     // ------------------------------------------------------- Protected Methods
    222 
    223 
    224     /**
    225      * <p>Render nested child components by invoking the encode methods
    226      * on those components, but only when the <code>rendered</code>
    227      * property is <code>true</code>.</p>
    228      */
    229     protected void encodeRecursive(FacesContext context, UIComponent component)
    230         throws IOException {
    231 
    232         // suppress rendering if "rendered" property on the component is
    233         // false.
    234         if (!component.isRendered()) {
    235             return;
    236         }
    237 
    238         // Render this component and its children recursively
    239         if (log.isTraceEnabled()) {
    240             log.trace("encodeRecursive(id=" + component.getId() +
    241                     ", family=" + component.getFamily() +
    242                     ", rendererType=" + component.getRendererType() +
    243                     ") encodeBegin");
    244         }
    245         component.encodeBegin(context);
    246         if (component.getRendersChildren()) {
    247             if (log.isTraceEnabled()) {
    248                 log.trace("encodeRecursive(id=" + component.getId() +
    249                         ") delegating");
    250             }
    251             component.encodeChildren(context);
    252         } else {
    253             if (log.isTraceEnabled()) {
    254                 log.trace("encodeRecursive(id=" + component.getId() +
    255                         ") recursing");
    256             }
    257             Iterator kids = component.getChildren().iterator();
    258             while (kids.hasNext()) {
    259                 UIComponent kid = (UIComponent) kids.next();
    260                 encodeRecursive(context, kid);
    261             }
    262         }
    263         if (log.isTraceEnabled()) {
    264             log.trace("encodeRecursive(id=" + component.getId() + ") encodeEnd");
    265         }
    266         component.encodeEnd(context);
    267 
    268     }
    269 
    270 
    271     /**
    272      * <p>Return <code>true</code> if the specified component is disabled.</p>
    273      *
    274      * @param component <code>UIComponent</code> to be checked
    275      */
    276     protected boolean isDisabled(UIComponent component) {
    277 
    278         Object disabled = component.getAttributes().get("disabled");
    279         if (disabled == null) {
    280             return (false);
    281         }
    282         if (disabled instanceof String) {
    283             return (Boolean.valueOf((String) disabled).booleanValue());
    284         } else {
    285             return (disabled.equals(Boolean.TRUE));
    286         }
    287 
    288     }
    289 
    290 
    291     /**
    292      * <p>Return <code>true</code> if the specified component is read only.</p>
    293      *
    294      * @param component <code>UIComponent</code> to be checked
    295      */
    296     protected boolean isReadOnly(UIComponent component) {
    297 
    298         Object readonly = component.getAttributes().get("readonly");
    299         if (readonly == null) {
    300             return (false);
    301         }
    302         if (readonly instanceof String) {
    303             return (Boolean.valueOf((String) readonly).booleanValue());
    304         } else {
    305             return (readonly.equals(Boolean.TRUE));
    306         }
    307 
    308     }
    309 
    310 
    311     /**
    312      * <p>Render the element attributes for the generated markup related to this
    313      * component.  Simple renderers that create a single markup element
    314      * for this component should override this method and include calls to
    315      * to <code>writeAttribute()</code> and <code>writeURIAttribute</code>
    316      * on the specified <code>ResponseWriter</code>.</p>
    317      *
    318      * <p>The default implementation does nothing.</p>
    319      *
    320      * @param context <code>FacesContext</code> for the current request
    321      * @param component <code>EditableValueHolder</code> component whose
    322      *  submitted value is to be stored
    323      * @param writer <code>ResponseWriter</code> to which the element
    324      *  start should be rendered
    325      *
    326      * @exception IOException if an input/output error occurs
    327      */
    328     protected void renderAttributes(FacesContext context, UIComponent component,
    329                                     ResponseWriter writer) throws IOException {
    330 
    331     }
    332 
    333 
    334     /**
    335      * <p>Render the element end for the generated markup related to this
    336      * component.  Simple renderers that create a single markup element
    337      * for this component should override this method and include a call
    338      * to <code>endElement()</code> on the specified
    339      * <code>ResponseWriter</code>.</p>
    340      *
    341      * <p>The default implementation does nothing.</p>
    342      *
    343      * @param context <code>FacesContext</code> for the current request
    344      * @param component <code>EditableValueHolder</code> component whose
    345      *  submitted value is to be stored
    346      * @param writer <code>ResponseWriter</code> to which the element
    347      *  start should be rendered
    348      *
    349      * @exception IOException if an input/output error occurs
    350      */
    351     protected void renderEnd(FacesContext context, UIComponent component,
    352                              ResponseWriter writer) throws IOException {
    353 
    354     }
    355 
    356 
    357     /**
    358      * <p>Render any boolean attributes on the specified list that have
    359      * <code>true</code> values on the corresponding attribute of the
    360      * specified <code>UIComponent</code>.</p>
    361      *
    362      * @param context <code>FacesContext</code> for the current request
    363      * @param component <code>EditableValueHolder</code> component whose
    364      *  submitted value is to be stored
    365      * @param writer <code>ResponseWriter</code> to which the element
    366      *  start should be rendered
    367      * @param names List of attribute names to be passed through
    368      *
    369      * @exception IOException if an input/output error occurs
    370      */
    371     protected void renderBoolean(FacesContext context,
    372                                  UIComponent component,
    373                                  ResponseWriter writer,
    374                                  String names[]) throws IOException {
    375 
    376         if (names == null) {
    377             return;
    378         }
    379         Map attributes = component.getAttributes();
    380         boolean flag;
    381         Object value;
    382         for (int i = 0; i < names.length; i++) {
    383             value = attributes.get(names[i]);
    384             if (value != null) {
    385                 if (value instanceof String) {
    386                     flag = Boolean.valueOf((String) value).booleanValue();
    387                 } else {
    388                     flag = Boolean.valueOf(value.toString()).booleanValue();
    389                 }
    390                 if (flag) {
    391                     writer.writeAttribute(names[i], names[i], names[i]);
    392                     flag = false;
    393                 }
    394             }
    395         }
    396 
    397     }
    398 
    399 
    400     /**
    401      * <p>Render any attributes on the specified list directly to the
    402      * specified <code>ResponseWriter</code> for which the specified
    403      * <code>UIComponent</code> has a non-<code>null</code> attribute value.
    404      * This method may be used to "pass through" commonly used attribute
    405      * name/value pairs with a minimum of code.</p>
    406      *
    407      * @param context <code>FacesContext</code> for the current request
    408      * @param component <code>EditableValueHolder</code> component whose
    409      *  submitted value is to be stored
    410      * @param writer <code>ResponseWriter</code> to which the element
    411      *  start should be rendered
    412      * @param names List of attribute names to be passed through
    413      *
    414      * @exception IOException if an input/output error occurs
    415      */
    416     protected void renderPassThrough(FacesContext context,
    417                                      UIComponent component,
    418                                      ResponseWriter writer,
    419                                      String names[]) throws IOException {
    420 
    421         if (names == null) {
    422             return;
    423         }
    424         Map attributes = component.getAttributes();
    425         Object value;
    426         for (int i = 0; i < names.length; i++) {
    427             value = attributes.get(names[i]);
    428             if (value != null) {
    429                 if (value instanceof String) {
    430                     writer.writeAttribute(names[i], value, names[i]);
    431                 } else {
    432                     writer.writeAttribute(names[i], value.toString(), names[i]);
    433                 }
    434             }
    435         }
    436 
    437     }
    438 
    439 
    440     /**
    441      * <p>Render the element start for the generated markup related to this
    442      * component.  Simple renderers that create a single markup element
    443      * for this component should override this method and include a call
    444      * to <code>startElement()</code> on the specified
    445      * <code>ResponseWriter</code>.</p>
    446      *
    447      * <p>The default implementation does nothing.</p>
    448      *
    449      * @param context <code>FacesContext</code> for the current request
    450      * @param component <code>EditableValueHolder</code> component whose
    451      *  submitted value is to be stored
    452      * @param writer <code>ResponseWriter</code> to which the element
    453      *  start should be rendered
    454      *
    455      * @exception IOException if an input/output error occurs
    456      */
    457     protected void renderStart(FacesContext context, UIComponent component,
    458                                ResponseWriter writer) throws IOException {
    459 
    460     }
    461 
    462 
    463     /**
    464      * <p>If a submitted value was included on this request, store it in the
    465      * component as appropriate.</p>
    466      *
    467      * <p>The default implementation determines whether this component
    468      * implements <code>EditableValueHolder</code>.  If so, it checks for a
    469      * request parameter with the same name as the <code>clientId</code>
    470      * of this <code>UIComponent</code>.  If there is such a parameter, its
    471      * value is passed (as a String) to the <code>setSubmittedValue()</code>
    472      * method on the <code>EditableValueHolder</code> component.</p>
    473      *
    474      * @param context <code>FacesContext</code> for the current request
    475      * @param component <code>EditableValueHolder</code> component whose
    476      *  submitted value is to be stored
    477      */
    478     protected void setSubmittedValue
    479         (FacesContext context, UIComponent component) {
    480 
    481         if (!(component instanceof EditableValueHolder)) {
    482             return;
    483         }
    484         String clientId = component.getClientId(context);
    485         Map parameters = context.getExternalContext().getRequestParameterMap();
    486         if (parameters.containsKey(clientId)) {
    487             if (log.isTraceEnabled()) {
    488                 log.trace("setSubmittedValue(" + clientId + "," +
    489                           (String) parameters.get(clientId));
    490             }
    491             component.getAttributes().put("submittedValue",
    492                                           parameters.get(clientId));
    493         }
    494 
    495     }
    496 
    497 
    498     // --------------------------------------------------------- Private Methods
    499 
    500 
    501     /**
    502      * <p>Decode the current state of the specified UIComponent from the
    503      * request contained in the specified <code>FacesContext</code>, and
    504      * attempt to convert this state information into an object of the
    505      * type equired for this component.</p>
    506      *
    507      * @param context FacesContext for the request we are processing
    508      * @param component UIComponent to be decoded
    509      *
    510      * @exception NullPointerException if context or component is null
    511      */
    512     /*
    513     public void decode(FacesContext context, UIComponent component) {
    514 
    515         // Enforce NPE requirements in the Javadocs
    516         if ((context == null) || (component == null)) {
    517             throw new NullPointerException();
    518         }
    519 
    520         // Only input components need to be decoded
    521         if (!(component instanceof UIInput)) {
    522             return;
    523         }
    524         UIInput input = (UIInput) component;
    525 
    526         // Save the old value for use in generating ValueChangedEvents
    527         Object oldValue = input.getValue();
    528         if (oldValue instanceof String) {
    529             try {
    530                 oldValue = getAsObject(context, component, (String) oldValue);
    531             } catch (ConverterException e) {
    532                 ;
    533             }
    534         }
    535         input.setPrevious(oldValue);
    536 
    537         // Decode and convert (if needed) the new value
    538         String clientId = component.getClientId(context);
    539         Map map = context.getExternalContext().getRequestParameterMap();
    540         String newString = (String) map.get(clientId);
    541         Object newValue = null;
    542         try {
    543             newValue = getAsObject(context, component, newString);
    544             input.setValue(newValue);
    545             input.setValid(true);
    546         } catch (ConverterException e) {
    547             input.setValue(newValue);
    548             input.setValid(false);
    549             addConverterMessage(context, component, e.getMessage());
    550         }
    551 
    552     }
    553     */
    554 
    555 
    556     // --------------------------------------------------------- Package Methods
    557 
    558 
    559     // ------------------------------------------------------- Protected Methods
    560 
    561 
    562     /**
    563      * <p>Add an error message denoting a conversion failure.</p>
    564      *
    565      * @param context The <code>FacesContext</code> for this request
    566      * @param component The <code>UIComponent</code> that experienced
    567      *  the conversion failure
    568      * @param text The text of the error message
    569      */
    570     /*
    571     protected void addConverterMessage(FacesContext context,
    572                                        UIComponent component,
    573                                        String text) {
    574 
    575         String clientId = component.getClientId(context);
    576         FacesMessage message = new FacesMessage
    577             (text,
    578              "Conversion error on component '" + clientId + "'");
    579         context.addMessage(clientId, message);
    580 
    581     }
    582     */
    583 
    584 
    585     /**
    586      * <p>Convert the String representation of this component's value
    587      * to the corresponding Object representation.  The default
    588      * implementation utilizes the <code>getAsObject()</code> method of any
    589      * associated <code>Converter</code>.</p>
    590      *
    591      * @param context The <code>FacesContext</code> for this request
    592      * @param component The <code>UIComponent</code> whose value is
    593      *  being converted
    594      * @param value The String representation to be converted
    595      *
    596      * @exception ConverterException if conversion fails
    597      */
    598     /*
    599     protected Object getAsObject(FacesContext context, UIComponent component,
    600                                  String value) throws ConverterException {
    601 
    602         // Identify any Converter associated with this component value
    603         ValueBinding vb = component.getValueBinding("value");
    604         Converter converter = null;
    605         if (component instanceof ValueHolder) {
    606             // Acquire explicitly assigned Converter (if any)
    607             converter = ((ValueHolder) component).getConverter();
    608         }
    609         if ((converter == null) && (vb != null)) {
    610             Class type = vb.getType(context);
    611             if ((type == null) || (type == String.class)) {
    612                 return (value); // No conversion required for Strings
    613             }
    614             // Acquire implicit by-type Converter (if any)
    615             converter = context.getApplication().createConverter(type);
    616         }
    617 
    618         // Convert the result if we identified a Converter
    619         if (converter != null) {
    620             return (converter.getAsObject(context, component, value));
    621         } else {
    622             return (value);
    623         }
    624 
    625     }
    626     */
    627 
    628 
    629     /**
    630      * <p>Convert the Object representation of this component's value
    631      * to the corresponding String representation.  The default implementation
    632      * utilizes the <code>getAsString()</code> method of any associated
    633      * <code>Converter</code>.</p>
    634      *
    635      * @param context The <code>FacesContext</code> for this request
    636      * @param component The <code>UIComponent</code> whose value is
    637      *  being converted
    638      * @param value The Object representation to be converted
    639      *
    640      * @exception ConverterException if conversion fails
    641      */
    642     protected String getAsString(FacesContext context, UIComponent component,
    643                                  Object value) throws ConverterException {
    644 
    645         // Identify any Converter associated with this component value
    646         ValueBinding vb = component.getValueBinding("value");
    647         Converter converter = null;
    648         if (component instanceof ValueHolder) {
    649             // Acquire explicitly assigned Converter (if any)
    650             converter = ((ValueHolder) component).getConverter();
    651         }
    652         if ((converter == null) && (vb != null)) {
    653             // Acquire implicit by-type Converter (if any)
    654             Class type = vb.getType(context);
    655             if (type != null) {
    656                 converter = context.getApplication().createConverter(type);
    657             }
    658         }
    659 
    660         // Convert the result if we identified a Converter
    661         if (converter != null) {
    662             return (converter.getAsString(context, component, value));
    663         } else if (value == null) {
    664             return ("");
    665         } else if (value instanceof String) {
    666             return ((String) value);
    667         } else {
    668             return (value.toString());
    669         }
    670 
    671     }
    672 
    673 
    674 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
