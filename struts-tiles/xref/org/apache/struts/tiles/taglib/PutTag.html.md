[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/PutTag.html.md)


    1   /*
    2    * $Id: PutTag.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.lang.reflect.InvocationTargetException;
    25  
    26  import javax.servlet.jsp.JspException;
    27  import javax.servlet.jsp.tagext.BodyTagSupport;
    28  
    29  import org.apache.commons.beanutils.PropertyUtils;
    30  import org.apache.struts.tiles.taglib.util.TagUtils;
    31  import org.apache.struts.tiles.AttributeDefinition;
    32  import org.apache.struts.tiles.DefinitionNameAttribute;
    33  import org.apache.struts.tiles.DirectStringAttribute;
    34  import org.apache.struts.tiles.PathAttribute;
    35  
    36  /**
    37   * Put an attribute in enclosing attribute container tag.
    38   * Enclosing attribute container tag can be : &lt;insert&gt; or &lt;definition&gt;.
    39   * Exception is thrown if no appropriate tag can be found.
    40   * Put tag can have following atributes :
    41   * <li>
    42   * <ul>name : Name of the attribute</ul>
    43   * <ul>value | content : value to put as attribute</ul>
    44   * <ul>type : value type. Only valid if value is a String and is set by
    45   * value="something" or by a bean.
    46   * Possible type are : string (value is used as direct string),
    47   * page | template (value is used as a page url to insert),
    48   * definition (value is used as a definition name to insert)</ul>
    49   * <ul>direct : Specify if value is to be used as a direct string or as a
    50   * page url to insert. This is another way to specify the type. It only apply
    51   * if value is set as a string, and type is not present.</ul>
    52   * <ul>beanName : Name of a bean used for setting value. Only valid if value is not set.
    53   * If property is specified, value come from bean's property. Otherwise, bean
    54   * itself is used for value.</ul>
    55   * <ul>beanProperty : Name of the property used for retrieving value.</ul>
    56   * <ul>beanScope : Scope containing bean. </ul>
    57   * <ul>role : Role to check when 'insert' will be called. If enclosing tag is
    58   * &lt;insert&gt;, role is checked immediately. If enclosing tag is
    59   * &lt;definition&gt;, role will be checked when this definition will be
    60   * inserted.</ul>
    61   * </li>
    62   * Value can also come from tag body. Tag body is taken into account only if
    63   * value is not set by one of the tag attributes. In this case Attribute type is
    64   * "string", unless tag body define another type.
    65   */
    66  public class PutTag extends BodyTagSupport implements ComponentConstants {
    67  
    68      /* JSP Tag attributes */
    69  
    70      /**
    71       * Name of attribute to put in component context.
    72       */
    73      protected String attributeName = null;
    74  
    75      /**
    76       * Associated attribute value.
    77       */
    78      private Object value = null;
    79  
    80      /**
    81       * JSP Template compatibility.
    82       */
    83      private String direct = null;
    84  
    85      /**
    86       * Requested type for the value.
    87       */
    88      private String valueType = null;
    89  
    90      /**
    91       * Bean name attribute.
    92       */
    93      private String beanName = null;
    94  
    95      /**
    96       * Bean property attribute.
    97       */
    98      private String beanProperty = null;
    99  
    100     /**
    101      * Bean scope attribute.
    102      */
    103     private String beanScope = null;
    104 
    105     /**
    106      * Role attribute.
    107      */
    108     private String role = null;
    109 
    110     /* Internal properties */
    111 
    112     /**
    113      * Cached real value computed from tag attributes.
    114      */
    115     protected Object realValue = null;
    116 
    117     /**
    118      * The body content of this tag.
    119      */
    120     protected String body = null;
    121 
    122     /**
    123      * Default constructor.
    124      */
    125     public PutTag() {
    126         super();
    127     }
    128 
    129     /**
    130      * Release all allocated resources.
    131      */
    132     public void release() {
    133 
    134         super.release();
    135 
    136         attributeName = null;
    137         valueType = null;
    138         direct = null;
    139         value = null;
    140         beanName = null;
    141         beanProperty = null;
    142         beanScope = null;
    143         role = null;
    144         body = null;
    145     }
    146 
    147     /**
    148      * Release internal properties.
    149      */
    150     protected void releaseInternal() {
    151         realValue = null;
    152     }
    153 
    154     /**
    155      * Set name.
    156      */
    157     public void setName(String value) {
    158         this.attributeName = value;
    159     }
    160 
    161     /**
    162      * Get name.
    163      */
    164     public String getName() {
    165         return attributeName;
    166     }
    167 
    168     /**
    169      * Set value.
    170      * Method added to satisfy Tomcat (bug ?).
    171      */
    172     public void setValue(String value) {
    173         this.value = value;
    174     }
    175 
    176     /**
    177      * Get value.
    178      * Method added to satisfy Tomcat (bug ?).
    179      */
    180     public String getValue() {
    181         return (String) this.value;
    182     }
    183 
    184     /**
    185      * Set value.
    186      */
    187     public void setValue(Object value) {
    188         this.value = value;
    189     }
    190 
    191     /**
    192      * Set property value as an object.
    193      * Added because some web containers react badly to value as <code>Object</code>.
    194      */
    195     public void setObjectValue(Object value) {
    196         this.value = value;
    197     }
    198 
    199     /**
    200      * Set content.
    201      * Method added to satisfy Tomcat (bug ?).
    202      */
    203     public void setContent(String value) {
    204         this.value = value;
    205     }
    206 
    207     /**
    208      * Get content.
    209      * Method added to satisfy Tomcat (bug ?).
    210      */
    211     public String getContent() {
    212         return (String) value;
    213     }
    214 
    215     /**
    216      * Set content.
    217      */
    218     public void setContent(Object value) {
    219         this.value = value;
    220     }
    221 
    222     /**
    223      * Set direct.
    224      * Method added for compatibility with JSP1.1.
    225      */
    226     public void setDirect(String isDirect) {
    227         this.direct = isDirect;
    228     }
    229 
    230     /**
    231      * Set type.
    232      */
    233     public void setType(String value) {
    234         this.valueType = value;
    235     }
    236 
    237     /**
    238      * Get type.
    239      */
    240     public String getType() {
    241         return this.valueType;
    242     }
    243 
    244     /**
    245      * Set bean name.
    246      */
    247     public void setBeanName(String value) {
    248         this.beanName = value;
    249     }
    250 
    251     /**
    252      * Get bean name.
    253      */
    254     public String getBeanName() {
    255         return beanName;
    256     }
    257 
    258     /**
    259      * Set bean property.
    260      */
    261     public void setBeanProperty(String value) {
    262         this.beanProperty = value;
    263     }
    264 
    265     /**
    266      * Get bean property.
    267      */
    268     public String getBeanProperty() {
    269         return beanProperty;
    270     }
    271 
    272     /**
    273      * Set bean scope.
    274      */
    275     public void setBeanScope(String value) {
    276         this.beanScope = value;
    277     }
    278 
    279     /**
    280      * Get bean scope.
    281      */
    282     public String getBeanScope() {
    283         return beanScope;
    284     }
    285 
    286     /**
    287      * Set role attribute.
    288      * @param role The role the user must be in to store content.
    289      */
    290     public void setRole(String role) {
    291         this.role = role;
    292     }
    293 
    294     /**
    295      * Get role attribute
    296      * @return The role defined in the tag or <code>null</code>.
    297      */
    298     public String getRole() {
    299         return role;
    300     }
    301 
    302     /**
    303      * Get real value according to tag attribute.
    304      * Real value is the value computed after attribute processing.
    305      * @return Real value.
    306      * @throws JspException If something goes wrong while getting value from bean.
    307      */
    308     public Object getRealValue() throws JspException {
    309         if (realValue == null) {
    310             computeRealValue();
    311         }
    312 
    313         return realValue;
    314     }
    315 
    316     /**
    317      * Compute real value according to tag attributes.
    318      * @throws JspException If something goes wrong while getting value from bean.
    319      */
    320     protected void computeRealValue() throws JspException {
    321         // Compute real value from attributes set.
    322         realValue = value;
    323 
    324         // If realValue is not set, value must come from body
    325         if (value == null && beanName == null) {
    326             // Test body content in case of empty body.
    327             if (body != null) {
    328                 realValue = body;
    329             } else {
    330                 realValue = "";
    331             }
    332         }
    333 
    334         // Does value comes from a bean ?
    335         if (realValue == null && beanName != null) {
    336             getRealValueFromBean();
    337             return;
    338         }
    339 
    340         // Is there a type set ?
    341         // First check direct attribute, and translate it to a valueType.
    342         // Then, evaluate valueType, and create requested typed attribute.
    343         // If valueType is not set, use the value "as is".
    344         if (valueType == null && direct != null) {
    345             if (Boolean.valueOf(direct).booleanValue() == true) {
    346                 valueType = "string";
    347             } else {
    348                 valueType = "page";
    349             }
    350         }
    351 
    352         if (realValue != null
    353             && valueType != null
    354             && !(value instanceof AttributeDefinition)) {
    355 
    356             String strValue = realValue.toString();
    357             if (valueType.equalsIgnoreCase("string")) {
    358                 realValue = new DirectStringAttribute(strValue);
    359 
    360             } else if (valueType.equalsIgnoreCase("page")) {
    361                 realValue = new PathAttribute(strValue);
    362 
    363             } else if (valueType.equalsIgnoreCase("template")) {
    364                 realValue = new PathAttribute(strValue);
    365 
    366             } else if (valueType.equalsIgnoreCase("instance")) {
    367                 realValue = new DefinitionNameAttribute(strValue);
    368 
    369             } else if (valueType.equalsIgnoreCase("definition")) {
    370                 realValue = new DefinitionNameAttribute(strValue);
    371 
    372             } else { // bad type
    373                 throw new JspException(
    374                     "Warning - Tag put : Bad type '" + valueType + "'.");
    375             }
    376         }
    377 
    378     }
    379 
    380     /**
    381      * Extract real value from specified bean.
    382      * @throws JspException If something goes wrong while getting value from bean.
    383      */
    384     protected void getRealValueFromBean() throws JspException {
    385         try {
    386             Object bean = TagUtils.retrieveBean(beanName, beanScope, pageContext);
    387             if (bean != null && beanProperty != null) {
    388                 realValue = PropertyUtils.getProperty(bean, beanProperty);
    389             } else {
    390                 realValue = bean; // value can be null
    391             }
    392 
    393         } catch (NoSuchMethodException ex) {
    394             throw new JspException(
    395                 "Error - component.PutAttributeTag : Error while retrieving value from bean '"
    396                     + beanName
    397                     + "' with property '"
    398                     + beanProperty
    399                     + "' in scope '"
    400                     + beanScope
    401                     + "'. (exception : "
    402                     + ex.getMessage(), ex);
    403 
    404         } catch (InvocationTargetException ex) {
    405             throw new JspException(
    406                 "Error - component.PutAttributeTag : Error while retrieving value from bean '"
    407                     + beanName
    408                     + "' with property '"
    409                     + beanProperty
    410                     + "' in scope '"
    411                     + beanScope
    412                     + "'. (exception : "
    413                     + ex.getMessage(), ex);
    414 
    415         } catch (IllegalAccessException ex) {
    416             throw new JspException(
    417                 "Error - component.PutAttributeTag : Error while retrieving value from bean '"
    418                     + beanName
    419                     + "' with property '"
    420                     + beanProperty
    421                     + "' in scope '"
    422                     + beanScope
    423                     + "'. (exception : "
    424                     + ex.getMessage(), ex);
    425         }
    426     }
    427 
    428     /**
    429      * Do start tag.
    430      */
    431     public int doStartTag() throws JspException {
    432 
    433         // clear body content
    434         body = null;
    435 
    436         // Do we need to evaluate body ?
    437         if (value == null && beanName == null) {
    438             return EVAL_BODY_TAG;
    439         }
    440 
    441         // Value is set, don't evaluate body.
    442         return SKIP_BODY;
    443     }
    444 
    445     /**
    446      * Save the body content of this tag (if any)
    447      *
    448      * @exception JspException if a JSP exception has occurred
    449      */
    450     public int doAfterBody() throws JspException {
    451 
    452         if (bodyContent != null) {
    453             body = bodyContent.getString();
    454         }
    455         return (SKIP_BODY);
    456 
    457     }
    458 
    459     /**
    460      * Do end tag.
    461      */
    462     public int doEndTag() throws JspException {
    463         // Call parent tag which in turn does what it want
    464         callParent();
    465 
    466         // clean up tag handler for reuse.
    467         releaseInternal();
    468 
    469         return EVAL_PAGE;
    470     }
    471 
    472     /**
    473      * Find parent tag which must implement AttributeContainer.
    474      * @throws JspException If we can't find an appropriate enclosing tag.
    475      */
    476     protected void callParent() throws JspException {
    477         // Get enclosing parent
    478         PutTagParent enclosingParent = findEnclosingPutTagParent();
    479         enclosingParent.processNestedTag(this);
    480     }
    481 
    482     /**
    483      * Find parent tag which must implement AttributeContainer.
    484      * @throws JspException If we can't find an appropriate enclosing tag.
    485      */
    486     protected PutTagParent findEnclosingPutTagParent() throws JspException {
    487         try {
    488             PutTagParent parent =
    489                 (PutTagParent) findAncestorWithClass(this, PutTagParent.class);
    490 
    491             if (parent == null) {
    492                 throw new JspException("Error - tag put : enclosing tag doesn't accept 'put' tag.");
    493             }
    494 
    495             return parent;
    496 
    497         } catch (ClassCastException ex) {
    498             throw new JspException("Error - tag put : enclosing tag doesn't accept 'put' tag.", ex);
    499         }
    500     }
    501 
    502 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
