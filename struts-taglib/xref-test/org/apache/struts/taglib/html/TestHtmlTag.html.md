
    1   /*
    2    * $Id: TestHtmlTag.java 482895 2006-12-06 05:12:27Z niallp $
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
    23  import java.util.Locale;
    24  import junit.framework.Test;
    25  import junit.framework.TestSuite;
    26  import junit.framework.TestCase;
    27  import org.apache.struts.mock.MockHttpServletRequest;
    28  import org.apache.struts.mock.MockHttpServletResponse;
    29  import org.apache.struts.mock.MockPageContext;
    30  import org.apache.struts.mock.MockServletConfig;
    31  
    32  /**
    33   * Unit tests for the HtmlTag.
    34   */
    35  public class TestHtmlTag extends TestCase {
    36  
    37      private MockServletConfig       config;
    38      private MockHttpServletRequest  request;
    39      private MockHttpServletResponse response;
    40      private MockPageContext         pageContext;
    41      private HtmlTag                .html.mdTag;
    42  
    43      /**
    44       * Defines the testcase name for JUnit.
    45       *
    46       * @param theName the testcase's name.
    47       */
    48      public TestHtmlTag(String theName) {
    49          super(theName);
    50      }
    51  
    52      /**
    53       * Start the tests.
    54       *
    55       * @param theArgs the arguments. Not used
    56       */
    57      public static void main(String[] theArgs) {
    58          junit.awtui.TestRunner.main(new String[] { TestHtmlTag.class.getName() });
    59      }
    60  
    61      /**
    62       * @return a test suite (<code>TestSuite</code>) that includes all methods
    63       *         starting with "test"
    64       */
    65      public static Test suite() {
    66          // All methods starting with "test" will be executed in the test suite.
    67          return new TestSuite(TestHtmlTag.class);
    68      }
    69  
    70      /**
    71       * Set up mock objects.
    72       */
    73      public void setUp() {
    74          config      = new MockServletConfig();
    75          request     = new MockHttpServletRequest();
    76          response    = new MockHttpServletResponse();
    77          pageContext = new MockPageContext(config, request, response);
    78         .html.mdTag     = new HtmlTag();
    79         .html.mdTag.setPageContext(pageContext);
    80      }
    81  
    82      /**
    83       * Test the "lang" attribute with valid characters.
    84       */
    85      public void testValidLangTrue() {
    86          
    87          // switch to render "lang" attribute
    88         .html.mdTag.setLang(true);
    89  
    90          // Render for Locale.US
    91          request.setLocale(Locale.US);
    92          assertEquals("render en_US", ".html.md lang=\"en-US\">", htmlTag.renderHtmlStartElement());
    93  
    94          // Render for Locale.ENGLISH
    95          request.setLocale(Locale.ENGLISH);
    96          assertEquals("render en", ".html.md lang=\"en\">", htmlTag.renderHtmlStartElement());
    97  
    98          // Test valid characters
    99          request.setLocale(new Locale("abcd-efghijklmnopqrstuvwxyz", "ABCDEFGHIJKLM-NOPQRSTUVWXYZ", ""));
    100         assertEquals("valid characters", ".html.md lang=\"abcd-efghijklmnopqrstuvwxyz-ABCDEFGHIJKLM-NOPQRSTUVWXYZ\">", htmlTag.renderHtmlStartElement());
    101 
    102     }
    103 
    104     /**
    105      * Test the "lang" attribute with valid characters.
    106      */
    107     public void testValidLangFalse() {
    108         
    109         // switch to NOT render "lang" attribute
    110        .html.mdTag.setLang(false);
    111 
    112         // Ignore for Locale.US
    113         request.setLocale(Locale.US);
    114         assertEquals("ignore en_US", ".html.md>", htmlTag.renderHtmlStartElement());
    115 
    116         // Ignore for Locale.ENGLISH
    117         request.setLocale(Locale.ENGLISH);
    118         assertEquals("ignore en", ".html.md>", htmlTag.renderHtmlStartElement());
    119 
    120     }
    121 
    122     /**
    123      * Test an invalid "language"
    124      */
    125     public void testInvalidLanguage() {
    126         
    127         // switch to render "lang" attribute
    128        .html.mdTag.setLang(true);
    129 
    130         // make sure HtmlTag is setup to render "lang" using a valid value
    131         request.setLocale(Locale.US);
    132         assertEquals("check valid", ".html.md lang=\"en-US\">", htmlTag.renderHtmlStartElement());
    133 
    134         // Test script injection
    135         request.setLocale(new Locale("/><script>alert()</script>", "", ""));
    136         assertEquals("invalid <script>", ".html.md>", htmlTag.renderHtmlStartElement());
    137 
    138         // Test <
    139         request.setLocale(new Locale("abc<def", "", ""));
    140         assertEquals("invalid LT", ".html.md>", htmlTag.renderHtmlStartElement());
    141 
    142         // Test >
    143         request.setLocale(new Locale("abc>def", "", ""));
    144         assertEquals("invalid GT", ".html.md>", htmlTag.renderHtmlStartElement());
    145 
    146         // Test /
    147         request.setLocale(new Locale("abc/def", "", ""));
    148         assertEquals("invalid SLASH", ".html.md>", htmlTag.renderHtmlStartElement());
    149 
    150         // Test &
    151         request.setLocale(new Locale("abc&def", "", ""));
    152         assertEquals("invalid AMP", ".html.md>", htmlTag.renderHtmlStartElement());
    153 
    154     }
    155 
    156     /**
    157      * Test an invalid "country"
    158      */
    159     public void testInvalidCountry() {
    160         
    161         // switch to render "lang" attribute
    162        .html.mdTag.setLang(true);
    163 
    164         // make sure HtmlTag is setup to render "lang" using a valid value
    165         request.setLocale(Locale.US);
    166         assertEquals("check valid", ".html.md lang=\"en-US\">", htmlTag.renderHtmlStartElement());
    167 
    168         // Test script injection
    169         request.setLocale(new Locale("en", "/><script>alert()</script>", ""));
    170         assertEquals("invalid <script>", ".html.md lang=\"en\">", htmlTag.renderHtmlStartElement());
    171 
    172         // Test <
    173         request.setLocale(new Locale("en", "abc<def", ""));
    174         assertEquals("invalid LT", ".html.md lang=\"en\">", htmlTag.renderHtmlStartElement());
    175 
    176         // Test >
    177         request.setLocale(new Locale("en", "abc>def", ""));
    178         assertEquals("invalid GT", ".html.md lang=\"en\">", htmlTag.renderHtmlStartElement());
    179 
    180         // Test /
    181         request.setLocale(new Locale("en", "abc/def", ""));
    182         assertEquals("invalid SLASH", ".html.md lang=\"en\">", htmlTag.renderHtmlStartElement());
    183 
    184         // Test &
    185         request.setLocale(new Locale("en", "abc&def", ""));
    186         assertEquals("invalid AMP", ".html.md lang=\"en\">", htmlTag.renderHtmlStartElement());
    187 
    188     }
    189 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
