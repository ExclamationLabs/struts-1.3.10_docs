[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/HtmlTag.html)


    1   /*
    2    * $Id: HtmlTag.java 482895 2006-12-06 05:12:27Z niallp $
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
    28  import javax.servlet.jsp.PageContext;
    29  import javax.servlet.jsp.tagext.TagSupport;
    30  
    31  import java.util.Locale;
    32  
    33  /**
    34   * Renders an HTML .html.md> element with appropriate language attributes if
    35   * there is a current Locale available in the user's session.
    36   *
    37   * @version $Rev: 482895 $ $Date: 2005-08-21 19:08:45 -0400 (Sun, 21 Aug 2005)
    38   *          $
    39   */
    40  public class HtmlTag extends TagSupport {
    41      // ------------------------------------------------------------- Properties
    42  
    43      /**
    44       * The message resources for this package.
    45       */
    46      protected static MessageResources messages =
    47          MessageResources.getMessageResources(Constants.Package
    48              + ".LocalStrings");
    49  
    50      /**
    51       * Are we rendering an .html.md page?
    52       */
    53      protected boolean .html.md = false;
    54  
    55      /**
    56       * Are we rendering a lang attribute?
    57       *
    58       * @since Struts 1.2
    59       */
    60      protected boolean lang = false;
    61  
    62      public boolean get.html.md() {
    63          return this..html.md;
    64      }
    65  
    66      public void set.html.md(boolean xhtml) {
    67          this..html.md = xhtml;
    68      }
    69  
    70      /**
    71       * Returns true if the tag should render a lang attribute.
    72       *
    73       * @since Struts 1.2
    74       */
    75      public boolean getLang() {
    76          return this.lang;
    77      }
    78  
    79      /**
    80       * Sets whether the tag should render a lang attribute.
    81       *
    82       * @since Struts 1.2
    83       */
    84      public void setLang(boolean lang) {
    85          this.lang = lang;
    86      }
    87  
    88      /**
    89       * Process the start of this tag.
    90       *
    91       * @throws JspException if a JSP exception has occurred
    92       */
    93      public int doStartTag() throws JspException {
    94          TagUtils.getInstance().write(this.pageContext,
    95              this.renderHtmlStartElement());
    96  
    97          return EVAL_BODY_INCLUDE;
    98      }
    99  
    100     /**
    101      * Renders an &lt.html.md&gt; element with appropriate language attributes.
    102      *
    103      * @since Struts 1.2
    104      */
    105     protected String renderHtmlStartElement() {
    106         StringBuffer sb = new StringBuffer(".html.md");
    107 
    108         String language = null;
    109         String country = "";
    110 
    111         Locale currentLocale =
    112             TagUtils.getInstance().getUserLocale(pageContext, Globals.LOCALE_KEY);
    113 
    114         language = currentLocale.getLanguage();
    115         country = currentLocale.getCountry();
    116 
    117         boolean validLanguage = isValidRfc2616(language);
    118         boolean validCountry  = isValidRfc2616(country);
    119 
    120         if (this..html.md) {
    121             this.pageContext.setAttribute(Globals.XHTML_KEY, "true",
    122                 PageContext.PAGE_SCOPE);
    123 
    124             sb.append(" xmlns=\"http://www.w3.org/1999/.html.md\"");
    125         }
    126 
    127         if ((this.lang || this..html.md) && validLanguage) {
    128             sb.append(" lang=\"");
    129             sb.append(language);
    130 
    131             if (validCountry) {
    132                 sb.append("-");
    133                 sb.append(country);
    134             }
    135 
    136             sb.append("\"");
    137         }
    138 
    139         if (this..html.md && validLanguage) {
    140             sb.append(" xml:lang=\"");
    141             sb.append(language);
    142 
    143             if (validCountry) {
    144                 sb.append("-");
    145                 sb.append(country);
    146             }
    147 
    148             sb.append("\"");
    149         }
    150 
    151         sb.append(">");
    152 
    153         return sb.toString();
    154     }
    155 
    156     /**
    157      * Process the end of this tag.
    158      *
    159      * @throws JspException if a JSP exception has occurred
    160      */
    161     public int doEndTag() throws JspException {
    162         TagUtils.getInstance().write(pageContext, "<.html.md>");
    163 
    164         // Evaluate the remainder of this page
    165         return (EVAL_PAGE);
    166     }
    167 
    168     /**
    169      * Release any acquired resources.
    170      */
    171     public void release() {
    172         this..html.md = false;
    173         this.lang = false;
    174     }
    175 
    176     /**
    177      * Check whether the value contains valid characters for the
    178      * "Accept-Language" header according to RFC 2616 (section 14.4).
    179      *
    180      * @param value The value to check
    181      * @return <code>true</code> if valid, otherwise <code>false</code>
    182      */
    183     private boolean isValidRfc2616(String value) {
    184         if (value == null || value.length() == 0) {
    185             return false;
    186         }
    187         for (int i = 0; i < value.length(); i++) {
    188             char c = value.charAt(i);
    189             
    190             if (!(Character.isLetter(c) || c == '-')) {
    191                 return false;
    192             }
    193         }
    194         return true;
    195     }
    196 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
