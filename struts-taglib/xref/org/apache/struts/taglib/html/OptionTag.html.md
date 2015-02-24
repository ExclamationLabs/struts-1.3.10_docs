[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/OptionTag.html)


    1   /*
    2    * $Id: OptionTag.java 479633 2006-11-27 14:25:35Z pbenedict $
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
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.MessageResources;
    26  
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.BodyTagSupport;
    29  
    30  /**
    31   * Tag for select options.  The body of this tag is presented to the user in
    32   * the option list, while the value attribute is the value returned to the
    33   * server if this option is selected.
    34   *
    35   * @version $Rev: 479633 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005)
    36   *          $
    37   */
    38  public class OptionTag extends BodyTagSupport {
    39      // ----------------------------------------------------- Instance Variables
    40  
    41      /**
    42       * The message resources for this package.
    43       */
    44      protected static MessageResources messages =
    45          MessageResources.getMessageResources(Constants.Package
    46              + ".LocalStrings");
    47  
    48  
    49      /**
    50       * The message text to be displayed to the user for this tag (if any)
    51       */
    52      protected String text = null;
    53  
    54      // ------------------------------------------------------------- Properties
    55  
    56      /**
    57       * The name of the servlet context attribute containing our message
    58       * resources.
    59       */
    60      protected String bundle = Globals.MESSAGES_KEY;
    61  
    62      /**
    63       * Is this option disabled?
    64       */
    65      protected boolean disabled = false;
    66  
    67      /**
    68       * Should the label be filtered for HTML sensitive characters?
    69       */
    70      protected boolean filter = false;
    71  
    72      /**
    73       * The key used to look up the text displayed to the user for this option,
    74       * if any.
    75       */
    76      protected String key = null;
    77  
    78      /**
    79       * The name of the attribute containing the Locale to be used for looking
    80       * up internationalized messages.
    81       */
    82      protected String locale = Globals.LOCALE_KEY;
    83  
    84      /**
    85       * The style associated with this tag.
    86       */
    87      private String style = null;
    88  
    89      /**
    90       * The named style class associated with this tag.
    91       */
    92      private String styleClass = null;
    93  
    94      /**
    95       * The identifier associated with this tag.
    96       */
    97      protected String styleId = null;
    98  
    99      /**
    100      * The language code of this element.
    101      */
    102     private String lang = null;
    103     
    104     /**
    105      * The direction for weak/neutral text of this element.
    106      */
    107     private String dir = null;
    108 
    109     /**
    110      * The server value for this option, also used to match against the
    111      * current property value to determine whether this option should be
    112      * marked as selected.
    113      */
    114     protected String value = null;
    115 
    116     public String getBundle() {
    117         return (this.bundle);
    118     }
    119 
    120     public void setBundle(String bundle) {
    121         this.bundle = bundle;
    122     }
    123 
    124     public boolean getDisabled() {
    125         return (this.disabled);
    126     }
    127 
    128     public void setDisabled(boolean disabled) {
    129         this.disabled = disabled;
    130     }
    131 
    132     public boolean getFilter() {
    133         return (this.filter);
    134     }
    135 
    136     public void setFilter(boolean filter) {
    137         this.filter = filter;
    138     }
    139 
    140     public String getKey() {
    141         return (this.key);
    142     }
    143 
    144     public void setKey(String key) {
    145         this.key = key;
    146     }
    147 
    148     public String getLocale() {
    149         return (this.locale);
    150     }
    151 
    152     public void setLocale(String locale) {
    153         this.locale = locale;
    154     }
    155 
    156     public String getStyle() {
    157         return style;
    158     }
    159 
    160     public void setStyle(String style) {
    161         this.style = style;
    162     }
    163 
    164     public String getStyleClass() {
    165         return styleClass;
    166     }
    167 
    168     public void setStyleClass(String styleClass) {
    169         this.styleClass = styleClass;
    170     }
    171 
    172     /**
    173      * Return the style identifier for this tag.
    174      */
    175     public String getStyleId() {
    176         return (this.styleId);
    177     }
    178 
    179     /**
    180      * Set the style identifier for this tag.
    181      *
    182      * @param styleId The new style identifier
    183      */
    184     public void setStyleId(String styleId) {
    185         this.styleId = styleId;
    186     }
    187 
    188     public String getValue() {
    189         return (this.value);
    190     }
    191 
    192     public void setValue(String value) {
    193         this.value = value;
    194     }
    195 
    196     /**
    197      * Returns the language code of this element.
    198      * 
    199      * @since Struts 1.3.6
    200      */
    201     public String getLang() {
    202         return this.lang;
    203     }
    204 
    205     /**
    206      * Sets the language code of this element.
    207      * 
    208      * @since Struts 1.3.6
    209      */
    210     public void setLang(String lang) {
    211         this.lang = lang;
    212     }
    213 
    214     /**
    215      * Returns the direction for weak/neutral text this element.
    216      * 
    217      * @since Struts 1.3.6
    218      */
    219     public String getDir() {
    220         return this.dir;
    221     }
    222 
    223     /**
    224      * Sets the direction for weak/neutral text of this element.
    225      * 
    226      * @since Struts 1.3.6
    227      */
    228     public void setDir(String dir) {
    229         this.dir = dir;
    230     }
    231 
    232     // --------------------------------------------------------- Public Methods
    233 
    234     /**
    235      * Process the start of this tag.
    236      *
    237      * @throws JspException if a JSP exception has occurred
    238      */
    239     public int doStartTag() throws JspException {
    240         // Initialize the placeholder for our body content
    241         this.text = null;
    242 
    243         // Do nothing until doEndTag() is called
    244         return (EVAL_BODY_TAG);
    245     }
    246 
    247     /**
    248      * Process the body text of this tag (if any).
    249      *
    250      * @throws JspException if a JSP exception has occurred
    251      */
    252     public int doAfterBody() throws JspException {
    253         if (bodyContent != null) {
    254             String text = bodyContent.getString();
    255 
    256             if (text != null) {
    257                 text = text.trim();
    258 
    259                 if (text.length() > 0) {
    260                     this.text = text;
    261                 }
    262             }
    263         }
    264 
    265         return (SKIP_BODY);
    266     }
    267 
    268     /**
    269      * Process the end of this tag.
    270      *
    271      * @throws JspException if a JSP exception has occurred
    272      */
    273     public int doEndTag() throws JspException {
    274         TagUtils.getInstance().write(pageContext, this.renderOptionElement());
    275 
    276         return (EVAL_PAGE);
    277     }
    278 
    279     /**
    280      * Generate an HTML %lt;option&gt; element.
    281      *
    282      * @throws JspException
    283      * @since Struts 1.1
    284      */
    285     protected String renderOptionElement()
    286         throws JspException {
    287         StringBuffer results = new StringBuffer("<option value=\"");
    288 
    289         if (filter) {
    290             results.append(TagUtils.getInstance().filter(this.value));
    291         }
    292         else {
    293             results.append(this.value);
    294         }
    295         results.append("\"");
    296 
    297         if (disabled) {
    298             results.append(" disabled=\"disabled\"");
    299         }
    300 
    301         if (this.selectTag().isMatched(this.value)) {
    302             results.append(" selected=\"selected\"");
    303         }
    304 
    305         if (style != null) {
    306             results.append(" style=\"");
    307             results.append(style);
    308             results.append("\"");
    309         }
    310 
    311         if (styleId != null) {
    312             results.append(" id=\"");
    313             results.append(styleId);
    314             results.append("\"");
    315         }
    316 
    317         if (styleClass != null) {
    318             results.append(" class=\"");
    319             results.append(styleClass);
    320             results.append("\"");
    321         }
    322 
    323         if (dir != null) {
    324             results.append(" dir=\"");
    325             results.append(dir);
    326             results.append("\"");
    327         }
    328 
    329         if (lang != null) {
    330             results.append(" lang=\"");
    331             results.append(lang);
    332             results.append("\"");
    333         }
    334 
    335         results.append(">");
    336 
    337         results.append(text());
    338 
    339         results.append("</option>");
    340 
    341         return results.toString();
    342     }
    343 
    344     /**
    345      * Acquire the select tag we are associated with.
    346      *
    347      * @throws JspException
    348      */
    349     private SelectTag selectTag()
    350         throws JspException {
    351         SelectTag selectTag =
    352             (SelectTag) pageContext.getAttribute(Constants.SELECT_KEY);
    353 
    354         if (selectTag == null) {
    355             JspException e =
    356                 new JspException(messages.getMessage("optionTag.select"));
    357 
    358             TagUtils.getInstance().saveException(pageContext, e);
    359             throw e;
    360         }
    361 
    362         return selectTag;
    363     }
    364 
    365     /**
    366      * Release any acquired resources.
    367      */
    368     public void release() {
    369         super.release();
    370         bundle = Globals.MESSAGES_KEY;
    371         dir = null;
    372         disabled = false;
    373         key = null;
    374         lang = null;
    375         locale = Globals.LOCALE_KEY;
    376         style = null;
    377         styleClass = null;
    378         text = null;
    379         value = null;
    380     }
    381 
    382     // ------------------------------------------------------ Protected Methods
    383 
    384     /**
    385      * Return the text to be displayed to the user for this option (if any).
    386      *
    387      * @throws JspException if an error occurs
    388      */
    389     protected String text() throws JspException {
    390         String optionText = this.text;
    391 
    392         if ((optionText == null) && (this.key != null)) {
    393             optionText =
    394                 TagUtils.getInstance().message(pageContext, bundle, locale, key);
    395         }
    396 
    397         // no body text and no key to lookup so display the value
    398         if (optionText == null) {
    399             optionText = this.value;
    400         }
    401 
    402         return optionText;
    403     }
    404 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
