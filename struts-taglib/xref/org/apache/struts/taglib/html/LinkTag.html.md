[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/LinkTag.html)


    1   /*
    2    * $Id: LinkTag.java 519563 2007-03-18 05:55:07Z pbenedict $
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
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.MessageResources;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  import java.net.MalformedURLException;
    29  
    30  import java.util.HashMap;
    31  import java.util.Map;
    32  
    33  /**
    34   * Generate a URL-encoded hyperlink to the specified URI.
    35   *
    36   * @version $Rev: 519563 $ $Date: 2005-04-06 02:37:00 -0400 (Wed, 06 Apr 2005)
    37   *          $
    38   */
    39  public class LinkTag extends BaseHandlerTag {
    40      /**
    41       * The message resources for this package.
    42       */
    43      protected static MessageResources messages =
    44          MessageResources.getMessageResources(Constants.Package
    45              + ".LocalStrings");
    46  
    47      // ----------------------------------------------------- Instance Variables
    48  
    49      /**
    50       * The body content of this tag (if any).
    51       */
    52      protected String text = null;
    53  
    54      // ------------------------------------------------------------- Properties
    55  
    56      /**
    57       * The anchor to be added to the end of the generated hyperlink.
    58       */
    59      protected String anchor = null;
    60  
    61      /**
    62       * <p>The logical forward name from which to retrieve the hyperlink
    63       * URI.</p> <p>Usage note: If a forward config is used in a hyperlink, and
    64       * a module is specified, the path must lead to another action and not
    65       * directly to a page. This is in keeping with rule that in a modular
    66       * application all links must be to an action rather than a page. </p>
    67       */
    68      protected String forward = null;
    69  
    70      /**
    71       * The hyperlink URI.
    72       */
    73      protected String href = null;
    74  
    75      /**
    76       * The link name for named links.
    77       */
    78      protected String linkName = null;
    79  
    80      /**
    81       * The JSP bean name for query parameters.
    82       */
    83      protected String name = null;
    84  
    85      /**
    86       * The module-relative page URL (beginning with a slash) to which this
    87       * hyperlink will be rendered.
    88       */
    89      protected String page = null;
    90  
    91      /**
    92       * The module-relative action (beginning with a slash) which will be
    93       * called by this link
    94       */
    95      protected String action = null;
    96  
    97      /**
    98       * The module prefix (beginning with a slash) which will be used to find
    99       * the action for this link.
    100      */
    101     protected String module = null;
    102 
    103     /**
    104      * The single-parameter request parameter name to generate.
    105      */
    106     protected String paramId = null;
    107 
    108     /**
    109      * The single-parameter JSP bean name.
    110      */
    111     protected String paramName = null;
    112 
    113     /**
    114      * The single-parameter JSP bean property.
    115      */
    116     protected String paramProperty = null;
    117 
    118     /**
    119      * The single-parameter JSP bean scope.
    120      */
    121     protected String paramScope = null;
    122 
    123     /**
    124      * The JSP bean property name for query parameters.
    125      */
    126     protected String property = null;
    127 
    128     /**
    129      * The scope of the bean specified by the name property, if any.
    130      */
    131     protected String scope = null;
    132 
    133     /**
    134      * The window target.
    135      */
    136     protected String target = null;
    137 
    138     /**
    139      * Include transaction token (if any) in the hyperlink?
    140      */
    141     protected boolean transaction = false;
    142 
    143     /**
    144      * Additional parameters included programatically.
    145      */
    146     protected Map parameters = new HashMap();
    147 
    148     /**
    149      * Name of parameter to generate to hold index number
    150      */
    151     protected String indexId = null;
    152     protected boolean useLocalEncoding = false;
    153 
    154     // ----------------------------------------------------- Constructor
    155     public LinkTag() {
    156         super();
    157         doDisabled = false;
    158     }
    159 
    160     public String getAnchor() {
    161         return (this.anchor);
    162     }
    163 
    164     public void setAnchor(String anchor) {
    165         this.anchor = anchor;
    166     }
    167 
    168     public String getForward() {
    169         return (this.forward);
    170     }
    171 
    172     public void setForward(String forward) {
    173         this.forward = forward;
    174     }
    175 
    176     public String getHref() {
    177         return (this.href);
    178     }
    179 
    180     public void setHref(String href) {
    181         this.href = href;
    182     }
    183 
    184     public String getLinkName() {
    185         return (this.linkName);
    186     }
    187 
    188     public void setLinkName(String linkName) {
    189         this.linkName = linkName;
    190     }
    191 
    192     public String getName() {
    193         return (this.name);
    194     }
    195 
    196     public void setName(String name) {
    197         this.name = name;
    198     }
    199 
    200     public String getPage() {
    201         return (this.page);
    202     }
    203 
    204     public void setPage(String page) {
    205         this.page = page;
    206     }
    207 
    208     public String getAction() {
    209         return (this.action);
    210     }
    211 
    212     public void setAction(String action) {
    213         this.action = action;
    214     }
    215 
    216     public String getModule() {
    217         return (this.module);
    218     }
    219 
    220     public void setModule(String module) {
    221         this.module = module;
    222     }
    223 
    224     public String getParamId() {
    225         return (this.paramId);
    226     }
    227 
    228     public void setParamId(String paramId) {
    229         this.paramId = paramId;
    230     }
    231 
    232     public String getParamName() {
    233         return (this.paramName);
    234     }
    235 
    236     public void setParamName(String paramName) {
    237         this.paramName = paramName;
    238     }
    239 
    240     public String getParamProperty() {
    241         return (this.paramProperty);
    242     }
    243 
    244     public void setParamProperty(String paramProperty) {
    245         this.paramProperty = paramProperty;
    246     }
    247 
    248     public String getParamScope() {
    249         return (this.paramScope);
    250     }
    251 
    252     public void setParamScope(String paramScope) {
    253         this.paramScope = paramScope;
    254     }
    255 
    256     public String getProperty() {
    257         return (this.property);
    258     }
    259 
    260     public void setProperty(String property) {
    261         this.property = property;
    262     }
    263 
    264     public String getScope() {
    265         return (this.scope);
    266     }
    267 
    268     public void setScope(String scope) {
    269         this.scope = scope;
    270     }
    271 
    272     public String getTarget() {
    273         return (this.target);
    274     }
    275 
    276     public void setTarget(String target) {
    277         this.target = target;
    278     }
    279 
    280     public boolean getTransaction() {
    281         return (this.transaction);
    282     }
    283 
    284     public void setTransaction(boolean transaction) {
    285         this.transaction = transaction;
    286     }
    287 
    288     public String getIndexId() {
    289         return (this.indexId);
    290     }
    291 
    292     public void setIndexId(String indexId) {
    293         this.indexId = indexId;
    294     }
    295 
    296     public boolean isUseLocalEncoding() {
    297         return useLocalEncoding;
    298     }
    299 
    300     public void setUseLocalEncoding(boolean b) {
    301         useLocalEncoding = b;
    302     }
    303 
    304     // --------------------------------------------------------- Public Methods
    305 
    306     /**
    307      * Render the beginning of the hyperlink. <p> Support for indexed property
    308      * since Struts 1.1
    309      *
    310      * @throws JspException if a JSP exception has occurred
    311      */
    312     public int doStartTag() throws JspException {
    313         this.text = null;
    314         this.parameters.clear();
    315 
    316         // Evaluate the body of this tag
    317         return (EVAL_BODY_TAG);
    318     }
    319 
    320     /**
    321      * Save the associated label from the body content.
    322      *
    323      * @throws JspException if a JSP exception has occurred
    324      */
    325     public int doAfterBody() throws JspException {
    326         if (bodyContent != null) {
    327             String value = bodyContent.getString().trim();
    328 
    329             if (value.length() > 0) {
    330                 text = value;
    331             }
    332         }
    333 
    334         return (SKIP_BODY);
    335     }
    336 
    337     /**
    338      * Render the end of the hyperlink.
    339      *
    340      * @throws JspException if a JSP exception has occurred
    341      */
    342     public int doEndTag() throws JspException {
    343         // Generate the opening anchor element
    344         StringBuffer results = new StringBuffer("<a");
    345 
    346         // Special case for name anchors
    347         prepareAttribute(results, "name", getLinkName());
    348 
    349         // * @since Struts 1.1
    350         if ((getLinkName() == null) || (getForward() != null)
    351             || (getHref() != null) || (getPage() != null)
    352             || (getAction() != null)) {
    353             prepareAttribute(results, "href", calculateURL());
    354         }
    355 
    356         prepareAttribute(results, "target", getTarget());
    357         prepareAttribute(results, "accesskey", getAccesskey());
    358         prepareAttribute(results, "tabindex", getTabindex());
    359         results.append(prepareStyles());
    360         results.append(prepareEventHandlers());
    361         prepareOtherAttributes(results);
    362         results.append(">");
    363 
    364         // Prepare the textual content and ending element of this hyperlink
    365         if (text != null) {
    366             results.append(text);
    367         }
    368         results.append("</a>");
    369         TagUtils.getInstance().write(pageContext, results.toString());
    370 
    371         return (EVAL_PAGE);
    372     }
    373 
    374     /**
    375      * Release any acquired resources.
    376      */
    377     public void release() {
    378         super.release();
    379         anchor = null;
    380         forward = null;
    381         href = null;
    382         linkName = null;
    383         name = null;
    384         page = null;
    385         action = null;
    386         module = null;
    387         paramId = null;
    388         paramName = null;
    389         paramProperty = null;
    390         paramScope = null;
    391         parameters.clear();
    392         property = null;
    393         scope = null;
    394         target = null;
    395         text = null;
    396         transaction = false;
    397         indexId = null;
    398         useLocalEncoding = false;
    399     }
    400 
    401     // ------------------------------------------------------ Protected Methods
    402 
    403     /**
    404      * Return the complete URL to which this hyperlink will direct the user.
    405      * Support for indexed property since Struts 1.1
    406      *
    407      * @throws JspException if an exception is thrown calculating the value
    408      */
    409     protected String calculateURL()
    410         throws JspException {
    411         // Identify the parameters we will add to the completed URL
    412         Map params =
    413             TagUtils.getInstance().computeParameters(pageContext, paramId,
    414                 paramName, paramProperty, paramScope, name, property, scope,
    415                 transaction);
    416 
    417         // Add parameters collected from the tag's inner body
    418         if (!this.parameters.isEmpty()) {
    419             if (params == null) {
    420                 params = new HashMap();
    421             }
    422             params.putAll(this.parameters);
    423         }
    424 
    425         // if "indexed=true", add "index=x" parameter to query string
    426         // * @since Struts 1.1
    427         if (indexed) {
    428             int indexValue = getIndexValue();
    429 
    430             //calculate index, and add as a parameter
    431             if (params == null) {
    432                 params = new HashMap(); //create new HashMap if no other params
    433             }
    434 
    435             if (indexId != null) {
    436                 params.put(indexId, Integer.toString(indexValue));
    437             } else {
    438                 params.put("index", Integer.toString(indexValue));
    439             }
    440         }
    441 
    442         String url = null;
    443 
    444         try {
    445             url = TagUtils.getInstance().computeURLWithCharEncoding(pageContext,
    446                     forward, href, page, action, module, params, anchor, false,
    447                     useLocalEncoding);
    448         } catch (MalformedURLException e) {
    449             TagUtils.getInstance().saveException(pageContext, e);
    450             throw new JspException(messages.getMessage("rewrite.url",
    451                     e.toString()));
    452         }
    453 
    454         return (url);
    455     }
    456 
    457     /**
    458      * <p>Adds a parameter to this link.</p>
    459      *
    460      * @param paramName the parameter name
    461      * @param paramValue the parameter value
    462      * @since Struts 1.3.6
    463      */
    464     public void addParameter(String paramName, Object paramValue) {
    465         this.parameters.put(paramName, paramValue);
    466     }
    467 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
