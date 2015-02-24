[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/ImageTag.html)


    1   /*
    2    * $Id: ImageTag.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import org.apache.struts.config.ModuleConfig;
    25  import org.apache.struts.taglib.TagUtils;
    26  import org.apache.struts.util.ModuleUtils;
    27  
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  import javax.servlet.jsp.JspException;
    31  
    32  /**
    33   * Tag for input fields of type "image".
    34   *
    35   * @version $Rev: 471754 $ $Date: 2005-04-26 20:11:47 -0400 (Tue, 26 Apr 2005)
    36   *          $
    37   */
    38  public class ImageTag extends SubmitTag {
    39      // ------------------------------------------------------------- Properties
    40  
    41      /**
    42       * The alignment for this image.
    43       */
    44      protected String align = null;
    45  
    46      /**
    47       * The border size around the image.
    48       */
    49      protected String border = null;
    50  
    51      /**
    52       * The module-relative URI of the image.
    53       */
    54      protected String page = null;
    55  
    56      /**
    57       * The message resources key of the module-relative URI of the image.
    58       */
    59      protected String pageKey = null;
    60  
    61      /**
    62       * The URL of this image.
    63       */
    64      protected String src = null;
    65  
    66      /**
    67       * The message resources key for the URL of this image.
    68       */
    69      protected String srcKey = null;
    70  
    71      /**
    72       * The module prefix (beginning with a slash) which will be used to find
    73       * the action for this link.
    74       */
    75      protected String module = null;
    76  
    77      // --------------------------------------------------------- Constructor
    78      public ImageTag() {
    79          super();
    80          property = "";
    81      }
    82  
    83      /**
    84       * @deprecated Align attribute is deprecated in HTML 4.x.
    85       */
    86      public String getAlign() {
    87          return (this.align);
    88      }
    89  
    90      /**
    91       * @deprecated Align attribute is deprecated in HTML 4.x.
    92       */
    93      public void setAlign(String align) {
    94          this.align = align;
    95      }
    96  
    97      public String getBorder() {
    98          return (this.border);
    99      }
    100 
    101     public void setBorder(String border) {
    102         this.border = border;
    103     }
    104 
    105     public String getPage() {
    106         return (this.page);
    107     }
    108 
    109     public void setPage(String page) {
    110         this.page = page;
    111     }
    112 
    113     public String getPageKey() {
    114         return (this.pageKey);
    115     }
    116 
    117     public void setPageKey(String pageKey) {
    118         this.pageKey = pageKey;
    119     }
    120 
    121     public String getSrc() {
    122         return (this.src);
    123     }
    124 
    125     public void setSrc(String src) {
    126         this.src = src;
    127     }
    128 
    129     public String getSrcKey() {
    130         return (this.srcKey);
    131     }
    132 
    133     public void setSrcKey(String srcKey) {
    134         this.srcKey = srcKey;
    135     }
    136 
    137     public String getModule() {
    138         return (this.module);
    139     }
    140 
    141     public void setModule(String module) {
    142         this.module = module;
    143     }
    144 
    145     // --------------------------------------------------------- Protected Methods
    146 
    147     /**
    148      * Render the opening element.
    149      *
    150      * @return The opening part of the element.
    151      */
    152     protected String getElementOpen() {
    153         return "<input type=\"image\"";
    154     }
    155 
    156     /**
    157      * Render the button attributes
    158      *
    159      * @param results The StringBuffer that output will be appended to.
    160      */
    161     protected void prepareButtonAttributes(StringBuffer results)
    162         throws JspException {
    163         String tmp = src();
    164 
    165         if (tmp != null) {
    166             HttpServletResponse response =
    167                 (HttpServletResponse) pageContext.getResponse();
    168 
    169             prepareAttribute(results, "src", response.encodeURL(tmp));
    170         }
    171 
    172         prepareAttribute(results, "align", getAlign());
    173         prepareAttribute(results, "border", getBorder());
    174         prepareAttribute(results, "value", getValue());
    175         prepareAttribute(results, "accesskey", getAccesskey());
    176         prepareAttribute(results, "tabindex", getTabindex());
    177     }
    178 
    179     /**
    180      * Release any acquired resources.
    181      */
    182     public void release() {
    183         super.release();
    184         page = null;
    185         pageKey = null;
    186         property = "";
    187         src = null;
    188         srcKey = null;
    189     }
    190 
    191     // ------------------------------------------------------ Protected Methods
    192 
    193     /**
    194      * Return the base source URL that will be rendered in the
    195      * <code>src</code> property for this generated element, or
    196      * <code>null</code> if there is no such URL.
    197      *
    198      * @throws JspException if an error occurs
    199      */
    200     protected String src() throws JspException {
    201         // Deal with a direct context-relative page that has been specified
    202         if (this.page != null) {
    203             if ((this.src != null) || (this.srcKey != null)
    204                 || (this.pageKey != null)) {
    205                 JspException e =
    206                     new JspException(messages.getMessage("imgTag.src"));
    207 
    208                 TagUtils.getInstance().saveException(pageContext, e);
    209                 throw e;
    210             }
    211 
    212             HttpServletRequest request =
    213                 (HttpServletRequest) pageContext.getRequest();
    214 
    215             ModuleConfig config =
    216                 ModuleUtils.getInstance().getModuleConfig(this.module,
    217                     request, pageContext.getServletContext());
    218 
    219             String pageValue = this.page;
    220 
    221             if (config != null) {
    222                 pageValue =
    223                     TagUtils.getInstance().pageURL(request, this.page, config);
    224             }
    225 
    226             return (request.getContextPath() + pageValue);
    227         }
    228 
    229         // Deal with an indirect context-relative page that has been specified
    230         if (this.pageKey != null) {
    231             if ((this.src != null) || (this.srcKey != null)) {
    232                 JspException e =
    233                     new JspException(messages.getMessage("imgTag.src"));
    234 
    235                 TagUtils.getInstance().saveException(pageContext, e);
    236                 throw e;
    237             }
    238 
    239             HttpServletRequest request =
    240                 (HttpServletRequest) pageContext.getRequest();
    241 
    242             ModuleConfig config =
    243                 ModuleUtils.getInstance().getModuleConfig(this.module,
    244                     request, pageContext.getServletContext());
    245 
    246             String pageValue =
    247                 TagUtils.getInstance().message(pageContext, getBundle(),
    248                     getLocale(), this.pageKey);
    249 
    250             if (config != null) {
    251                 pageValue =
    252                     TagUtils.getInstance().pageURL(request, pageValue, config);
    253             }
    254 
    255             return (request.getContextPath() + pageValue);
    256         }
    257 
    258         // Deal with an absolute source that has been specified
    259         if (this.src != null) {
    260             if (this.srcKey != null) {
    261                 JspException e =
    262                     new JspException(messages.getMessage("imgTag.src"));
    263 
    264                 TagUtils.getInstance().saveException(pageContext, e);
    265                 throw e;
    266             }
    267 
    268             return (this.src);
    269         }
    270 
    271         // Deal with an indirect source that has been specified
    272         if (this.srcKey == null) {
    273             JspException e =
    274                 new JspException(messages.getMessage("imgTag.src"));
    275 
    276             TagUtils.getInstance().saveException(pageContext, e);
    277             throw e;
    278         }
    279 
    280         return TagUtils.getInstance().message(pageContext, getBundle(),
    281             getLocale(), this.srcKey);
    282     }
    283 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
