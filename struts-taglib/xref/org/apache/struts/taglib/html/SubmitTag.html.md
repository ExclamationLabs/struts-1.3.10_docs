[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/SubmitTag.html)


    1   /*
    2    * $Id: SubmitTag.java 471754 2006-11-06 14:55:09Z husted $
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
    29   * Tag for input fields of type "submit".
    30   *
    31   * @version $Rev: 471754 $ $Date: 2005-04-06 02:22:39 -0400 (Wed, 06 Apr 2005)
    32   *          $
    33   */
    34  public class SubmitTag extends BaseHandlerTag {
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
    45       * The name of the generated input field.
    46       */
    47      protected String property = null;
    48  
    49      /**
    50       * The body content of this tag (if any).
    51       */
    52      protected String text = null;
    53  
    54      /**
    55       * The value of the button label.
    56       */
    57      protected String value = null;
    58  
    59      // ------------------------------------------------------------- Properties
    60  
    61      /**
    62       * Return the property.
    63       */
    64      public String getProperty() {
    65          return (this.property);
    66      }
    67  
    68      /**
    69       * Set the property name.
    70       *
    71       * @param property The property name
    72       */
    73      public void setProperty(String property) {
    74          this.property = property;
    75      }
    76  
    77      /**
    78       * Return the label value.
    79       */
    80      public String getValue() {
    81          return (this.value);
    82      }
    83  
    84      /**
    85       * Set the label value.
    86       *
    87       * @param value The label value
    88       */
    89      public void setValue(String value) {
    90          this.value = value;
    91      }
    92  
    93      // --------------------------------------------------------- Public Methods
    94  
    95      /**
    96       * Process the start of this tag.
    97       *
    98       * @throws JspException if a JSP exception has occurred
    99       */
    100     public int doStartTag() throws JspException {
    101         // Do nothing until doEndTag() is called
    102         this.text = null;
    103 
    104         return (EVAL_BODY_TAG);
    105     }
    106 
    107     /**
    108      * Save the associated label from the body content.
    109      *
    110      * @throws JspException if a JSP exception has occurred
    111      */
    112     public int doAfterBody() throws JspException {
    113         if (bodyContent != null) {
    114             String value = bodyContent.getString().trim();
    115 
    116             if (value.length() > 0) {
    117                 text = value;
    118             }
    119         }
    120 
    121         return (SKIP_BODY);
    122     }
    123 
    124     /**
    125      * Process the end of this tag. <p> Support for Indexed property since
    126      * Struts 1.1
    127      *
    128      * @throws JspException if a JSP exception has occurred
    129      */
    130     public int doEndTag() throws JspException {
    131         // Generate an HTML element
    132         StringBuffer results = new StringBuffer();
    133 
    134         results.append(getElementOpen());
    135         prepareAttribute(results, "name", prepareName());
    136         prepareButtonAttributes(results);
    137         results.append(prepareEventHandlers());
    138         results.append(prepareStyles());
    139         prepareOtherAttributes(results);
    140         results.append(getElementClose());
    141 
    142         TagUtils.getInstance().write(pageContext, results.toString());
    143 
    144         return (EVAL_PAGE);
    145     }
    146 
    147     /**
    148      * Render the opening element.
    149      *
    150      * @return The opening part of the element.
    151      */
    152     protected String getElementOpen() {
    153         return "<input type=\"submit\"";
    154     }
    155 
    156     /**
    157      * Prepare the name element
    158      *
    159      * @return The element name.
    160      */
    161     protected String prepareName()
    162         throws JspException {
    163         if (property == null) {
    164             return null;
    165         }
    166 
    167         // * @since Struts 1.1
    168         if (indexed) {
    169             StringBuffer results = new StringBuffer();
    170 
    171             results.append(property);
    172             prepareIndex(results, null);
    173 
    174             return results.toString();
    175         }
    176 
    177         return property;
    178     }
    179 
    180     /**
    181      * Render the button attributes
    182      *
    183      * @param results The StringBuffer that output will be appended to.
    184      */
    185     protected void prepareButtonAttributes(StringBuffer results)
    186         throws JspException {
    187         prepareAttribute(results, "accesskey", getAccesskey());
    188         prepareAttribute(results, "tabindex", getTabindex());
    189         prepareValue(results);
    190     }
    191 
    192     /**
    193      * Render the value element
    194      *
    195      * @param results The StringBuffer that output will be appended to.
    196      */
    197     protected void prepareValue(StringBuffer results) {
    198         // Acquire the label value we will be generating
    199         String label = value;
    200 
    201         if ((label == null) && (text != null)) {
    202             label = text;
    203         }
    204 
    205         if ((label == null) || (label.length() < 1)) {
    206             label = getDefaultValue();
    207         }
    208 
    209         prepareAttribute(results, "value", label);
    210     }
    211 
    212     /**
    213      * Return the default value.
    214      *
    215      * @return The default value if none supplied.
    216      */
    217     protected String getDefaultValue() {
    218         return "Submit";
    219     }
    220 
    221     /**
    222      * Release any acquired resources.
    223      */
    224     public void release() {
    225         super.release();
    226         property = null;
    227         text = null;
    228         value = null;
    229     }
    230 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
