[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELOptionsTag.html)


    1   /*
    2    * $Id: ELOptionsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.html.md.OptionsTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Tag for creating multiple &lt;select&gt; options from a collection.  The
    30   * associated values displayed to the user may optionally be specified by a
    31   * second collection, or will be the same as the values themselves.  Each
    32   * collection may be an array of objects, a Collection, an Enumeration, an
    33   * Iterator, or a Map. <b>NOTE</b> - This tag requires a Java2 (JDK 1.2 or
    34   * later) platform. <p> This class is a subclass of the class
    35   * <code>org.apache.struts.taglib.html.md.OptionsTag</code> which provides most
    36   * of the described functionality.  This subclass allows all attribute values
    37   * to be specified as expressions utilizing the JavaServer Pages Standard
    38   * Library expression language.
    39   *
    40   * @version $Rev: 471754 $
    41   */
    42  public class ELOptionsTag extends OptionsTag {
    43      /**
    44       * Instance variable mapped to "collection" tag attribute. (Mapping set in
    45       * associated BeanInfo class.)
    46       */
    47      private String collectionExpr;
    48  
    49      /**
    50       * Instance variable mapped to "filter" tag attribute. (Mapping set in
    51       * associated BeanInfo class.)
    52       */
    53      private String filterExpr;
    54  
    55      /**
    56       * Instance variable mapped to "labelName" tag attribute. (Mapping set in
    57       * associated BeanInfo class.)
    58       */
    59      private String labelNameExpr;
    60  
    61      /**
    62       * Instance variable mapped to "labelProperty" tag attribute. (Mapping set
    63       * in associated BeanInfo class.)
    64       */
    65      private String labelPropertyExpr;
    66  
    67      /**
    68       * Instance variable mapped to "name" tag attribute. (Mapping set in
    69       * associated BeanInfo class.)
    70       */
    71      private String nameExpr;
    72  
    73      /**
    74       * Instance variable mapped to "property" tag attribute. (Mapping set in
    75       * associated BeanInfo class.)
    76       */
    77      private String propertyExpr;
    78  
    79      /**
    80       * Instance variable mapped to "style" tag attribute. (Mapping set in
    81       * associated BeanInfo class.)
    82       */
    83      private String styleExpr;
    84  
    85      /**
    86       * Instance variable mapped to "styleClass" tag attribute. (Mapping set in
    87       * associated BeanInfo class.)
    88       */
    89      private String styleClassExpr;
    90  
    91      /**
    92       * Getter method for "collection" tag attribute. (Mapping set in
    93       * associated BeanInfo class.)
    94       */
    95      public String getCollectionExpr() {
    96          return (collectionExpr);
    97      }
    98  
    99      /**
    100      * Getter method for "filter" tag attribute. (Mapping set in associated
    101      * BeanInfo class.)
    102      */
    103     public String getFilterExpr() {
    104         return (filterExpr);
    105     }
    106 
    107     /**
    108      * Getter method for "labelName" tag attribute. (Mapping set in associated
    109      * BeanInfo class.)
    110      */
    111     public String getLabelNameExpr() {
    112         return (labelNameExpr);
    113     }
    114 
    115     /**
    116      * Getter method for "labelProperty" tag attribute. (Mapping set in
    117      * associated BeanInfo class.)
    118      */
    119     public String getLabelPropertyExpr() {
    120         return (labelPropertyExpr);
    121     }
    122 
    123     /**
    124      * Getter method for "name" tag attribute. (Mapping set in associated
    125      * BeanInfo class.)
    126      */
    127     public String getNameExpr() {
    128         return (nameExpr);
    129     }
    130 
    131     /**
    132      * Getter method for "property" tag attribute. (Mapping set in associated
    133      * BeanInfo class.)
    134      */
    135     public String getPropertyExpr() {
    136         return (propertyExpr);
    137     }
    138 
    139     /**
    140      * Getter method for "style" tag attribute. (Mapping set in associated
    141      * BeanInfo class.)
    142      */
    143     public String getStyleExpr() {
    144         return (styleExpr);
    145     }
    146 
    147     /**
    148      * Getter method for "styleClass" tag attribute. (Mapping set in
    149      * associated BeanInfo class.)
    150      */
    151     public String getStyleClassExpr() {
    152         return (styleClassExpr);
    153     }
    154 
    155     /**
    156      * Setter method for "collection" tag attribute. (Mapping set in
    157      * associated BeanInfo class.)
    158      */
    159     public void setCollectionExpr(String collectionExpr) {
    160         this.collectionExpr = collectionExpr;
    161     }
    162 
    163     /**
    164      * Setter method for "filter" tag attribute. (Mapping set in associated
    165      * BeanInfo class.)
    166      */
    167     public void setFilterExpr(String filterExpr) {
    168         this.filterExpr = filterExpr;
    169     }
    170 
    171     /**
    172      * Setter method for "labelName" tag attribute. (Mapping set in associated
    173      * BeanInfo class.)
    174      */
    175     public void setLabelNameExpr(String labelNameExpr) {
    176         this.labelNameExpr = labelNameExpr;
    177     }
    178 
    179     /**
    180      * Setter method for "labelProperty" tag attribute. (Mapping set in
    181      * associated BeanInfo class.)
    182      */
    183     public void setLabelPropertyExpr(String labelPropertyExpr) {
    184         this.labelPropertyExpr = labelPropertyExpr;
    185     }
    186 
    187     /**
    188      * Setter method for "name" tag attribute. (Mapping set in associated
    189      * BeanInfo class.)
    190      */
    191     public void setNameExpr(String nameExpr) {
    192         this.nameExpr = nameExpr;
    193     }
    194 
    195     /**
    196      * Setter method for "property" tag attribute. (Mapping set in associated
    197      * BeanInfo class.)
    198      */
    199     public void setPropertyExpr(String propertyExpr) {
    200         this.propertyExpr = propertyExpr;
    201     }
    202 
    203     /**
    204      * Setter method for "style" tag attribute. (Mapping set in associated
    205      * BeanInfo class.)
    206      */
    207     public void setStyleExpr(String styleExpr) {
    208         this.styleExpr = styleExpr;
    209     }
    210 
    211     /**
    212      * Setter method for "styleClass" tag attribute. (Mapping set in
    213      * associated BeanInfo class.)
    214      */
    215     public void setStyleClassExpr(String styleClassExpr) {
    216         this.styleClassExpr = styleClassExpr;
    217     }
    218 
    219     /**
    220      * Resets attribute values for tag reuse.
    221      */
    222     public void release() {
    223         super.release();
    224         setCollectionExpr(null);
    225         setFilterExpr(null);
    226         setLabelNameExpr(null);
    227         setLabelPropertyExpr(null);
    228         setNameExpr(null);
    229         setPropertyExpr(null);
    230         setStyleExpr(null);
    231         setStyleClassExpr(null);
    232     }
    233 
    234     /**
    235      * Process the start tag.
    236      *
    237      * @throws JspException if a JSP exception has occurred
    238      */
    239     public int doStartTag() throws JspException {
    240         evaluateExpressions();
    241 
    242         return (super.doStartTag());
    243     }
    244 
    245     /**
    246      * Processes all attribute values which use the JSTL expression evaluation
    247      * engine to determine their values.
    248      *
    249      * @throws JspException if a JSP exception has occurred
    250      */
    251     private void evaluateExpressions()
    252         throws JspException {
    253         String string = null;
    254         Boolean bool = null;
    255 
    256         if ((string =
    257                 EvalHelper.evalString("collection", getCollectionExpr(), this,
    258                     pageContext)) != null) {
    259             setCollection(string);
    260         }
    261 
    262         if ((bool =
    263                 EvalHelper.evalBoolean("filter", getFilterExpr(), this,
    264                     pageContext)) != null) {
    265             setFilter(bool.booleanValue());
    266         }
    267 
    268         if ((string =
    269                 EvalHelper.evalString("labelName", getLabelNameExpr(), this,
    270                     pageContext)) != null) {
    271             setLabelName(string);
    272         }
    273 
    274         if ((string =
    275                 EvalHelper.evalString("labelProperty", getLabelPropertyExpr(),
    276                     this, pageContext)) != null) {
    277             setLabelProperty(string);
    278         }
    279 
    280         if ((string =
    281                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    282             setName(string);
    283         }
    284 
    285         if ((string =
    286                 EvalHelper.evalString("property", getPropertyExpr(), this,
    287                     pageContext)) != null) {
    288             setProperty(string);
    289         }
    290 
    291         if ((string =
    292                 EvalHelper.evalString("style", getStyleExpr(), this, pageContext)) != null) {
    293             setStyle(string);
    294         }
    295 
    296         if ((string =
    297                 EvalHelper.evalString("styleClass", getStyleClassExpr(), this,
    298                     pageContext)) != null) {
    299             setStyleClass(string);
    300         }
    301 
    302         // Note that in contrast to other elements which have "style" and
    303         // "styleClass" attributes, this tag does not have a "styleId"
    304         // attribute.  This is because this produces the "id" attribute, which
    305         // has to be unique document-wide, but this tag can generate more than
    306         // one "option" element.  Thus, the base tag, "Options" does not
    307         // support this attribute.
    308     }
    309 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
