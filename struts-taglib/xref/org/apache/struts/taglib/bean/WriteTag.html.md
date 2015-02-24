[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/WriteTag.html.md)


    1   /*
    2    * $Id: WriteTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.bean;
    22  
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.MessageResources;
    25  
    26  import javax.servlet.jsp.JspException;
    27  import javax.servlet.jsp.tagext.TagSupport;
    28  
    29  import java.math.BigDecimal;
    30  import java.math.BigInteger;
    31  
    32  import java.text.DecimalFormat;
    33  import java.text.Format;
    34  import java.text.NumberFormat;
    35  import java.text.SimpleDateFormat;
    36  
    37  import java.util.Locale;
    38  
    39  /**
    40   * Tag that retrieves the specified property of the specified bean, converts
    41   * it to a String representation (if necessary), and writes it to the current
    42   * output stream, optionally filtering characters that are sensitive in HTML.
    43   *
    44   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    45   *          $
    46   */
    47  public class WriteTag extends TagSupport {
    48      /**
    49       * The key to search default format string for java.sql.Timestamp in
    50       * resources.
    51       */
    52      public static final String SQL_TIMESTAMP_FORMAT_KEY =
    53          "org.apache.struts.taglib.bean.format.sql.timestamp";
    54  
    55      /**
    56       * The key to search default format string for java.sql.Date in
    57       * resources.
    58       */
    59      public static final String SQL_DATE_FORMAT_KEY =
    60          "org.apache.struts.taglib.bean.format.sql.date";
    61  
    62      /**
    63       * The key to search default format string for java.sql.Time in
    64       * resources.
    65       */
    66      public static final String SQL_TIME_FORMAT_KEY =
    67          "org.apache.struts.taglib.bean.format.sql.time";
    68  
    69      /**
    70       * The key to search default format string for java.util.Date in
    71       * resources.
    72       */
    73      public static final String DATE_FORMAT_KEY =
    74          "org.apache.struts.taglib.bean.format.date";
    75  
    76      /**
    77       * The key to search default format string for int (byte, short, etc.) in
    78       * resources.
    79       */
    80      public static final String INT_FORMAT_KEY =
    81          "org.apache.struts.taglib.bean.format.int";
    82  
    83      /**
    84       * The key to search default format string for float (double, BigDecimal)
    85       * in resources.
    86       */
    87      public static final String FLOAT_FORMAT_KEY =
    88          "org.apache.struts.taglib.bean.format.float";
    89  
    90      /**
    91       * The message resources for this package.
    92       */
    93      protected static MessageResources messages =
    94          MessageResources.getMessageResources(
    95              "org.apache.struts.taglib.bean.LocalStrings");
    96  
    97      // ------------------------------------------------------------- Properties
    98  
    99      /**
    100      * Filter the rendered output for characters that are sensitive in HTML?
    101      */
    102     protected boolean filter = true;
    103 
    104     /**
    105      * Should we ignore missing beans and simply output nothing?
    106      */
    107     protected boolean ignore = false;
    108 
    109     /**
    110      * Name of the bean that contains the data we will be rendering.
    111      */
    112     protected String name = null;
    113 
    114     /**
    115      * Name of the property to be accessed on the specified bean.
    116      */
    117     protected String property = null;
    118 
    119     /**
    120      * The scope to be searched to retrieve the specified bean.
    121      */
    122     protected String scope = null;
    123 
    124     /**
    125      * The format string to be used as format to convert value to String.
    126      */
    127     protected String formatStr = null;
    128 
    129     /**
    130      * The key to search format string in applciation resources
    131      */
    132     protected String formatKey = null;
    133 
    134     /**
    135      * The session scope key under which our Locale is stored.
    136      */
    137     protected String localeKey = null;
    138 
    139     /**
    140      * The servlet context attribute key for our resources.
    141      */
    142     protected String bundle = null;
    143 
    144     public boolean getFilter() {
    145         return (this.filter);
    146     }
    147 
    148     public void setFilter(boolean filter) {
    149         this.filter = filter;
    150     }
    151 
    152     public boolean getIgnore() {
    153         return (this.ignore);
    154     }
    155 
    156     public void setIgnore(boolean ignore) {
    157         this.ignore = ignore;
    158     }
    159 
    160     public String getName() {
    161         return (this.name);
    162     }
    163 
    164     public void setName(String name) {
    165         this.name = name;
    166     }
    167 
    168     public String getProperty() {
    169         return (this.property);
    170     }
    171 
    172     public void setProperty(String property) {
    173         this.property = property;
    174     }
    175 
    176     public String getScope() {
    177         return (this.scope);
    178     }
    179 
    180     public void setScope(String scope) {
    181         this.scope = scope;
    182     }
    183 
    184     public String getFormat() {
    185         return (this.formatStr);
    186     }
    187 
    188     public void setFormat(String formatStr) {
    189         this.formatStr = formatStr;
    190     }
    191 
    192     public String getFormatKey() {
    193         return (this.formatKey);
    194     }
    195 
    196     public void setFormatKey(String formatKey) {
    197         this.formatKey = formatKey;
    198     }
    199 
    200     public String getLocale() {
    201         return (this.localeKey);
    202     }
    203 
    204     public void setLocale(String localeKey) {
    205         this.localeKey = localeKey;
    206     }
    207 
    208     public String getBundle() {
    209         return (this.bundle);
    210     }
    211 
    212     public void setBundle(String bundle) {
    213         this.bundle = bundle;
    214     }
    215 
    216     // --------------------------------------------------------- Public Methods
    217 
    218     /**
    219      * Process the start tag.
    220      *
    221      * @throws JspException if a JSP exception has occurred
    222      */
    223     public int doStartTag() throws JspException {
    224         // Look up the requested bean (if necessary)
    225         if (ignore) {
    226             if (TagUtils.getInstance().lookup(pageContext, name, scope)
    227                 == null) {
    228                 return (SKIP_BODY); // Nothing to output
    229             }
    230         }
    231 
    232         // Look up the requested property value
    233         Object value =
    234             TagUtils.getInstance().lookup(pageContext, name, property, scope);
    235 
    236         if (value == null) {
    237             return (SKIP_BODY); // Nothing to output
    238         }
    239 
    240         // Convert value to the String with some formatting
    241         String output = formatValue(value);
    242 
    243         // Print this property value to our output writer, suitably filtered
    244         if (filter) {
    245             TagUtils.getInstance().write(pageContext,
    246                 TagUtils.getInstance().filter(output));
    247         } else {
    248             TagUtils.getInstance().write(pageContext, output);
    249         }
    250 
    251         // Continue processing this page
    252         return (SKIP_BODY);
    253     }
    254 
    255     /**
    256      * Retrieve format string from message bundle and return null if message
    257      * not found or message string.
    258      *
    259      * @param formatKey value to use as key to search message in bundle
    260      * @throws JspException if a JSP exception has occurred
    261      */
    262     protected String retrieveFormatString(String formatKey)
    263         throws JspException {
    264         String result =
    265             TagUtils.getInstance().message(pageContext, this.bundle,
    266                 this.localeKey, formatKey);
    267 
    268         if ((result != null)
    269             && !(result.startsWith("???") && result.endsWith("???"))) {
    270             return result;
    271         } else {
    272             return null;
    273         }
    274     }
    275 
    276     /**
    277      * Format value according to specified format string (as tag attribute or
    278      * as string from message resources) or to current user locale.
    279      *
    280      * When a format string is retrieved from the message resources,
    281      * <code>applyLocalizedPattern</code> is used. For more about localized
    282      * patterns, see
    283      * <http://www.dei.unipd.it/corsi/fi2ae-docs/source/jdk1.1.7/src/java/text/resources/>.
    284      * (To obtain the correct value for some characters, you may need to view
    285      * the file in a hex editor and then use the Unicode escape form in the
    286      * property resources file.)
    287      *
    288      * @param valueToFormat value to process and convert to String
    289      * @throws JspException if a JSP exception has occurred
    290      */
    291     protected String formatValue(Object valueToFormat)
    292         throws JspException {
    293         Format format = null;
    294         Object value = valueToFormat;
    295         Locale locale =
    296             TagUtils.getInstance().getUserLocale(pageContext, this.localeKey);
    297         boolean formatStrFromResources = false;
    298         String formatString = formatStr;
    299 
    300         // Return String object as is.
    301         if (value instanceof java.lang.String) {
    302             return (String) value;
    303         } else {
    304             // Try to retrieve format string from resources by the key from
    305             // formatKey.
    306             if ((formatString == null) && (formatKey != null)) {
    307                 formatString = retrieveFormatString(this.formatKey);
    308 
    309                 if (formatString != null) {
    310                     formatStrFromResources = true;
    311                 }
    312             }
    313 
    314             // Prepare format object for numeric values.
    315             if (value instanceof Number) {
    316                 if (formatString == null) {
    317                     if ((value instanceof Byte) || (value instanceof Short)
    318                         || (value instanceof Integer)
    319                         || (value instanceof Long)
    320                         || (value instanceof BigInteger)) {
    321                         formatString = retrieveFormatString(INT_FORMAT_KEY);
    322                     } else if ((value instanceof Float)
    323                         || (value instanceof Double)
    324                         || (value instanceof BigDecimal)) {
    325                         formatString = retrieveFormatString(FLOAT_FORMAT_KEY);
    326                     }
    327 
    328                     if (formatString != null) {
    329                         formatStrFromResources = true;
    330                     }
    331                 }
    332 
    333                 if (formatString != null) {
    334                     try {
    335                         format = NumberFormat.getNumberInstance(locale);
    336 
    337                         if (formatStrFromResources) {
    338                             ((DecimalFormat) format).applyLocalizedPattern(
    339                                 formatString);
    340                         } else {
    341                             ((DecimalFormat) format).applyPattern(formatString);
    342                         }
    343                     } catch (IllegalArgumentException e) {
    344                         JspException ex =
    345                             new JspException(messages.getMessage(
    346                                     "write.format", formatString));
    347 
    348                         TagUtils.getInstance().saveException(pageContext, ex);
    349                         throw ex;
    350                     }
    351                 }
    352             } else if (value instanceof java.util.Date) {
    353                 if (formatString == null) {
    354                     if (value instanceof java.sql.Timestamp) {
    355                         formatString =
    356                             retrieveFormatString(SQL_TIMESTAMP_FORMAT_KEY);
    357                     } else if (value instanceof java.sql.Date) {
    358                         formatString =
    359                             retrieveFormatString(SQL_DATE_FORMAT_KEY);
    360                     } else if (value instanceof java.sql.Time) {
    361                         formatString =
    362                             retrieveFormatString(SQL_TIME_FORMAT_KEY);
    363                     } else if (value instanceof java.util.Date) {
    364                         formatString = retrieveFormatString(DATE_FORMAT_KEY);
    365                     }
    366                 }
    367 
    368                 if (formatString != null) {
    369                     format = new SimpleDateFormat(formatString, locale);
    370                 }
    371             }
    372         }
    373 
    374         if (format != null) {
    375             return format.format(value);
    376         } else {
    377             return value.toString();
    378         }
    379     }
    380 
    381     /**
    382      * Release all allocated resources.
    383      */
    384     public void release() {
    385         super.release();
    386         filter = true;
    387         ignore = false;
    388         name = null;
    389         property = null;
    390         scope = null;
    391         formatStr = null;
    392         formatKey = null;
    393         localeKey = null;
    394         bundle = null;
    395     }
    396 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
