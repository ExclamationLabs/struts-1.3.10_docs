[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/DefineTag.html.md)


    1   /*
    2    * $Id: DefineTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.bean;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.taglib.TagUtils;
    26  import org.apache.struts.util.MessageResources;
    27  
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.PageContext;
    30  import javax.servlet.jsp.tagext.BodyTagSupport;
    31  
    32  /**
    33   * Define a scripting variable based on the value(s) of the specified bean
    34   * property.
    35   *
    36   * @version $Rev: 471754 $ $Date: 2005-06-15 12:16:32 -0400 (Wed, 15 Jun 2005)
    37   *          $
    38   */
    39  public class DefineTag extends BodyTagSupport {
    40      /**
    41       * Commons logging instance.
    42       */
    43      private static final Log log = LogFactory.getLog(DefineTag.class);
    44  
    45      // ---------------------------------------------------- Protected variables
    46  
    47      /**
    48       * The message resources for this package.
    49       */
    50      protected static MessageResources messages =
    51          MessageResources.getMessageResources(
    52              "org.apache.struts.taglib.bean.LocalStrings");
    53  
    54      /**
    55       * The body content of this tag (if any).
    56       */
    57      protected String body = null;
    58  
    59      // ------------------------------------------------------------- Properties
    60  
    61      /**
    62       * The name of the scripting variable that will be exposed as a page scope
    63       * attribute.
    64       */
    65      protected String id = null;
    66  
    67      /**
    68       * The name of the bean owning the property to be exposed.
    69       */
    70      protected String name = null;
    71  
    72      /**
    73       * The name of the property to be retrieved.
    74       */
    75      protected String property = null;
    76  
    77      /**
    78       * The scope within which to search for the specified bean.
    79       */
    80      protected String scope = null;
    81  
    82      /**
    83       * The scope within which the newly defined bean will be creatd.
    84       */
    85      protected String toScope = null;
    86  
    87      /**
    88       * The fully qualified Java class name of the value to be exposed.
    89       */
    90      protected String type = null;
    91  
    92      /**
    93       * The (String) value to which the defined bean will be set.
    94       */
    95      protected String value = null;
    96  
    97      public String getId() {
    98          return (this.id);
    99      }
    100 
    101     public void setId(String id) {
    102         this.id = id;
    103     }
    104 
    105     public String getName() {
    106         return (this.name);
    107     }
    108 
    109     public void setName(String name) {
    110         this.name = name;
    111     }
    112 
    113     public String getProperty() {
    114         return (this.property);
    115     }
    116 
    117     public void setProperty(String property) {
    118         this.property = property;
    119     }
    120 
    121     public String getScope() {
    122         return (this.scope);
    123     }
    124 
    125     public void setScope(String scope) {
    126         this.scope = scope;
    127     }
    128 
    129     public String getToScope() {
    130         return (this.toScope);
    131     }
    132 
    133     public void setToScope(String toScope) {
    134         this.toScope = toScope;
    135     }
    136 
    137     public String getType() {
    138         return (this.type);
    139     }
    140 
    141     public void setType(String type) {
    142         this.type = type;
    143     }
    144 
    145     public String getValue() {
    146         return (this.value);
    147     }
    148 
    149     public void setValue(String value) {
    150         this.value = value;
    151     }
    152 
    153     // --------------------------------------------------------- Public Methods
    154 
    155     /**
    156      * Check if we need to evaluate the body of the tag
    157      *
    158      * @throws JspException if a JSP exception has occurred
    159      */
    160     public int doStartTag() throws JspException {
    161         return (EVAL_BODY_TAG);
    162     }
    163 
    164     /**
    165      * Save the body content of this tag (if any), or throw a JspException if
    166      * the value was already defined.
    167      *
    168      * @throws JspException if value was defined by an attribute
    169      */
    170     public int doAfterBody() throws JspException {
    171         if (bodyContent != null) {
    172             body = bodyContent.getString();
    173 
    174             if (body != null) {
    175                 body = body.trim();
    176             }
    177 
    178             if (body.length() < 1) {
    179                 body = null;
    180             }
    181         }
    182 
    183         return (SKIP_BODY);
    184     }
    185 
    186     /**
    187      * Retrieve the required property and expose it as a scripting variable.
    188      *
    189      * @throws JspException if a JSP exception has occurred
    190      */
    191     public int doEndTag() throws JspException {
    192         // Enforce restriction on ways to declare the new value
    193         int n = 0;
    194 
    195         if (this.body != null) {
    196             n++;
    197         }
    198 
    199         if (this.name != null) {
    200             n++;
    201         }
    202 
    203         if (this.value != null) {
    204             n++;
    205         }
    206 
    207         if (n > 1) {
    208             JspException e =
    209                 new JspException(messages.getMessage("define.value", id));
    210 
    211             TagUtils.getInstance().saveException(pageContext, e);
    212             throw e;
    213         }
    214 
    215         // Retrieve the required property value
    216         Object value = this.value;
    217 
    218         if ((value == null) && (name != null)) {
    219             value =
    220                 TagUtils.getInstance().lookup(pageContext, name, property, scope);
    221         }
    222 
    223         if ((value == null) && (body != null)) {
    224             value = body;
    225         }
    226 
    227         if (value == null) {
    228             JspException e =
    229                 new JspException(messages.getMessage("define.null", id));
    230 
    231             TagUtils.getInstance().saveException(pageContext, e);
    232             throw e;
    233         }
    234 
    235         // Expose this value as a scripting variable
    236         int inScope = PageContext.PAGE_SCOPE;
    237 
    238         try {
    239             if (toScope != null) {
    240                 inScope = TagUtils.getInstance().getScope(toScope);
    241             }
    242         } catch (JspException e) {
    243             log.warn("toScope was invalid name so we default to PAGE_SCOPE", e);
    244         }
    245 
    246         pageContext.setAttribute(id, value, inScope);
    247 
    248         // Continue processing this page
    249         return (EVAL_PAGE);
    250     }
    251 
    252     /**
    253      * Release all allocated resources.
    254      */
    255     public void release() {
    256         super.release();
    257         body = null;
    258         id = null;
    259         name = null;
    260         property = null;
    261         scope = null;
    262         toScope = "page";
    263         type = null;
    264         value = null;
    265     }
    266 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
