[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELOptionsCollectionTag.html)


    1   /*
    2    * $Id: ELOptionsCollectionTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.html.md;
    22  
    23  import org.apache.struts.taglib.html.md.OptionsCollectionTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for creating multiple &lt;select&gt; options from a collection. The
    30   * collection may be part of the enclosing form, or may be independent of the
    31   * form. Each element of the collection must expose a 'label' and a 'value',
    32   * the property names of which are configurable by attributes of this tag. <p>
    33   * The collection may be an array of objects, a Collection, an Enumeration, an
    34   * Iterator, or a Map. <p> <b>NOTE</b> - This tag requires a Java2 (JDK 1.2 or
    35   * later) platform. <p> This class is a subclass of the class
    36   * <code>org.apache.struts.taglib.html.md.OptionsCollectionTag</code> which
    37   * provides most of the described functionality.  This subclass allows all
    38   * attribute values to be specified as expressions utilizing the JavaServer
    39   * Pages Standard Library expression language.
    40   *
    41   * @version $Rev: 471754 $
    42   */
    43  public class ELOptionsCollectionTag extends OptionsCollectionTag {
    44      /**
    45       * Instance variable mapped to "filter" tag attribute. (Mapping set in
    46       * associated BeanInfo class.)
    47       */
    48      private String filterExpr;
    49  
    50      /**
    51       * Instance variable mapped to "label" tag attribute. (Mapping set in
    52       * associated BeanInfo class.)
    53       */
    54      private String labelExpr;
    55  
    56      /**
    57       * Instance variable mapped to "name" tag attribute. (Mapping set in
    58       * associated BeanInfo class.)
    59       */
    60      private String nameExpr;
    61  
    62      /**
    63       * Instance variable mapped to "property" tag attribute. (Mapping set in
    64       * associated BeanInfo class.)
    65       */
    66      private String propertyExpr;
    67  
    68      /**
    69       * Instance variable mapped to "style" tag attribute. (Mapping set in
    70       * associated BeanInfo class.)
    71       */
    72      private String styleExpr;
    73  
    74      /**
    75       * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    76       * associated BeanInfo class.)
    77       */
    78      private String styleClassExpr;
    79  
    80      /**
    81       * Instance variable mapped to "value" tag attribute. (Mapping set in
    82       * associated BeanInfo class.)
    83       */
    84      private String valueExpr;
    85  
    86      /**
    87       * Getter method for "filter" tag attribute. (Mapping set in associated
    88       * BeanInfo class.)
    89       */
    90      public String getFilterExpr() {
    91          return (filterExpr);
    92      }
    93  
    94      /**
    95       * Getter method for "label" tag attribute. (Mapping set in associated
    96       * BeanInfo class.)
    97       */
    98      public String getLabelExpr() {
    99          return (labelExpr);
    100     }
    101 
    102     /**
    103      * Getter method for "name" tag attribute. (Mapping set in associated
    104      * BeanInfo class.)
    105      */
    106     public String getNameExpr() {
    107         return (nameExpr);
    108     }
    109 
    110     /**
    111      * Getter method for "property" tag attribute. (Mapping set in associated
    112      * BeanInfo class.)
    113      */
    114     public String getPropertyExpr() {
    115         return (propertyExpr);
    116     }
    117 
    118     /**
    119      * Getter method for "style" tag attribute. (Mapping set in associated
    120      * BeanInfo class.)
    121      */
    122     public String getStyleExpr() {
    123         return (styleExpr);
    124     }
    125 
    126     /**
    127      * Getter method for "styleClass" tag attribute. (Mapping set in
    128      * associated BeanInfo class.)
    129      */
    130     public String getStyleClassExpr() {
    131         return (styleClassExpr);
    132     }
    133 
    134     /**
    135      * Getter method for "value" tag attribute. (Mapping set in associated
    136      * BeanInfo class.)
    137      */
    138     public String getValueExpr() {
    139         return (valueExpr);
    140     }
    141 
    142     /**
    143      * Setter method for "filter" tag attribute. (Mapping set in associated
    144      * BeanInfo class.)
    145      */
    146     public void setFilterExpr(String filterExpr) {
    147         this.filterExpr = filterExpr;
    148     }
    149 
    150     /**
    151      * Setter method for "label" tag attribute. (Mapping set in associated
    152      * BeanInfo class.)
    153      */
    154     public void setLabelExpr(String labelExpr) {
    155         this.labelExpr = labelExpr;
    156     }
    157 
    158     /**
    159      * Setter method for "name" tag attribute. (Mapping set in associated
    160      * BeanInfo class.)
    161      */
    162     public void setNameExpr(String nameExpr) {
    163         this.nameExpr = nameExpr;
    164     }
    165 
    166     /**
    167      * Setter method for "property" tag attribute. (Mapping set in associated
    168      * BeanInfo class.)
    169      */
    170     public void setPropertyExpr(String propertyExpr) {
    171         this.propertyExpr = propertyExpr;
    172     }
    173 
    174     /**
    175      * Setter method for "style" tag attribute. (Mapping set in associated
    176      * BeanInfo class.)
    177      */
    178     public void setStyleExpr(String styleExpr) {
    179         this.styleExpr = styleExpr;
    180     }
    181 
    182     /**
    183      * Setter method for "styleClass" tag attribute. (Mapping set in
    184      * associated BeanInfo class.)
    185      */
    186     public void setStyleClassExpr(String styleClassExpr) {
    187         this.styleClassExpr = styleClassExpr;
    188     }
    189 
    190     /**
    191      * Setter method for "value" tag attribute. (Mapping set in associated
    192      * BeanInfo class.)
    193      */
    194     public void setValueExpr(String valueExpr) {
    195         this.valueExpr = valueExpr;
    196     }
    197 
    198     /**
    199      * Resets attribute values for tag reuse.
    200      */
    201     public void release() {
    202         super.release();
    203         setFilterExpr(null);
    204         setLabelExpr(null);
    205         setNameExpr(null);
    206         setPropertyExpr(null);
    207         setStyleExpr(null);
    208         setStyleClassExpr(null);
    209         setValueExpr(null);
    210     }
    211 
    212     /**
    213      * Process the start tag.
    214      *
    215      * @throws JspException if a JSP exception has occurred
    216      */
    217     public int doStartTag() throws JspException {
    218         evaluateExpressions();
    219 
    220         return (super.doStartTag());
    221     }
    222 
    223     /**
    224      * Processes all attribute values which use the JSTL expression evaluation
    225      * engine to determine their values.
    226      *
    227      * @throws JspException if a JSP exception has occurred
    228      */
    229     private void evaluateExpressions()
    230         throws JspException {
    231         String string = null;
    232         Boolean bool = null;
    233 
    234         if ((bool =
    235                 EvalHelper.evalBoolean("filter", getFilterExpr(), this,
    236                     pageContext)) != null) {
    237             setFilter(bool.booleanValue());
    238         }
    239 
    240         if ((string =
    241                 EvalHelper.evalString("label", getLabelExpr(), this, pageContext)) != null) {
    242             setLabel(string);
    243         }
    244 
    245         if ((string =
    246                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    247             setName(string);
    248         }
    249 
    250         if ((string =
    251                 EvalHelper.evalString("property", getPropertyExpr(), this,
    252                     pageContext)) != null) {
    253             setProperty(string);
    254         }
    255 
    256         if ((string =
    257                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    258             setStyle(string);
    259         }
    260 
    261         if ((string =
    262                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    263                     pageContext)) != null) {
    264             setStyleClass(string);
    265         }
    266 
    267         // Note that in contrast to other elements which have "style" and
    268         // "styleClass" attributes, this tag does not have a "styleId"
    269         // attribute.  This is because this produces the "id" attribute, which
    270         // has to be unique document-wide, but this tag can generate more than
    271         // one "option" element.  Thus, the base tag, "OptionsCollectionTag"
    272         // does not support this attribute.
    273         if ((string =
    274                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    275             setValue(string);
    276         }
    277     }
    278 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
