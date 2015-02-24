[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/logic/ELIterateTag.html.md)


    1   /*
    2    * $Id: ELIterateTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.logic;
    22  
    23  import org.apache.struts.taglib.logic.IterateTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * Custom tag that iterates the elements of a collection, which can be either
    30   * an attribute or the property of an attribute.  The collection can be any of
    31   * the following:  an array of objects, an Enumeration, an Iterator, a
    32   * Collection (which includes Lists, Sets and Vectors), or a Map (which
    33   * includes Hashtables) whose elements will be iterated over. <p> This class
    34   * is a subclass of the class <code>org.apache.struts.taglib.logic.IterateTag</code>
    35   * which provides most of the described functionality.  This subclass allows
    36   * all attribute values to be specified as expressions utilizing the
    37   * JavaServer Pages Standard Library expression language.
    38   *
    39   * @version $Rev: 471754 $
    40   */
    41  public class ELIterateTag extends IterateTag {
    42      /**
    43       * Instance variable mapped to "collection" tag attribute. (Mapping set in
    44       * associated BeanInfo class.)
    45       */
    46      private String collectionExpr;
    47  
    48      /**
    49       * Instance variable mapped to "id" tag attribute. (Mapping set in
    50       * associated BeanInfo class.)
    51       */
    52      private String idExpr;
    53  
    54      /**
    55       * Instance variable mapped to "indexId" tag attribute. (Mapping set in
    56       * associated BeanInfo class.)
    57       */
    58      private String indexIdExpr;
    59  
    60      /**
    61       * Instance variable mapped to "length" tag attribute. (Mapping set in
    62       * associated BeanInfo class.)
    63       */
    64      private String lengthExpr;
    65  
    66      /**
    67       * Instance variable mapped to "name" tag attribute. (Mapping set in
    68       * associated BeanInfo class.)
    69       */
    70      private String nameExpr;
    71  
    72      /**
    73       * Instance variable mapped to "offset" tag attribute. (Mapping set in
    74       * associated BeanInfo class.)
    75       */
    76      private String offsetExpr;
    77  
    78      /**
    79       * Instance variable mapped to "property" tag attribute. (Mapping set in
    80       * associated BeanInfo class.)
    81       */
    82      private String propertyExpr;
    83  
    84      /**
    85       * Instance variable mapped to "scope" tag attribute. (Mapping set in
    86       * associated BeanInfo class.)
    87       */
    88      private String scopeExpr;
    89  
    90      /**
    91       * Instance variable mapped to "type" tag attribute. (Mapping set in
    92       * associated BeanInfo class.)
    93       */
    94      private String typeExpr;
    95  
    96      /**
    97       * Getter method for "collection" tag attribute. (Mapping set in
    98       * associated BeanInfo class.)
    99       */
    100     public String getCollectionExpr() {
    101         return (collectionExpr);
    102     }
    103 
    104     /**
    105      * Getter method for "id" tag attribute. (Mapping set in associated
    106      * BeanInfo class.)
    107      */
    108     public String getIdExpr() {
    109         return (idExpr);
    110     }
    111 
    112     /**
    113      * Getter method for "indexId" tag attribute. (Mapping set in associated
    114      * BeanInfo class.)
    115      */
    116     public String getIndexIdExpr() {
    117         return (indexIdExpr);
    118     }
    119 
    120     /**
    121      * Getter method for "length" tag attribute. (Mapping set in associated
    122      * BeanInfo class.)
    123      */
    124     public String getLengthExpr() {
    125         return (lengthExpr);
    126     }
    127 
    128     /**
    129      * Getter method for "name" tag attribute. (Mapping set in associated
    130      * BeanInfo class.)
    131      */
    132     public String getNameExpr() {
    133         return (nameExpr);
    134     }
    135 
    136     /**
    137      * Getter method for "offset" tag attribute. (Mapping set in associated
    138      * BeanInfo class.)
    139      */
    140     public String getOffsetExpr() {
    141         return (offsetExpr);
    142     }
    143 
    144     /**
    145      * Getter method for "property" tag attribute. (Mapping set in associated
    146      * BeanInfo class.)
    147      */
    148     public String getPropertyExpr() {
    149         return (propertyExpr);
    150     }
    151 
    152     /**
    153      * Getter method for "scope" tag attribute. (Mapping set in associated
    154      * BeanInfo class.)
    155      */
    156     public String getScopeExpr() {
    157         return (scopeExpr);
    158     }
    159 
    160     /**
    161      * Getter method for "type" tag attribute. (Mapping set in associated
    162      * BeanInfo class.)
    163      */
    164     public String getTypeExpr() {
    165         return (typeExpr);
    166     }
    167 
    168     /**
    169      * Setter method for "collection" tag attribute. (Mapping set in
    170      * associated BeanInfo class.)
    171      */
    172     public void setCollectionExpr(String collectionExpr) {
    173         this.collectionExpr = collectionExpr;
    174     }
    175 
    176     /**
    177      * Setter method for "id" tag attribute. (Mapping set in associated
    178      * BeanInfo class.)
    179      */
    180     public void setIdExpr(String idExpr) {
    181         this.idExpr = idExpr;
    182     }
    183 
    184     /**
    185      * Setter method for "indexId" tag attribute. (Mapping set in associated
    186      * BeanInfo class.)
    187      */
    188     public void setIndexIdExpr(String indexIdExpr) {
    189         this.indexIdExpr = indexIdExpr;
    190     }
    191 
    192     /**
    193      * Setter method for "length" tag attribute. (Mapping set in associated
    194      * BeanInfo class.)
    195      */
    196     public void setLengthExpr(String lengthExpr) {
    197         this.lengthExpr = lengthExpr;
    198     }
    199 
    200     /**
    201      * Setter method for "name" tag attribute. (Mapping set in associated
    202      * BeanInfo class.)
    203      */
    204     public void setNameExpr(String nameExpr) {
    205         this.nameExpr = nameExpr;
    206     }
    207 
    208     /**
    209      * Setter method for "offset" tag attribute. (Mapping set in associated
    210      * BeanInfo class.)
    211      */
    212     public void setOffsetExpr(String offsetExpr) {
    213         this.offsetExpr = offsetExpr;
    214     }
    215 
    216     /**
    217      * Setter method for "property" tag attribute. (Mapping set in associated
    218      * BeanInfo class.)
    219      */
    220     public void setPropertyExpr(String propertyExpr) {
    221         this.propertyExpr = propertyExpr;
    222     }
    223 
    224     /**
    225      * Setter method for "scope" tag attribute. (Mapping set in associated
    226      * BeanInfo class.)
    227      */
    228     public void setScopeExpr(String scopeExpr) {
    229         this.scopeExpr = scopeExpr;
    230     }
    231 
    232     /**
    233      * Setter method for "type" tag attribute. (Mapping set in associated
    234      * BeanInfo class.)
    235      */
    236     public void setTypeExpr(String typeExpr) {
    237         this.typeExpr = typeExpr;
    238     }
    239 
    240     /**
    241      * Releases state of custom tag so this instance can be reused.
    242      */
    243     public void release() {
    244         super.release();
    245         setCollectionExpr(null);
    246         setIdExpr(null);
    247         setIndexIdExpr(null);
    248         setLengthExpr(null);
    249         setNameExpr(null);
    250         setOffsetExpr(null);
    251         setPropertyExpr(null);
    252         setScopeExpr(null);
    253         setTypeExpr(null);
    254     }
    255 
    256     /**
    257      * Process the start tag.
    258      *
    259      * @throws JspException if a JSP exception has occurred
    260      */
    261     public int doStartTag() throws JspException {
    262         evaluateExpressions();
    263 
    264         return (super.doStartTag());
    265     }
    266 
    267     /**
    268      * Processes all attribute values which use the JSTL expression evaluation
    269      * engine to determine their values.
    270      *
    271      * @throws JspException if a JSP exception has occurred
    272      */
    273     private void evaluateExpressions()
    274         throws JspException {
    275         String string = null;
    276         Object object = null;
    277 
    278         if ((object =
    279                 EvalHelper.eval("collection", getCollectionExpr(), this,
    280                     pageContext)) != null) {
    281             setCollection(object);
    282         }
    283 
    284         if ((string =
    285                 EvalHelper.evalString("id", getIdExpr(), this, pageContext)) != null) {
    286             setId(string);
    287         }
    288 
    289         if ((string =
    290                 EvalHelper.evalString("indexId", getIndexIdExpr(), this,
    291                     pageContext)) != null) {
    292             setIndexId(string);
    293         }
    294 
    295         if ((string =
    296                 EvalHelper.evalString("length", getLengthExpr(), this,
    297                     pageContext)) != null) {
    298             setLength(string);
    299         }
    300 
    301         if ((string =
    302                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    303             setName(string);
    304         }
    305 
    306         if ((string =
    307                 EvalHelper.evalString("offset", getOffsetExpr(), this,
    308                     pageContext)) != null) {
    309             setOffset(string);
    310         }
    311 
    312         if ((string =
    313                 EvalHelper.evalString("property", getPropertyExpr(), this,
    314                     pageContext)) != null) {
    315             setProperty(string);
    316         }
    317 
    318         if ((string =
    319                 EvalHelper.evalString("scope", getScopeExpr(), this, pageContext)) != null) {
    320             setScope(string);
    321         }
    322 
    323         if ((string =
    324                 EvalHelper.evalString("type", getTypeExpr(), this, pageContext)) != null) {
    325             setType(string);
    326         }
    327     }
    328 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
