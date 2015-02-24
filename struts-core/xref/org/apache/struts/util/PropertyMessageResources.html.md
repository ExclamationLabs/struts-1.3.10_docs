[View Javadoc](../../../../../apidocs/org/apache/struts/util/PropertyMessageResources.html.md)


    1   /*
    2    * $Id: PropertyMessageResources.java 480549 2006-11-29 12:16:15Z niallp $
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
    26  import java.io.IOException;
    27  import java.io.InputStream;
    28  
    29  import java.util.HashMap;
    30  import java.util.Iterator;
    31  import java.util.Locale;
    32  import java.util.Properties;
    33  
    34  /**
    35   * Concrete subclass of <code>MessageResources</code> that reads message keys
    36   * and corresponding strings from named property resources in a <b><i>similar</i></b> manner
    37   * (see <i>modes</i> below) that <code>java.util.PropertyResourceBundle</code> does.  The
    38   * <code>base</code> property defines the base property resource name, and
    39   * must be specified. <p> <strong>IMPLEMENTATION NOTE</strong> - This class
    40   * trades memory for speed by caching all messages located via generalizing
    41   * the Locale under the original locale as well. This results in specific
    42   * messages being stored in the message cache more than once, but improves
    43   * response time on subsequent requests for the same locale + key
    44   * combination.
    45   *
    46   * <h2>Operating Modes</h2>
    47   * This implementation can be configured to operate in one of three modes:
    48   * <ul>
    49   *    <li>1. <b>Default</b> - default, backwardly compatible, Struts behaviour (i.e. the way
    50   *    its always worked).</li>
    51   *    <li>2. <b>JSTL</b> - compatible with how JSTL finds messages
    52   *        (fix for <a href="http://issues.apache.org/struts/browse/STR-2925">STR-2925</a>)</li>
    53   *    <li>3. <b>Resource</b> - compatible with how Java's <code>PropertyResourceBundle</code>
    54   *        finds messages (fix for
    55   *        <a href="http://issues.apache.org/struts/browse/STR-2077">STR-2077</a>)</li>
    56   * </ul>
    57   *
    58   * <h3>1. Default Mode</h3>
    59   * <i>Default mode</i> is the way this implementation has always operated. It searches
    60   * for a message key for property resources in the following sequence:
    61   * <pre>
    62   *      base + "_" + localeLanguage + "_" + localeCountry + "_" + localeVariant
    63   *      base + "_" + localeLanguage + "_" + localeCountry
    64   *      base + "_" + localeLanguage
    65   *      base + "_" + default locale
    66   *      base
    67   * </pre>
    68   * <p>
    69   * This mode is the <i>default</i> and requires no additional configuration.
    70   *
    71   * <h3>2. JSTL Mode</h3>
    72   * <i>JSTL mode</i> is compatible with how JSTL operates and the default Locale
    73   * is not used when looking for a message key. <i>JSTL mode</i> searches for
    74   * a message key for property resources in the following sequence:
    75   * <pre>
    76   *      base + "_" + localeLanguage + "_" + localeCountry + "_" + localeVariant
    77   *      base + "_" + localeLanguage + "_" + localeCountry
    78   *      base + "_" + localeLanguage
    79   *      base
    80   * </pre>
    81   * <p>
    82   * Configure <code>PropertyMessageResources</code> to operate in this mode by
    83   * specifying a value of <code>JSTL</code> for the <code>mode</code>
    84   * key in your <code>struts-config.xml</code>:
    85   * <pre>
    86   *      &lt;message-resources parameter="mypackage.MyMessageResources"&gt;
    87   *          &lt;set-property key="mode" value="JSTL"/&gt;
    88   *      &lt;/message-resources&gt;
    89   * </pre>
    90   *
    91   * <h3>3. Resource Mode</h3>
    92   * <i>Resource mode</i> is compatible with how Java's <code>PropertyResourceBundle</code>
    93   * operates. <i>Resource mode</i> searches first through the specified Locale's language,
    94   * country and variant, then through the default Locale's language,
    95   * country and variant and finally using just the <code>base</code>:
    96   * <pre>
    97   *      base + "_" + localeLanguage + "_" + localeCountry + "_" + localeVariant
    98   *      base + "_" + localeLanguage + "_" + localeCountry
    99   *      base + "_" + localeLanguage
    100  *      base + "_" + defaultLanguage + "_" + defaultCountry + "_" + defaultVariant
    101  *      base + "_" + defaultLanguage + "_" + defaultCountry
    102  *      base + "_" + defaultLanguage
    103  *      base
    104  * </pre>
    105  * <p>
    106  * Configure <code>PropertyMessageResources</code> to operate in this mode by
    107  * specifying a value of <code>resource</code> for the <code>mode</code>
    108  * key in your <code>struts-config.xml</code>:
    109  * <pre>
    110  *      &lt;message-resources parameter="mypackage.MyMessageResources"&gt;
    111  *          &lt;set-property key="mode" value="resource"/&gt;
    112  *      &lt;/message-resources&gt;
    113  * </pre>
    114  * 
    115  * @version $Rev: 480549 $ $Date: 2006-11-29 06:16:15 -0600 (Wed, 29 Nov 2006) $
    116  */
    117 public class PropertyMessageResources extends MessageResources {
    118 
    119 
    120     /** Indicates compatibility with how PropertyMessageResources has always looked up messages */
    121     private static final int MODE_DEFAULT = 0;
    122 
    123     /** Indicates compatibility with how JSTL looks up messages */
    124     private static final int MODE_JSTL = 1;
    125 
    126     /** Indicates compatibility with how java's PropertyResourceBundle looks up messages */
    127     private static final int MODE_RESOURCE_BUNDLE = 2;
    128 
    129     /**
    130      * The <code>Log</code> instance for this class.
    131      */
    132     protected static final Log log =
    133         LogFactory.getLog(PropertyMessageResources.class);
    134 
    135     // ------------------------------------------------------------- Properties
    136 
    137     /**
    138      * The set of locale keys for which we have already loaded messages, keyed
    139      * by the value calculated in <code>localeKey()</code>.
    140      */
    141     protected HashMap locales = new HashMap();
    142 
    143     /**
    144      * The cache of messages we have accumulated over time, keyed by the value
    145      * calculated in <code>messageKey()</code>.
    146      */
    147     protected HashMap messages = new HashMap();
    148 
    149     /**
    150      * Compatibility mode that PropertyMessageResources is operating in.
    151      */
    152     private int mode = MODE_DEFAULT;
    153 
    154     // ----------------------------------------------------------- Constructors
    155 
    156     /**
    157      * Construct a new PropertyMessageResources according to the specified
    158      * parameters.
    159      *
    160      * @param factory The MessageResourcesFactory that created us
    161      * @param config  The configuration parameter for this MessageResources
    162      */
    163     public PropertyMessageResources(MessageResourcesFactory factory,
    164         String config) {
    165         super(factory, config);
    166         log.trace("Initializing, config='" + config + "'");
    167     }
    168 
    169     /**
    170      * Construct a new PropertyMessageResources according to the specified
    171      * parameters.
    172      *
    173      * @param factory    The MessageResourcesFactory that created us
    174      * @param config     The configuration parameter for this
    175      *                   MessageResources
    176      * @param returnNull The returnNull property we should initialize with
    177      */
    178     public PropertyMessageResources(MessageResourcesFactory factory,
    179         String config, boolean returnNull) {
    180         super(factory, config, returnNull);
    181         log.trace("Initializing, config='" + config + "', returnNull="
    182             + returnNull);
    183     }
    184 
    185     // --------------------------------------------------------- Public Methods
    186 
    187     /**
    188      * Set the compatibility mode this implementation uses for message lookup.
    189      *
    190      * @param mode <code>JSTL</code> for JSTL compatibility,
    191      *  <code>resource</code> for PropertyResourceBundle compatibility or
    192      *  <code>default</code> for Struts backward compatibility.
    193      */
    194     public void setMode(String mode) {
    195         String value = (mode == null ? null : mode.trim());
    196         if ("jstl".equalsIgnoreCase(value)) {
    197             this.mode = MODE_JSTL;
    198             if (log.isDebugEnabled()) {
    199                 log.info("Operating in JSTL compatible mode [" + mode + "]");
    200             }
    201         } else if ("resource".equalsIgnoreCase(value)) {
    202             this.mode = MODE_RESOURCE_BUNDLE;
    203             if (log.isDebugEnabled()) {
    204                 log.info("Operating in PropertyResourceBundle compatible mode [" + mode + "]");
    205             }
    206         } else {
    207             this.mode = MODE_DEFAULT;
    208             if (log.isDebugEnabled()) {
    209                 log.info("Operating in Default mode [" + mode + "]");
    210             }
    211         }
    212     }
    213 
    214     /**
    215      * Returns a text message for the specified key, for the specified or default
    216      * Locale. A null string result will be returned by this method if no relevant
    217      * message resource is found for this key or Locale, if the
    218      * <code>returnNull</code> property is set.  Otherwise, an appropriate
    219      * error message will be returned. <p> This method must be implemented by
    220      * a concrete subclass.
    221      *
    222      * @param locale The requested message Locale, or <code>null</code> for
    223      *               the system default Locale
    224      * @param key    The message key to look up
    225      * @return text message for the specified key and locale
    226      */
    227     public String getMessage(Locale locale, String key) {
    228         if (log.isDebugEnabled()) {
    229             log.debug("getMessage(" + locale + "," + key + ")");
    230         }
    231 
    232         // Initialize variables we will require
    233         String localeKey = localeKey(locale);
    234         String originalKey = messageKey(localeKey, key);
    235         String message = null;
    236 
    237         // Search the specified Locale
    238         message = findMessage(locale, key, originalKey);
    239         if (message != null) {
    240             return message;
    241         }
    242 
    243         // JSTL Compatibility - JSTL doesn't use the default locale
    244         if (mode == MODE_JSTL) {
    245 
    246            // do nothing (i.e. don't use default Locale)
    247 
    248         // PropertyResourcesBundle - searches through the hierarchy
    249         // for the default Locale (e.g. first en_US then en)
    250         } else if (mode == MODE_RESOURCE_BUNDLE) {
    251 
    252             if (!defaultLocale.equals(locale)) {
    253                 message = findMessage(defaultLocale, key, originalKey);
    254             }
    255 
    256         // Default (backwards) Compatibility - just searches the
    257         // specified Locale (e.g. just en_US)
    258         } else {
    259 
    260             if (!defaultLocale.equals(locale)) {
    261                 localeKey = localeKey(defaultLocale);
    262                 message = findMessage(localeKey, key, originalKey);
    263             }
    264 
    265         }
    266         if (message != null) {
    267             return message;
    268         }
    269 
    270         // Find the message in the default properties file
    271         message = findMessage("", key, originalKey);
    272         if (message != null) {
    273             return message;
    274         }
    275 
    276         // Return an appropriate error indication
    277         if (returnNull) {
    278             return (null);
    279         } else {
    280             return ("???" + messageKey(locale, key) + "???");
    281         }
    282     }
    283 
    284     // ------------------------------------------------------ Protected Methods
    285 
    286     /**
    287      * Load the messages associated with the specified Locale key.  For this
    288      * implementation, the <code>config</code> property should contain a fully
    289      * qualified package and resource name, separated by periods, of a series
    290      * of property resources to be loaded from the class loader that created
    291      * this PropertyMessageResources instance.  This is exactly the same name
    292      * format you would use when utilizing the <code>java.util.PropertyResourceBundle</code>
    293      * class.
    294      *
    295      * @param localeKey Locale key for the messages to be retrieved
    296      */
    297     protected synchronized void loadLocale(String localeKey) {
    298         if (log.isTraceEnabled()) {
    299             log.trace("loadLocale(" + localeKey + ")");
    300         }
    301 
    302         // Have we already attempted to load messages for this locale?
    303         if (locales.get(localeKey) != null) {
    304             return;
    305         }
    306 
    307         locales.put(localeKey, localeKey);
    308 
    309         // Set up to load the property resource for this locale key, if we can
    310         String name = config.replace('.', '/');
    311 
    312         if (localeKey.length() > 0) {
    313             name += ("_" + localeKey);
    314         }
    315 
    316         name += ".properties";
    317 
    318         InputStream is = null;
    319         Properties props = new Properties();
    320 
    321         // Load the specified property resource
    322         if (log.isTraceEnabled()) {
    323             log.trace("  Loading resource '" + name + "'");
    324         }
    325 
    326         ClassLoader classLoader =
    327             Thread.currentThread().getContextClassLoader();
    328 
    329         if (classLoader == null) {
    330             classLoader = this.getClass().getClassLoader();
    331         }
    332 
    333         is = classLoader.getResourceAsStream(name);
    334 
    335         if (is != null) {
    336             try {
    337                 props.load(is);
    338             } catch (IOException e) {
    339                 log.error("loadLocale()", e);
    340             } finally {
    341                 try {
    342                     is.close();
    343                 } catch (IOException e) {
    344                     log.error("loadLocale()", e);
    345                 }
    346             }
    347             if (log.isTraceEnabled()) {
    348                 log.trace("  Loading resource completed");
    349             }
    350         } else {
    351             if (log.isWarnEnabled()) {
    352                 log.warn("  Resource "+name+" Not Found.");
    353             }
    354         }
    355 
    356 
    357         // Copy the corresponding values into our cache
    358         if (props.size() < 1) {
    359             return;
    360         }
    361 
    362         synchronized (messages) {
    363             Iterator names = props.keySet().iterator();
    364 
    365             while (names.hasNext()) {
    366                 String key = (String) names.next();
    367 
    368                 if (log.isTraceEnabled()) {
    369                     log.trace("  Saving message key '"
    370                         + messageKey(localeKey, key));
    371                 }
    372 
    373                 messages.put(messageKey(localeKey, key), props.getProperty(key));
    374             }
    375         }
    376     }
    377 
    378     // -------------------------------------------------------- Private Methods
    379 
    380     /**
    381      * Returns a text message for the specified key, for the specified Locale.
    382      * <p>
    383      * A null string result will be returned by this method if no relevant
    384      * message resource is found. This method searches through the locale
    385      * <i>hierarchy</i> (i.e. variant --> languge --> country) for the message.
    386      *
    387      * @param locale The requested message Locale, or <code>null</code> for
    388      *  the system default Locale
    389      * @param key The message key to look up
    390      * @param originalKey The original message key to cache any found message under
    391      * @return text message for the specified key and locale
    392      */
    393     private String findMessage(Locale locale, String key, String originalKey) {
    394 
    395         // Initialize variables we will require
    396         String localeKey = localeKey(locale);
    397         String messageKey = null;
    398         String message = null;
    399         int underscore = 0;
    400 
    401         // Loop from specific to general Locales looking for this message
    402         while (true) {
    403             message = findMessage(localeKey, key, originalKey);
    404             if (message != null) {
    405                 break;
    406             }
    407 
    408             // Strip trailing modifiers to try a more general locale key
    409             underscore = localeKey.lastIndexOf("_");
    410 
    411             if (underscore < 0) {
    412                 break;
    413             }
    414 
    415             localeKey = localeKey.substring(0, underscore);
    416         }
    417 
    418         return message;
    419 
    420     }
    421 
    422     /**
    423      * Returns a text message for the specified key, for the specified Locale.
    424      * <p>
    425      * A null string result will be returned by this method if no relevant
    426      * message resource is found.
    427      *
    428      * @param locale The requested key of the Locale
    429      * @param key The message key to look up
    430      * @param originalKey The original message key to cache any found message under
    431      * @return text message for the specified key and locale
    432      */
    433     private String findMessage(String localeKey, String key, String originalKey) {
    434 
    435         // Load this Locale's messages if we have not done so yet
    436         loadLocale(localeKey);
    437 
    438         // Check if we have this key for the current locale key
    439         String messageKey = messageKey(localeKey, key);
    440 
    441         // Add if not found under the original key
    442         boolean addIt = !messageKey.equals(originalKey);
    443 
    444         synchronized (messages) {
    445             String message = (String) messages.get(messageKey);
    446 
    447             if (message != null) {
    448                 if (addIt) {
    449                     messages.put(originalKey, message);
    450                 }
    451 
    452             }
    453             return (message);
    454         }
    455     }
    456 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
