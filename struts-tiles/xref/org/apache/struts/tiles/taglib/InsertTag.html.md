[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/InsertTag.html.md)


    1   /*
    2    * $Id: InsertTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.tiles.taglib;
    23  
    24  import java.io.IOException;
    25  import java.io.PrintWriter;
    26  import java.util.Map;
    27  import java.util.StringTokenizer;
    28  
    29  import javax.servlet.ServletException;
    30  import javax.servlet.http.HttpServletRequest;
    31  import javax.servlet.http.HttpServletResponse;
    32  import javax.servlet.jsp.JspException;
    33  import javax.servlet.jsp.PageContext;
    34  
    35  import org.apache.commons.logging.Log;
    36  import org.apache.commons.logging.LogFactory;
    37  import org.apache.struts.Globals;
    38  import org.apache.struts.tiles.taglib.util.TagUtils;
    39  import org.apache.struts.tiles.AttributeDefinition;
    40  import org.apache.struts.tiles.ComponentContext;
    41  import org.apache.struts.tiles.ComponentDefinition;
    42  import org.apache.struts.tiles.Controller;
    43  import org.apache.struts.tiles.DefinitionAttribute;
    44  import org.apache.struts.tiles.DefinitionNameAttribute;
    45  import org.apache.struts.tiles.DefinitionsFactoryException;
    46  import org.apache.struts.tiles.DirectStringAttribute;
    47  import org.apache.struts.tiles.FactoryNotFoundException;
    48  import org.apache.struts.tiles.NoSuchDefinitionException;
    49  import org.apache.struts.tiles.TilesUtil;
    50  
    51  /**
    52   * This is the tag handler for &lt;tiles:insert&gt;, which includes
    53   * a template. The tag's body content consists of &lt;tiles:put&gt;
    54   * tags, which are accessed by &lt;tiles:get&gt; in the template.
    55   *
    56   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    57   */
    58  public class InsertTag
    59      extends DefinitionTagSupport
    60      implements PutTagParent, ComponentConstants, PutListTagParent {
    61  
    62      /**
    63       * The role delimiter.
    64       * @deprecated This will be removed in a release after Struts 1.2.
    65       */
    66      public static final String ROLE_DELIMITER = ",";
    67  
    68      /**
    69       * Commons Logging instance.
    70       */
    71      protected static Log log = LogFactory.getLog(InsertTag.class);
    72  
    73      /* JSP Tag attributes */
    74  
    75      /**
    76       * Flush attribute value.
    77       */
    78      protected boolean flush = true;
    79  
    80      /**
    81       * Name to insert.
    82       */
    83      protected String name = null;
    84  
    85      /**
    86       * Name of attribute from which to read page name to include.
    87       */
    88      protected String attribute = null;
    89  
    90      /**
    91       * Name of bean used as entity to include.
    92       */
    93      protected String beanName = null;
    94  
    95      /**
    96       * Name of bean property, if any.
    97       */
    98      protected String beanProperty = null;
    99  
    100     /**
    101      * Scope of bean, if any.
    102      */
    103     protected String beanScope = null;
    104 
    105     /**
    106      * Are errors ignored. This is the property for attribute 'ignore'.
    107      * Default value is false, which throw an exception.
    108      * Only 'attribute not found' errors are ignored.
    109      */
    110     protected boolean isErrorIgnored = false;
    111 
    112     /**
    113      * Name of component instance to include.
    114      */
    115     protected String definitionName = null;
    116 
    117     /* Internal properties */
    118     /**
    119      * Does the end tag need to be processed.
    120      * Default value is true. Boolean set in case of ignored errors.
    121      */
    122     protected boolean processEndTag = true;
    123 
    124     /**
    125      * Current component context.
    126      */
    127     protected ComponentContext cachedCurrentContext;
    128 
    129     /**
    130      * Final handler of tag methods.
    131      */
    132     protected TagHandler tagHandler = null;
    133 
    134     /**
    135      * Trick to allows inner classes to access pageContext.
    136      */
    137     protected PageContext pageContext = null;
    138 
    139     /**
    140      * Reset member values for reuse. This method calls super.release(),
    141      * which invokes TagSupport.release(), which typically does nothing.
    142      */
    143     public void release() {
    144 
    145         super.release();
    146         attribute = null;
    147         beanName = null;
    148         beanProperty = null;
    149         beanScope = null;
    150 
    151         definitionName = null;
    152         flush = true;
    153         name = null;
    154         page = null;
    155         role = null;
    156         isErrorIgnored = false;
    157 
    158         releaseInternal();
    159     }
    160 
    161     /**
    162      * Reset internal member values for reuse.
    163      */
    164     protected void releaseInternal() {
    165         cachedCurrentContext = null;
    166         processEndTag = true;
    167         // pageContext = null;  // orion doesn't set it between two tags
    168         tagHandler = null;
    169     }
    170 
    171     /**
    172      * Set the current page context.
    173      * Called by the page implementation prior to doStartTag().
    174      * <p>
    175      * Needed to allow inner classes to access pageContext.
    176      */
    177     public void setPageContext(PageContext pc) {
    178         this.pageContext = pc;
    179         super.setPageContext(pc);
    180     }
    181 
    182     /**
    183      * Get the pageContext property.
    184      */
    185     public PageContext getPageContext() {
    186         return pageContext;
    187     }
    188 
    189     /**
    190      * Set name.
    191      */
    192     public void setName(String value) {
    193         this.name = value;
    194     }
    195 
    196     /**
    197      * Get name.
    198      */
    199     public String getName() {
    200         return name;
    201     }
    202 
    203     /**
    204      * Set component.
    205      */
    206     public void setComponent(String name) {
    207         this.page = name;
    208     }
    209 
    210     /**
    211      * Set definition.
    212      */
    213     public void setDefinition(String name) {
    214         this.definitionName = name;
    215     }
    216 
    217     /**
    218      * Get definition name.
    219      */
    220     public String getDefinitionName() {
    221         return definitionName;
    222     }
    223 
    224     /**
    225      * Set attribute.
    226      */
    227     public void setAttribute(String value) {
    228         this.attribute = value;
    229     }
    230 
    231     /**
    232      * Set bean name.
    233      */
    234     public void setBeanName(String value) {
    235         this.beanName = value;
    236     }
    237 
    238     /**
    239      * Get bean name.
    240      */
    241     public String getBeanName() {
    242         return beanName;
    243     }
    244 
    245     /**
    246      * Set bean property.
    247      */
    248     public void setBeanProperty(String value) {
    249         this.beanProperty = value;
    250     }
    251 
    252     /**
    253      * Get bean property.
    254      */
    255     public String getBeanProperty() {
    256         return beanProperty;
    257     }
    258 
    259     /**
    260      * Set bean scope.
    261      */
    262     public void setBeanScope(String value) {
    263         this.beanScope = value;
    264     }
    265 
    266     /**
    267      * Get bean scope.
    268      */
    269     public String getBeanScope() {
    270         return beanScope;
    271     }
    272 
    273     /**
    274      * Set flush.
    275      */
    276     public void setFlush(boolean flush) {
    277         this.flush = flush;
    278     }
    279 
    280     /**
    281      * Get flush.
    282      */
    283     public boolean getFlush() {
    284         return flush;
    285     }
    286 
    287     /**
    288      * Set flush.
    289      * Method added for compatibility with JSP1.1
    290      */
    291     public void setFlush(String flush) {
    292         this.flush = (Boolean.valueOf(flush).booleanValue());
    293     }
    294 
    295     /**
    296      * Set ignore.
    297      */
    298     public void setIgnore(boolean ignore) {
    299         this.isErrorIgnored = ignore;
    300     }
    301 
    302     /**
    303      * Get ignore.
    304      */
    305     public boolean getIgnore() {
    306         return isErrorIgnored;
    307     }
    308 
    309     /////////////////////////////////////////////////////////////////////////
    310 
    311     /**
    312      * Add a body attribute.
    313      * Erase any attribute with same name previously set.
    314      */
    315     public void putAttribute(String name, Object value) {
    316         tagHandler.putAttribute(name, value);
    317     }
    318 
    319     /**
    320      * Process nested &lg;put&gt; tag.
    321      * Method calls by nested &lg;put&gt; tags.
    322      * Nested list is added to current list.
    323      * If role is defined, it is checked immediately.
    324      */
    325     public void processNestedTag(PutTag nestedTag) throws JspException {
    326         // Check role
    327         HttpServletRequest request =
    328             (HttpServletRequest) pageContext.getRequest();
    329         String role = nestedTag.getRole();
    330         if (role != null && !request.isUserInRole(role)) {
    331             // not allowed : skip attribute
    332             return;
    333         }
    334 
    335         putAttribute(nestedTag.getName(), nestedTag.getRealValue());
    336     }
    337 
    338     /**
    339      * Process nested &lg;putList&gt; tag.
    340      * Method calls by nested &lg;putList&gt; tags.
    341      * Nested list is added to sub-component attributes
    342      * If role is defined, it is checked immediately.
    343      */
    344     public void processNestedTag(PutListTag nestedTag) throws JspException {
    345         // Check role
    346         HttpServletRequest request =
    347             (HttpServletRequest) pageContext.getRequest();
    348         String role = nestedTag.getRole();
    349         if (role != null && !request.isUserInRole(role)) {
    350             // not allowed : skip attribute
    351             return;
    352         }
    353 
    354         // Check if a name is defined
    355         if (nestedTag.getName() == null) {
    356             throw new JspException("Error - PutList : attribute name is not defined. It is mandatory as the list is added as attribute of 'insert'.");
    357         }
    358 
    359         // now add attribute to enclosing parent (i.e. : this object).
    360         putAttribute(nestedTag.getName(), nestedTag.getList());
    361     }
    362 
    363     /**
    364      * Method calls by nested &lg;putList&gt; tags.
    365      * A new list is added to current insert object.
    366      */
    367     public void putAttribute(PutListTag nestedTag) throws JspException {
    368         // Check role
    369         HttpServletRequest request =
    370             (HttpServletRequest) pageContext.getRequest();
    371         String role = nestedTag.getRole();
    372         if (role != null && !request.isUserInRole(role)) {
    373             // not allowed : skip attribute
    374             return;
    375         }
    376 
    377         putAttribute(nestedTag.getName(), nestedTag.getList());
    378     }
    379 
    380     /**
    381      * Get current component context.
    382      */
    383     private ComponentContext getCurrentContext() {
    384         if (cachedCurrentContext == null) {
    385             cachedCurrentContext =
    386                 (ComponentContext) pageContext.getAttribute(
    387                     ComponentConstants.COMPONENT_CONTEXT,
    388                     PageContext.REQUEST_SCOPE);
    389         }
    390 
    391         return cachedCurrentContext;
    392     }
    393 
    394     /**
    395      * Get instantiated Controller.
    396      * Return controller denoted by controllerType, or <code>null</code> if controllerType
    397      * is null.
    398      * @throws JspException If controller can't be created.
    399      */
    400     private Controller getController() throws JspException {
    401         if (controllerType == null) {
    402             return null;
    403         }
    404 
    405         try {
    406             return ComponentDefinition.createController(
    407                 controllerName,
    408                 controllerType);
    409 
    410         } catch (InstantiationException ex) {
    411             throw new JspException(ex);
    412         }
    413     }
    414 
    415     /**
    416      * Process the start tag by checking tag's attributes and creating appropriate handler.
    417      * Possible handlers :
    418      * <ul>
    419      * <li> URL
    420      * <li> definition
    421      * <li> direct String
    422      * </ul>
    423      * Handlers also contain sub-component context.
    424      */
    425     public int doStartTag() throws JspException {
    426 
    427             // Additional fix for Bug 20034 (2005-04-28)
    428             cachedCurrentContext = null;
    429 
    430         // Check role immediatly to avoid useless stuff.
    431         // In case of insertion of a "definition", definition's role still checked later.
    432         // This lead to a double check of "role" ;-(
    433         HttpServletRequest request =
    434             (HttpServletRequest) pageContext.getRequest();
    435         if (role != null && !request.isUserInRole(role)) {
    436             processEndTag = false;
    437             return SKIP_BODY;
    438         }
    439 
    440         try {
    441             tagHandler = createTagHandler();
    442 
    443         } catch (JspException e) {
    444             if (isErrorIgnored) {
    445                 processEndTag = false;
    446                 return SKIP_BODY;
    447             } else {
    448                 throw e;
    449             }
    450         }
    451 
    452         return tagHandler.doStartTag();
    453     }
    454 
    455     /**
    456      * Process the end tag by including the template.
    457      * Simply call the handler doEndTag
    458      */
    459     public int doEndTag() throws JspException {
    460         if (!processEndTag) {
    461             releaseInternal();
    462             return EVAL_PAGE;
    463         }
    464 
    465         int res = tagHandler.doEndTag();
    466         // Reset properties used by object, in order to be able to reuse object.
    467         releaseInternal();
    468         return res;
    469     }
    470 
    471     /**
    472      * Process tag attribute and create corresponding tag handler.
    473      */
    474     public TagHandler createTagHandler() throws JspException {
    475         // Check each tag attribute.
    476         // page Url attribute must be the last checked  because it can appears concurrently
    477         // with others attributes.
    478         if (definitionName != null) {
    479             return processDefinitionName(definitionName);
    480         } else if (attribute != null) {
    481             return processAttribute(attribute);
    482         } else if (beanName != null) {
    483             return processBean(beanName, beanProperty, beanScope);
    484         } else if (name != null) {
    485             return processName(name);
    486         } else if (page != null) {
    487             return processUrl(page);
    488         } else {
    489             throw new JspException("Error - Tag Insert : At least one of the following attribute must be defined : template|page|attribute|definition|name|beanName. Check tag syntax");
    490         }
    491     }
    492 
    493     /**
    494      * Process an object retrieved as a bean or attribute.
    495      * Object can be a typed attribute, a String, or anything else.
    496      * If typed attribute, use associated type.
    497      * Otherwise, apply toString() on object, and use returned string as a name.
    498      * @throws JspException - Throws by underlying nested call to
    499      * processDefinitionName()
    500      */
    501     public TagHandler processObjectValue(Object value) throws JspException {
    502         // First, check if value is one of the Typed Attribute
    503         if (value instanceof AttributeDefinition) {
    504             // We have a type => return appropriate IncludeType
    505             return processTypedAttribute((AttributeDefinition) value);
    506 
    507         } else if (value instanceof ComponentDefinition) {
    508             return processDefinition((ComponentDefinition) value);
    509         }
    510 
    511         // Value must denote a valid String
    512         return processAsDefinitionOrURL(value.toString());
    513     }
    514 
    515     /**
    516      * Process name.
    517      * Search in following order :
    518      * <ul>
    519      * <li>Component context -  if found, process it as value.</li>
    520      * <li>definitions factory</li>
    521      * <li>URL</li>
    522      * <li></li>
    523      * </ul>
    524      *
    525      * @return appropriate tag handler.
    526      * @throws JspException - Throws by underlying nested call to
    527      * processDefinitionName()
    528      */
    529     public TagHandler processName(String name) throws JspException {
    530         Object attrValue = getCurrentContext().getAttribute(name);
    531 
    532         if (attrValue != null) {
    533             return processObjectValue(attrValue);
    534         }
    535 
    536         return processAsDefinitionOrURL(name);
    537     }
    538 
    539     /**
    540      * Process the url.
    541      * @throws JspException If failed to create controller
    542      */
    543     public TagHandler processUrl(String url) throws JspException {
    544         return new InsertHandler(url, role, getController());
    545     }
    546 
    547     /**
    548      * Process tag attribute "definition".
    549      * First, search definition in the factory, then create handler from this definition.
    550      * @param name Name of the definition.
    551      * @return Appropriate TagHandler.
    552      * @throws JspException- NoSuchDefinitionException No Definition  found for name.
    553      * @throws JspException- FactoryNotFoundException Can't find Definitions factory.
    554      * @throws JspException- DefinedComponentFactoryException General error in factory.
    555      * @throws JspException InstantiationException Can't create requested controller
    556      */
    557     protected TagHandler processDefinitionName(String name)
    558         throws JspException {
    559 
    560         try {
    561             ComponentDefinition definition =
    562                 TilesUtil.getDefinition(
    563                     name,
    564                     (HttpServletRequest) pageContext.getRequest(),
    565                     pageContext.getServletContext());
    566 
    567             if (definition == null) { // is it possible ?
    568                 throw new NoSuchDefinitionException();
    569             }
    570 
    571             return processDefinition(definition);
    572 
    573         } catch (NoSuchDefinitionException ex) {
    574             throw new JspException(
    575                 "Error -  Tag Insert : Can't get definition '"
    576                     + definitionName
    577                     + "'. Check if this name exist in definitions factory.", ex);
    578 
    579         } catch (FactoryNotFoundException ex) {
    580             throw new JspException(ex.getMessage());
    581 
    582         } catch (DefinitionsFactoryException ex) {
    583             if (log.isDebugEnabled()) {
    584                 ex.printStackTrace();
    585             }
    586 
    587             // Save exception to be able to show it later
    588             pageContext.setAttribute(
    589                 Globals.EXCEPTION_KEY,
    590                 ex,
    591                 PageContext.REQUEST_SCOPE);
    592             throw new JspException(ex);
    593         }
    594     }
    595 
    596     /**
    597      * End of Process tag attribute "definition".
    598      * Overload definition with tag attributes "template" and "role".
    599      * Then, create appropriate tag handler.
    600      * @param definition Definition to process.
    601      * @return Appropriate TagHandler.
    602      * @throws JspException InstantiationException Can't create requested controller
    603      */
    604     protected TagHandler processDefinition(ComponentDefinition definition)
    605         throws JspException {
    606         // Declare local variable in order to not change Tag attribute values.
    607         String role = this.role;
    608         String page = this.page;
    609         Controller controller = null;
    610 
    611         try {
    612             controller = definition.getOrCreateController();
    613 
    614             // Overload definition with tag's template and role.
    615             if (role == null) {
    616                 role = definition.getRole();
    617             }
    618 
    619             if (page == null) {
    620                 page = definition.getTemplate();
    621             }
    622 
    623             if (controllerName != null) {
    624                 controller =
    625                     ComponentDefinition.createController(
    626                         controllerName,
    627                         controllerType);
    628             }
    629 
    630             // Can check if page is set
    631             return new InsertHandler(
    632                 definition.getAttributes(),
    633                 page,
    634                 role,
    635                 controller);
    636 
    637         } catch (InstantiationException ex) {
    638             throw new JspException(ex);
    639         }
    640     }
    641 
    642     /**
    643      * Process a bean.
    644      * Get bean value, eventually using property and scope. Found value is process by processObjectValue().
    645      * @param beanName Name of the bean
    646      * @param beanProperty Property in the bean, or null.
    647      * @param beanScope bean scope, or null.
    648      * @return Appropriate TagHandler.
    649      * @throws JspException - NoSuchDefinitionException No value associated to bean.
    650      * @throws JspException an error occur while reading bean, or no definition found.
    651      * @throws JspException - Throws by underlying nested call to processDefinitionName()
    652      */
    653     protected TagHandler processBean(
    654         String beanName,
    655         String beanProperty,
    656         String beanScope)
    657         throws JspException {
    658 
    659         Object beanValue =
    660             TagUtils.getRealValueFromBean(
    661                 beanName,
    662                 beanProperty,
    663                 beanScope,
    664                 pageContext);
    665 
    666         if (beanValue == null) {
    667             throw new JspException(
    668                 "Error - Tag Insert : No value defined for bean '"
    669                     + beanName
    670                     + "' with property '"
    671                     + beanProperty
    672                     + "' in scope '"
    673                     + beanScope
    674                     + "'.");
    675         }
    676 
    677         return processObjectValue(beanValue);
    678     }
    679 
    680     /**
    681      * Process tag attribute "attribute".
    682      * Get value from component attribute.
    683      * Found value is process by processObjectValue().
    684      * @param name Name of the attribute.
    685      * @return Appropriate TagHandler.
    686      * @throws JspException - NoSuchDefinitionException No Definition  found for name.
    687      * @throws JspException - Throws by underlying nested call to processDefinitionName()
    688      */
    689     public TagHandler processAttribute(String name) throws JspException {
    690         Object attrValue = getCurrentContext().getAttribute(name);
    691 
    692         if (attrValue == null) {
    693             throw new JspException(
    694                 "Error - Tag Insert : No value found for attribute '"
    695                     + name
    696                     + "'.");
    697         }
    698 
    699         return processObjectValue(attrValue);
    700     }
    701 
    702     /**
    703      * Try to process name as a definition, or as an URL if not found.
    704      * @param name Name to process.
    705      * @return appropriate TagHandler
    706      * @throws JspException InstantiationException Can't create requested controller
    707      */
    708     public TagHandler processAsDefinitionOrURL(String name)
    709         throws JspException {
    710         try {
    711             ComponentDefinition definition =
    712                 TilesUtil.getDefinition(
    713                     name,
    714                     pageContext.getRequest(),
    715                     pageContext.getServletContext());
    716 
    717             if (definition != null) {
    718                 return processDefinition(definition);
    719             }
    720 
    721         } catch (DefinitionsFactoryException ex) {
    722             // silently failed, because we can choose to not define a factory.
    723         }
    724 
    725         // no definition found, try as url
    726         return processUrl(name);
    727     }
    728 
    729     /**
    730      * Process typed attribute according to its type.
    731      * @param value Typed attribute to process.
    732      * @return appropriate TagHandler.
    733      * @throws JspException - Throws by underlying nested call to processDefinitionName()
    734      */
    735     public TagHandler processTypedAttribute(AttributeDefinition value)
    736         throws JspException {
    737         if (value instanceof DirectStringAttribute) {
    738             return new DirectStringHandler((String) value.getValue());
    739 
    740         } else if (value instanceof DefinitionAttribute) {
    741             return processDefinition((ComponentDefinition) value.getValue());
    742 
    743         } else if (value instanceof DefinitionNameAttribute) {
    744             return processDefinitionName((String) value.getValue());
    745         }
    746 
    747         return new InsertHandler(
    748             (String) value.getValue(),
    749             role,
    750             getController());
    751     }
    752 
    753     /**
    754      * Do an include of specified page.
    755      * This method is used internally to do all includes from this class. It delegates
    756      * the include call to the TilesUtil.doInclude().
    757      * @param page The page that will be included
    758      * @param flush If the writer should be flushed before the include
    759      * @throws ServletException - Thrown by call to pageContext.include()
    760      * @throws IOException - Thrown by call to pageContext.include()
    761      */
    762     protected void doInclude(String page, boolean flush)
    763         throws ServletException, IOException {
    764         TilesUtil.doInclude(page, pageContext, flush);
    765     }
    766 
    767     /////////////////////////////////////////////////////////////////////////////
    768 
    769     /**
    770      * Inner Interface.
    771      * Sub handler for tag.
    772      */
    773     protected interface TagHandler {
    774         /**
    775          * Create ComponentContext for type depicted by implementation class.
    776          */
    777         public int doStartTag() throws JspException;
    778         /**
    779          * Do include for type depicted by implementation class.
    780          */
    781         public int doEndTag() throws JspException;
    782         /**
    783          * Add a component parameter (attribute) to subContext.
    784          */
    785         public void putAttribute(String name, Object value);
    786     } // end inner interface
    787 
    788     /////////////////////////////////////////////////////////////////////////////
    789 
    790     /**
    791      * Real handler, after attribute resolution.
    792      * Handle include sub-component.
    793      */
    794     protected class InsertHandler implements TagHandler {
    795         protected String page;
    796         protected ComponentContext currentContext;
    797         protected ComponentContext subCompContext;
    798         protected String role;
    799         protected Controller controller;
    800 
    801         /**
    802          * Constructor.
    803          * Create insert handler using Component definition.
    804          */
    805         public InsertHandler(
    806             Map attributes,
    807             String page,
    808             String role,
    809             Controller controller) {
    810 
    811             this.page = page;
    812             this.role = role;
    813             this.controller = controller;
    814             subCompContext = new ComponentContext(attributes);
    815         }
    816 
    817         /**
    818          * Constructor.
    819          * Create insert handler to insert page at specified location.
    820          */
    821         public InsertHandler(String page, String role, Controller controller) {
    822             this.page = page;
    823             this.role = role;
    824             this.controller = controller;
    825             subCompContext = new ComponentContext();
    826         }
    827 
    828         /**
    829          * Create a new empty context.
    830          */
    831         public int doStartTag() throws JspException {
    832             // Check role
    833             HttpServletRequest request =
    834                 (HttpServletRequest) pageContext.getRequest();
    835 
    836             if (role != null && !request.isUserInRole(role)) {
    837                 return SKIP_BODY;
    838             }
    839 
    840             // save current context
    841             this.currentContext = getCurrentContext();
    842             return EVAL_BODY_INCLUDE;
    843         }
    844 
    845         /**
    846          * Add attribute to sub context.
    847          * Do nothing.
    848          */
    849         public void putAttribute(String name, Object value) {
    850             subCompContext.putAttribute(name, value);
    851         }
    852 
    853         /**
    854          * Include requested page.
    855          */
    856         public int doEndTag() throws JspException {
    857             // Check role
    858             HttpServletRequest request =
    859                 (HttpServletRequest) pageContext.getRequest();
    860 
    861             if (role != null && !request.isUserInRole(role)) {
    862                 return EVAL_PAGE;
    863             }
    864 
    865             try {
    866                 if (log.isDebugEnabled()) {
    867                     log.debug("insert page='" + page + "'.");
    868                 }
    869 
    870                 // set new context for included component.
    871                 pageContext.setAttribute(
    872                     ComponentConstants.COMPONENT_CONTEXT,
    873                     subCompContext,
    874                     PageContext.REQUEST_SCOPE);
    875 
    876                 // Call controller if any
    877                 if (controller != null) {
    878                     try {
    879                         controller.execute(
    880                             subCompContext,
    881                             (HttpServletRequest) pageContext.getRequest(),
    882                             (HttpServletResponse) pageContext.getResponse(),
    883                             pageContext.getServletContext());
    884 
    885                     } catch (Exception e) {
    886                         throw new ServletException(e);
    887                     }
    888 
    889                 }
    890 
    891                 // include requested component.
    892                 if (flush) {
    893                     pageContext.getOut().flush();
    894                 }
    895 
    896                 doInclude(page, flush);
    897 
    898             } catch (IOException e) {
    899                 String msg =
    900                     "Can't insert page '" + page + "' : " + e.getMessage();
    901                 log.error(msg, e);
    902                 throw new JspException(msg);
    903 
    904             } catch (IllegalArgumentException e) {
    905                 // Can't resolve page uri, should we ignore it?
    906                 if (!(page == null && isErrorIgnored)) {
    907                     String msg =
    908                         "Can't insert page '"
    909                             + page
    910                             + "'. Check if it exists.\n"
    911                             + e.getMessage();
    912 
    913                     log.error(msg, e);
    914                     throw new JspException(msg,e);
    915                 }
    916 
    917             } catch (ServletException e) {
    918                 Throwable cause = e;
    919                 if (e.getRootCause() != null) {
    920                     cause = e.getRootCause();
    921                 }
    922 
    923                 String msg =
    924                     "ServletException in '" + page + "': " + cause.getMessage();
    925 
    926                 log.error(msg, e);
    927                 throw new JspException(msg,e);
    928 
    929             } finally {
    930                 // restore old context only if currentContext not null
    931                 // (bug with Silverstream ?; related by Arvindra Sehmi 20010712)
    932                 if (currentContext != null) {
    933                     pageContext.setAttribute(
    934                         ComponentConstants.COMPONENT_CONTEXT,
    935                         currentContext,
    936                         PageContext.REQUEST_SCOPE);
    937                 }
    938             }
    939 
    940             return EVAL_PAGE;
    941         }
    942 
    943         /**
    944          * Process an exception.
    945          * Depending of debug attribute, print full exception trace or only
    946          * its message in output page.
    947          * @param ex Exception
    948          * @param msg An additional message to show in console and to propagate if we can't output exception.
    949          * @deprecated This method will be removed in a release after Struts 1.2.
    950          */
    951         protected void processException(Throwable ex, String msg)
    952             throws JspException {
    953 
    954             try {
    955                 if (msg == null) {
    956                     msg = ex.getMessage();
    957                 }
    958 
    959                 if (log.isDebugEnabled()) { // show full trace
    960                     log.debug(msg, ex);
    961                     pageContext.getOut().println(msg);
    962                     ex.printStackTrace(
    963                         new PrintWriter(pageContext.getOut(), true));
    964                 } else { // show only message
    965                     pageContext.getOut().println(msg);
    966                 }
    967 
    968             } catch (IOException ioex) { // problems. Propagate original exception
    969                 pageContext.setAttribute(
    970                     ComponentConstants.EXCEPTION_KEY,
    971                     ex,
    972                     PageContext.REQUEST_SCOPE);
    973                 throw new JspException(msg,ioex);
    974             }
    975         }
    976     }
    977 
    978     /**
    979      * Parse the list of roles and return <code>true</code> or <code>false</code> based on whether
    980      * the user has that role or not.
    981      * @param role Comma-delimited list of roles.
    982      * @param request The request.
    983      */
    984     static public boolean userHasRole(
    985         HttpServletRequest request,
    986         String role) {
    987         StringTokenizer st = new StringTokenizer(role, ",");
    988         while (st.hasMoreTokens()) {
    989             if (request.isUserInRole(st.nextToken())) {
    990                 return true;
    991             }
    992         }
    993 
    994         return false;
    995     }
    996 
    997     /////////////////////////////////////////////////////////////////////////////
    998 
    999     /**
    1000      * Handle insert direct string.
    1001      */
    1002     protected class DirectStringHandler implements TagHandler {
    1003         /** Object to print as a direct string */
    1004         private Object value;
    1005 
    1006         /**
    1007          * Constructor.
    1008          */
    1009         public DirectStringHandler(Object value) {
    1010             this.value = value;
    1011         }
    1012 
    1013         /**
    1014          * Do nothing, there is no context for a direct string.
    1015          */
    1016         public int doStartTag() throws JspException {
    1017             return SKIP_BODY;
    1018         }
    1019 
    1020         /**
    1021          * Add attribute to sub context.
    1022          * Do nothing.
    1023          */
    1024         public void putAttribute(String name, Object value) {
    1025         }
    1026 
    1027         /**
    1028          * Print String in page output stream.
    1029          */
    1030         public int doEndTag() throws JspException {
    1031             try {
    1032                 if (flush) {
    1033                     pageContext.getOut().flush();
    1034                 }
    1035 
    1036                 pageContext.getOut().print(value);
    1037 
    1038             } catch (IOException ex) {
    1039                 if (log.isDebugEnabled()) {
    1040                     log.debug("Can't write string '" + value + "' : ", ex);
    1041                 }
    1042 
    1043                 pageContext.setAttribute(
    1044                     ComponentConstants.EXCEPTION_KEY,
    1045                     ex,
    1046                     PageContext.REQUEST_SCOPE);
    1047 
    1048                 throw new JspException(
    1049                     "Can't write string '" + value + "' : " + ex.getMessage(), ex);
    1050             }
    1051 
    1052             return EVAL_PAGE;
    1053         }
    1054     }
    1055 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
