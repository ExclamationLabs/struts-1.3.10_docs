[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/RadioTag.html)


    1   /*
    2    * $Id: RadioTag.java 471754 2006-11-06 14:55:09Z husted $
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
    29   * Tag for input fields of type "radio".
    30   *
    31   * @version $Rev: 471754 $ $Date: 2005-06-14 14:26:17 -0400 (Tue, 14 Jun 2005)
    32   *          $
    33   */
    34  public class RadioTag extends BaseHandlerTag {
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
    64      /**
    65       * Name of the bean (in some scope) that will return the value of the
    66       * radio tag. <p> If an iterator is used to render a series of radio tags,
    67       * this field may be used to specify the name of the bean exposed by the
    68       * iterator. In this case, the value attribute is used as the name of a
    69       * property on the <code>idName</code> bean that returns the value of the
    70       * radio tag in this iteration.
    71       */
    72      protected String idName = null;
    73  
    74      public String getName() {
    75          return (this.name);
    76      }
    77  
    78      public void setName(String name) {
    79          this.name = name;
    80      }
    81  
    82      // ------------------------------------------------------------- Properties
    83  
    84      /**
    85       * Return the property name.
    86       */
    87      public String getProperty() {
    88          return (this.property);
    89      }
    90  
    91      /**
    92       * Set the property name.
    93       *
    94       * @param property The new property name
    95       */
    96      public void setProperty(String property) {
    97          this.property = property;
    98      }
    99  
    100     /**
    101      * Return the server value.
    102      */
    103     public String getValue() {
    104         return (this.value);
    105     }
    106 
    107     /**
    108      * Set the server value.
    109      *
    110      * @param value The new server value
    111      */
    112     public void setValue(String value) {
    113         this.value = value;
    114     }
    115 
    116     /**
    117      * Return the idName.
    118      *
    119      * @since Struts 1.1
    120      */
    121     public String getIdName() {
    122         return (this.idName);
    123     }
    124 
    125     /**
    126      * Set the idName.
    127      *
    128      * @param idName The new idName
    129      * @since Struts 1.1
    130      */
    131     public void setIdName(String idName) {
    132         this.idName = idName;
    133     }
    134 
    135     // --------------------------------------------------------- Public Methods
    136 
    137     /**
    138      * Generate the required input tag. [Indexed property since Struts 1.1]
    139      *
    140      * @throws JspException if a JSP exception has occurred
    141      */
    142     public int doStartTag() throws JspException {
    143         String radioTag = renderRadioElement(serverValue(), currentValue());
    144 
    145         TagUtils.getInstance().write(pageContext, radioTag);
    146 
    147         this.text = null;
    148 
    149         return (EVAL_BODY_TAG);
    150     }
    151 
    152     /**
    153      * Return the String to be used in the radio tag's <code>value</code>
    154      * attribute that gets sent to the server on form submission.
    155      *
    156      * @throws JspException
    157      */
    158     private String serverValue()
    159         throws JspException {
    160         // Not using indexed radio buttons
    161         if (this.idName == null) {
    162             return this.value;
    163         }
    164 
    165         String serverValue = this.lookupProperty(this.idName, this.value);
    166 
    167         return (serverValue == null) ? "" : serverValue;
    168     }
    169 
    170     /**
    171      * Acquire the current value of the bean specified by the
    172      * <code>name</code> attribute and the property specified by the
    173      * <code>property</code> attribute. This radio button with this value will
    174      * be checked.
    175      *
    176      * @throws JspException
    177      */
    178     private String currentValue()
    179         throws JspException {
    180         String current = this.lookupProperty(this.name, this.property);
    181 
    182         return (current == null) ? "" : current;
    183     }
    184 
    185     /**
    186      * Renders an HTML &lt;input type="radio"&gt; element.
    187      *
    188      * @param serverValue  The data to be used in the tag's <code>value</code>
    189      *                     attribute and sent to the server when the form is
    190      *                     submitted.
    191      * @param checkedValue If the serverValue equals this value the radio
    192      *                     button will be checked.
    193      * @return A radio input element.
    194      * @throws JspException
    195      * @since Struts 1.1
    196      */
    197     protected String renderRadioElement(String serverValue, String checkedValue)
    198         throws JspException {
    199         StringBuffer results = new StringBuffer("<input type=\"radio\"");
    200 
    201         prepareAttribute(results, "name", prepareName());
    202         prepareAttribute(results, "accesskey", getAccesskey());
    203         prepareAttribute(results, "tabindex", getTabindex());
    204         prepareAttribute(results, "value",
    205             TagUtils.getInstance().filter(serverValue));
    206 
    207         if (serverValue.equals(checkedValue)) {
    208             results.append(" checked=\"checked\"");
    209         }
    210 
    211         results.append(prepareEventHandlers());
    212         results.append(prepareStyles());
    213         prepareOtherAttributes(results);
    214         results.append(getElementClose());
    215 
    216         return results.toString();
    217     }
    218 
    219     /**
    220      * Save the associated label from the body content.
    221      *
    222      * @throws JspException if a JSP exception has occurred
    223      */
    224     public int doAfterBody() throws JspException {
    225         if (this.bodyContent != null) {
    226             String value = this.bodyContent.getString().trim();
    227 
    228             if (value.length() > 0) {
    229                 this.text = value;
    230             }
    231         }
    232 
    233         return (SKIP_BODY);
    234     }
    235 
    236     /**
    237      * Optionally render the associated label from the body content.
    238      *
    239      * @throws JspException if a JSP exception has occurred
    240      */
    241     public int doEndTag() throws JspException {
    242         // Render any description for this radio button
    243         if (this.text != null) {
    244             TagUtils.getInstance().write(pageContext, text);
    245         }
    246 
    247         return (EVAL_PAGE);
    248     }
    249 
    250     /**
    251      * Prepare the name element
    252      *
    253      * @return The element name.
    254      */
    255     protected String prepareName()
    256         throws JspException {
    257         if (property == null) {
    258             return null;
    259         }
    260 
    261         // * @since Struts 1.1
    262         if (indexed) {
    263             StringBuffer results = new StringBuffer();
    264 
    265             prepareIndex(results, name);
    266             results.append(property);
    267 
    268             return results.toString();
    269         }
    270 
    271         return property;
    272     }
    273 
    274     /**
    275      * Release any acquired resources.
    276      */
    277     public void release() {
    278         super.release();
    279         idName = null;
    280         name = Constants.BEAN_KEY;
    281         property = null;
    282         text = null;
    283         value = null;
    284     }
    285 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
