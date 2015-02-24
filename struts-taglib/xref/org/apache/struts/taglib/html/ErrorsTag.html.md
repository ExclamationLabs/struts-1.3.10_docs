[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/ErrorsTag.html)


    1   /*
    2    * $Id: ErrorsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import org.apache.struts.action.ActionMessage;
    25  import org.apache.struts.action.ActionMessages;
    26  import org.apache.struts.taglib.TagUtils;
    27  import org.apache.struts.util.MessageResources;
    28  
    29  import javax.servlet.jsp.JspException;
    30  import javax.servlet.jsp.tagext.TagSupport;
    31  
    32  import java.util.Iterator;
    33  
    34  /**
    35   * Custom tag that renders error messages if an appropriate request attribute
    36   * has been created.  The tag looks for a request attribute with a reserved
    37   * key, and assumes that it is either a String, a String array, containing
    38   * message keys to be looked up in the module's MessageResources, or an object
    39   * of type <code>org.apache.struts.action.ActionErrors</code>. <p> The
    40   * following optional message keys will be utilized if corresponding messages
    41   * exist for them in the application resources:
    42   *
    43   * <ul>
    44   *
    45   * <li><b>errors.header</b> - If present, the corresponding message will be
    46   * rendered prior to the individual list of error messages.</li>
    47   *
    48   * <li><b>errors.footer</b> - If present, the corresponding message will be
    49   * rendered following the individual list of error messages.</li>
    50   *
    51   * <li><b>errors.prefix</b> - If present, the corresponding message will be
    52   * rendered before each individual error message.</li>
    53   *
    54   * <li><b>errors.suffix</b> - If present, the corresponding message will be
    55   * rendered after each individual error message.</li>
    56   *
    57   * </ul>
    58   *
    59   * @version $Rev: 471754 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005)
    60   *          $
    61   */
    62  public class ErrorsTag extends TagSupport {
    63      /**
    64       * The message resources for this package.
    65       */
    66      protected static MessageResources messages =
    67          MessageResources.getMessageResources(Constants.Package
    68              + ".LocalStrings");
    69  
    70      // ----------------------------------------------------------- Properties
    71  
    72      /**
    73       * The servlet context attribute key for our resources.
    74       */
    75      protected String bundle = null;
    76  
    77      /**
    78       * The session attribute key for our locale.
    79       */
    80      protected String locale = Globals.LOCALE_KEY;
    81  
    82      /**
    83       * The request attribute key for our error messages (if any).
    84       */
    85      protected String name = Globals.ERROR_KEY;
    86  
    87      /**
    88       * The name of the property for which error messages should be returned,
    89       * or <code>null</code> to return all errors.
    90       */
    91      protected String property = null;
    92  
    93      /**
    94       * The message resource key for errors header.
    95       */
    96      protected String header = null;
    97  
    98      /**
    99       * The message resource key for errors footer.
    100      */
    101     protected String footer = null;
    102 
    103     /**
    104      * The message resource key for errors prefix.
    105      */
    106     protected String prefix = null;
    107 
    108     /**
    109      * The message resource key for errors suffix.
    110      */
    111     protected String suffix = null;
    112 
    113     public String getBundle() {
    114         return (this.bundle);
    115     }
    116 
    117     public void setBundle(String bundle) {
    118         this.bundle = bundle;
    119     }
    120 
    121     public String getLocale() {
    122         return (this.locale);
    123     }
    124 
    125     public void setLocale(String locale) {
    126         this.locale = locale;
    127     }
    128 
    129     public String getName() {
    130         return (this.name);
    131     }
    132 
    133     public void setName(String name) {
    134         this.name = name;
    135     }
    136 
    137     public String getProperty() {
    138         return (this.property);
    139     }
    140 
    141     public void setProperty(String property) {
    142         this.property = property;
    143     }
    144 
    145     public String getHeader() {
    146         return (header == null) ? "errors.header" : header;
    147     }
    148 
    149     public void setHeader(String header) {
    150         this.header = header;
    151     }
    152 
    153     public String getFooter() {
    154         return (footer == null) ? "errors.footer" : footer;
    155     }
    156 
    157     public void setFooter(String footer) {
    158         this.footer = footer;
    159     }
    160 
    161     public String getPrefix() {
    162         return (prefix == null) ? "errors.prefix" : prefix;
    163     }
    164 
    165     public void setPrefix(String prefix) {
    166         this.prefix = prefix;
    167     }
    168 
    169     public String getSuffix() {
    170         return (suffix == null) ? "errors.suffix" : suffix;
    171     }
    172 
    173     public void setSuffix(String suffix) {
    174         this.suffix = suffix;
    175     }
    176 
    177     // ------------------------------------------------------- Public Methods
    178 
    179     /**
    180      * Render the specified error messages if there are any.
    181      *
    182      * @throws JspException if a JSP exception has occurred
    183      */
    184     public int doStartTag() throws JspException {
    185         // Were any error messages specified?
    186         ActionMessages errors = null;
    187 
    188         try {
    189             errors =
    190                 TagUtils.getInstance().getActionMessages(pageContext, name);
    191         } catch (JspException e) {
    192             TagUtils.getInstance().saveException(pageContext, e);
    193             throw e;
    194         }
    195 
    196         if ((errors == null) || errors.isEmpty()) {
    197             return (EVAL_BODY_INCLUDE);
    198         }
    199 
    200         boolean headerPresent =
    201             TagUtils.getInstance().present(pageContext, bundle, locale,
    202                 getHeader());
    203 
    204         boolean footerPresent =
    205             TagUtils.getInstance().present(pageContext, bundle, locale,
    206                 getFooter());
    207 
    208         boolean prefixPresent =
    209             TagUtils.getInstance().present(pageContext, bundle, locale,
    210                 getPrefix());
    211 
    212         boolean suffixPresent =
    213             TagUtils.getInstance().present(pageContext, bundle, locale,
    214                 getSuffix());
    215 
    216         // Render the error messages appropriately
    217         StringBuffer results = new StringBuffer();
    218         boolean headerDone = false;
    219         String message = null;
    220         Iterator reports =
    221             (property == null) ? errors.get() : errors.get(property);
    222 
    223         while (reports.hasNext()) {
    224             ActionMessage report = (ActionMessage) reports.next();
    225 
    226             if (!headerDone) {
    227                 if (headerPresent) {
    228                     message =
    229                         TagUtils.getInstance().message(pageContext, bundle,
    230                             locale, getHeader());
    231 
    232                     results.append(message);
    233                 }
    234 
    235                 headerDone = true;
    236             }
    237 
    238             if (prefixPresent) {
    239                 message =
    240                     TagUtils.getInstance().message(pageContext, bundle, locale,
    241                         getPrefix());
    242                 results.append(message);
    243             }
    244 
    245             if (report.isResource()) {
    246                 message =
    247                     TagUtils.getInstance().message(pageContext, bundle, locale,
    248                         report.getKey(), report.getValues());
    249             } else {
    250                 message = report.getKey();
    251             }
    252 
    253             if (message != null) {
    254                 results.append(message);
    255             }
    256 
    257             if (suffixPresent) {
    258                 message =
    259                     TagUtils.getInstance().message(pageContext, bundle, locale,
    260                         getSuffix());
    261                 results.append(message);
    262             }
    263         }
    264 
    265         if (headerDone && footerPresent) {
    266             message =
    267                 TagUtils.getInstance().message(pageContext, bundle, locale,
    268                     getFooter());
    269             results.append(message);
    270         }
    271 
    272         TagUtils.getInstance().write(pageContext, results.toString());
    273 
    274         return (EVAL_BODY_INCLUDE);
    275     }
    276 
    277     /**
    278      * Release any acquired resources.
    279      */
    280     public void release() {
    281         super.release();
    282         bundle = Globals.MESSAGES_KEY;
    283         locale = Globals.LOCALE_KEY;
    284         name = Globals.ERROR_KEY;
    285         property = null;
    286         header = null;
    287         footer = null;
    288         prefix = null;
    289         suffix = null;
    290     }
    291 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
