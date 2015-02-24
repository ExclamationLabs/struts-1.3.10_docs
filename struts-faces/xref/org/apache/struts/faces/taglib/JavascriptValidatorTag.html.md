[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/taglib/JavascriptValidatorTag.html.md)


    1   /*
    2    * $Id: JavascriptValidatorTag.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.taglib;
    23  
    24  import java.io.IOException;
    25  import java.util.ArrayList;
    26  import java.util.Collections;
    27  import java.util.Comparator;
    28  import java.util.Iterator;
    29  import java.util.List;
    30  import java.util.Locale;
    31  import java.util.Map;
    32  
    33  import javax.faces.component.UIComponent;
    34  import javax.faces.context.FacesContext;
    35  import javax.faces.webapp.UIComponentTag;
    36  import javax.servlet.http.HttpServletRequest;
    37  import javax.servlet.jsp.JspException;
    38  import javax.servlet.jsp.JspWriter;
    39  import javax.servlet.jsp.PageContext;
    40  import javax.servlet.jsp.tagext.BodyTagSupport;
    41  import javax.servlet.jsp.tagext.Tag;
    42  import javax.servlet.ServletContext;
    43  
    44  import org.apache.commons.validator.Field;
    45  import org.apache.commons.validator.Form;
    46  import org.apache.commons.validator.ValidatorAction;
    47  import org.apache.commons.validator.ValidatorResources;
    48  import org.apache.commons.validator.Var;
    49  import org.apache.commons.validator.util.ValidatorUtils;
    50  import org.apache.struts.Globals;
    51  import org.apache.struts.config.ModuleConfig;
    52  import org.apache.struts.faces.component.FormComponent;
    53  import org.apache.struts.taglib.TagUtils;
    54  import org.apache.struts.util.MessageResources;
    55  import org.apache.struts.util.ModuleUtils;
    56  import org.apache.struts.validator.Resources;
    57  import org.apache.struts.validator.ValidatorPlugIn;
    58  
    59  /**
    60   * Custom tag that generates JavaScript for client side validation based
    61   * on the validation rules loaded by the <code>ValidatorPlugIn</code>
    62   * defined in the struts-config.xml file.  This is based on the code in
    63   * the corresponding class of the Struts HTML tag library, modified as needed
    64   * to reflect differences in the way JavaServer Faces renders field
    65   * identifiers.
    66   *
    67   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    68   */
    69  public class JavascriptValidatorTag extends BodyTagSupport {
    70  
    71      // ----------------------------------------------------------- Properties
    72  
    73      /**
    74       * The servlet context attribute key for our resources.
    75       */
    76      protected String bundle = Globals.MESSAGES_KEY;
    77  
    78      /**
    79       * The default locale on our server.
    80       * @deprecated This variable is no longer used.
    81       */
    82      protected static Locale defaultLocale = Locale.getDefault();
    83  
    84      /**
    85       * The name of the form that corresponds with the action name
    86       * in struts-config.xml. Specifying a form name places a
    87       * &lt;script&gt; &lt;/script&gt; around the javascript.
    88       */
    89      protected String formName = null;
    90  
    91      /**
    92       * The line ending string.
    93       */
    94      protected static String lineEnd = System.getProperty("line.separator");
    95  
    96      /**
    97       * The current page number of a multi-part form.
    98       * Only valid when the formName attribute is set.
    99       */
    100     protected int page = 0;
    101 
    102     /**
    103      * This will be used as is for the JavaScript validation method name if it
    104      * has a value.  This is the method name of the main JavaScript method that
    105      * the form calls to perform validations.
    106      */
    107     protected String methodName = null;
    108 
    109     /**
    110      * The static JavaScript methods will only be printed if this is set to
    111      * "true".
    112      */
    113     protected String staticJavascript = "true";
    114 
    115     /**
    116      * The dynamic JavaScript objects will only be generated if this is set to
    117      * "true".
    118      */
    119     protected String dynamicJavascript = "true";
    120 
    121     /**
    122      * The src attribute for.html.md script element (used to include an external
    123      * script resource). The src attribute is only recognized
    124      * when the formName attribute is specified.
    125      */
    126     protected String src = null;
    127 
    128     /**
    129      * The JavaScript methods will enclosed with.html.md comments if this is set to
    130      * "true".
    131      */
    132     protected String.html.mdComment = "true";
    133 
    134     /**
    135      * Hide JavaScript methods in a CDATA section for XHTML when "true".
    136      */
    137     protected String cdata = "true";
    138 
    139     private String.html.mdBeginComment = "\n<!-- Begin \n";
    140 
    141     private String.html.mdEndComment = "//End --> \n";
    142 
    143     /**
    144      * Gets the key (form name) that will be used
    145      * to retrieve a set of validation rules to be
    146      * performed on the bean passed in for validation.
    147      */
    148     public String getFormName() {
    149         return formName;
    150     }
    151 
    152     /**
    153      * Sets the key (form name) that will be used
    154      * to retrieve a set of validation rules to be
    155      * performed on the bean passed in for validation.
    156      * Specifying a form name places a
    157      * &lt;script&gt; &lt;/script&gt; tag around the javascript.
    158      */
    159     public void setFormName(String formName) {
    160         this.formName = formName;
    161     }
    162 
    163     /**
    164      * Gets the current page number of a multi-part form.
    165      * Only field validations with a matching page numer
    166      * will be generated that match the current page number.
    167      * Only valid when the formName attribute is set.
    168      */
    169     public int getPage() {
    170         return page;
    171     }
    172 
    173     /**
    174      * Sets the current page number of a multi-part form.
    175      * Only field validations with a matching page numer
    176      * will be generated that match the current page number.
    177      * Only valid when the formName attribute is set.
    178      */
    179     public void setPage(int page) {
    180         this.page = page;
    181     }
    182 
    183     /**
    184      * Gets the method name that will be used for the Javascript
    185      * validation method name if it has a value.  This overrides
    186      * the auto-generated method name based on the key (form name)
    187      * passed in.
    188      */
    189     public String getMethod() {
    190         return methodName;
    191     }
    192 
    193     /**
    194      * Sets the method name that will be used for the Javascript
    195      * validation method name if it has a value.  This overrides
    196      * the auto-generated method name based on the key (form name)
    197      * passed in.
    198      */
    199     public void setMethod(String methodName) {
    200         this.methodName = methodName;
    201     }
    202 
    203     /**
    204      * Gets whether or not to generate the static
    205      * JavaScript.  If this is set to 'true', which
    206      * is the default, the static JavaScript will be generated.
    207      */
    208     public String getStaticJavascript() {
    209         return staticJavascript;
    210     }
    211 
    212     /**
    213      * Sets whether or not to generate the static
    214      * JavaScript.  If this is set to 'true', which
    215      * is the default, the static JavaScript will be generated.
    216      */
    217     public void setStaticJavascript(String staticJavascript) {
    218         this.staticJavascript = staticJavascript;
    219     }
    220 
    221     /**
    222      * Gets whether or not to generate the dynamic
    223      * JavaScript.  If this is set to 'true', which
    224      * is the default, the dynamic JavaScript will be generated.
    225      */
    226     public String getDynamicJavascript() {
    227         return dynamicJavascript;
    228     }
    229 
    230     /**
    231      * Sets whether or not to generate the dynamic
    232      * JavaScript.  If this is set to 'true', which
    233      * is the default, the dynamic JavaScript will be generated.
    234      */
    235     public void setDynamicJavascript(String dynamicJavascript) {
    236         this.dynamicJavascript = dynamicJavascript;
    237     }
    238 
    239     /**
    240       * Gets whether or not to delimit the
    241       * JavaScript with.html.md comments.  If this is set to 'true', which
    242       * is the default, the.html.mdComment will be surround the JavaScript.
    243       */
    244     public String getHtmlComment() {
    245         return.html.mdComment;
    246     }
    247 
    248     /**
    249      * Sets whether or not to delimit the
    250      * JavaScript with.html.md comments.  If this is set to 'true', which
    251      * is the default, the.html.mdComment will be surround the JavaScript.
    252      */
    253     public void setHtmlComment(String.html.mdComment) {
    254         this.html.mdComment = htmlComment;
    255     }
    256 
    257     /**
    258      * Gets the src attribute's value when defining
    259      * the.html.md script element.
    260      */
    261     public String getSrc() {
    262         return src;
    263     }
    264 
    265     /**
    266      * Sets the src attribute's value when defining
    267      * the.html.md script element. The src attribute is only recognized
    268      * when the formName attribute is specified.
    269      */
    270     public void setSrc(String src) {
    271         this.src = src;
    272     }
    273 
    274     /**
    275      * Render the JavaScript for to perform validations based on the form name.
    276      *
    277      * @exception JspException if a JSP exception has occurred
    278      */
    279     public int doStartTag() throws JspException {
    280         StringBuffer results = new StringBuffer();
    281 
    282         HttpServletRequest request =
    283           (HttpServletRequest)pageContext.getRequest();
    284         ServletContext servletContext = pageContext.getServletContext();
    285         ModuleConfig config =
    286           ModuleUtils.getInstance().getModuleConfig(request, servletContext);
    287 
    288         ValidatorResources resources =
    289             (ValidatorResources) pageContext.getAttribute(
    290                 ValidatorPlugIn.VALIDATOR_KEY + config.getPrefix(),
    291                 PageContext.APPLICATION_SCOPE);
    292 
    293         Locale locale = TagUtils.getInstance().getUserLocale(pageContext, null);
    294 
    295         Form form = resources.getForm(locale, formName);
    296         if (form != null) {
    297             if ("true".equalsIgnoreCase(dynamicJavascript)) {
    298                 MessageResources messages =
    299                     (MessageResources) pageContext.getAttribute(
    300                         bundle + config.getPrefix(),
    301                         PageContext.APPLICATION_SCOPE);
    302 
    303                 List lActions = new ArrayList();
    304                 List lActionMethods = new ArrayList();
    305 
    306                 // Get List of actions for this Form
    307                 for (Iterator i = form.getFields().iterator(); i.hasNext();) {
    308                     Field field = (Field) i.next();
    309 
    310                     for (Iterator x = field.getDependencyList().iterator();
    311                         x.hasNext();) {
    312                         Object o = x.next();
    313 
    314                         if (o != null && !lActionMethods.contains(o)) {
    315                             lActionMethods.add(o);
    316                         }
    317                     }
    318 
    319                 }
    320 
    321                 // Create list of ValidatorActions based on lActionMethods
    322                 for (Iterator i = lActionMethods.iterator(); i.hasNext();) {
    323                     String depends = (String) i.next();
    324                     ValidatorAction va = resources.getValidatorAction(depends);
    325 
    326                     // throw nicer NPE for easier debugging
    327                     if (va == null) {
    328                         throw new NullPointerException(
    329                             "Depends string \""
    330                                 + depends
    331                                 + "\" was not found in validator-rules.xml.");
    332                     }
    333 
    334                     String javascript = va.getJavascript();
    335                     if (javascript != null && javascript.length() > 0) {
    336                         lActions.add(va);
    337                     } else {
    338                         i.remove();
    339                     }
    340                 }
    341 
    342                 Collections.sort(lActions, new Comparator() {
    343                     public int compare(Object o1, Object o2) {
    344                         ValidatorAction va1 = (ValidatorAction) o1;
    345                         ValidatorAction va2 = (ValidatorAction) o2;
    346 
    347                         if ((va1.getDepends() == null
    348                             || va1.getDepends().length() == 0)
    349                             && (va2.getDepends() == null
    350                             || va2.getDepends().length() == 0)) {
    351                             return 0;
    352                         } else if (
    353                             (va1.getDepends() != null
    354                             && va1.getDepends().length() > 0)
    355                             && (va2.getDepends() == null
    356                             || va2.getDepends().length() == 0)) {
    357                             return 1;
    358                         } else if (
    359                             (va1.getDepends() == null
    360                             || va1.getDepends().length() == 0)
    361                             && (va2.getDepends() != null
    362                             && va2.getDepends().length() > 0)) {
    363                             return -1;
    364                         } else {
    365                             return va1.getDependencyList().size() -
    366                               va2.getDependencyList().size();
    367                         }
    368                     }
    369                 });
    370 
    371                 String methods = null;
    372                 for (Iterator i = lActions.iterator(); i.hasNext();) {
    373                     ValidatorAction va = (ValidatorAction) i.next();
    374 
    375                     if (methods == null) {
    376                         methods = va.getMethod() + "(form)";
    377                     } else {
    378                         methods += " && " + va.getMethod() + "(form)";
    379                     }
    380                 }
    381 
    382                 results.append(getJavascriptBegin(methods));
    383 
    384                 for (Iterator i = lActions.iterator(); i.hasNext();) {
    385                     ValidatorAction va = (ValidatorAction) i.next();
    386                     String jscriptVar = null;
    387                     String functionName = null;
    388 
    389                     if (va.getJsFunctionName() != null
    390                         && va.getJsFunctionName().length() > 0) {
    391                         functionName = va.getJsFunctionName();
    392                     } else {
    393                         functionName = va.getName();
    394                     }
    395 
    396                     if (isStruts11()) {
    397                         results.append("    function " +
    398                           functionName + " () { \n");
    399                     } else {
    400                         results.append("    function " +
    401                           formName + "_" + functionName +
    402                           " () { \n");
    403                     }
    404                     for (Iterator x = form.getFields().iterator();
    405                         x.hasNext();) {
    406                         Field field = (Field) x.next();
    407 
    408                         // Skip indexed fields for now until there is a good
    409                         // way to handle error messages (and the length of the
    410                         // list (could retrieve from scope?))
    411                         if (field.isIndexed()
    412                             || field.getPage() != page
    413                             || !field.isDependency(va.getName())) {
    414 
    415                             continue;
    416                         }
    417 
    418                         String message =
    419                             Resources.getMessage(messages, locale, va, field);
    420 
    421                         message = (message != null) ? message : "";
    422 
    423                         jscriptVar = this.getNextVar(jscriptVar);
    424 
    425                         results.append(
    426                             "     this."
    427                                 + jscriptVar
    428                                 + " = new Array(\""
    429                                 + getFormClientId()
    430                                 + ":"
    431                                 + field.getKey()
    432                                 + "\", \""
    433                                 + message
    434                                 + "\", ");
    435 
    436                         results.append("new Function (\"varName\", \"");
    437 
    438                         Map vars = field.getVars();
    439                         // Loop through the field's variables.
    440                         Iterator varsIterator = vars.keySet().iterator();
    441                         while (varsIterator.hasNext()) {
    442                             String varName = (String) varsIterator.next();
    443                             Var var = (Var) vars.get(varName);
    444                             String varValue = var.getValue();
    445                             String jsType = var.getJsType();
    446 
    447                             // skip requiredif variables field, fieldIndexed,
    448                             // fieldTest, fieldValue
    449                             if (varName.startsWith("field")) {
    450                                 continue;
    451                             }
    452 
    453                             if (Var.JSTYPE_INT.equalsIgnoreCase(jsType)) {
    454                                 results.append(
    455                                     "this."
    456                                         + varName
    457                                         + "="
    458                                         + ValidatorUtils.replace(
    459                                             varValue,
    460                                             "\\",
    461                                             "\\\\")
    462                                         + "; ");
    463                             } else if (Var.JSTYPE_REGEXP.equalsIgnoreCase(
    464                                 jsType)) {
    465                                 results.append(
    466                                     "this."
    467                                         + varName
    468                                         + "=/"
    469                                         + ValidatorUtils.replace(
    470                                             varValue,
    471                                             "\\",
    472                                             "\\\\")
    473                                         + "/; ");
    474                             } else if (Var.JSTYPE_STRING.equalsIgnoreCase(
    475                                 jsType)) {
    476                                 results.append(
    477                                     "this."
    478                                         + varName
    479                                         + "='"
    480                                         + ValidatorUtils.replace(
    481                                             varValue,
    482                                             "\\",
    483                                             "\\\\")
    484                                         + "'; ");
    485                                 // So everyone using the latest format doesn't
    486                                 // need to change their xml files immediately.
    487                             } else if ("mask".equalsIgnoreCase(varName)) {
    488                                 results.append(
    489                                     "this."
    490                                         + varName
    491                                         + "=/"
    492                                         + ValidatorUtils.replace(
    493                                             varValue,
    494                                             "\\",
    495                                             "\\\\")
    496                                         + "/; ");
    497                             } else {
    498                                 results.append(
    499                                     "this."
    500                                         + varName
    501                                         + "='"
    502                                         + ValidatorUtils.replace(
    503                                             varValue,
    504                                             "\\",
    505                                             "\\\\")
    506                                         + "'; ");
    507                             }
    508                         }
    509 
    510                         results.append(" return this[varName];\"));\n");
    511                     }
    512                     results.append("    } \n\n");
    513                 }
    514             } else if ("true".equalsIgnoreCase(staticJavascript)) {
    515                 results.append(this.getStartElement());
    516                 if ("true".equalsIgnoreCase.html.mdComment)) {
    517                     results.append.html.mdBeginComment);
    518                 }
    519             }
    520         }
    521 
    522         if ("true".equalsIgnoreCase(staticJavascript)) {
    523             results.append(getJavascriptStaticMethods(resources));
    524         }
    525 
    526         if (form != null
    527             && ("true".equalsIgnoreCase(dynamicJavascript)
    528                 || "true".equalsIgnoreCase(staticJavascript))) {
    529 
    530             results.append(getJavascriptEnd());
    531         }
    532 
    533 
    534         JspWriter writer = pageContext.getOut();
    535         try {
    536             writer.print(results.toString());
    537         } catch (IOException e) {
    538             throw new JspException(e.getMessage());
    539         }
    540 
    541         return (EVAL_BODY_TAG);
    542 
    543     }
    544 
    545     /**
    546      * Release any acquired resources.
    547      */
    548     public void release() {
    549         super.release();
    550         bundle = Globals.MESSAGES_KEY;
    551         formName = null;
    552         page = 0;
    553         methodName = null;
    554         staticJavascript = "true";
    555         dynamicJavascript = "true";
    556        .html.mdComment = "true";
    557         cdata = "true";
    558         src = null;
    559         formClientId = null;
    560     }
    561 
    562     /**
    563      * Returns the opening script element and some initial javascript.
    564      */
    565     protected String getJavascriptBegin(String methods) {
    566         StringBuffer sb = new StringBuffer();
    567         String name =
    568             formName.substring(0, 1).toUpperCase()
    569                 + formName.substring(1, formName.length());
    570 
    571         sb.append(this.getStartElement());
    572 
    573         if (this.is.html.md() && "true".equalsIgnoreCase(this.cdata)) {
    574             sb.append("<![CDATA[\r\n");
    575         }
    576 
    577         if (!this.is.html.md() && "true".equals(htmlComment)) {
    578             sb.append.html.mdBeginComment);
    579         }
    580         sb.append("\n     var bCancel = false; \n\n");
    581 
    582         if (methodName == null || methodName.length() == 0) {
    583             sb.append(
    584                 "    function validate"
    585                     + name
    586                     + "(form) {                                          "
    587                     + "                         \n");
    588         } else {
    589             sb.append(
    590                 "    function "
    591                     + methodName
    592                     + "(form) {                                          "
    593                     + "                         \n");
    594         }
    595         sb.append("        if (bCancel) \n");
    596         sb.append("      return true; \n");
    597         sb.append("        else \n");
    598 
    599         // Always return true if there aren't any Javascript validation methods
    600         if (methods == null || methods.length() == 0) {
    601             sb.append("       return true; \n");
    602         } else {
    603             sb.append("       return " + methods + "; \n");
    604         }
    605 
    606         sb.append("   } \n\n");
    607 
    608         return sb.toString();
    609     }
    610 
    611     protected String getJavascriptStaticMethods(ValidatorResources resources) {
    612         StringBuffer sb = new StringBuffer();
    613 
    614         sb.append("\n\n");
    615 
    616         Iterator actions = resources.getValidatorActions().values().iterator();
    617         while (actions.hasNext()) {
    618             ValidatorAction va = (ValidatorAction) actions.next();
    619             if (va != null) {
    620                 String javascript = va.getJavascript();
    621                 if (javascript != null && javascript.length() > 0) {
    622                     sb.append(javascript + "\n");
    623                 }
    624             }
    625         }
    626 
    627         return sb.toString();
    628     }
    629 
    630     /**
    631      * Returns the closing script element.
    632      */
    633     protected String getJavascriptEnd() {
    634         StringBuffer sb = new StringBuffer();
    635 
    636         sb.append("\n");
    637         if (!this.is.html.md() && "true".equals(htmlComment)){
    638             sb.append.html.mdEndComment);
    639         }
    640 
    641         if (this.is.html.md() && "true".equalsIgnoreCase(this.cdata)) {
    642             sb.append("]]>\r\n");
    643         }
    644 
    645         sb.append("</script>\n\n");
    646 
    647         return sb.toString();
    648     }
    649 
    650     /**
    651      * The value <code>null</code> will be returned at the end of the sequence.
    652      * &nbsp;&nbsp;&nbsp; ex: "zz" will return <code>null</code>
    653      */
    654     private String getNextVar(String input) {
    655         if (input == null) {
    656             return "aa";
    657         }
    658 
    659         input = input.toLowerCase();
    660 
    661         for (int i = input.length(); i > 0; i--) {
    662             int pos = i - 1;
    663 
    664             char c = input.charAt(pos);
    665             c++;
    666 
    667             if (c <= 'z') {
    668                 if (i == 0) {
    669                     return c + input.substring(pos, input.length());
    670                 } else if (i == input.length()) {
    671                     return input.substring(0, pos) + c;
    672                 } else {
    673                     return input.substring(0, pos) + c + input.substring(pos,
    674                       input.length() - 1);
    675                 }
    676             } else {
    677                 input = replaceChar(input, pos, 'a');
    678             }
    679 
    680         }
    681 
    682         return null;
    683 
    684     }
    685 
    686     /**
    687      * Replaces a single character in a <code>String</code>
    688      */
    689     private String replaceChar(String input, int pos, char c) {
    690         if (pos == 0) {
    691             return c + input.substring(pos, input.length());
    692         } else if (pos == input.length()) {
    693             return input.substring(0, pos) + c;
    694         } else {
    695             return input.substring(0, pos) + c + input.substring(pos,
    696               input.length() - 1);
    697         }
    698     }
    699 
    700     /**
    701      * Constructs the beginning &lt;script&gt; element depending on
    702      * .html.md status.
    703      */
    704     private String getStartElement() {
    705         StringBuffer start =
    706           new StringBuffer("<script type=\"text/javascript\"");
    707 
    708         // there is no language attribute in .html.md
    709         if (!this.is.html.md()) {
    710             start.append(" language=\"Javascript1.1\"");
    711         }
    712 
    713         if (this.src != null) {
    714             start.append(" src=\"" + src + "\"");
    715         }
    716 
    717         start.append("> \n");
    718         return start.toString();
    719     }
    720 
    721     /**
    722      * Returns true if this is an .html.md page.
    723      */
    724     private boolean is.html.md() {
    725         return TagUtils.getInstance().is.html.md(this.pageContext);
    726     }
    727 
    728     /**
    729      * Returns the cdata setting "true" or "false".
    730      * @return String - "true" if JavaScript will be hidden in a CDATA section
    731      */
    732     public String getCdata() {
    733         return cdata;
    734     }
    735 
    736     /**
    737      * Sets the cdata status.
    738      * @param cdata The cdata to set
    739      */
    740     public void setCdata(String cdata) {
    741         this.cdata = cdata;
    742     }
    743 
    744 
    745     private String formClientId = null;
    746 
    747     /**
    748      * <p>Return the <code>clientId</code> of the form component for which
    749      * we are rendering validation Javascript.</p>
    750      *
    751      * @exception IllegalStateException if we are not nested inside a
    752      *  UIComponentTag with a child FormComponent matching our form name
    753      */
    754     private String getFormClientId(){
    755 
    756         // Return any cached value
    757         if (formClientId != null) {
    758             return (formClientId);
    759         }
    760 
    761         // Locate our parent tag that is a component tag
    762         Tag parent = getParent();
    763         while (parent != null) {
    764             if (parent instanceof UIComponentTag) {
    765                 break;
    766             }
    767             parent = parent.getParent();
    768         }
    769         if (parent == null) {
    770             throw new IllegalArgumentException
    771                 ("Not nested inside a UIComponentTag");
    772         }
    773 
    774         // Are we nested inside our corresponding form tag?
    775         UIComponent parentComponent =
    776             ((UIComponentTag) parent).getComponentInstance();
    777         if (parentComponent instanceof FormComponent) {
    778             if (formName.equals(
    779                 parentComponent.getAttributes().get("beanName"))) {
    780                 formClientId = parentComponent.getClientId
    781                     (FacesContext.getCurrentInstance());
    782                 return (formClientId);
    783             }
    784         }
    785 
    786         // Scan the children of this tag's component
    787         Iterator kids = ((UIComponentTag) parent).
    788             getComponentInstance().getChildren().iterator();
    789         while (kids.hasNext()) {
    790             UIComponent kid = (UIComponent) kids.next();
    791             if (!(kid instanceof FormComponent)) {
    792                 continue;
    793             }
    794             if (formName.equals(kid.getAttributes().get("beanName"))) {
    795                 formClientId =
    796                     kid.getClientId(FacesContext.getCurrentInstance());
    797                 return (formClientId);
    798             }
    799         }
    800         throw new IllegalArgumentException
    801             ("Cannot find child FormComponent for form '" + formName + "'");
    802 
    803     }
    804 
    805 
    806     // ---------------------------------------------------------- Static Methods
    807 
    808 
    809     private static boolean struts11;
    810 
    811     static {
    812         try {
    813             JavascriptValidatorTag.class.getClassLoader().loadClass
    814                 ("org.apache.struts.taglib.TagUtils");
    815             struts11 = false;
    816         } catch (Exception e) {
    817             struts11 = true;
    818         }
    819     }
    820 
    821 
    822     /**
    823      * <p>Return <code>true</code> if we are running on top of Struts 1.1</p>
    824      */
    825     private static boolean isStruts11() {
    826         return struts11;
    827     }
    828 
    829 
    830 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
