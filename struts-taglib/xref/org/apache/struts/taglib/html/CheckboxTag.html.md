[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/CheckboxTag.html)


    1   /*
    2    * $Id: CheckboxTag.java 471754 2006-11-06 14:55:09Z husted $
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
    28  /**
    29   * Tag for input fields of type "checkbox".
    30   *
    31   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    32   *          $
    33   */
    34  public class CheckboxTag extends BaseHandlerTag {
    35      // ----------------------------------------------------- Instance Variables
    36  
    37      /**
    38       * The message resources for this package.
    39       */
    40      protected static MessageResources messages =
    41          MessageResources.getMessageResources(Constants.Package
    42              + ".LocalStrings");
    43  
    44      /**
    45       * The name of the bean containing our underlying property.
    46       */
    47      protected String name = Constants.BEAN_KEY;
    48  
    49      /**
    50       * The property name for this field.
    51       */
    52      protected String property = null;
    53  
    54      /**
    55       * The body content of this tag (if any).
    56       */
    57      protected String text = null;
    58  
    59      /**
    60       * The server value for this option.
    61       */
    62      protected String value = null;
    63  
    64      public String getName() {
    65          return (this.name);
    66      }
    67  
    68      public void setName(String name) {
    69          this.name = name;
    70      }
    71  
    72      // ------------------------------------------------------------- Properties
    73  
    74      /**
    75       * Return the property name.
    76       */
    77      public String getProperty() {
    78          return (this.property);
    79      }
    80  
    81      /**
    82       * Set the property name.
    83       *
    84       * @param property The new property name
    85       */
    86      public void setProperty(String property) {
    87          this.property = property;
    88      }
    89  
    90      /**
    91       * Return the server value.
    92       */
    93      public String getValue() {
    94          return (value == null) ? "on" : value;
    95      }
    96  
    97      /**
    98       * Set the server value.
    99       *
    100      * @param value The new server value
    101      */
    102     public void setValue(String value) {
    103         this.value = value;
    104     }
    105 
    106     // --------------------------------------------------------- Public Methods
    107 
    108     /**
    109      * Generate the required input tag. <p> Support for indexed property since
    110      * Struts 1.1
    111      *
    112      * @throws JspException if a JSP exception has occurred
    113      */
    114     public int doStartTag() throws JspException {
    115         // Create an appropriate "input" element based on our parameters
    116         StringBuffer results = new StringBuffer("<input type=\"checkbox\"");
    117 
    118         prepareAttribute(results, "name", prepareName());
    119         prepareAttribute(results, "accesskey", getAccesskey());
    120         prepareAttribute(results, "tabindex", getTabindex());
    121 
    122         prepareAttribute(results, "value", getValue());
    123 
    124         if (isChecked()) {
    125             results.append(" checked=\"checked\"");
    126         }
    127 
    128         results.append(prepareEventHandlers());
    129         results.append(prepareStyles());
    130         prepareOtherAttributes(results);
    131         results.append(getElementClose());
    132 
    133         // Print this field to our output writer
    134         TagUtils.getInstance().write(pageContext, results.toString());
    135 
    136         // Continue processing this page
    137         this.text = null;
    138 
    139         return (EVAL_BODY_TAG);
    140     }
    141 
    142     /**
    143      * Determines if the checkbox should be checked.
    144      *
    145      * @return true if checked="checked" should be rendered.
    146      * @throws JspException
    147      * @since Struts 1.2
    148      */
    149     protected boolean isChecked()
    150         throws JspException {
    151         Object result =
    152             TagUtils.getInstance().lookup(pageContext, name, property, null);
    153 
    154         if (result == null) {
    155             result = "";
    156         }
    157 
    158         result = result.toString();
    159 
    160         String checked = (String) result;
    161 
    162         return (checked.equalsIgnoreCase(this.value)
    163         || checked.equalsIgnoreCase("true") || checked.equalsIgnoreCase("yes")
    164         || checked.equalsIgnoreCase("on"));
    165     }
    166 
    167     /**
    168      * Save the associated label from the body content.
    169      *
    170      * @throws JspException if a JSP exception has occurred
    171      */
    172     public int doAfterBody() throws JspException {
    173         if (bodyContent != null) {
    174             String value = bodyContent.getString().trim();
    175 
    176             if (value.length() > 0) {
    177                 text = value;
    178             }
    179         }
    180 
    181         return (SKIP_BODY);
    182     }
    183 
    184     /**
    185      * Process the remainder of this page normally.
    186      *
    187      * @throws JspException if a JSP exception has occurred
    188      */
    189     public int doEndTag() throws JspException {
    190         // Render any description for this checkbox
    191         if (text != null) {
    192             TagUtils.getInstance().write(pageContext, text);
    193         }
    194 
    195         // Evaluate the remainder of this page
    196         return (EVAL_PAGE);
    197     }
    198 
    199     /**
    200      * Prepare the name element
    201      *
    202      * @return The element name.
    203      */
    204     protected String prepareName()
    205         throws JspException {
    206         if (property == null) {
    207             return null;
    208         }
    209 
    210         // * @since Struts 1.1
    211         if (indexed) {
    212             StringBuffer results = new StringBuffer();
    213 
    214             prepareIndex(results, name);
    215             results.append(property);
    216 
    217             return results.toString();
    218         }
    219 
    220         return property;
    221     }
    222 
    223     /**
    224      * Release any acquired resources.
    225      */
    226     public void release() {
    227         super.release();
    228         name = Constants.BEAN_KEY;
    229         property = null;
    230         text = null;
    231         value = null;
    232     }
    233 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
