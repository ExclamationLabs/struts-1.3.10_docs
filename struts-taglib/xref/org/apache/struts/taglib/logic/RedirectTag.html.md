[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/RedirectTag.html.md)


    1   /*
    2    * $Id: RedirectTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.logic;
    22  
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.MessageResources;
    25  
    26  import javax.servlet.http.HttpServletResponse;
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  import java.io.IOException;
    31  
    32  import java.net.MalformedURLException;
    33  
    34  import java.util.Map;
    35  
    36  /**
    37   * Generate a URL-encoded redirect to the specified URI.
    38   *
    39   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    40   *          $
    41   */
    42  public class RedirectTag extends TagSupport {
    43      /**
    44       * The message resources for this package.
    45       */
    46      protected static MessageResources messages =
    47          MessageResources.getMessageResources(
    48              "org.apache.struts.taglib.logic.LocalStrings");
    49  
    50      // ------------------------------------------------------------- Properties
    51  
    52      /**
    53       * The anchor to be added to the end of the generated hyperlink.
    54       */
    55      protected String anchor = null;
    56  
    57      /**
    58       * The logical forward name from which to retrieve the redirect URI.
    59       */
    60      protected String forward = null;
    61  
    62      /**
    63       * The redirect URI.
    64       */
    65      protected String href = null;
    66  
    67      /**
    68       * The JSP bean name for query parameters.
    69       */
    70      protected String name = null;
    71  
    72      /**
    73       * The module-relative page URL (beginning with a slash) to which this
    74       * redirect will be rendered.
    75       */
    76      protected String page = null;
    77  
    78      /**
    79       * The module-relative action (beginning with a slash) which will be
    80       * called by this link
    81       */
    82      protected String action = null;
    83  
    84      /**
    85       * The module prefix (beginning with a slash) which will be used to find
    86       * the action for this link.
    87       */
    88      protected String module = null;
    89  
    90      /**
    91       * The single-parameter request parameter name to generate.
    92       */
    93      protected String paramId = null;
    94  
    95      /**
    96       * The single-parameter JSP bean name.
    97       */
    98      protected String paramName = null;
    99  
    100     /**
    101      * The single-parameter JSP bean property.
    102      */
    103     protected String paramProperty = null;
    104 
    105     /**
    106      * The single-parameter JSP bean scope.
    107      */
    108     protected String paramScope = null;
    109 
    110     /**
    111      * The JSP bean property name for query parameters.
    112      */
    113     protected String property = null;
    114 
    115     /**
    116      * The scope of the bean specified by the name property, if any.
    117      */
    118     protected String scope = null;
    119 
    120     /**
    121      * Include our transaction control token?
    122      */
    123     protected boolean transaction = false;
    124 
    125     /**
    126      * Use character encoding from ServletResponse#getCharacterEncoding to get
    127      * bytes of the url string for urlencoding?
    128      */
    129     protected boolean useLocalEncoding = false;
    130 
    131     public String getAnchor() {
    132         return (this.anchor);
    133     }
    134 
    135     public void setAnchor(String anchor) {
    136         this.anchor = anchor;
    137     }
    138 
    139     public String getForward() {
    140         return (this.forward);
    141     }
    142 
    143     public void setForward(String forward) {
    144         this.forward = forward;
    145     }
    146 
    147     public String getHref() {
    148         return (this.href);
    149     }
    150 
    151     public void setHref(String href) {
    152         this.href = href;
    153     }
    154 
    155     public String getName() {
    156         return (this.name);
    157     }
    158 
    159     public void setName(String name) {
    160         this.name = name;
    161     }
    162 
    163     public String getPage() {
    164         return (this.page);
    165     }
    166 
    167     public void setPage(String page) {
    168         this.page = page;
    169     }
    170 
    171     public String getAction() {
    172         return (this.action);
    173     }
    174 
    175     public void setAction(String action) {
    176         this.action = action;
    177     }
    178 
    179     public String getModule() {
    180         return (this.module);
    181     }
    182 
    183     public void setModule(String module) {
    184         this.module = module;
    185     }
    186 
    187     public String getParamId() {
    188         return (this.paramId);
    189     }
    190 
    191     public void setParamId(String paramId) {
    192         this.paramId = paramId;
    193     }
    194 
    195     public String getParamName() {
    196         return (this.paramName);
    197     }
    198 
    199     public void setParamName(String paramName) {
    200         this.paramName = paramName;
    201     }
    202 
    203     public String getParamProperty() {
    204         return (this.paramProperty);
    205     }
    206 
    207     public void setParamProperty(String paramProperty) {
    208         this.paramProperty = paramProperty;
    209     }
    210 
    211     public String getParamScope() {
    212         return (this.paramScope);
    213     }
    214 
    215     public void setParamScope(String paramScope) {
    216         this.paramScope = paramScope;
    217     }
    218 
    219     public String getProperty() {
    220         return (this.property);
    221     }
    222 
    223     public void setProperty(String property) {
    224         this.property = property;
    225     }
    226 
    227     public String getScope() {
    228         return (this.scope);
    229     }
    230 
    231     public void setScope(String scope) {
    232         this.scope = scope;
    233     }
    234 
    235     public boolean getTransaction() {
    236         return (this.transaction);
    237     }
    238 
    239     public void setTransaction(boolean transaction) {
    240         this.transaction = transaction;
    241     }
    242 
    243     public boolean isUseLocalEncoding() {
    244         return useLocalEncoding;
    245     }
    246 
    247     public void setUseLocalEncoding(boolean b) {
    248         useLocalEncoding = b;
    249     }
    250 
    251     // --------------------------------------------------------- Public Methods
    252 
    253     /**
    254      * Defer generation until the end of this tag is encountered.
    255      *
    256      * @throws JspException if a JSP exception has occurred
    257      */
    258     public int doStartTag() throws JspException {
    259         return (SKIP_BODY);
    260     }
    261 
    262     /**
    263      * Render the redirect and skip the remainder of this page.
    264      *
    265      * @throws JspException if a JSP exception has occurred
    266      */
    267     public int doEndTag() throws JspException {
    268         this.doRedirect(this.generateRedirectURL());
    269 
    270         return (SKIP_PAGE);
    271     }
    272 
    273     /**
    274      * Calculate the url to redirect to.
    275      *
    276      * @throws JspException
    277      * @since Struts 1.2
    278      */
    279     protected String generateRedirectURL()
    280         throws JspException {
    281         Map params =
    282             TagUtils.getInstance().computeParameters(pageContext, paramId,
    283                 paramName, paramProperty, paramScope, name, property, scope,
    284                 transaction);
    285 
    286         String url = null;
    287 
    288         try {
    289             url = TagUtils.getInstance().computeURLWithCharEncoding(pageContext,
    290                     forward, href, page, action, module, params, anchor, true,
    291                     useLocalEncoding);
    292         } catch (MalformedURLException e) {
    293             TagUtils.getInstance().saveException(pageContext, e);
    294             throw new JspException(messages.getMessage("redirect.url",
    295                     e.toString()));
    296         }
    297 
    298         return url;
    299     }
    300 
    301     /**
    302      * Redirect to the given url converting exceptions to JspException.
    303      *
    304      * @param url The path to redirect to.
    305      * @throws JspException
    306      * @since Struts 1.2
    307      */
    308     protected void doRedirect(String url)
    309         throws JspException {
    310         HttpServletResponse response =
    311             (HttpServletResponse) pageContext.getResponse();
    312 
    313         try {
    314             response.sendRedirect(url);
    315         } catch (IOException e) {
    316             TagUtils.getInstance().saveException(pageContext, e);
    317             throw new JspException(e.getMessage());
    318         }
    319     }
    320 
    321     /**
    322      * Release any acquired resources.
    323      */
    324     public void release() {
    325         super.release();
    326         anchor = null;
    327         forward = null;
    328         href = null;
    329         name = null;
    330         page = null;
    331         action = null;
    332         paramId = null;
    333         paramName = null;
    334         paramProperty = null;
    335         paramScope = null;
    336         property = null;
    337         scope = null;
    338     }
    339 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
