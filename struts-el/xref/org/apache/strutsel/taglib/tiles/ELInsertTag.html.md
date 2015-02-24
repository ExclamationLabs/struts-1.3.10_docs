[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELInsertTag.html.md)


    1   /*
    2    * $Id: ELInsertTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.tiles.taglib.InsertTag;
    24  import org.apache.strutsel.taglib.utils.EvalHelper;
    25  
    26  import javax.servlet.jsp.JspException;
    27  
    28  /**
    29   * This is the tag handler for &lt;tiles:insert&gt;, which includes a
    30   * template. The tag's body content consists of &lt;tiles:put&gt; tags, which
    31   * are accessed by &lt;tiles:get&gt; in the template. <p> This class is a
    32   * subclass of the class <code>org.apache.struts.taglib.tiles.InsertTag</code>
    33   * which provides most of the described functionality.  This subclass allows
    34   * all attribute values to be specified as expressions utilizing the
    35   * JavaServer Pages Standard Library expression language.
    36   *
    37   * @version $Rev: 471754 $
    38   */
    39  public class ELInsertTag extends InsertTag {
    40      /**
    41       * Instance variable mapped to "template" tag attribute. (Mapping set in
    42       * associated BeanInfo class.)
    43       */
    44      private String templateExpr;
    45  
    46      /**
    47       * Instance variable mapped to "component" tag attribute. (Mapping set in
    48       * associated BeanInfo class.)
    49       */
    50      private String componentExpr;
    51  
    52      /**
    53       * Instance variable mapped to "page" tag attribute. (Mapping set in
    54       * associated BeanInfo class.)
    55       */
    56      private String pageExpr;
    57  
    58      /**
    59       * Instance variable mapped to "definition" tag attribute. (Mapping set in
    60       * associated BeanInfo class.)
    61       */
    62      private String definitionExpr;
    63  
    64      /**
    65       * Instance variable mapped to "attribute" tag attribute. (Mapping set in
    66       * associated BeanInfo class.)
    67       */
    68      private String attributeExpr;
    69  
    70      /**
    71       * Instance variable mapped to "name" tag attribute. (Mapping set in
    72       * associated BeanInfo class.)
    73       */
    74      private String nameExpr;
    75  
    76      /**
    77       * Instance variable mapped to "beanName" tag attribute. (Mapping set in
    78       * associated BeanInfo class.)
    79       */
    80      private String beanNameExpr;
    81  
    82      /**
    83       * Instance variable mapped to "beanProperty" tag attribute. (Mapping set
    84       * in associated BeanInfo class.)
    85       */
    86      private String beanPropertyExpr;
    87  
    88      /**
    89       * Instance variable mapped to "beanScope" tag attribute. (Mapping set in
    90       * associated BeanInfo class.)
    91       */
    92      private String beanScopeExpr;
    93  
    94      /**
    95       * Instance variable mapped to "flush" tag attribute. (Mapping set in
    96       * associated BeanInfo class.)
    97       */
    98      private String flushExpr;
    99  
    100     /**
    101      * (Mapping set in associated BeanInfo class.) Instance variable mapped to
    102      * "ignore" tag attribute.
    103      */
    104     private String ignoreExpr;
    105 
    106     /**
    107      * Instance variable mapped to "role" tag attribute. (Mapping set in
    108      * associated BeanInfo class.)
    109      */
    110     private String roleExpr;
    111 
    112     /**
    113      * Instance variable mapped to "controllerUrl" tag attribute. (Mapping set
    114      * in associated BeanInfo class.)
    115      */
    116     private String controllerUrlExpr;
    117 
    118     /**
    119      * Instance variable mapped to "controllerClass" tag attribute. (Mapping
    120      * set in associated BeanInfo class.)
    121      */
    122     private String controllerClassExpr;
    123 
    124     /**
    125      * Getter method for "template" tag attribute. (Mapping set in associated
    126      * BeanInfo class.)
    127      */
    128     public String getTemplateExpr() {
    129         return (templateExpr);
    130     }
    131 
    132     /**
    133      * Getter method for "component" tag attribute. (Mapping set in associated
    134      * BeanInfo class.)
    135      */
    136     public String getComponentExpr() {
    137         return (componentExpr);
    138     }
    139 
    140     /**
    141      * Getter method for "page" tag attribute. (Mapping set in associated
    142      * BeanInfo class.)
    143      */
    144     public String getPageExpr() {
    145         return (pageExpr);
    146     }
    147 
    148     /**
    149      * Getter method for "definition" tag attribute. (Mapping set in
    150      * associated BeanInfo class.)
    151      */
    152     public String getDefinitionExpr() {
    153         return (definitionExpr);
    154     }
    155 
    156     /**
    157      * Getter method for "attribute" tag attribute. (Mapping set in associated
    158      * BeanInfo class.)
    159      */
    160     public String getAttributeExpr() {
    161         return (attributeExpr);
    162     }
    163 
    164     /**
    165      * Getter method for "name" tag attribute. (Mapping set in associated
    166      * BeanInfo class.)
    167      */
    168     public String getNameExpr() {
    169         return (nameExpr);
    170     }
    171 
    172     /**
    173      * Getter method for "beanName" tag attribute. (Mapping set in associated
    174      * BeanInfo class.)
    175      */
    176     public String getBeanNameExpr() {
    177         return (beanNameExpr);
    178     }
    179 
    180     /**
    181      * Getter method for "beanProperty" tag attribute. (Mapping set in
    182      * associated BeanInfo class.)
    183      */
    184     public String getBeanPropertyExpr() {
    185         return (beanPropertyExpr);
    186     }
    187 
    188     /**
    189      * Getter method for "beanScope" tag attribute. (Mapping set in associated
    190      * BeanInfo class.)
    191      */
    192     public String getBeanScopeExpr() {
    193         return (beanScopeExpr);
    194     }
    195 
    196     /**
    197      * Getter method for "flush" tag attribute. (Mapping set in associated
    198      * BeanInfo class.)
    199      */
    200     public String getFlushExpr() {
    201         return (flushExpr);
    202     }
    203 
    204     /**
    205      * Getter method for "ignore" tag attribute. (Mapping set in associated
    206      * BeanInfo class.)
    207      */
    208     public String getIgnoreExpr() {
    209         return (ignoreExpr);
    210     }
    211 
    212     /**
    213      * Getter method for "role" tag attribute. (Mapping set in associated
    214      * BeanInfo class.)
    215      */
    216     public String getRoleExpr() {
    217         return (roleExpr);
    218     }
    219 
    220     /**
    221      * Getter method for "controllerUrl" tag attribute. (Mapping set in
    222      * associated BeanInfo class.)
    223      */
    224     public String getControllerUrlExpr() {
    225         return (controllerUrlExpr);
    226     }
    227 
    228     /**
    229      * Getter method for "controllerClass" tag attribute. (Mapping set in
    230      * associated BeanInfo class.)
    231      */
    232     public String getControllerClassExpr() {
    233         return (controllerClassExpr);
    234     }
    235 
    236     /**
    237      * Setter method for "template" tag attribute. (Mapping set in associated
    238      * BeanInfo class.)
    239      */
    240     public void setTemplateExpr(String templateExpr) {
    241         this.templateExpr = templateExpr;
    242     }
    243 
    244     /**
    245      * Setter method for "component" tag attribute. (Mapping set in associated
    246      * BeanInfo class.)
    247      */
    248     public void setComponentExpr(String componentExpr) {
    249         this.componentExpr = componentExpr;
    250     }
    251 
    252     /**
    253      * Setter method for "page" tag attribute. (Mapping set in associated
    254      * BeanInfo class.)
    255      */
    256     public void setPageExpr(String pageExpr) {
    257         this.pageExpr = pageExpr;
    258     }
    259 
    260     /**
    261      * Setter method for "definition" tag attribute. (Mapping set in
    262      * associated BeanInfo class.)
    263      */
    264     public void setDefinitionExpr(String definitionExpr) {
    265         this.definitionExpr = definitionExpr;
    266     }
    267 
    268     /**
    269      * Setter method for "attribute" tag attribute. (Mapping set in associated
    270      * BeanInfo class.)
    271      */
    272     public void setAttributeExpr(String attributeExpr) {
    273         this.attributeExpr = attributeExpr;
    274     }
    275 
    276     /**
    277      * Setter method for "name" tag attribute. (Mapping set in associated
    278      * BeanInfo class.)
    279      */
    280     public void setNameExpr(String nameExpr) {
    281         this.nameExpr = nameExpr;
    282     }
    283 
    284     /**
    285      * Setter method for "beanName" tag attribute. (Mapping set in associated
    286      * BeanInfo class.)
    287      */
    288     public void setBeanNameExpr(String beanNameExpr) {
    289         this.beanNameExpr = beanNameExpr;
    290     }
    291 
    292     /**
    293      * Setter method for "beanProperty" tag attribute. (Mapping set in
    294      * associated BeanInfo class.)
    295      */
    296     public void setBeanPropertyExpr(String beanPropertyExpr) {
    297         this.beanPropertyExpr = beanPropertyExpr;
    298     }
    299 
    300     /**
    301      * Setter method for "beanScope" tag attribute. (Mapping set in associated
    302      * BeanInfo class.)
    303      */
    304     public void setBeanScopeExpr(String beanScopeExpr) {
    305         this.beanScopeExpr = beanScopeExpr;
    306     }
    307 
    308     /**
    309      * Setter method for "flush" tag attribute. (Mapping set in associated
    310      * BeanInfo class.)
    311      */
    312     public void setFlushExpr(String flushExpr) {
    313         this.flushExpr = flushExpr;
    314     }
    315 
    316     /**
    317      * Setter method for "ignore" tag attribute. (Mapping set in associated
    318      * BeanInfo class.)
    319      */
    320     public void setIgnoreExpr(String ignoreExpr) {
    321         this.ignoreExpr = ignoreExpr;
    322     }
    323 
    324     /**
    325      * Setter method for "role" tag attribute. (Mapping set in associated
    326      * BeanInfo class.)
    327      */
    328     public void setRoleExpr(String roleExpr) {
    329         this.roleExpr = roleExpr;
    330     }
    331 
    332     /**
    333      * Setter method for "controllerUrl" tag attribute. (Mapping set in
    334      * associated BeanInfo class.)
    335      */
    336     public void setControllerUrlExpr(String controllerUrlExpr) {
    337         this.controllerUrlExpr = controllerUrlExpr;
    338     }
    339 
    340     /**
    341      * Setter method for "controllerClass" tag attribute. (Mapping set in
    342      * associated BeanInfo class.)
    343      */
    344     public void setControllerClassExpr(String controllerClassExpr) {
    345         this.controllerClassExpr = controllerClassExpr;
    346     }
    347 
    348     /**
    349      * Resets attribute values for tag reuse.
    350      */
    351     public void release() {
    352         super.release();
    353         setTemplateExpr(null);
    354         setComponentExpr(null);
    355         setPageExpr(null);
    356         setDefinitionExpr(null);
    357         setAttributeExpr(null);
    358         setNameExpr(null);
    359         setBeanNameExpr(null);
    360         setBeanPropertyExpr(null);
    361         setBeanScopeExpr(null);
    362         setFlushExpr(null);
    363         setIgnoreExpr(null);
    364         setRoleExpr(null);
    365         setControllerUrlExpr(null);
    366         setControllerClassExpr(null);
    367     }
    368 
    369     /**
    370      * Process the start tag.
    371      *
    372      * @throws JspException if a JSP exception has occurred
    373      */
    374     public int doStartTag() throws JspException {
    375         evaluateExpressions();
    376 
    377         return (super.doStartTag());
    378     }
    379 
    380     /**
    381      * Processes all attribute values which use the JSTL expression evaluation
    382      * engine to determine their values.
    383      *
    384      * @throws JspException if a JSP exception has occurred
    385      */
    386     private void evaluateExpressions()
    387         throws JspException {
    388         String string = null;
    389         Boolean bool = null;
    390 
    391         if ((string =
    392                 EvalHelper.evalString("template", getTemplateExpr(), this,
    393                     pageContext)) != null) {
    394             setTemplate(string);
    395         }
    396 
    397         if ((string =
    398                 EvalHelper.evalString("component", getComponentExpr(), this,
    399                     pageContext)) != null) {
    400             setComponent(string);
    401         }
    402 
    403         if ((string =
    404                 EvalHelper.evalString("page", getPageExpr(), this, pageContext)) != null) {
    405             setPage(string);
    406         }
    407 
    408         if ((string =
    409                 EvalHelper.evalString("definition", getDefinitionExpr(), this,
    410                     pageContext)) != null) {
    411             setDefinition(string);
    412         }
    413 
    414         if ((string =
    415                 EvalHelper.evalString("attribute", getAttributeExpr(), this,
    416                     pageContext)) != null) {
    417             setAttribute(string);
    418         }
    419 
    420         if ((string =
    421                 EvalHelper.evalString("name", getNameExpr(), this, pageContext)) != null) {
    422             setName(string);
    423         }
    424 
    425         if ((string =
    426                 EvalHelper.evalString("beanName", getBeanNameExpr(), this,
    427                     pageContext)) != null) {
    428             setBeanName(string);
    429         }
    430 
    431         if ((string =
    432                 EvalHelper.evalString("beanProperty", getBeanPropertyExpr(),
    433                     this, pageContext)) != null) {
    434             setBeanProperty(string);
    435         }
    436 
    437         if ((string =
    438                 EvalHelper.evalString("beanScope", getBeanScopeExpr(), this,
    439                     pageContext)) != null) {
    440             setBeanScope(string);
    441         }
    442 
    443         if ((string =
    444                 EvalHelper.evalString("flush", getFlushExpr(), this, pageContext)) != null) {
    445             setFlush(string);
    446         }
    447 
    448         if ((bool =
    449                 EvalHelper.evalBoolean("ignore", getIgnoreExpr(), this,
    450                     pageContext)) != null) {
    451             setIgnore(bool.booleanValue());
    452         }
    453 
    454         if ((string =
    455                 EvalHelper.evalString("role", getRoleExpr(), this, pageContext)) != null) {
    456             setRole(string);
    457         }
    458 
    459         if ((string =
    460                 EvalHelper.evalString("controllerUrl", getControllerUrlExpr(),
    461                     this, pageContext)) != null) {
    462             setControllerUrl(string);
    463         }
    464 
    465         if ((string =
    466                 EvalHelper.evalString("controllerClass",
    467                     getControllerClassExpr(), this, pageContext)) != null) {
    468             setControllerClass(string);
    469         }
    470     }
    471 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
