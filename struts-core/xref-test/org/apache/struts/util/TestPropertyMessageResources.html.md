
    1   /*
    2    * $Id: TestPropertyMessageResources.java 480549 2006-11-29 12:16:15Z niallp $
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
    23  import junit.framework.Test;
    24  import junit.framework.TestSuite;
    25  import junit.framework.TestCase;
    26  
    27  import java.util.Locale;
    28  import org.apache.struts.config.MessageResourcesConfig;
    29  
    30  /**
    31   * Unit tests for PropertyMessageResources.
    32   *
    33   * @version $Revision: 480549 $
    34   */
    35  public class TestPropertyMessageResources extends TestCase {
    36  
    37  
    38      private static final String FOO_RESOURCES = "org.apache.struts.util.Foo";
    39  
    40      private Locale defaultLocale;
    41      
    42      // ----------------------------------------------------------------- Basics
    43      public TestPropertyMessageResources(String name) {
    44          super(name);
    45      }
    46  
    47      public static void main(String[] args) {
    48          junit.awtui.TestRunner.main(new String[] {
    49                  TestPropertyMessageResources.class.getName()
    50              });
    51      }
    52  
    53      public static Test suite() {
    54          return (new TestSuite(TestPropertyMessageResources.class));
    55      }
    56  
    57      // ----------------------------------------------------- Setup and Teardown
    58      public void setUp() {
    59          // cache the default locale
    60          defaultLocale = Locale.getDefault();
    61      }
    62  
    63      public void tearDown() {
    64          // restore the default locale
    65          Locale.setDefault(defaultLocale);
    66      }
    67  
    68      // ------------------------------------------------------- Individual Tests
    69  
    70      /**
    71       * Test Struts default PropertyMessageResources behaviour
    72       */
    73      public void testDefaultMode() {
    74  
    75          Locale.setDefault(Locale.US);
    76          
    77          // Create message resources - default Struts Behaviour
    78  //        MessageResources resources = createMessageResources(FOO_RESOURCES, true, "DEFAULT");
    79          MessageResources resources = createMessageResources(FOO_RESOURCES, true, null);
    80  
    81          // Test language (& default) only keys
    82          assertEquals("key.lang FRANCE",  "LANG default", resources.getMessage(Locale.FRANCE,  "key.lang")); // no cached en_US
    83          assertEquals("key.lang English", "LANG en",      resources.getMessage(Locale.ENGLISH, "key.lang"));
    84          assertEquals("key.lang US",      "LANG en",      resources.getMessage(Locale.US,      "key.lang"));
    85          assertEquals("key.lang ITALY",   "LANG en",      resources.getMessage(Locale.ITALY,   "key.lang")); // cached en_US
    86          assertEquals("key.lang German",  "LANG de",      resources.getMessage(Locale.GERMAN,  "key.lang"));
    87          assertEquals("key.lang GERMANY", "LANG de",      resources.getMessage(Locale.GERMANY, "key.lang"));
    88  
    89          // Test country (& default) only keys
    90          assertEquals("key.country FRANCE",  "COUNTRY en_US", resources.getMessage(Locale.FRANCE,  "key.country"));
    91          assertEquals("key.country English", "COUNTRY en_US", resources.getMessage(Locale.ENGLISH, "key.country"));
    92          assertEquals("key.country US",      "COUNTRY en_US", resources.getMessage(Locale.US,      "key.country"));
    93          assertEquals("key.country ITALY",   "COUNTRY en_US", resources.getMessage(Locale.ITALY,   "key.country"));
    94          assertEquals("key.country German",  "COUNTRY en_US", resources.getMessage(Locale.GERMAN,  "key.country"));
    95          assertEquals("key.country GERMANY", "COUNTRY de_DE", resources.getMessage(Locale.GERMANY, "key.country"));
    96  
    97          // Test Unique Keys with wrong Locale
    98          assertEquals("Wrong Locale en only",    null,         resources.getMessage(Locale.GERMAN,  "key.en"));
    99          assertEquals("Wrong Locale en_US only", "en_US only", resources.getMessage(Locale.GERMANY, "key.en_US"));
    100 
    101         // Run tests with common expected results
    102         commonTests(resources);
    103     }
    104 
    105     /**
    106      * Test JSTL compatible PropertyMessageResources behaviour
    107      */
    108     public void testJstlMode() {
    109 
    110         Locale.setDefault(Locale.US);
    111         
    112         // Create message resources - default Struts Behaviour
    113         MessageResources resources = createMessageResources(FOO_RESOURCES, true, "JSTL");
    114 
    115         // Test language (& default) only keys
    116         assertEquals("key.lang FRANCE",  "LANG default", resources.getMessage(Locale.FRANCE,  "key.lang"));
    117         assertEquals("key.lang English", "LANG en",      resources.getMessage(Locale.ENGLISH, "key.lang"));
    118         assertEquals("key.lang US",      "LANG en",      resources.getMessage(Locale.US,      "key.lang"));
    119         assertEquals("key.lang ITALY",   "LANG default", resources.getMessage(Locale.ITALY,   "key.lang"));
    120         assertEquals("key.lang German",  "LANG de",      resources.getMessage(Locale.GERMAN,  "key.lang"));
    121         assertEquals("key.lang GERMANY", "LANG de",      resources.getMessage(Locale.GERMANY, "key.lang"));
    122 
    123         // Test country (& default) only keys
    124         assertEquals("key.country FRANCE",  "COUNTRY default", resources.getMessage(Locale.FRANCE,  "key.country"));
    125         assertEquals("key.country English", "COUNTRY default", resources.getMessage(Locale.ENGLISH, "key.country"));
    126         assertEquals("key.country US",      "COUNTRY en_US",   resources.getMessage(Locale.US,      "key.country"));
    127         assertEquals("key.country ITALY",   "COUNTRY default", resources.getMessage(Locale.ITALY,   "key.country"));
    128         assertEquals("key.country German",  "COUNTRY default", resources.getMessage(Locale.GERMAN,  "key.country"));
    129         assertEquals("key.country GERMANY", "COUNTRY de_DE",   resources.getMessage(Locale.GERMANY, "key.country"));
    130 
    131         // Test Unique Keys with wrong Locale
    132         assertEquals("Wrong Locale en only",    null, resources.getMessage(Locale.GERMAN,  "key.en"));
    133         assertEquals("Wrong Locale en_US only", null, resources.getMessage(Locale.GERMANY, "key.en_US"));
    134 
    135         // Run tests with common expected results
    136         commonTests(resources);
    137 
    138     }
    139 
    140     /**
    141      * Test "PropertyResourceBundle" compatible PropertyMessageResources behaviour
    142      */
    143     public void testResourceBundleMode() {
    144 
    145         Locale.setDefault(Locale.US);
    146         
    147         // Create message resources - default Struts Behaviour
    148         MessageResources resources = createMessageResources(FOO_RESOURCES, true, "RESOURCE");
    149 
    150         // Test language (& default) only keys
    151         assertEquals("key.lang FRANCE",  "LANG en",      resources.getMessage(Locale.FRANCE,  "key.lang"));
    152         assertEquals("key.lang English", "LANG en",      resources.getMessage(Locale.ENGLISH, "key.lang"));
    153         assertEquals("key.lang US",      "LANG en",      resources.getMessage(Locale.US,      "key.lang"));
    154         assertEquals("key.lang ITALY",   "LANG en",      resources.getMessage(Locale.ITALY,   "key.lang"));
    155         assertEquals("key.lang German",  "LANG de",      resources.getMessage(Locale.GERMAN,  "key.lang"));
    156         assertEquals("key.lang GERMANY", "LANG de",      resources.getMessage(Locale.GERMANY, "key.lang"));
    157 
    158         // Test country (& default) only keys
    159         assertEquals("key.country FRANCE",  "COUNTRY en_US", resources.getMessage(Locale.FRANCE,  "key.country"));
    160         assertEquals("key.country English", "COUNTRY en_US", resources.getMessage(Locale.ENGLISH, "key.country"));
    161         assertEquals("key.country US",      "COUNTRY en_US", resources.getMessage(Locale.US,      "key.country"));
    162         assertEquals("key.country ITALY",   "COUNTRY en_US", resources.getMessage(Locale.ITALY,   "key.country"));
    163         assertEquals("key.country German",  "COUNTRY en_US", resources.getMessage(Locale.GERMAN,  "key.country"));
    164         assertEquals("key.country GERMANY", "COUNTRY de_DE", resources.getMessage(Locale.GERMANY, "key.country"));
    165 
    166         // Test Unique Keys with wrong Locale
    167         assertEquals("Wrong Locale en only",    "en only",    resources.getMessage(Locale.GERMAN,  "key.en"));
    168         assertEquals("Wrong Locale en_US only", "en_US only", resources.getMessage(Locale.GERMANY, "key.en_US"));
    169 
    170         // Run tests with common expected results
    171         commonTests(resources);
    172     }
    173 
    174     /**
    175      * Tests with common expected results
    176      */
    177     public void commonTests(MessageResources resources) {
    178 
    179         // Test "null" Locale
    180         assertEquals("null Locale",  "ALL default", resources.getMessage((Locale)null,  "key.all"));
    181 
    182         // Test Default only key with all Locales
    183         assertEquals("Check default en",    "default only", resources.getMessage(Locale.ENGLISH, "key.default"));
    184         assertEquals("Check default en_US", "default only", resources.getMessage(Locale.US,      "key.default"));
    185         assertEquals("Check default de",    "default only", resources.getMessage(Locale.GERMAN,  "key.default"));
    186         assertEquals("Check default de_DE", "default only", resources.getMessage(Locale.GERMANY, "key.default"));
    187 
    188         // Test key in all locales
    189         assertEquals("Check ALL en",        "ALL en",       resources.getMessage(Locale.ENGLISH, "key.all"));
    190         assertEquals("Check ALL en_US",     "ALL en_US",    resources.getMessage(Locale.US,      "key.all"));
    191         assertEquals("Check ALL de",        "ALL de",       resources.getMessage(Locale.GERMAN,  "key.all"));
    192         assertEquals("Check ALL de_DE",     "ALL de_DE",    resources.getMessage(Locale.GERMANY, "key.all"));
    193 
    194         // Test key unique to each locale
    195         assertEquals("Check en only",       "en only",      resources.getMessage(Locale.ENGLISH, "key.en"));
    196         assertEquals("Check en_US only",    "en_US only",   resources.getMessage(Locale.US,      "key.en_US"));
    197         assertEquals("Check de only",       "de only",      resources.getMessage(Locale.GERMAN,  "key.de"));
    198         assertEquals("Check de_DE only",    "de_DE only",   resources.getMessage(Locale.GERMANY, "key.de_DE"));
    199 
    200         // Test unique keys with incorrect Locale
    201         assertEquals("Missing default",     null,           resources.getMessage(Locale.ENGLISH, "missing"));
    202         assertEquals("Missing de only",     null,           resources.getMessage(Locale.US,      "key.de"));
    203         assertEquals("Missing de_DE only",  null,           resources.getMessage(Locale.US,      "key.de_DE"));
    204     }
    205 
    206     /**
    207      * Create the PropertyMessageResources.
    208      */
    209     private MessageResources createMessageResources(String file, boolean returnNull, String mode) {
    210         MessageResourcesConfig config = new MessageResourcesConfig();
    211         config.setNull(returnNull);
    212         if (mode != null) {
    213             config.setProperty("mode", mode);
    214         }
    215         PropertyMessageResourcesFactory factory = new PropertyMessageResourcesFactory();
    216         factory.setConfig(config);
    217         factory.setReturnNull(returnNull);
    218         return factory.createResources(file);
    219     }
    220 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
