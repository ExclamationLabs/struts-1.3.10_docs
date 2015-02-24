[View Javadoc](../../../../../apidocs/org/apache/struts/util/MessageResources.html.md)


    1   /*
    2    * $Id: MessageResources.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  
    26  import java.io.Serializable;
    27  
    28  import java.text.MessageFormat;
    29  
    30  import java.util.HashMap;
    31  import java.util.Locale;
    32  
    33  /**
    34   * General purpose abstract class that describes an API for retrieving
    35   * Locale-sensitive messages from underlying resource locations of an
    36   * unspecified design, and optionally utilizing the <code>MessageFormat</code>
    37   * class to produce internationalized messages with parametric replacement.
    38   * <p> Calls to <code>getMessage()</code> variants without a
    39   * <code>Locale</code> argument are presumed to be requesting a message string
    40   * in the default <code>Locale</code> for this JVM. <p> Calls to
    41   * <code>getMessage()</code> with an unknown key, or an unknown
    42   * <code>Locale</code> will return <code>null</code> if the
    43   * <code>returnNull</code> property is set to <code>true</code>.  Otherwise, a
    44   * suitable error message will be returned instead. <p> <strong>IMPLEMENTATION
    45   * NOTE</strong> - Classes that extend this class must be Serializable so that
    46   * instances may be used in distributable application server environments.
    47   *
    48   * @version $Rev: 471754 $ $Date: 2005-08-29 23:57:50 -0400 (Mon, 29 Aug 2005)
    49   *          $
    50   */
    51  public abstract class MessageResources implements Serializable {
    52      // ------------------------------------------------------------- Properties
    53  
    54      /**
    55       * Commons Logging instance.
    56       */
    57      protected static Log log = LogFactory.getLog(MessageResources.class);
    58  
    59      // --------------------------------------------------------- Static Methods
    60  
    61      /**
    62       * The default MessageResourcesFactory used to create MessageResources
    63       * instances.
    64       */
    65      protected static MessageResourcesFactory defaultFactory = null;
    66  
    67      /**
    68       * The configuration parameter used to initialize this MessageResources.
    69       */
    70      protected String config = null;
    71  
    72      /**
    73       * The default Locale for our environment.
    74       */
    75      protected Locale defaultLocale = Locale.getDefault();
    76  
    77      /**
    78       * The <code>MessageResourcesFactory</code> that created this instance.
    79       */
    80      protected MessageResourcesFactory factory = null;
    81  
    82      /**
    83       * The set of previously created MessageFormat objects, keyed by the key
    84       * computed in <code>messageKey()</code>.
    85       */
    86      protected HashMap formats = new HashMap();
    87  
    88      /**
    89       * Indicate is a <code>null</code> is returned instead of an error message
    90       * string when an unknown Locale or key is requested.
    91       */
    92      protected boolean returnNull = false;
    93  
    94      /**
    95       * Indicates whether 'escape processing' should be performed on the error
    96       * message string.
    97       */
    98      private boolean escape = true;
    99  
    100     // ----------------------------------------------------------- Constructors
    101 
    102     /**
    103      * Construct a new MessageResources according to the specified
    104      * parameters.
    105      *
    106      * @param factory The MessageResourcesFactory that created us
    107      * @param config  The configuration parameter for this MessageResources
    108      */
    109     public MessageResources(MessageResourcesFactory factory, String config) {
    110         this(factory, config, false);
    111     }
    112 
    113     /**
    114      * Construct a new MessageResources according to the specified
    115      * parameters.
    116      *
    117      * @param factory    The MessageResourcesFactory that created us
    118      * @param config     The configuration parameter for this
    119      *                   MessageResources
    120      * @param returnNull The returnNull property we should initialize with
    121      */
    122     public MessageResources(MessageResourcesFactory factory, String config,
    123         boolean returnNull) {
    124         super();
    125         this.factory = factory;
    126         this.config = config;
    127         this.returnNull = returnNull;
    128     }
    129 
    130     /**
    131      * The configuration parameter used to initialize this MessageResources.
    132      *
    133      * @return parameter used to initialize this MessageResources
    134      */
    135     public String getConfig() {
    136         return (this.config);
    137     }
    138 
    139     /**
    140      * The <code>MessageResourcesFactory</code> that created this instance.
    141      *
    142      * @return <code>MessageResourcesFactory</code> that created instance
    143      */
    144     public MessageResourcesFactory getFactory() {
    145         return (this.factory);
    146     }
    147 
    148     /**
    149      * Indicates that a <code>null</code> is returned instead of an error
    150      * message string if an unknown Locale or key is requested.
    151      *
    152      * @return true if null is returned if unknown key or locale is requested
    153      */
    154     public boolean getReturnNull() {
    155         return (this.returnNull);
    156     }
    157 
    158     /**
    159      * Indicates that a <code>null</code> is returned instead of an error
    160      * message string if an unknown Locale or key is requested.
    161      *
    162      * @param returnNull true Indicates that a <code>null</code> is returned
    163      *                   if an unknown Locale or key is requested.
    164      */
    165     public void setReturnNull(boolean returnNull) {
    166         this.returnNull = returnNull;
    167     }
    168 
    169     /**
    170      * Indicates whether 'escape processing' should be performed on the error
    171      * message string.
    172      *
    173      * @since Struts 1.2.8
    174      */
    175     public boolean isEscape() {
    176         return escape;
    177     }
    178 
    179     /**
    180      * Set whether 'escape processing' should be performed on the error
    181      * message string.
    182      *
    183      * @since Struts 1.2.8
    184      */
    185     public void setEscape(boolean escape) {
    186         this.escape = escape;
    187     }
    188 
    189     // --------------------------------------------------------- Public Methods
    190 
    191     /**
    192      * Returns a text message for the specified key, for the default Locale.
    193      *
    194      * @param key The message key to look up
    195      */
    196     public String getMessage(String key) {
    197         return this.getMessage((Locale) null, key, null);
    198     }
    199 
    200     /**
    201      * Returns a text message after parametric replacement of the specified
    202      * parameter placeholders.
    203      *
    204      * @param key  The message key to look up
    205      * @param args An array of replacement parameters for placeholders
    206      */
    207     public String getMessage(String key, Object[] args) {
    208         return this.getMessage((Locale) null, key, args);
    209     }
    210 
    211     /**
    212      * Returns a text message after parametric replacement of the specified
    213      * parameter placeholders.
    214      *
    215      * @param key  The message key to look up
    216      * @param arg0 The replacement for placeholder {0} in the message
    217      */
    218     public String getMessage(String key, Object arg0) {
    219         return this.getMessage((Locale) null, key, arg0);
    220     }
    221 
    222     /**
    223      * Returns a text message after parametric replacement of the specified
    224      * parameter placeholders.
    225      *
    226      * @param key  The message key to look up
    227      * @param arg0 The replacement for placeholder {0} in the message
    228      * @param arg1 The replacement for placeholder {1} in the message
    229      */
    230     public String getMessage(String key, Object arg0, Object arg1) {
    231         return this.getMessage((Locale) null, key, arg0, arg1);
    232     }
    233 
    234     /**
    235      * Returns a text message after parametric replacement of the specified
    236      * parameter placeholders.
    237      *
    238      * @param key  The message key to look up
    239      * @param arg0 The replacement for placeholder {0} in the message
    240      * @param arg1 The replacement for placeholder {1} in the message
    241      * @param arg2 The replacement for placeholder {2} in the message
    242      */
    243     public String getMessage(String key, Object arg0, Object arg1, Object arg2) {
    244         return this.getMessage((Locale) null, key, arg0, arg1, arg2);
    245     }
    246 
    247     /**
    248      * Returns a text message after parametric replacement of the specified
    249      * parameter placeholders.
    250      *
    251      * @param key  The message key to look up
    252      * @param arg0 The replacement for placeholder {0} in the message
    253      * @param arg1 The replacement for placeholder {1} in the message
    254      * @param arg2 The replacement for placeholder {2} in the message
    255      * @param arg3 The replacement for placeholder {3} in the message
    256      */
    257     public String getMessage(String key, Object arg0, Object arg1, Object arg2,
    258         Object arg3) {
    259         return this.getMessage((Locale) null, key, arg0, arg1, arg2, arg3);
    260     }
    261 
    262     /**
    263      * Returns a text message for the specified key, for the default Locale. A
    264      * null string result will be returned by this method if no relevant
    265      * message resource is found for this key or Locale, if the
    266      * <code>returnNull</code> property is set.  Otherwise, an appropriate
    267      * error message will be returned. <p> This method must be implemented by
    268      * a concrete subclass.
    269      *
    270      * @param locale The requested message Locale, or <code>null</code> for
    271      *               the system default Locale
    272      * @param key    The message key to look up
    273      */
    274     public abstract String getMessage(Locale locale, String key);
    275 
    276     /**
    277      * Returns a text message after parametric replacement of the specified
    278      * parameter placeholders.  A null string result will be returned by this
    279      * method if no resource bundle has been configured.
    280      *
    281      * @param locale The requested message Locale, or <code>null</code> for
    282      *               the system default Locale
    283      * @param key    The message key to look up
    284      * @param args   An array of replacement parameters for placeholders
    285      */
    286     public String getMessage(Locale locale, String key, Object[] args) {
    287         // Cache MessageFormat instances as they are accessed
    288         if (locale == null) {
    289             locale = defaultLocale;
    290         }
    291 
    292         MessageFormat format = null;
    293         String formatKey = messageKey(locale, key);
    294 
    295         synchronized (formats) {
    296             format = (MessageFormat) formats.get(formatKey);
    297 
    298             if (format == null) {
    299                 String formatString = getMessage(locale, key);
    300 
    301                 if (formatString == null) {
    302                     return returnNull ? null : ("???" + formatKey + "???");
    303                 }
    304 
    305                 format = new MessageFormat(escape(formatString));
    306                 format.setLocale(locale);
    307                 formats.put(formatKey, format);
    308             }
    309         }
    310 
    311         return format.format(args);
    312     }
    313 
    314     /**
    315      * Returns a text message after parametric replacement of the specified
    316      * parameter placeholders.  A null string result will never be returned by
    317      * this method.
    318      *
    319      * @param locale The requested message Locale, or <code>null</code> for
    320      *               the system default Locale
    321      * @param key    The message key to look up
    322      * @param arg0   The replacement for placeholder {0} in the message
    323      */
    324     public String getMessage(Locale locale, String key, Object arg0) {
    325         return this.getMessage(locale, key, new Object[] { arg0 });
    326     }
    327 
    328     /**
    329      * Returns a text message after parametric replacement of the specified
    330      * parameter placeholders.  A null string result will never be returned by
    331      * this method.
    332      *
    333      * @param locale The requested message Locale, or <code>null</code> for
    334      *               the system default Locale
    335      * @param key    The message key to look up
    336      * @param arg0   The replacement for placeholder {0} in the message
    337      * @param arg1   The replacement for placeholder {1} in the message
    338      */
    339     public String getMessage(Locale locale, String key, Object arg0, Object arg1) {
    340         return this.getMessage(locale, key, new Object[] { arg0, arg1 });
    341     }
    342 
    343     /**
    344      * Returns a text message after parametric replacement of the specified
    345      * parameter placeholders.  A null string result will never be returned by
    346      * this method.
    347      *
    348      * @param locale The requested message Locale, or <code>null</code> for
    349      *               the system default Locale
    350      * @param key    The message key to look up
    351      * @param arg0   The replacement for placeholder {0} in the message
    352      * @param arg1   The replacement for placeholder {1} in the message
    353      * @param arg2   The replacement for placeholder {2} in the message
    354      */
    355     public String getMessage(Locale locale, String key, Object arg0,
    356         Object arg1, Object arg2) {
    357         return this.getMessage(locale, key, new Object[] { arg0, arg1, arg2 });
    358     }
    359 
    360     /**
    361      * Returns a text message after parametric replacement of the specified
    362      * parameter placeholders.  A null string result will never be returned by
    363      * this method.
    364      *
    365      * @param locale The requested message Locale, or <code>null</code> for
    366      *               the system default Locale
    367      * @param key    The message key to look up
    368      * @param arg0   The replacement for placeholder {0} in the message
    369      * @param arg1   The replacement for placeholder {1} in the message
    370      * @param arg2   The replacement for placeholder {2} in the message
    371      * @param arg3   The replacement for placeholder {3} in the message
    372      */
    373     public String getMessage(Locale locale, String key, Object arg0,
    374         Object arg1, Object arg2, Object arg3) {
    375         return this.getMessage(locale, key,
    376             new Object[] { arg0, arg1, arg2, arg3 });
    377     }
    378 
    379     /**
    380      * Return <code>true</code> if there is a defined message for the
    381      * specified key in the system default locale.
    382      *
    383      * @param key The message key to look up
    384      */
    385     public boolean isPresent(String key) {
    386         return this.isPresent(null, key);
    387     }
    388 
    389     /**
    390      * Return <code>true</code> if there is a defined message for the
    391      * specified key in the specified Locale.
    392      *
    393      * @param locale The requested message Locale, or <code>null</code> for
    394      *               the system default Locale
    395      * @param key    The message key to look up
    396      */
    397     public boolean isPresent(Locale locale, String key) {
    398         String message = getMessage(locale, key);
    399 
    400         if (message == null) {
    401             return false;
    402         } else if (message.startsWith("???") && message.endsWith("???")) {
    403             return false; // FIXME - Only valid for default implementation
    404         } else {
    405             return true;
    406         }
    407     }
    408 
    409     // ------------------------------------------------------ Protected Methods
    410 
    411     /**
    412      * Escape any single quote characters that are included in the specified
    413      * message string.
    414      *
    415      * @param string The string to be escaped
    416      */
    417     protected String escape(String string) {
    418         if (!isEscape()) {
    419             return string;
    420         }
    421 
    422         if ((string == null) || (string.indexOf('\'') < 0)) {
    423             return string;
    424         }
    425 
    426         int n = string.length();
    427         StringBuffer sb = new StringBuffer(n);
    428 
    429         for (int i = 0; i < n; i++) {
    430             char ch = string.charAt(i);
    431 
    432             if (ch == '\'') {
    433                 sb.append('\'');
    434             }
    435 
    436             sb.append(ch);
    437         }
    438 
    439         return sb.toString();
    440     }
    441 
    442     /**
    443      * Compute and return a key to be used in caching information by a Locale.
    444      * <strong>NOTE</strong> - The locale key for the default Locale in our
    445      * environment is a zero length String.
    446      *
    447      * @param locale The locale for which a key is desired
    448      */
    449     protected String localeKey(Locale locale) {
    450         return (locale == null) ? "" : locale.toString();
    451     }
    452 
    453     /**
    454      * Compute and return a key to be used in caching information by Locale
    455      * and message key.
    456      *
    457      * @param locale The Locale for which this format key is calculated
    458      * @param key    The message key for which this format key is calculated
    459      */
    460     protected String messageKey(Locale locale, String key) {
    461         return (localeKey(locale) + "." + key);
    462     }
    463 
    464     /**
    465      * Compute and return a key to be used in caching information by locale
    466      * key and message key.
    467      *
    468      * @param localeKey The locale key for which this cache key is calculated
    469      * @param key       The message key for which this cache key is
    470      *                  calculated
    471      */
    472     protected String messageKey(String localeKey, String key) {
    473         return (localeKey + "." + key);
    474     }
    475 
    476     /**
    477      * Create and return an instance of <code>MessageResources</code> for the
    478      * created by the default <code>MessageResourcesFactory</code>.
    479      *
    480      * @param config Configuration parameter for this message bundle.
    481      */
    482     public synchronized static MessageResources getMessageResources(
    483         String config) {
    484         if (defaultFactory == null) {
    485             defaultFactory = MessageResourcesFactory.createFactory();
    486         }
    487 
    488         return defaultFactory.createResources(config);
    489     }
    490 
    491     /**
    492      * Log a message to the Writer that has been configured for our use.
    493      *
    494      * @param message The message to be logged
    495      */
    496     public void log(String message) {
    497         log.debug(message);
    498     }
    499 
    500     /**
    501      * Log a message and exception to the Writer that has been configured for
    502      * our use.
    503      *
    504      * @param message   The message to be logged
    505      * @param throwable The exception to be logged
    506      */
    507     public void log(String message, Throwable throwable) {
    508         log.debug(message, throwable);
    509     }
    510 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
