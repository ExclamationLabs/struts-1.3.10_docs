[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/JavascriptValidatorTag.html)


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
    21  package org.apache.struts.taglib.html.md;
    22  
    23  import org.apache.commons.validator.Field;
    24  import org.apache.commons.validator.Form;
    25  import org.apache.commons.validator.ValidatorAction;
    26  import org.apache.commons.validator.ValidatorResources;
    27  import org.apache.commons.validator.Var;
    28  import org.apache.struts.Globals;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.config.ModuleConfig;
    31  import org.apache.struts.taglib.TagUtils;
    32  import org.apache.struts.util.MessageResources;
    33  import org.apache.struts.validator.Resources;
    34  import org.apache.struts.validator.ValidatorPlugIn;
    35  
    36  import javax.servlet.ServletContext;
    37  import javax.servlet.http.HttpServletRequest;
    38  import javax.servlet.jsp.JspException;
    39  import javax.servlet.jsp.JspWriter;
    40  import javax.servlet.jsp.PageContext;
    41  import javax.servlet.jsp.tagext.BodyTagSupport;
    42  
    43  import java.io.IOException;
    44  
    45  import java.util.ArrayList;
    46  import java.util.Collections;
    47  import java.util.Comparator;
    48  import java.util.Iterator;
    49  import java.util.List;
    50  import java.util.Locale;
    51  import java.util.Map;
    52  import java.util.StringTokenizer;
    53  
    54  /**
    55   * Custom tag that generates JavaScript for client side validation based on
    56   * the validation rules loaded by the <code>ValidatorPlugIn</code> defined in
    57   * the struts-config.xml file.
    58   *
    59   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    60   * @since Struts 1.1
    61   */
    62  public class JavascriptValidatorTag extends BodyTagSupport {
    63      /**
    64       * A Comparator to use when sorting ValidatorAction objects.
    65       */
    66      private static final Comparator actionComparator =
    67          new Comparator() {
    68              public int compare(Object o1, Object o2) {
    69                  ValidatorAction va1 = (ValidatorAction) o1;
    70                  ValidatorAction va2 = (ValidatorAction) o2;
    71  
    72                  if (((va1.getDepends() == null)
    73                      || (va1.getDepends().length() == 0))
    74                      && ((va2.getDepends() == null)
    75                      || (va2.getDepends().length() == 0))) {
    76                      return 0;
    77                  } else if (((va1.getDepends() != null)
    78                      && (va1.getDepends().length() > 0))
    79                      && ((va2.getDepends() == null)
    80                      || (va2.getDepends().length() == 0))) {
    81                      return 1;
    82                  } else if (((va1.getDepends() == null)
    83                      || (va1.getDepends().length() == 0))
    84                      && ((va2.getDepends() != null)
    85                      && (va2.getDepends().length() > 0))) {
    86                      return -1;
    87                  } else {
    88                      return va1.getDependencyList().size()
    89                      - va2.getDependencyList().size();
    90                  }
    91              }
    92          };
    93  
    94      /**
    95       * The start of the HTML comment hiding JavaScript from old browsers.
    96       *
    97       * @since Struts 1.2
    98       */
    99      protected static final String HTML_BEGIN_COMMENT = "\n<!-- Begin \n";
    100 
    101     /**
    102      * The end of the HTML comment hiding JavaScript from old browsers.
    103      *
    104      * @since Struts 1.2
    105      */
    106     protected static final String HTML_END_COMMENT = "//End --> \n";
    107 
    108     /**
    109      * The line ending string.
    110      */
    111     protected static String lineEnd = System.getProperty("line.separator");
    112 
    113     // ----------------------------------------------------------- Properties
    114 
    115     /**
    116      * The servlet context attribute key for our resources.
    117      */
    118     protected String bundle = Globals.MESSAGES_KEY;
    119 
    120     /**
    121      * The name of the form that corresponds with the action name in
    122      * struts-config.xml. Specifying a form name places a &lt;script&gt;
    123      * &lt;/script&gt; around the javascript.
    124      */
    125     protected String formName = null;
    126 
    127     /**
    128      * formName is used for both Javascript and non-javascript validations.
    129      * For the javascript validations, there is the possibility that we will
    130      * be rewriting the formName (if it is a ValidatorActionForm instead of
    131      * just a ValidatorForm) so we need another variable to hold the formName
    132      * just for javascript usage.
    133      */
    134     protected String jsFormName = null;
    135 
    136     /**
    137      * The current page number of a multi-part form. Only valid when the
    138      * formName attribute is set.
    139      */
    140     protected int page = 0;
    141 
    142     /**
    143      * This will be used as is for the JavaScript validation method name if it
    144      * has a value.  This is the method name of the main JavaScript method
    145      * that the form calls to perform validations.
    146      */
    147     protected String methodName = null;
    148 
    149     /**
    150      * Include language attribute in the &lt;script&gt; element.  This
    151      * property is ignored in XHTML mode.
    152      *
    153      * @since Struts 1.2
    154      */
    155     protected boolean scriptLanguage = true;
    156 
    157     /**
    158      * The static JavaScript methods will only be printed if this is set to
    159      * "true".
    160      */
    161     protected String staticJavascript = "true";
    162 
    163     /**
    164      * The dynamic JavaScript objects will only be generated if this is set to
    165      * "true".
    166      */
    167     protected String dynamicJavascript = "true";
    168 
    169     /**
    170      * The src attribute for.html.md script element (used to include an external
    171      * script resource). The src attribute is only recognized when the
    172      * formName attribute is specified.
    173      */
    174     protected String src = null;
    175 
    176     /**
    177      * The JavaScript methods will enclosed with.html.md comments if this is set
    178      * to "true".
    179      */
    180     protected String.html.mdComment = "true";
    181 
    182     /**
    183      * Hide JavaScript methods in a CDATA section for XHTML when "true".
    184      */
    185     protected String cdata = "true";
    186 
    187     /**
    188      * Gets the key (form name) that will be used to retrieve a set of
    189      * validation rules to be performed on the bean passed in for validation.
    190      */
    191     public String getFormName() {
    192         return formName;
    193     }
    194 
    195     /**
    196      * Sets the key (form name) that will be used to retrieve a set of
    197      * validation rules to be performed on the bean passed in for validation.
    198      * Specifying a form name places a &lt;script&gt; &lt;/script&gt; tag
    199      * around the javascript.
    200      */
    201     public void setFormName(String formName) {
    202         this.formName = formName;
    203     }
    204 
    205     /**
    206      * @return Returns the jsFormName.
    207      */
    208     public String getJsFormName() {
    209         return jsFormName;
    210     }
    211 
    212     /**
    213      * @param jsFormName The jsFormName to set.
    214      */
    215     public void setJsFormName(String jsFormName) {
    216         this.jsFormName = jsFormName;
    217     }
    218 
    219     /**
    220      * Gets the current page number of a multi-part form. Only field
    221      * validations with a matching page numer will be generated that match the
    222      * current page number. Only valid when the formName attribute is set.
    223      */
    224     public int getPage() {
    225         return page;
    226     }
    227 
    228     /**
    229      * Sets the current page number of a multi-part form. Only field
    230      * validations with a matching page numer will be generated that match the
    231      * current page number. Only valid when the formName attribute is set.
    232      */
    233     public void setPage(int page) {
    234         this.page = page;
    235     }
    236 
    237     /**
    238      * Gets the method name that will be used for the Javascript validation
    239      * method name if it has a value.  This overrides the auto-generated
    240      * method name based on the key (form name) passed in.
    241      */
    242     public String getMethod() {
    243         return methodName;
    244     }
    245 
    246     /**
    247      * Sets the method name that will be used for the Javascript validation
    248      * method name if it has a value.  This overrides the auto-generated
    249      * method name based on the key (form name) passed in.
    250      */
    251     public void setMethod(String methodName) {
    252         this.methodName = methodName;
    253     }
    254 
    255     /**
    256      * Gets whether or not to generate the static JavaScript.  If this is set
    257      * to 'true', which is the default, the static JavaScript will be
    258      * generated.
    259      */
    260     public String getStaticJavascript() {
    261         return staticJavascript;
    262     }
    263 
    264     /**
    265      * Sets whether or not to generate the static JavaScript.  If this is set
    266      * to 'true', which is the default, the static JavaScript will be
    267      * generated.
    268      */
    269     public void setStaticJavascript(String staticJavascript) {
    270         this.staticJavascript = staticJavascript;
    271     }
    272 
    273     /**
    274      * Gets whether or not to generate the dynamic JavaScript.  If this is set
    275      * to 'true', which is the default, the dynamic JavaScript will be
    276      * generated.
    277      */
    278     public String getDynamicJavascript() {
    279         return dynamicJavascript;
    280     }
    281 
    282     /**
    283      * Sets whether or not to generate the dynamic JavaScript.  If this is set
    284      * to 'true', which is the default, the dynamic JavaScript will be
    285      * generated.
    286      */
    287     public void setDynamicJavascript(String dynamicJavascript) {
    288         this.dynamicJavascript = dynamicJavascript;
    289     }
    290 
    291     /**
    292      * Gets whether or not to delimit the JavaScript with.html.md comments.  If
    293      * this is set to 'true', which is the default, the.html.mdComment will be
    294      * surround the JavaScript.
    295      */
    296     public String getHtmlComment() {
    297         return.html.mdComment;
    298     }
    299 
    300     /**
    301      * Sets whether or not to delimit the JavaScript with.html.md comments.  If
    302      * this is set to 'true', which is the default, the.html.mdComment will be
    303      * surround the JavaScript.
    304      */
    305     public void setHtmlComment(String.html.mdComment) {
    306         this.html.mdComment = htmlComment;
    307     }
    308 
    309     /**
    310      * Gets the src attribute's value when defining the.html.md script element.
    311      */
    312     public String getSrc() {
    313         return src;
    314     }
    315 
    316     /**
    317      * Sets the src attribute's value when defining the.html.md script element.
    318      * The src attribute is only recognized when the formName attribute is
    319      * specified.
    320      */
    321     public void setSrc(String src) {
    322         this.src = src;
    323     }
    324 
    325     /**
    326      * Sets the servlet context attribute key for our resources.
    327      */
    328     public String getBundle() {
    329         return bundle;
    330     }
    331 
    332     /**
    333      * Gets the servlet context attribute key for our resources.
    334      */
    335     public void setBundle(String bundle) {
    336         this.bundle = bundle;
    337     }
    338 
    339     /**
    340      * Render the JavaScript for to perform validations based on the form
    341      * name.
    342      *
    343      * @throws JspException if a JSP exception has occurred
    344      */
    345     public int doStartTag() throws JspException {
    346         JspWriter writer = pageContext.getOut();
    347 
    348         try {
    349             writer.print(this.renderJavascript());
    350         } catch (IOException e) {
    351             throw new JspException(e.getMessage());
    352         }
    353 
    354         return EVAL_BODY_TAG;
    355     }
    356 
    357     /**
    358      * Returns fully rendered JavaScript.
    359      *
    360      * @since Struts 1.2
    361      */
    362     protected String renderJavascript()
    363         throws JspException {
    364         StringBuffer results = new StringBuffer();
    365 
    366         ModuleConfig config =
    367             TagUtils.getInstance().getModuleConfig(pageContext);
    368         ValidatorResources resources =
    369             (ValidatorResources) pageContext.getAttribute(
    370               ValidatorPlugIn.VALIDATOR_KEY
    371                 + config.getPrefix(), PageContext.APPLICATION_SCOPE);
    372 
    373         if (resources == null) {
    374             throw new JspException(
    375                 "ValidatorResources not found in application scope under key \""
    376                 + ValidatorPlugIn.VALIDATOR_KEY + config.getPrefix() + "\"");
    377         }
    378 
    379         Locale locale =
    380             TagUtils.getInstance().getUserLocale(this.pageContext, null);
    381 
    382         Form form = null;
    383         if ("true".equalsIgnoreCase(dynamicJavascript)) {
    384             form = resources.getForm(locale, formName);
    385             if (form == null) {
    386                 throw new JspException("No form found under '" + formName
    387                     + "' in locale '" + locale
    388                     + "'.  A form must be defined in the "
    389                     + "Commons Validator configuration when "
    390                     + "dynamicJavascript=\"true\" is set.");
    391             }
    392         }
    393 
    394         if (form != null) {
    395             if ("true".equalsIgnoreCase(dynamicJavascript)) {
    396                 results.append(this.createDynamicJavascript(config, resources,
    397                         locale, form));
    398             } else if ("true".equalsIgnoreCase(staticJavascript)) {
    399                 results.append(this.renderStartElement());
    400 
    401                 if ("true".equalsIgnoreCase.html.mdComment)) {
    402                     results.append(HTML_BEGIN_COMMENT);
    403                 }
    404             }
    405         }
    406 
    407         if ("true".equalsIgnoreCase(staticJavascript)) {
    408             results.append(getJavascriptStaticMethods(resources));
    409         }
    410 
    411         if ((form != null)
    412             && ("true".equalsIgnoreCase(dynamicJavascript)
    413             || "true".equalsIgnoreCase(staticJavascript))) {
    414             results.append(getJavascriptEnd());
    415         }
    416 
    417         return results.toString();
    418     }
    419 
    420     /**
    421      * Generates the dynamic JavaScript for the form.
    422      *
    423      * @param config
    424      * @param resources
    425      * @param locale
    426      * @param form
    427      */
    428     private String createDynamicJavascript(ModuleConfig config,
    429         ValidatorResources resources, Locale locale, Form form)
    430         throws JspException {
    431         StringBuffer results = new StringBuffer();
    432 
    433         MessageResources messages =
    434             TagUtils.getInstance().retrieveMessageResources(pageContext,
    435                 bundle, true);
    436 
    437         HttpServletRequest request =
    438             (HttpServletRequest) pageContext.getRequest();
    439         ServletContext application = pageContext.getServletContext();
    440 
    441         List actions = this.createActionList(resources, form);
    442 
    443         final String methods =
    444             this.createMethods(actions, this.stopOnError(config));
    445 
    446         String formName = form.getName();
    447 
    448         jsFormName = formName;
    449 
    450         if (jsFormName.charAt(0) == '/') {
    451             String mappingName =
    452                 TagUtils.getInstance().getActionMappingName(jsFormName);
    453             ActionMapping mapping =
    454                 (ActionMapping) config.findActionConfig(mappingName);
    455 
    456             if (mapping == null) {
    457                 JspException e =
    458                     new JspException(messages.getMessage("formTag.mapping",
    459                             mappingName));
    460 
    461                 pageContext.setAttribute(Globals.EXCEPTION_KEY, e,
    462                     PageContext.REQUEST_SCOPE);
    463                 throw e;
    464             }
    465 
    466             jsFormName = mapping.getAttribute();
    467         }
    468 
    469         results.append(this.getJavascriptBegin(methods));
    470 
    471         for (Iterator i = actions.iterator(); i.hasNext();) {
    472             ValidatorAction va = (ValidatorAction) i.next();
    473             int jscriptVar = 0;
    474             String functionName = null;
    475 
    476             if ((va.getJsFunctionName() != null)
    477                 && (va.getJsFunctionName().length() > 0)) {
    478                 functionName = va.getJsFunctionName();
    479             } else {
    480                 functionName = va.getName();
    481             }
    482 
    483             results.append("    function " + jsFormName + "_" + functionName
    484                 + " () { \n");
    485 
    486             for (Iterator x = form.getFields().iterator(); x.hasNext();) {
    487                 Field field = (Field) x.next();
    488 
    489                 // Skip indexed fields for now until there is a good way to
    490                 // handle error messages (and the length of the list (could
    491                 // retrieve from scope?))
    492                 if (field.isIndexed() || (field.getPage() != page)
    493                     || !field.isDependency(va.getName())) {
    494                     continue;
    495                 }
    496 
    497                 String message =
    498                     Resources.getMessage(application, request, messages,
    499                         locale, va, field);
    500 
    501                 message = (message != null) ? message : "";
    502 
    503                 // prefix variable with 'a' to make it a legal identifier
    504                 results.append("     this.a" + jscriptVar++ + " = new Array(\""
    505                     + field.getKey() + "\", \"" + escapeQuotes(message)
    506                     + "\", ");
    507 
    508                 results.append("new Function (\"varName\", \"");
    509 
    510                 Map vars = field.getVars();
    511 
    512                 // Loop through the field's variables.
    513                 Iterator varsIterator = vars.keySet().iterator();
    514 
    515                 while (varsIterator.hasNext()) {
    516                     String varName = (String) varsIterator.next();
    517                     Var var = (Var) vars.get(varName);
    518                     String varValue =
    519                         Resources.getVarValue(var, application, request, false);
    520                     String jsType = var.getJsType();
    521 
    522                     // skip requiredif variables field, fieldIndexed, fieldTest,
    523                     // fieldValue
    524                     if (varName.startsWith("field")) {
    525                         continue;
    526                     }
    527 
    528                     String varValueEscaped = escapeJavascript(varValue);
    529 
    530                     if (Var.JSTYPE_INT.equalsIgnoreCase(jsType)) {
    531                         results.append("this." + varName + "="
    532                             + varValueEscaped + "; ");
    533                     } else if (Var.JSTYPE_REGEXP.equalsIgnoreCase(jsType)) {
    534                         results.append("this." + varName + "=/"
    535                             + varValueEscaped + "/; ");
    536                     } else if (Var.JSTYPE_STRING.equalsIgnoreCase(jsType)) {
    537                         results.append("this." + varName + "='"
    538                             + varValueEscaped + "'; ");
    539 
    540                         // So everyone using the latest format doesn't need to
    541                         // change their xml files immediately.
    542                     } else if ("mask".equalsIgnoreCase(varName)) {
    543                         results.append("this." + varName + "=/"
    544                             + varValueEscaped + "/; ");
    545                     } else {
    546                         results.append("this." + varName + "='"
    547                             + varValueEscaped + "'; ");
    548                     }
    549                 }
    550 
    551                 results.append(" return this[varName];\"));\n");
    552             }
    553 
    554             results.append("    } \n\n");
    555         }
    556 
    557         return results.toString();
    558     }
    559 
    560     private String escapeQuotes(String in) {
    561         if ((in == null) || (in.indexOf("\"") == -1)) {
    562             return in;
    563         }
    564 
    565         StringBuffer buffer = new StringBuffer();
    566         StringTokenizer tokenizer = new StringTokenizer(in, "\"", true);
    567 
    568         while (tokenizer.hasMoreTokens()) {
    569             String token = tokenizer.nextToken();
    570 
    571             if (token.equals("\"")) {
    572                 buffer.append("\\");
    573             }
    574 
    575             buffer.append(token);
    576         }
    577 
    578         return buffer.toString();
    579     }
    580 
    581     /**
    582      * <p>Backslash-escapes the following characters from the input string:
    583      * &quot;, &apos;, \, \r, \n.</p>
    584      *
    585      * <p>This method escapes characters that will result in an invalid
    586      * Javascript statement within the validator Javascript.</p>
    587      *
    588      * @param str The string to escape.
    589      * @return The string <code>s</code> with each instance of a double quote,
    590      *         single quote, backslash, carriage-return, or line feed escaped
    591      *         with a leading backslash.
    592      */
    593     private String escapeJavascript(String str) {
    594         if (str == null) {
    595             return null;
    596         }
    597 
    598         int length = str.length();
    599 
    600         if (length == 0) {
    601             return str;
    602         }
    603 
    604         // guess at how many chars we'll be adding...
    605         StringBuffer out = new StringBuffer(length + 4);
    606 
    607         // run through the string escaping sensitive chars
    608         for (int i = 0; i < length; i++) {
    609             char c = str.charAt(i);
    610 
    611             if ((c == '"') || (c == '\'') || (c == '\\') || (c == '\n')
    612                 || (c == '\r')) {
    613                 out.append('\\');
    614             }
    615 
    616             out.append(c);
    617         }
    618 
    619         return out.toString();
    620     }
    621 
    622     /**
    623      * Determines if validations should stop on an error.
    624      *
    625      * @param config The <code>ModuleConfig</code> used to lookup the
    626      *               stopOnError setting.
    627      * @return <code>true</code> if validations should stop on errors.
    628      */
    629     private boolean stopOnError(ModuleConfig config) {
    630         Object stopOnErrorObj =
    631             pageContext.getAttribute(ValidatorPlugIn.STOP_ON_ERROR_KEY + '.'
    632                 + config.getPrefix(), PageContext.APPLICATION_SCOPE);
    633 
    634         boolean stopOnError = true;
    635 
    636         if (stopOnErrorObj instanceof Boolean) {
    637             stopOnError = ((Boolean) stopOnErrorObj).booleanValue();
    638         }
    639 
    640         return stopOnError;
    641     }
    642 
    643     /**
    644      * Creates the JavaScript methods list from the given actions.
    645      *
    646      * @param actions     A List of ValidatorAction objects.
    647      * @param stopOnError If true, behaves like released version of struts 1.1
    648      *                    and stops after first error. If false, evaluates all
    649      *                    validations.
    650      * @return JavaScript methods.
    651      */
    652     private String createMethods(List actions, boolean stopOnError) {
    653         StringBuffer methods = new StringBuffer();
    654         final String methodOperator = stopOnError ? " && " : " & ";
    655 
    656         Iterator iter = actions.iterator();
    657 
    658         while (iter.hasNext()) {
    659             ValidatorAction va = (ValidatorAction) iter.next();
    660 
    661             if (methods.length() > 0) {
    662                 methods.append(methodOperator);
    663             }
    664 
    665             methods.append(va.getMethod()).append("(form)");
    666         }
    667 
    668         return methods.toString();
    669     }
    670 
    671     /**
    672      * Get List of actions for the given Form.
    673      *
    674      * @param resources
    675      * @param form
    676      * @return A sorted List of ValidatorAction objects.
    677      */
    678     private List createActionList(ValidatorResources resources, Form form) {
    679         List actionMethods = new ArrayList();
    680 
    681         Iterator iterator = form.getFields().iterator();
    682 
    683         while (iterator.hasNext()) {
    684             Field field = (Field) iterator.next();
    685 
    686             for (Iterator x = field.getDependencyList().iterator();
    687                 x.hasNext();) {
    688                 Object o = x.next();
    689 
    690                 if ((o != null) && !actionMethods.contains(o)) {
    691                     actionMethods.add(o);
    692                 }
    693             }
    694         }
    695 
    696         List actions = new ArrayList();
    697 
    698         // Create list of ValidatorActions based on actionMethods
    699         iterator = actionMethods.iterator();
    700 
    701         while (iterator.hasNext()) {
    702             String depends = (String) iterator.next();
    703             ValidatorAction va = resources.getValidatorAction(depends);
    704 
    705             // throw nicer NPE for easier debugging
    706             if (va == null) {
    707                 throw new NullPointerException("Depends string \"" + depends
    708                     + "\" was not found in validator-rules.xml.");
    709             }
    710 
    711             if ((va.getJavascript() != null)
    712                 && (va.getJavascript().length() > 0)) {
    713                 actions.add(va);
    714             } else {
    715                 iterator.remove();
    716             }
    717         }
    718 
    719         Collections.sort(actions, actionComparator);
    720 
    721         return actions;
    722     }
    723 
    724     /**
    725      * Release any acquired resources.
    726      */
    727     public void release() {
    728         super.release();
    729         bundle = Globals.MESSAGES_KEY;
    730         formName = null;
    731         jsFormName = null;
    732         page = 0;
    733         methodName = null;
    734         staticJavascript = "true";
    735         dynamicJavascript = "true";
    736        .html.mdComment = "true";
    737         cdata = "true";
    738         src = null;
    739     }
    740 
    741     /**
    742      * Returns the opening script element and some initial javascript.
    743      */
    744     protected String getJavascriptBegin(String methods) {
    745         StringBuffer sb = new StringBuffer();
    746         String name = jsFormName.replace('/', '_'); // remove any '/' characters
    747 
    748         name =
    749             jsFormName.substring(0, 1).toUpperCase()
    750             + jsFormName.substring(1, jsFormName.length());
    751 
    752         sb.append(this.renderStartElement());
    753 
    754         if (this.is.html.md() && "true".equalsIgnoreCase(this.cdata)) {
    755             sb.append("//<![CDATA[\r\n");
    756         }
    757 
    758         if (!this.is.html.md() && "true".equals(htmlComment)) {
    759             sb.append(HTML_BEGIN_COMMENT);
    760         }
    761 
    762         sb.append("\n    var bCancel = false; \n\n");
    763 
    764         if ((methodName == null) || (methodName.length() == 0)) {
    765             sb.append("    function validate" + name + "(form) { \n");
    766         } else {
    767             sb.append("    function " + methodName + "(form) { \n");
    768         }
    769 
    770         sb.append("        if (bCancel) { \n");
    771         sb.append("            return true; \n");
    772         sb.append("        } else { \n");
    773 
    774         // Always return true if there aren't any Javascript validation methods
    775         if ((methods == null) || (methods.length() == 0)) {
    776             sb.append("            return true; \n");
    777         } else {
    778             sb.append("            var formValidationResult; \n");
    779             sb.append("            formValidationResult = " + methods + "; \n");
    780             if (methods.indexOf("&&") >= 0) {
    781                 sb.append("            return (formValidationResult); \n");
    782             } else {
    783                 //Making Sure that Bitwise operator works:
    784                 sb.append("            return (formValidationResult == 1); \n");
    785             }
    786         }
    787         sb.append("        } \n");
    788         sb.append("    } \n\n");
    789 
    790         return sb.toString();
    791     }
    792 
    793     protected String getJavascriptStaticMethods(ValidatorResources resources) {
    794         StringBuffer sb = new StringBuffer();
    795 
    796         sb.append("\n\n");
    797 
    798         Iterator actions = resources.getValidatorActions().values().iterator();
    799 
    800         while (actions.hasNext()) {
    801             ValidatorAction va = (ValidatorAction) actions.next();
    802 
    803             if (va != null) {
    804                 String javascript = va.getJavascript();
    805 
    806                 if ((javascript != null) && (javascript.length() > 0)) {
    807                     sb.append(javascript + "\n");
    808                 }
    809             }
    810         }
    811 
    812         return sb.toString();
    813     }
    814 
    815     /**
    816      * Returns the closing script element.
    817      */
    818     protected String getJavascriptEnd() {
    819         StringBuffer sb = new StringBuffer();
    820 
    821         sb.append("\n");
    822 
    823         if (!this.is.html.md() && "true".equals(htmlComment)) {
    824             sb.append(HTML_END_COMMENT);
    825         }
    826 
    827         if (this.is.html.md() && "true".equalsIgnoreCase(this.cdata)) {
    828             sb.append("//]]>\r\n");
    829         }
    830 
    831         sb.append("</script>\n\n");
    832 
    833         return sb.toString();
    834     }
    835 
    836     /**
    837      * Constructs the beginning &lt;script&gt; element depending on XHTML
    838      * status.
    839      *
    840      * @since Struts 1.2
    841      */
    842     protected String renderStartElement() {
    843         StringBuffer start =
    844             new StringBuffer("<script type=\"text/javascript\"");
    845 
    846         // there is no language attribute in XHTML
    847         if (!this.is.html.md() && this.scriptLanguage) {
    848             start.append(" language=\"Javascript1.1\"");
    849         }
    850 
    851         if (this.src != null) {
    852             start.append(" src=\"" + src + "\"");
    853         }
    854 
    855         start.append("> \n");
    856 
    857         return start.toString();
    858     }
    859 
    860     /**
    861      * Returns true if this is an .html.md page.
    862      */
    863     private boolean is.html.md() {
    864         return TagUtils.getInstance().is.html.md(this.pageContext);
    865     }
    866 
    867     /**
    868      * Returns the cdata setting "true" or "false".
    869      *
    870      * @return String - "true" if JavaScript will be hidden in a CDATA
    871      *         section
    872      */
    873     public String getCdata() {
    874         return cdata;
    875     }
    876 
    877     /**
    878      * Sets the cdata status.
    879      *
    880      * @param cdata The cdata to set
    881      */
    882     public void setCdata(String cdata) {
    883         this.cdata = cdata;
    884     }
    885 
    886     /**
    887      * Gets whether or not the &lt;script&gt; element will include the
    888      * language attribute.
    889      *
    890      * @return true if language attribute will be included.
    891      * @since Struts 1.2
    892      */
    893     public boolean getScriptLanguage() {
    894         return this.scriptLanguage;
    895     }
    896 
    897     /**
    898      * Sets whether or not the &lt;script&gt; element will include the
    899      * language attribute.
    900      *
    901      * @since Struts 1.2
    902      */
    903     public void setScriptLanguage(boolean scriptLanguage) {
    904         this.scriptLanguage = scriptLanguage;
    905     }
    906 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
