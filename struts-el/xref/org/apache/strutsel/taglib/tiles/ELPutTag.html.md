[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELPutTag.html.md)


    1   /*
    2    * $Id: ELPutTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.tiles;
    22  
    23  import org.apache.struts.tiles.taglib.PutTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * <p>Put an attribute in enclosing attribute container tag. Enclosing
    30   * attribute container tag can be : &lt;insert&gt; or &lt;definition&gt;.
    31   * Exception is thrown if no appropriate tag can be found. Put tag can have
    32   * following atributes :</p>
    33   *
    34   * <ul>
    35   *
    36   * <li>name : Name of the attribute</li>
    37   *
    38   * <li>value | content : value to put as attribute</li>
    39   *
    40   * <li>type : value type. Only valid if value is a String and is set by
    41   * value="something" or by a bean. Possible type are : string (value is used
    42   * as direct string), page | template (value is used as a page url to insert),
    43   * definition (value is used as a definition name to insert)</li>
    44   *
    45   * <li>direct : Specify if value is to be used as a direct string or as a page
    46   * url to insert. This is another way to specify the type. It only apply if
    47   * value is set as a string, and type is not present.</li>
    48   *
    49   * <li>beanName : Name of a bean used for setting value. Only valid if value
    50   * is not set. If property is specified, value come from bean's property.
    51   * Otherwise, bean itself is used for value.</li>
    52   *
    53   * <li>beanProperty : Name of the property used for retrieving value.</li>
    54   *
    55   * <li>beanScope : Scope containing bean. </li>
    56   *
    57   * <li>role : Role to check when 'insert' will be called. If enclosing tag is
    58   * &lt;insert&gt;, role is checked immediately. If enclosing tag is
    59   * &lt;definition&gt;, role will be checked when this definition will be
    60   * inserted.</li>
    61   *
    62   * </li> Value can also come from tag body. Tag body is taken into account
    63   * only if value is not set by one of the tag attributes. In this case
    64   * Attribute type is "string", unless tag body define another type.</li>
    65   *
    66   * </ul>
    67   *
    68   * <p> This class is a subclass of the class <code>org.apache.struts.taglib.tiles.PutTag</code>
    69   * which provides most of the described functionality.  This subclass allows
    70   * all attribute values to be specified as expressions utilizing the
    71   * JavaServer Pages Standard Library expression language.  </p>
    72   *
    73   * @version $Rev: 471754 $
    74   */
    75  public class ELPutTag extends PutTag {
    76      /**
    77       * Instance variable mapped to "name" tag attribute. (Mapping set in
    78       * associated BeanInfo class.)
    79       */
    80      private String nameExpr;
    81  
    82      /**
    83       * Instance variable mapped to "value" tag attribute. (Mapping set in
    84       * associated BeanInfo class.)
    85       */
    86      private String valueExpr;
    87  
    88      /**
    89       * Instance variable mapped to "content" tag attribute. (Mapping set in
    90       * associated BeanInfo class.)
    91       */
    92      private String contentExpr;
    93  
    94      /**
    95       * Instance variable mapped to "direct" tag attribute. (Mapping set in
    96       * associated BeanInfo class.)
    97       */
    98      private String directExpr;
    99  
    100     /**
    101      * Instance variable mapped to "type" tag attribute. (Mapping set in
    102      * associated BeanInfo class.)
    103      */
    104     private String typeExpr;
    105 
    106     /**
    107      * Instance variable mapped to "beanName" tag attribute. (Mapping set in
    108      * associated BeanInfo class.)
    109      */
    110     private String beanNameExpr;
    111 
    112     /**
    113      * Instance variable mapped to "beanProperty" tag attribute. (Mapping set
    114      * in associated BeanInfo class.)
    115      */
    116     private String beanPropertyExpr;
    117 
    118     /**
    119      * Instance variable mapped to "beanScope" tag attribute. (Mapping set in
    120      * associated BeanInfo class.)
    121      */
    122     private String beanScopeExpr;
    123 
    124     /**
    125      * Instance variable mapped to "role" tag attribute. (Mapping set in
    126      * associated BeanInfo class.)
    127      */
    128     private String roleExpr;
    129 
    130     /**
    131      * Getter method for "name" tag attribute. (Mapping set in associated
    132      * BeanInfo class.)
    133      */
    134     public String getNameExpr() {
    135         return (nameExpr);
    136     }
    137 
    138     /**
    139      * Getter method for "value" tag attribute. (Mapping set in associated
    140      * BeanInfo class.)
    141      */
    142     public String getValueExpr() {
    143         return (valueExpr);
    144     }
    145 
    146     /**
    147      * Getter method for "content" tag attribute. (Mapping set in associated
    148      * BeanInfo class.)
    149      */
    150     public String getContentExpr() {
    151         return (contentExpr);
    152     }
    153 
    154     /**
    155      * Getter method for "direct" tag attribute. (Mapping set in associated
    156      * BeanInfo class.)
    157      */
    158     public String getDirectExpr() {
    159         return (directExpr);
    160     }
    161 
    162     /**
    163      * Getter method for "type" tag attribute. (Mapping set in associated
    164      * BeanInfo class.)
    165      */
    166     public String getTypeExpr() {
    167         return (typeExpr);
    168     }
    169 
    170     /**
    171      * Getter method for "beanName" tag attribute. (Mapping set in associated
    172      * BeanInfo class.)
    173      */
    174     public String getBeanNameExpr() {
    175         return (beanNameExpr);
    176     }
    177 
    178     /**
    179      * Getter method for "beanProperty" tag attribute. (Mapping set in
    180      * associated BeanInfo class.)
    181      */
    182     public String getBeanPropertyExpr() {
    183         return (beanPropertyExpr);
    184     }
    185 
    186     /**
    187      * Getter method for "beanScope" tag attribute. (Mapping set in associated
    188      * BeanInfo class.)
    189      */
    190     public String getBeanScopeExpr() {
    191         return (beanScopeExpr);
    192     }
    193 
    194     /**
    195      * Getter method for "role" tag attribute. (Mapping set in associated
    196      * BeanInfo class.)
    197      */
    198     public String getRoleExpr() {
    199         return (roleExpr);
    200     }
    201 
    202     /**
    203      * Setter method for "name" tag attribute. (Mapping set in associated
    204      * BeanInfo class.)
    205      */
    206     public void setNameExpr(String nameExpr) {
    207         this.nameExpr = nameExpr;
    208     }
    209 
    210     /**
    211      * Setter method for "value" tag attribute. (Mapping set in associated
    212      * BeanInfo class.)
    213      */
    214     public void setValueExpr(String valueExpr) {
    215         this.valueExpr = valueExpr;
    216     }
    217 
    218     /**
    219      * Setter method for "content" tag attribute. (Mapping set in associated
    220      * BeanInfo class.)
    221      */
    222     public void setContentExpr(String contentExpr) {
    223         this.contentExpr = contentExpr;
    224     }
    225 
    226     /**
    227      * Setter method for "direct" tag attribute. (Mapping set in associated
    228      * BeanInfo class.)
    229      */
    230     public void setDirectExpr(String directExpr) {
    231         this.directExpr = directExpr;
    232     }
    233 
    234     /**
    235      * Setter method for "type" tag attribute. (Mapping set in associated
    236      * BeanInfo class.)
    237      */
    238     public void setTypeExpr(String typeExpr) {
    239         this.typeExpr = typeExpr;
    240     }
    241 
    242     /**
    243      * Setter method for "beanName" tag attribute. (Mapping set in associated
    244      * BeanInfo class.)
    245      */
    246     public void setBeanNameExpr(String beanNameExpr) {
    247         this.beanNameExpr = beanNameExpr;
    248     }
    249 
    250     /**
    251      * Setter method for "beanProperty" tag attribute. (Mapping set in
    252      * associated BeanInfo class.)
    253      */
    254     public void setBeanPropertyExpr(String beanPropertyExpr) {
    255         this.beanPropertyExpr = beanPropertyExpr;
    256     }
    257 
    258     /**
    259      * Setter method for "beanScope" tag attribute. (Mapping set in associated
    260      * BeanInfo class.)
    261      */
    262     public void setBeanScopeExpr(String beanScopeExpr) {
    263         this.beanScopeExpr = beanScopeExpr;
    264     }
    265 
    266     /**
    267      * Setter method for "role" tag attribute. (Mapping set in associated
    268      * BeanInfo class.)
    269      */
    270     public void setRoleExpr(String roleExpr) {
    271         this.roleExpr = roleExpr;
    272     }
    273 
    274     /**
    275      * Resets attribute values for tag reuse.
    276      */
    277     public void release() {
    278         super.release();
    279         setNameExpr(null);
    280         setValueExpr(null);
    281         setContentExpr(null);
    282         setDirectExpr(null);
    283         setTypeExpr(null);
    284         setBeanNameExpr(null);
    285         setBeanPropertyExpr(null);
    286         setBeanScopeExpr(null);
    287         setRoleExpr(null);
    288     }
    289 
    290     /**
    291      * Process the start tag.
    292      *
    293      * @throws JspException if a JSP exception has occurred
    294      */
    295     public int doStartTag() throws JspException {
    296         evaluateExpressions();
    297 
    298         return (super.doStartTag());
    299     }
    300 
    301     /**
    302      * Processes all attribute values which use the JSTL expression evaluation
    303      * engine to determine their values.
    304      *
    305      * @throws JspException if a JSP exception has occurred
    306      */
    307     private void evaluateExpressions()
    308         throws JspException {
    309         String string = null;
    310 
    311         if ((string =
    312                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    313             setName(string);
    314         }
    315 
    316         if ((string =
    317                 EvalHelper.evalString("value", getValueExpr(), this, pageContext)) != null) {
    318             setValue(string);
    319         }
    320 
    321         if ((string =
    322                 EvalHelper.evalString("content", getContentExpr(), this,
    323                     pageContext)) != null) {
    324             setContent(string);
    325         }
    326 
    327         if ((string =
    328                 EvalHelper.evalString("direct", getDirectExpr(), this,
    329                     pageContext)) != null) {
    330             setDirect(string);
    331         }
    332 
    333         if ((string =
    334                 EvalHelper.evalString("type", getTypeExpr(), this, pageContext)) != null) {
    335             setType(string);
    336         }
    337 
    338         if ((string =
    339                 EvalHelper.evalString("beanName", getBeanNameExpr(), this,
    340                     pageContext)) != null) {
    341             setBeanName(string);
    342         }
    343 
    344         if ((string =
    345                 EvalHelper.evalString("beanProperty", getBeanPropertyExpr(),
    346                     this, pageContext)) != null) {
    347             setBeanProperty(string);
    348         }
    349 
    350         if ((string =
    351                 EvalHelper.evalString("beanScope", getBeanScopeExpr(), this,
    352                     pageContext)) != null) {
    353             setBeanScope(string);
    354         }
    355 
    356         if ((string =
    357                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    358             setRole(string);
    359         }
    360     }
    361 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
