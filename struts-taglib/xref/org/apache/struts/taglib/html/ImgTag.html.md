[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/ImgTag.html)


    1   /*
    2    * $Id: ImgTag.java 552353 2007-07-01 19:04:12Z pbenedict $
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
    23  import org.apache.struts.config.ActionConfig;
    24  import org.apache.struts.config.ModuleConfig;
    25  import org.apache.struts.taglib.TagUtils;
    26  import org.apache.struts.util.MessageResources;
    27  import org.apache.struts.util.ModuleUtils;
    28  
    29  import javax.servlet.http.HttpServletRequest;
    30  import javax.servlet.http.HttpServletResponse;
    31  import javax.servlet.jsp.JspException;
    32  
    33  import java.util.Iterator;
    34  import java.util.Map;
    35  
    36  /**
    37   * <p>Generate an IMG tag to the specified image URI. </p>
    38   *
    39   * <p>TODO:</p>
    40   *
    41   * <ul>
    42   *
    43   * <li>Make the <strong>alt</strong> and <strong>src</strong> settable from
    44   * properties (for i18n)</li>
    45   *
    46   * </ul>
    47   *
    48   * @version $Rev: 552353 $
    49   */
    50  public class ImgTag extends BaseHandlerTag {
    51      /**
    52       * The message resources for this package.
    53       */
    54      protected static MessageResources messages =
    55          MessageResources.getMessageResources(Constants.Package
    56              + ".LocalStrings");
    57  
    58      // ------------------------------------------------------------- Properties
    59  
    60      /**
    61       * The property to specify where to align the image.
    62       */
    63      protected String align = null;
    64  
    65      /**
    66       * The border size around the image.
    67       */
    68      protected String border = null;
    69  
    70      /**
    71       * The image height.
    72       */
    73      protected String height = null;
    74  
    75      /**
    76       * The horizontal spacing around the image.
    77       */
    78      protected String hspace = null;
    79  
    80      /**
    81       * The image name for named images.
    82       */
    83      protected String imageName = null;
    84  
    85      /**
    86       * Server-side image map declaration.
    87       */
    88      protected String ismap = null;
    89  
    90      /**
    91       * The JSP bean name for query parameters.
    92       */
    93      protected String name = null;
    94  
    95      /**
    96       * The module-relative path, starting with a slash character, of the image
    97       * to be displayed by this rendered tag.
    98       */
    99      protected String page = null;
    100 
    101     /**
    102      * The message resources key under which we should look up the
    103      * <code>page</code> attribute for this generated tag, if any.
    104      */
    105     protected String pageKey = null;
    106 
    107     /**
    108      * The module-relative action (beginning with a slash) which will be used
    109      * as the source for this image.
    110      */
    111     protected String action = null;
    112 
    113     /**
    114      * The module prefix (beginning with a slash) which will be used to find
    115      * the action for this link.
    116      */
    117     protected String module = null;
    118 
    119     /**
    120      * In situations where an image is dynamically generated (such as to
    121      * create a chart graph), this specifies the single-parameter request
    122      * parameter name to generate.
    123      */
    124     protected String paramId = null;
    125 
    126     /**
    127      * The single-parameter JSP bean name.
    128      */
    129     protected String paramName = null;
    130 
    131     /**
    132      * The single-parameter JSP bean property.
    133      */
    134     protected String paramProperty = null;
    135 
    136     /**
    137      * The single-parameter JSP bean scope.
    138      */
    139     protected String paramScope = null;
    140 
    141     /**
    142      * The JSP bean property name for query parameters.
    143      */
    144     protected String property = null;
    145 
    146     /**
    147      * The scope of the bean specified by the name property, if any.
    148      */
    149     protected String scope = null;
    150 
    151     /**
    152      * The image source URI.
    153      */
    154     protected String src = null;
    155 
    156     /**
    157      * The message resources key under which we should look up the
    158      * <code>src</code> attribute for this generated tag, if any.
    159      */
    160     protected String srcKey = null;
    161 
    162     /**
    163      * Client-side image map declaration.
    164      */
    165     protected String usemap = null;
    166 
    167     /**
    168      * The vertical spacing around the image.
    169      */
    170     protected String vspace = null;
    171 
    172     /**
    173      * The image width.
    174      */
    175     protected String width = null;
    176     protected boolean useLocalEncoding = false;
    177 
    178     // ----------------------------------------------------- Constructor
    179     public ImgTag() {
    180         super();
    181         doDisabled = false;
    182     }
    183 
    184     public String getAlign() {
    185         return (this.align);
    186     }
    187 
    188     public void setAlign(String align) {
    189         this.align = align;
    190     }
    191 
    192     public String getBorder() {
    193         return (this.border);
    194     }
    195 
    196     public void setBorder(String border) {
    197         this.border = border;
    198     }
    199 
    200     public String getHeight() {
    201         return (this.height);
    202     }
    203 
    204     public void setHeight(String height) {
    205         this.height = height;
    206     }
    207 
    208     public String getHspace() {
    209         return (this.hspace);
    210     }
    211 
    212     public void setHspace(String hspace) {
    213         this.hspace = hspace;
    214     }
    215 
    216     public String getImageName() {
    217         return (this.imageName);
    218     }
    219 
    220     public void setImageName(String imageName) {
    221         this.imageName = imageName;
    222     }
    223 
    224     public String getIsmap() {
    225         return (this.ismap);
    226     }
    227 
    228     public void setIsmap(String ismap) {
    229         this.ismap = ismap;
    230     }
    231 
    232     public String getName() {
    233         return (this.name);
    234     }
    235 
    236     public void setName(String name) {
    237         this.name = name;
    238     }
    239 
    240     public String getPage() {
    241         return (this.page);
    242     }
    243 
    244     public void setPage(String page) {
    245         this.page = page;
    246     }
    247 
    248     public String getPageKey() {
    249         return (this.pageKey);
    250     }
    251 
    252     public void setPageKey(String pageKey) {
    253         this.pageKey = pageKey;
    254     }
    255 
    256     public String getAction() {
    257         return (this.action);
    258     }
    259 
    260     public void setAction(String action) {
    261         this.action = action;
    262     }
    263 
    264     public String getModule() {
    265         return (this.module);
    266     }
    267 
    268     public void setModule(String module) {
    269         this.module = module;
    270     }
    271 
    272     public String getParamId() {
    273         return (this.paramId);
    274     }
    275 
    276     public void setParamId(String paramId) {
    277         this.paramId = paramId;
    278     }
    279 
    280     public String getParamName() {
    281         return (this.paramName);
    282     }
    283 
    284     public void setParamName(String paramName) {
    285         this.paramName = paramName;
    286     }
    287 
    288     public String getParamProperty() {
    289         return (this.paramProperty);
    290     }
    291 
    292     public void setParamProperty(String paramProperty) {
    293         this.paramProperty = paramProperty;
    294     }
    295 
    296     public String getParamScope() {
    297         return (this.paramScope);
    298     }
    299 
    300     public void setParamScope(String paramScope) {
    301         this.paramScope = paramScope;
    302     }
    303 
    304     public String getProperty() {
    305         return (this.property);
    306     }
    307 
    308     public void setProperty(String property) {
    309         this.property = property;
    310     }
    311 
    312     public String getScope() {
    313         return (this.scope);
    314     }
    315 
    316     public void setScope(String scope) {
    317         this.scope = scope;
    318     }
    319 
    320     public String getSrc() {
    321         return (this.src);
    322     }
    323 
    324     public void setSrc(String src) {
    325         this.src = src;
    326     }
    327 
    328     public String getSrcKey() {
    329         return (this.srcKey);
    330     }
    331 
    332     public void setSrcKey(String srcKey) {
    333         this.srcKey = srcKey;
    334     }
    335 
    336     public String getUsemap() {
    337         return (this.usemap);
    338     }
    339 
    340     public void setUsemap(String usemap) {
    341         this.usemap = usemap;
    342     }
    343 
    344     public String getVspace() {
    345         return (this.vspace);
    346     }
    347 
    348     public void setVspace(String vspace) {
    349         this.vspace = vspace;
    350     }
    351 
    352     public String getWidth() {
    353         return (this.width);
    354     }
    355 
    356     public void setWidth(String width) {
    357         this.width = width;
    358     }
    359 
    360     public boolean isUseLocalEncoding() {
    361         return useLocalEncoding;
    362     }
    363 
    364     public void setUseLocalEncoding(boolean b) {
    365         useLocalEncoding = b;
    366     }
    367 
    368     // --------------------------------------------------------- Public Methods
    369 
    370     /**
    371      * Render the beginning of the IMG tag.
    372      *
    373      * @throws JspException if a JSP exception has occurred
    374      */
    375     public int doStartTag() throws JspException {
    376         // Evaluate the body of this tag
    377         return (EVAL_BODY_TAG);
    378     }
    379 
    380     /**
    381      * Render the end of the IMG tag.
    382      *
    383      * @throws JspException if a JSP exception has occurred
    384      */
    385     public int doEndTag() throws JspException {
    386         // Generate the name definition or image element
    387         HttpServletResponse response =
    388             (HttpServletResponse) pageContext.getResponse();
    389         StringBuffer results = new StringBuffer("<img");
    390         String tmp = src();
    391         String srcurl = url(tmp);
    392 
    393         if (srcurl != null) {
    394             prepareAttribute(results, "src", response.encodeURL(srcurl));
    395         }
    396 
    397         prepareAttribute(results, "name", getImageName());
    398         prepareAttribute(results, "height", getHeight());
    399         prepareAttribute(results, "width", getWidth());
    400         prepareAttribute(results, "align", getAlign());
    401         prepareAttribute(results, "border", getBorder());
    402         prepareAttribute(results, "hspace", getHspace());
    403         prepareAttribute(results, "vspace", getVspace());
    404         prepareAttribute(results, "ismap", getIsmap());
    405         prepareAttribute(results, "usemap", getUsemap());
    406         results.append(prepareStyles());
    407         results.append(prepareEventHandlers());
    408         prepareOtherAttributes(results);
    409         results.append(getElementClose());
    410 
    411         TagUtils.getInstance().write(pageContext, results.toString());
    412 
    413         return (EVAL_PAGE);
    414     }
    415 
    416     /**
    417      * Release any acquired resources.
    418      */
    419     public void release() {
    420         super.release();
    421 
    422         border = null;
    423         height = null;
    424         hspace = null;
    425         imageName = null;
    426         ismap = null;
    427         name = null;
    428         page = null;
    429         pageKey = null;
    430         action = null;
    431         paramId = null;
    432         paramName = null;
    433         paramProperty = null;
    434         paramScope = null;
    435         property = null;
    436         scope = null;
    437         src = null;
    438         srcKey = null;
    439         usemap = null;
    440         vspace = null;
    441         width = null;
    442     }
    443 
    444     // ------------------------------------------------------ Protected Methods
    445 
    446     /**
    447      * Convenience method to throw a "imgTag.src" exception.
    448      *
    449      * @throws JspException
    450      */
    451     private void throwImgTagSrcException()
    452         throws JspException {
    453         JspException e = new JspException(messages.getMessage("imgTag.src"));
    454 
    455         TagUtils.getInstance().saveException(pageContext, e);
    456         throw e;
    457     }
    458 
    459     /**
    460      * Convenience method to test whether this is the default module.
    461      *
    462      * @param config Our Moduleconfig
    463      * @return True if this is the default module or contextRelative is set
    464      */
    465     private boolean srcDefaultReference(ModuleConfig config) {
    466         return (config == null);
    467     }
    468 
    469     /**
    470      * Return the base source URL that will be rendered in the
    471      * <code>src</code> property for this generated element, or
    472      * <code>null</code> if there is no such URL.
    473      *
    474      * @throws JspException if an error occurs
    475      */
    476     protected String src() throws JspException {
    477         ModuleConfig moduleConfig =
    478             ModuleUtils.getInstance().getModuleConfig(this.module,
    479                 (HttpServletRequest) pageContext.getRequest(),
    480                 pageContext.getServletContext());
    481 
    482 
    483         // Deal with a direct context-relative page that has been specified
    484         if (this.page != null) {
    485             if ((this.src != null) || (this.srcKey != null)
    486                 || (this.pageKey != null)) {
    487                 throwImgTagSrcException();
    488             }
    489 
    490             HttpServletRequest request =
    491                 (HttpServletRequest) pageContext.getRequest();
    492             String pageValue = this.page;
    493 
    494             if (!srcDefaultReference(moduleConfig)) {
    495                 pageValue =
    496                     TagUtils.getInstance().pageURL(request, this.page, moduleConfig);
    497             }
    498 
    499             return (request.getContextPath() + pageValue);
    500         }
    501 
    502         // Deal with an indirect context-relative page that has been specified
    503         if (this.pageKey != null) {
    504             if ((this.src != null) || (this.srcKey != null)) {
    505                 throwImgTagSrcException();
    506             }
    507 
    508             HttpServletRequest request =
    509                 (HttpServletRequest) pageContext.getRequest();
    510             String pageValue =
    511                 TagUtils.getInstance().message(pageContext, getBundle(),
    512                     getLocale(), this.pageKey);
    513 
    514             if (!srcDefaultReference(moduleConfig)) {
    515                 pageValue =
    516                     TagUtils.getInstance().pageURL(request, pageValue, moduleConfig);
    517             }
    518 
    519             return (request.getContextPath() + pageValue);
    520         }
    521 
    522         if (this.action != null) {
    523             if ((this.src != null) || (this.srcKey != null)) {
    524                 throwImgTagSrcException();
    525             }
    526 
    527             // Translate the action if it is an actionId
    528             ActionConfig actionConfig = moduleConfig.findActionConfigId(this.action);
    529             if (actionConfig != null) {
    530                 action = actionConfig.getPath();
    531             }
    532 
    533             return TagUtils.getInstance().getActionMappingURL(action, module,
    534                 pageContext, false);
    535         }
    536 
    537         // Deal with an absolute source that has been specified
    538         if (this.src != null) {
    539             if (this.srcKey != null) {
    540                 throwImgTagSrcException();
    541             }
    542 
    543             return (this.src);
    544         }
    545 
    546         // Deal with an indirect source that has been specified
    547         if (this.srcKey == null) {
    548             throwImgTagSrcException();
    549         }
    550 
    551         return TagUtils.getInstance().message(pageContext, getBundle(),
    552             getLocale(), this.srcKey);
    553     }
    554 
    555     /**
    556      * Return the specified src URL, modified as necessary with optional
    557      * request parameters.
    558      *
    559      * @param url The URL to be modified (or null if this url will not be
    560      *            used)
    561      * @throws JspException if an error occurs preparing the URL
    562      */
    563     protected String url(String url)
    564         throws JspException {
    565         if (url == null) {
    566             return (url);
    567         }
    568 
    569         String charEncoding = "UTF-8";
    570 
    571         if (useLocalEncoding) {
    572             charEncoding = pageContext.getResponse().getCharacterEncoding();
    573         }
    574 
    575         // Start with an unadorned URL as specified
    576         StringBuffer src = new StringBuffer(url);
    577 
    578         // Append a single-parameter name and value, if requested
    579         if ((paramId != null) && (paramName != null)) {
    580             if (src.toString().indexOf('?') < 0) {
    581                 src.append('?');
    582             } else {
    583                 src.append("&amp;");
    584             }
    585 
    586             src.append(paramId);
    587             src.append('=');
    588 
    589             Object value =
    590                 TagUtils.getInstance().lookup(pageContext, paramName,
    591                     paramProperty, paramScope);
    592 
    593             if (value != null) {
    594                 src.append(TagUtils.getInstance().encodeURL(value.toString(),
    595                         charEncoding));
    596             }
    597         }
    598 
    599         // Just return the URL if there is no bean to look up
    600         if ((property != null) && (name == null)) {
    601             JspException e =
    602                 new JspException(messages.getMessage("getter.name"));
    603 
    604             TagUtils.getInstance().saveException(pageContext, e);
    605             throw e;
    606         }
    607 
    608         if (name == null) {
    609             return (src.toString());
    610         }
    611 
    612         // Look up the map we will be using
    613         Object mapObject =
    614             TagUtils.getInstance().lookup(pageContext, name, property, scope);
    615         Map map = null;
    616 
    617         try {
    618             map = (Map) mapObject;
    619         } catch (ClassCastException e) {
    620             TagUtils.getInstance().saveException(pageContext, e);
    621             throw new JspException(messages.getMessage("imgTag.type"));
    622         }
    623 
    624         // Append the required query parameters
    625         boolean question = (src.toString().indexOf("?") >= 0);
    626         Iterator keys = map.keySet().iterator();
    627 
    628         while (keys.hasNext()) {
    629             String key = (String) keys.next();
    630             Object value = map.get(key);
    631 
    632             if (value == null) {
    633                 if (question) {
    634                     src.append("&amp;");
    635                 } else {
    636                     src.append('?');
    637                     question = true;
    638                 }
    639 
    640                 src.append(key);
    641                 src.append('=');
    642 
    643                 // Interpret null as "no value specified"
    644             } else if (value instanceof String[]) {
    645                 String[] values = (String[]) value;
    646 
    647                 for (int i = 0; i < values.length; i++) {
    648                     if (question) {
    649                         src.append("&amp;");
    650                     } else {
    651                         src.append('?');
    652                         question = true;
    653                     }
    654 
    655                     src.append(key);
    656                     src.append('=');
    657                     src.append(TagUtils.getInstance().encodeURL(values[i],
    658                             charEncoding));
    659                 }
    660             } else {
    661                 if (question) {
    662                     src.append("&amp;");
    663                 } else {
    664                     src.append('?');
    665                     question = true;
    666                 }
    667 
    668                 src.append(key);
    669                 src.append('=');
    670                 src.append(TagUtils.getInstance().encodeURL(value.toString(),
    671                         charEncoding));
    672             }
    673         }
    674 
    675         // Return the final result
    676         return (src.toString());
    677     }
    678 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
