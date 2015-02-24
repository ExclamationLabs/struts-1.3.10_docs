[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/MultiboxTag.html)


    1   /*
    2    * $Id: MultiboxTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.beanutils.BeanUtils;
    24  import org.apache.struts.Globals;
    25  import org.apache.struts.taglib.TagUtils;
    26  import org.apache.struts.util.MessageResources;
    27  
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.PageContext;
    30  
    31  import java.lang.reflect.InvocationTargetException;
    32  
    33  /**
    34   * Tag for input fields of type "checkbox".  This differs from CheckboxTag
    35   * because it assumes that the underlying property is an array getter (of any
    36   * supported primitive type, or String), and the checkbox is initialized to
    37   * "checked" if the value listed for the "value" attribute is present in the
    38   * values returned by the property getter.
    39   *
    40   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    41   *          $
    42   */
    43  public class MultiboxTag extends BaseHandlerTag {
    44      /**
    45       * The message resources for this package.
    46       */
    47      protected static MessageResources messages =
    48          MessageResources.getMessageResources(Constants.Package
    49              + ".LocalStrings");
    50  
    51      // ----------------------------------------------------- Instance Variables
    52  
    53      /**
    54       * The constant String value to be returned when this checkbox is selected
    55       * and the form is submitted.
    56       */
    57      protected String constant = null;
    58  
    59      /**
    60       * The name of the bean containing our underlying property.
    61       */
    62      protected String name = Constants.BEAN_KEY;
    63  
    64      /**
    65       * The property name for this field.
    66       */
    67      protected String property = null;
    68  
    69      /**
    70       * The value which will mark this checkbox as "checked" if present in the
    71       * array returned by our property getter.
    72       */
    73      protected String value = null;
    74  
    75      public String getName() {
    76          return (this.name);
    77      }
    78  
    79      public void setName(String name) {
    80          this.name = name;
    81      }
    82  
    83      // ------------------------------------------------------------- Properties
    84  
    85      /**
    86       * Return the property name.
    87       */
    88      public String getProperty() {
    89          return (this.property);
    90      }
    91  
    92      /**
    93       * Set the property name.
    94       *
    95       * @param property The new property name
    96       */
    97      public void setProperty(String property) {
    98          this.property = property;
    99      }
    100 
    101     /**
    102      * Return the server value.
    103      */
    104     public String getValue() {
    105         return (this.value);
    106     }
    107 
    108     /**
    109      * Set the server value.
    110      *
    111      * @param value The new server value
    112      */
    113     public void setValue(String value) {
    114         this.value = value;
    115     }
    116 
    117     // --------------------------------------------------------- Public Methods
    118 
    119     /**
    120      * Process the beginning of this tag.
    121      *
    122      * @throws JspException if a JSP exception has occurred
    123      */
    124     public int doStartTag() throws JspException {
    125         // Defer processing until the end of this tag is encountered
    126         this.constant = null;
    127 
    128         return (EVAL_BODY_TAG);
    129     }
    130 
    131     /**
    132      * Save the body contents of this tag as the constant that we will be
    133      * returning.
    134      *
    135      * @throws JspException if a JSP exception has occurred
    136      */
    137     public int doAfterBody() throws JspException {
    138         if (bodyContent != null) {
    139             this.constant = bodyContent.getString().trim();
    140         }
    141 
    142         if ("".equals(this.constant)) {
    143             this.constant = null;
    144         }
    145 
    146         return SKIP_BODY;
    147     }
    148 
    149     /**
    150      * Render an input element for this tag.
    151      *
    152      * @throws JspException if a JSP exception has occurred
    153      */
    154     public int doEndTag() throws JspException {
    155         // Create an appropriate "input" element based on our parameters
    156         StringBuffer results = new StringBuffer("<input type=\"checkbox\"");
    157 
    158         prepareAttribute(results, "name", prepareName());
    159         prepareAttribute(results, "accesskey", getAccesskey());
    160         prepareAttribute(results, "tabindex", getTabindex());
    161 
    162         String value = prepareValue(results);
    163 
    164         prepareChecked(results, value);
    165         results.append(prepareEventHandlers());
    166         results.append(prepareStyles());
    167         prepareOtherAttributes(results);
    168         results.append(getElementClose());
    169 
    170         TagUtils.getInstance().write(pageContext, results.toString());
    171 
    172         return EVAL_PAGE;
    173     }
    174 
    175     /**
    176      * Prepare the name element
    177      *
    178      * @return The element name.
    179      */
    180     protected String prepareName()
    181         throws JspException {
    182         return property;
    183     }
    184 
    185     /**
    186      * Render the value element
    187      *
    188      * @param results The StringBuffer that output will be appended to.
    189      */
    190     protected String prepareValue(StringBuffer results)
    191         throws JspException {
    192         String value = (this.value == null) ? this.constant : this.value;
    193 
    194         if (value == null) {
    195             JspException e =
    196                 new JspException(messages.getMessage("multiboxTag.value"));
    197 
    198             pageContext.setAttribute(Globals.EXCEPTION_KEY, e,
    199                 PageContext.REQUEST_SCOPE);
    200             throw e;
    201         }
    202 
    203         prepareAttribute(results, "value", TagUtils.getInstance().filter(value));
    204 
    205         return value;
    206     }
    207 
    208     /**
    209      * Render the checked element
    210      *
    211      * @param results The StringBuffer that output will be appended to.
    212      */
    213     protected void prepareChecked(StringBuffer results, String value)
    214         throws JspException {
    215         Object bean = TagUtils.getInstance().lookup(pageContext, name, null);
    216         String[] values = null;
    217 
    218         if (bean == null) {
    219             throw new JspException(messages.getMessage("getter.bean", name));
    220         }
    221 
    222         try {
    223             values = BeanUtils.getArrayProperty(bean, property);
    224 
    225             if (values == null) {
    226                 values = new String[0];
    227             }
    228         } catch (IllegalAccessException e) {
    229             throw new JspException(messages.getMessage("getter.access",
    230                     property, name));
    231         } catch (InvocationTargetException e) {
    232             Throwable t = e.getTargetException();
    233 
    234             throw new JspException(messages.getMessage("getter.result",
    235                     property, t.toString()));
    236         } catch (NoSuchMethodException e) {
    237             throw new JspException(messages.getMessage("getter.method",
    238                     property, name));
    239         }
    240 
    241         for (int i = 0; i < values.length; i++) {
    242             if (value.equals(values[i])) {
    243                 results.append(" checked=\"checked\"");
    244 
    245                 break;
    246             }
    247         }
    248     }
    249 
    250     /**
    251      * Release any acquired resources.
    252      */
    253     public void release() {
    254         super.release();
    255         constant = null;
    256         name = Constants.BEAN_KEY;
    257         property = null;
    258         value = null;
    259     }
    260 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
