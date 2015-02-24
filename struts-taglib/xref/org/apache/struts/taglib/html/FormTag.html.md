[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/FormTag.html)


    1   /*
    2    * $Id: FormTag.java 684382 2008-08-10 00:11:59Z niallp $
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
    21  package org.apache.struts.taglib.html.md;
    22  
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.action.ActionForm;
    25  import org.apache.struts.action.ActionMapping;
    26  import org.apache.struts.action.ActionServlet;
    27  import org.apache.struts.config.ActionConfig;
    28  import org.apache.struts.config.FormBeanConfig;
    29  import org.apache.struts.config.ModuleConfig;
    30  import org.apache.struts.taglib.TagUtils;
    31  import org.apache.struts.util.MessageResources;
    32  import org.apache.struts.util.RequestUtils;
    33  
    34  import javax.servlet.http.HttpServletRequest;
    35  import javax.servlet.http.HttpServletResponse;
    36  import javax.servlet.http.HttpSession;
    37  import javax.servlet.jsp.JspException;
    38  import javax.servlet.jsp.JspWriter;
    39  import javax.servlet.jsp.PageContext;
    40  import javax.servlet.jsp.tagext.TagSupport;
    41  
    42  import java.io.IOException;
    43  
    44  /**
    45   * Custom tag that represents an input form, associated with a bean whose
    46   * properties correspond to the various fields of the form.
    47   *
    48   * @version $Rev: 684382 $ $Date: 2008-08-09 19:11:59 -0500 (Sat, 09 Aug 2008) $
    49   */
    50  public class FormTag extends TagSupport {
    51      /**
    52       * The line ending string.
    53       */
    54      protected static String lineEnd = System.getProperty("line.separator");
    55  
    56      /**
    57       * The message resources for this package.
    58       */
    59      protected static MessageResources messages =
    60          MessageResources.getMessageResources(Constants.Package
    61              + ".LocalStrings");
    62  
    63      // ----------------------------------------------------- Instance Variables
    64  
    65      /**
    66       * The action URL to which this form should be submitted, if any.
    67       */
    68      protected String action = null;
    69  
    70      /**
    71       * Autocomplete non standard attribute
    72       */
    73      private String autocomplete = null;
    74  
    75      /**
    76       * A postback action URL to which this form should be submitted, if any.
    77       */
    78      private String postbackAction = null;
    79  
    80      /**
    81       * The module configuration for our module.
    82       */
    83      protected ModuleConfig moduleConfig = null;
    84  
    85      /**
    86       * The content encoding to be used on a POST submit.
    87       */
    88      protected String enctype = null;
    89  
    90      /**
    91       * The name of the field to receive focus, if any.
    92       */
    93      protected String focus = null;
    94  
    95      /**
    96       * The index in the focus field array to receive focus.  This only applies
    97       * if the field given in the focus attribute is actually an array of
    98       * fields.  This allows a specific field in a radio button array to
    99       * receive focus while still allowing indexed field names like
    100      * "myRadioButtonField[1]" to be passed in the focus attribute.
    101      *
    102      * @since Struts 1.1
    103      */
    104     protected String focusIndex = null;
    105 
    106     /**
    107      * The ActionMapping defining where we will be submitting this form
    108      */
    109     protected ActionMapping mapping = null;
    110 
    111     /**
    112      * The request method used when submitting this form.
    113      */
    114     protected String method = null;
    115 
    116     /**
    117      * The onReset event script.
    118      */
    119     protected String onreset = null;
    120 
    121     /**
    122      * The onSubmit event script.
    123      */
    124     protected String onsubmit = null;
    125 
    126     /**
    127      * Include language attribute in the focus script's &lt;script&gt;
    128      * element.  This property is ignored in XHTML mode.
    129      *
    130      * @since Struts 1.2
    131      */
    132     protected boolean scriptLanguage = true;
    133 
    134     /**
    135      * The ActionServlet instance we are associated with (so that we can
    136      * initialize the <code>servlet</code> property on any form bean that we
    137      * create).
    138      */
    139     protected ActionServlet servlet = null;
    140 
    141     /**
    142      * The style attribute associated with this tag.
    143      */
    144     protected String style = null;
    145 
    146     /**
    147      * The style class associated with this tag.
    148      */
    149     protected String styleClass = null;
    150 
    151     /**
    152      * The identifier associated with this tag.
    153      */
    154     protected String styleId = null;
    155 
    156     /**
    157      * The window target.
    158      */
    159     protected String target = null;
    160 
    161     /**
    162      * The name of the form bean to (create and) use. This is either the same
    163      * as the 'name' attribute, if that was specified, or is obtained from the
    164      * associated <code>ActionMapping</code> otherwise.
    165      */
    166     protected String beanName = null;
    167 
    168     /**
    169      * The scope of the form bean to (create and) use. This is either the same
    170      * as the 'scope' attribute, if that was specified, or is obtained from
    171      * the associated <code>ActionMapping</code> otherwise.
    172      */
    173     protected String beanScope = null;
    174 
    175     /**
    176      * The type of the form bean to (create and) use. This is either the same
    177      * as the 'type' attribute, if that was specified, or is obtained from the
    178      * associated <code>ActionMapping</code> otherwise.
    179      */
    180     protected String beanType = null;
    181 
    182     /**
    183      * The list of character encodings for input data that the server should
    184      * accept.
    185      */
    186     protected String acceptCharset = null;
    187 
    188     /**
    189      * Controls whether child controls should be 'disabled'.
    190      */
    191     private boolean disabled = false;
    192 
    193     /**
    194      * Controls whether child controls should be 'readonly'.
    195      */
    196     protected boolean readonly = false;
    197 
    198     /**
    199      * The language code of this element.
    200      */
    201     private String lang = null;
    202     
    203     /**
    204      * The direction for weak/neutral text of this element.
    205      */
    206     private String dir = null;
    207 
    208     // ------------------------------------------------------------- Properties
    209 
    210     /**
    211      * Return the name of the form bean corresponding to this tag. There is no
    212      * corresponding setter method; this method exists so that the nested tag
    213      * classes can obtain the actual bean name derived from other attributes
    214      * of the tag.
    215      */
    216     public String getBeanName() {
    217         return beanName;
    218     }
    219 
    220     /**
    221      * Return the action URL to which this form should be submitted.
    222      */
    223     public String getAction() {
    224         return (this.action);
    225     }
    226 
    227     /**
    228      * Set the action URL to which this form should be submitted.
    229      *
    230      * @param action The new action URL
    231      */
    232     public void setAction(String action) {
    233         this.action = action;
    234     }
    235 
    236     /**
    237      * Return autocomplete
    238      * @since 1.3.10
    239      */
    240     public String getAutocomplete() {
    241         return autocomplete;
    242     }
    243 
    244     /**
    245      * Activate/disactivate autocompletion (on/off)
    246      * @since 1.3.10
    247      */
    248     public void setAutocomplete(String autocomplete) {
    249         this.autocomplete = autocomplete;
    250     }
    251 
    252     /**
    253      * Return the content encoding used when submitting this form.
    254      */
    255     public String getEnctype() {
    256         return (this.enctype);
    257     }
    258 
    259     /**
    260      * Set the content encoding used when submitting this form.
    261      *
    262      * @param enctype The new content encoding
    263      */
    264     public void setEnctype(String enctype) {
    265         this.enctype = enctype;
    266     }
    267 
    268     /**
    269      * Return the focus field name for this form.
    270      */
    271     public String getFocus() {
    272         return (this.focus);
    273     }
    274 
    275     /**
    276      * Set the focus field name for this form.
    277      *
    278      * @param focus The new focus field name
    279      */
    280     public void setFocus(String focus) {
    281         this.focus = focus;
    282     }
    283 
    284     /**
    285      * Return the request method used when submitting this form.
    286      */
    287     public String getMethod() {
    288         return (this.method);
    289     }
    290 
    291     /**
    292      * Set the request method used when submitting this form.
    293      *
    294      * @param method The new request method
    295      */
    296     public void setMethod(String method) {
    297         this.method = method;
    298     }
    299 
    300     /**
    301      * Return the onReset event script.
    302      */
    303     public String getOnreset() {
    304         return (this.onreset);
    305     }
    306 
    307     /**
    308      * Set the onReset event script.
    309      *
    310      * @param onReset The new event script
    311      */
    312     public void setOnreset(String onReset) {
    313         this.onreset = onReset;
    314     }
    315 
    316     /**
    317      * Return the onSubmit event script.
    318      */
    319     public String getOnsubmit() {
    320         return (this.onsubmit);
    321     }
    322 
    323     /**
    324      * Set the onSubmit event script.
    325      *
    326      * @param onSubmit The new event script
    327      */
    328     public void setOnsubmit(String onSubmit) {
    329         this.onsubmit = onSubmit;
    330     }
    331 
    332     /**
    333      * Return the style attribute for this tag.
    334      */
    335     public String getStyle() {
    336         return (this.style);
    337     }
    338 
    339     /**
    340      * Set the style attribute for this tag.
    341      *
    342      * @param style The new style attribute
    343      */
    344     public void setStyle(String style) {
    345         this.style = style;
    346     }
    347 
    348     /**
    349      * Return the style class for this tag.
    350      */
    351     public String getStyleClass() {
    352         return (this.styleClass);
    353     }
    354 
    355     /**
    356      * Set the style class for this tag.
    357      *
    358      * @param styleClass The new style class
    359      */
    360     public void setStyleClass(String styleClass) {
    361         this.styleClass = styleClass;
    362     }
    363 
    364     /**
    365      * Return the style identifier for this tag.
    366      */
    367     public String getStyleId() {
    368         return (this.styleId);
    369     }
    370 
    371     /**
    372      * Set the style identifier for this tag.
    373      *
    374      * @param styleId The new style identifier
    375      */
    376     public void setStyleId(String styleId) {
    377         this.styleId = styleId;
    378     }
    379 
    380     /**
    381      * Return the window target.
    382      */
    383     public String getTarget() {
    384         return (this.target);
    385     }
    386 
    387     /**
    388      * Set the window target.
    389      *
    390      * @param target The new window target
    391      */
    392     public void setTarget(String target) {
    393         this.target = target;
    394     }
    395 
    396     /**
    397      * Return the list of character encodings accepted.
    398      */
    399     public String getAcceptCharset() {
    400         return acceptCharset;
    401     }
    402 
    403     /**
    404      * Set the list of character encodings accepted.
    405      *
    406      * @param acceptCharset The list of character encodings
    407      */
    408     public void setAcceptCharset(String acceptCharset) {
    409         this.acceptCharset = acceptCharset;
    410     }
    411 
    412     /**
    413      * Sets the disabled event handler.
    414      */
    415     public void setDisabled(boolean disabled) {
    416         this.disabled = disabled;
    417     }
    418 
    419     /**
    420      * Returns the disabled event handler.
    421      */
    422     public boolean isDisabled() {
    423         return disabled;
    424     }
    425 
    426     /**
    427      * Sets the readonly event handler.
    428      */
    429     public void setReadonly(boolean readonly) {
    430         this.readonly = readonly;
    431     }
    432 
    433     /**
    434      * Returns the readonly event handler.
    435      */
    436     public boolean isReadonly() {
    437         return readonly;
    438     }
    439 
    440     /**
    441      * Returns the language code of this element.
    442      * 
    443      * @since Struts 1.3.6
    444      */
    445     public String getLang() {
    446         return this.lang;
    447     }
    448 
    449     /**
    450      * Sets the language code of this element.
    451      * 
    452      * @since Struts 1.3.6
    453      */
    454     public void setLang(String lang) {
    455         this.lang = lang;
    456     }
    457 
    458     /**
    459      * Returns the direction for weak/neutral text this element.
    460      * 
    461      * @since Struts 1.3.6
    462      */
    463     public String getDir() {
    464         return this.dir;
    465     }
    466 
    467     /**
    468      * Sets the direction for weak/neutral text of this element.
    469      * 
    470      * @since Struts 1.3.6
    471      */
    472     public void setDir(String dir) {
    473         this.dir = dir;
    474     }
    475 
    476     // --------------------------------------------------------- Public Methods
    477 
    478     /**
    479      * Render the beginning of this form.
    480      *
    481      * @throws JspException if a JSP exception has occurred
    482      */
    483     public int doStartTag() throws JspException {
    484 
    485         postbackAction = null;
    486 
    487         // Look up the form bean name, scope, and type if necessary
    488         this.lookup();
    489 
    490         // Create an appropriate "form" element based on our parameters
    491         StringBuffer results = new StringBuffer();
    492 
    493         results.append(this.renderFormStartElement());
    494 
    495         results.append(this.renderToken());
    496 
    497         TagUtils.getInstance().write(pageContext, results.toString());
    498 
    499         // Store this tag itself as a page attribute
    500         pageContext.setAttribute(Constants.FORM_KEY, this,
    501             PageContext.REQUEST_SCOPE);
    502 
    503         this.initFormBean();
    504 
    505         return (EVAL_BODY_INCLUDE);
    506     }
    507 
    508     /**
    509      * Locate or create the bean associated with our form.
    510      *
    511      * @throws JspException
    512      * @since Struts 1.1
    513      */
    514     protected void initFormBean()
    515         throws JspException {
    516         int scope = PageContext.SESSION_SCOPE;
    517 
    518         if ("request".equalsIgnoreCase(beanScope)) {
    519             scope = PageContext.REQUEST_SCOPE;
    520         }
    521 
    522         Object bean = pageContext.getAttribute(beanName, scope);
    523 
    524         if (bean == null) {
    525             // New and improved - use the values from the action mapping
    526             bean =
    527                 RequestUtils.createActionForm((HttpServletRequest) pageContext
    528                     .getRequest(), mapping, moduleConfig, servlet);
    529 
    530             if (bean instanceof ActionForm) {
    531                 ((ActionForm) bean).reset(mapping,
    532                     (HttpServletRequest) pageContext.getRequest());
    533             }
    534 
    535             if (bean == null) {
    536                 throw new JspException(messages.getMessage("formTag.create",
    537                         beanType, beanName));
    538             }
    539 
    540             pageContext.setAttribute(beanName, bean, scope);
    541         }
    542 
    543         pageContext.setAttribute(Constants.BEAN_KEY, bean,
    544             PageContext.REQUEST_SCOPE);
    545     }
    546 
    547     /**
    548      * Generates the opening <code>&lt;form&gt;</code> element with
    549      * appropriate attributes.
    550      *
    551      * @since Struts 1.1
    552      */
    553     protected String renderFormStartElement()
    554         throws JspException {
    555         StringBuffer results = new StringBuffer("<form");
    556 
    557         // render attributes
    558         renderName(results);
    559 
    560         renderAttribute(results, "method",
    561             (getMethod() == null) ? "post" : getMethod());
    562         renderAction(results);
    563         renderAttribute(results, "accept-charset", getAcceptCharset());
    564         renderAttribute(results, "class", getStyleClass());
    565         renderAttribute(results, "dir", getDir());
    566         renderAttribute(results, "enctype", getEnctype());
    567         renderAttribute(results, "lang", getLang());
    568         renderAttribute(results, "onreset", getOnreset());
    569         renderAttribute(results, "onsubmit", getOnsubmit());
    570         renderAttribute(results, "style", getStyle());
    571         renderAttribute(results, "target", getTarget());
    572         if (!is.html.md()) {
    573             renderAttribute(results, "autocomplete", getAutocomplete());
    574         }
    575 
    576         // Hook for additional attributes
    577         renderOtherAttributes(results);
    578 
    579         results.append(">");
    580 
    581         return results.toString();
    582     }
    583 
    584     /**
    585      * Renders the name of the form.  If XHTML is set to true, the name will
    586      * be rendered as an 'id' attribute, otherwise as a 'name' attribute.
    587      */
    588     protected void renderName(StringBuffer results)
    589         throws JspException {
    590         if (this.is.html.md()) {
    591             if (getStyleId() == null) {
    592                 renderAttribute(results, "id", beanName);
    593             } else {
    594                 throw new JspException(messages.getMessage("formTag.ignoredId"));
    595             }
    596         } else {
    597             renderAttribute(results, "name", beanName);
    598             renderAttribute(results, "id", getStyleId());
    599         }
    600     }
    601 
    602     /**
    603      * Renders the action attribute
    604      */
    605     protected void renderAction(StringBuffer results) {
    606         String calcAction = (this.action == null ? postbackAction : this.action);
    607         HttpServletResponse response =
    608             (HttpServletResponse) this.pageContext.getResponse();
    609 
    610         results.append(" action=\"");
    611         results.append(response.encodeURL(
    612                 TagUtils.getInstance().getActionMappingURL(calcAction,
    613                     this.pageContext)));
    614 
    615         results.append("\"");
    616     }
    617 
    618     /**
    619      * 'Hook' to enable this tag to be extended and additional attributes
    620      * added.
    621      */
    622     protected void renderOtherAttributes(StringBuffer results) {
    623     }
    624 
    625     /**
    626      * Generates a hidden input field with token information, if any. The
    627      * field is added within a div element for HTML 4.01 Strict compliance.
    628      *
    629      * @return A hidden input field containing the token.
    630      * @since Struts 1.1
    631      */
    632     protected String renderToken() {
    633         StringBuffer results = new StringBuffer();
    634         HttpSession session = pageContext.getSession();
    635 
    636         if (session != null) {
    637             String token =
    638                 (String) session.getAttribute(Globals.TRANSACTION_TOKEN_KEY);
    639 
    640             if (token != null) {
    641                 results.append("<div><input type=\"hidden\" name=\"");
    642                 results.append(Constants.TOKEN_KEY);
    643                 results.append("\" value=\"");
    644                 results.append(token);
    645 
    646                 if (this.is.html.md()) {
    647                     results.append("\" />");
    648                 } else {
    649                     results.append("\">");
    650                 }
    651 
    652                 results.append("</div>");
    653             }
    654         }
    655 
    656         return results.toString();
    657     }
    658 
    659     /**
    660      * Renders attribute="value" if not null
    661      */
    662     protected void renderAttribute(StringBuffer results, String attribute,
    663         String value) {
    664         if (value != null) {
    665             results.append(" ");
    666             results.append(attribute);
    667             results.append("=\"");
    668             results.append(value);
    669             results.append("\"");
    670         }
    671     }
    672 
    673     /**
    674      * Render the end of this form.
    675      *
    676      * @throws JspException if a JSP exception has occurred
    677      */
    678     public int doEndTag() throws JspException {
    679         // Remove the page scope attributes we created
    680         pageContext.removeAttribute(Constants.BEAN_KEY,
    681             PageContext.REQUEST_SCOPE);
    682         pageContext.removeAttribute(Constants.FORM_KEY,
    683             PageContext.REQUEST_SCOPE);
    684 
    685         // Render a tag representing the end of our current form
    686         StringBuffer results = new StringBuffer("</form>");
    687 
    688         // Render JavaScript to set the input focus if required
    689         if (this.focus != null) {
    690             results.append(this.renderFocusJavascript());
    691         }
    692 
    693         // Print this value to our output writer
    694         JspWriter writer = pageContext.getOut();
    695 
    696         try {
    697             writer.print(results.toString());
    698         } catch (IOException e) {
    699             throw new JspException(messages.getMessage("common.io", e.toString()));
    700         }
    701 
    702         postbackAction = null;
    703 
    704         // Continue processing this page
    705         return (EVAL_PAGE);
    706     }
    707 
    708     /**
    709      * Generates javascript to set the initial focus to the form element given
    710      * in the tag's "focus" attribute.
    711      *
    712      * @since Struts 1.1
    713      */
    714     protected String renderFocusJavascript() {
    715         StringBuffer results = new StringBuffer();
    716 
    717         results.append(lineEnd);
    718         results.append("<script type=\"text/javascript\"");
    719 
    720         if (!this.is.html.md() && this.scriptLanguage) {
    721             results.append(" language=\"JavaScript\"");
    722         }
    723 
    724         results.append(">");
    725         results.append(lineEnd);
    726 
    727         // .html.md script content shouldn't use the browser hiding trick
    728         if (!this.is.html.md()) {
    729             results.append("  <!--");
    730             results.append(lineEnd);
    731         }
    732 
    733         // Construct the index if needed and insert into focus statement
    734         String index = "";
    735         if (this.focusIndex != null) {
    736             StringBuffer sb = new StringBuffer("[");
    737             sb.append(this.focusIndex);
    738             sb.append("]");
    739             index = sb.toString();
    740         }
    741         
    742         // Construct the control name that will receive focus.
    743         StringBuffer focusControl = new StringBuffer("document.forms[\"");
    744         focusControl.append(beanName);
    745         focusControl.append("\"].elements[\"");
    746         focusControl.append(this.focus);
    747         focusControl.append("\"]");
    748         focusControl.append(index);
    749 
    750         results.append("  var focusControl = ");
    751         results.append(focusControl.toString());
    752         results.append(";");
    753         results.append(lineEnd);
    754         results.append(lineEnd);
    755 
    756         results.append("  if (focusControl != null && ");
    757         results.append("focusControl.type != \"hidden\" && ");
    758         results.append("!focusControl.disabled && ");
    759         results.append("focusControl.style.display != \"none\") {");
    760         results.append(lineEnd);
    761 
    762         results.append("     focusControl");
    763         results.append(".focus();");
    764         results.append(lineEnd);
    765 
    766         results.append("  }");
    767         results.append(lineEnd);
    768 
    769         if (!this.is.html.md()) {
    770             results.append("  // -->");
    771             results.append(lineEnd);
    772         }
    773 
    774         results.append("</script>");
    775         results.append(lineEnd);
    776 
    777         return results.toString();
    778     }
    779 
    780     /**
    781      * Release any acquired resources.
    782      */
    783     public void release() {
    784         super.release();
    785         action = null;
    786         autocomplete = null;
    787         moduleConfig = null;
    788         enctype = null;
    789         dir = null;
    790         disabled = false;
    791         focus = null;
    792         focusIndex = null;
    793         lang = null;
    794         mapping = null;
    795         method = null;
    796         onreset = null;
    797         onsubmit = null;
    798         readonly = false;
    799         servlet = null;
    800         style = null;
    801         styleClass = null;
    802         styleId = null;
    803         target = null;
    804         acceptCharset = null;
    805     }
    806 
    807     // ------------------------------------------------------ Protected Methods
    808 
    809     /**
    810      * Look up values for the <code>name</code>, <code>scope</code>, and
    811      * <code>type</code> properties if necessary.
    812      *
    813      * @throws JspException if a required value cannot be looked up
    814      */
    815     protected void lookup() throws JspException {
    816 
    817         // Look up the module configuration information we need
    818         moduleConfig = TagUtils.getInstance().getModuleConfig(pageContext);
    819 
    820         if (moduleConfig == null) {
    821             JspException e =
    822                 new JspException(messages.getMessage("formTag.collections"));
    823 
    824             pageContext.setAttribute(Globals.EXCEPTION_KEY, e,
    825                 PageContext.REQUEST_SCOPE);
    826             throw e;
    827         }
    828 
    829         String calcAction = this.action;
    830 
    831         // If the action is not specified, use the original request uri
    832         if (this.action == null) {
    833             HttpServletRequest request =
    834                 (HttpServletRequest) pageContext.getRequest();
    835             postbackAction =
    836                 (String) request.getAttribute(Globals.ORIGINAL_URI_KEY);
    837 
    838             String prefix = moduleConfig.getPrefix();
    839             if (postbackAction != null && prefix.length() > 0 && postbackAction.startsWith(prefix)) {
    840                 postbackAction = postbackAction.substring(prefix.length());
    841             }
    842             calcAction = postbackAction;
    843         } else {
    844             // Translate the action if it is an actionId
    845             ActionConfig actionConfig = moduleConfig.findActionConfigId(this.action);
    846             if (actionConfig != null) {
    847                 this.action = actionConfig.getPath();
    848                 calcAction = this.action;
    849             }
    850         }
    851 
    852         servlet =
    853             (ActionServlet) pageContext.getServletContext().getAttribute(Globals.ACTION_SERVLET_KEY);
    854 
    855         // Look up the action mapping we will be submitting to
    856         String mappingName =
    857             TagUtils.getInstance().getActionMappingName(calcAction);
    858 
    859         mapping = (ActionMapping) moduleConfig.findActionConfig(mappingName);
    860 
    861         if (mapping == null) {
    862             JspException e =
    863                 new JspException(messages.getMessage("formTag.mapping",
    864                         mappingName));
    865 
    866             pageContext.setAttribute(Globals.EXCEPTION_KEY, e,
    867                 PageContext.REQUEST_SCOPE);
    868             throw e;
    869         }
    870 
    871         // Look up the form bean definition
    872         FormBeanConfig formBeanConfig =
    873             moduleConfig.findFormBeanConfig(mapping.getName());
    874 
    875         if (formBeanConfig == null) {
    876             JspException e = null;
    877 
    878             if (mapping.getName() == null) {
    879                 e = new JspException(messages.getMessage("formTag.name", calcAction));
    880             } else {
    881                 e = new JspException(messages.getMessage("formTag.formBean",
    882                             mapping.getName(), calcAction));
    883             }
    884 
    885             pageContext.setAttribute(Globals.EXCEPTION_KEY, e,
    886                 PageContext.REQUEST_SCOPE);
    887             throw e;
    888         }
    889 
    890         // Calculate the required values
    891         beanName = mapping.getAttribute();
    892         beanScope = mapping.getScope();
    893         beanType = formBeanConfig.getType();
    894     }
    895 
    896     /**
    897      * Returns true if this tag should render as .html.md.
    898      */
    899     private boolean is.html.md() {
    900         return TagUtils.getInstance().is.html.md(this.pageContext);
    901     }
    902 
    903     /**
    904      * Returns the focusIndex.
    905      *
    906      * @return String
    907      */
    908     public String getFocusIndex() {
    909         return focusIndex;
    910     }
    911 
    912     /**
    913      * Sets the focusIndex.
    914      *
    915      * @param focusIndex The focusIndex to set
    916      */
    917     public void setFocusIndex(String focusIndex) {
    918         this.focusIndex = focusIndex;
    919     }
    920 
    921     /**
    922      * Gets whether or not the focus script's &lt;script&gt; element will
    923      * include the language attribute.
    924      *
    925      * @return true if language attribute will be included.
    926      * @since Struts 1.2
    927      */
    928     public boolean getScriptLanguage() {
    929         return this.scriptLanguage;
    930     }
    931 
    932     /**
    933      * Sets whether or not the focus script's &lt;script&gt; element will
    934      * include the language attribute.
    935      *
    936      * @since Struts 1.2
    937      */
    938     public void setScriptLanguage(boolean scriptLanguage) {
    939         this.scriptLanguage = scriptLanguage;
    940     }
    941 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
