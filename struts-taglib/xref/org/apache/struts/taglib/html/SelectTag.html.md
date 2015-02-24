[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/SelectTag.html)


    1   /*
    2    * $Id: SelectTag.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.MessageResources;
    26  
    27  import javax.servlet.jsp.JspException;
    28  
    29  import java.lang.reflect.InvocationTargetException;
    30  
    31  /**
    32   * Custom tag that represents an HTML select element, associated with a bean
    33   * property specified by our attributes.  This tag must be nested inside a
    34   * form tag.
    35   *
    36   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    37   *          $
    38   */
    39  public class SelectTag extends BaseHandlerTag {
    40      /**
    41       * The message resources for this package.
    42       */
    43      protected static MessageResources messages =
    44          MessageResources.getMessageResources(Constants.Package
    45              + ".LocalStrings");
    46  
    47      // ----------------------------------------------------- Instance Variables
    48  
    49      /**
    50       * The actual values we will match against, calculated in doStartTag().
    51       */
    52      protected String[] match = null;
    53  
    54      /**
    55       * Should multiple selections be allowed.  Any non-null value will trigger
    56       * rendering this.
    57       */
    58      protected String multiple = null;
    59  
    60      /**
    61       * The name of the bean containing our underlying property.
    62       */
    63      protected String name = Constants.BEAN_KEY;
    64  
    65      /**
    66       * The property name we are associated with.
    67       */
    68      protected String property = null;
    69  
    70      /**
    71       * The saved body content of this tag.
    72       */
    73      protected String saveBody = null;
    74  
    75      /**
    76       * How many available options should be displayed when this element is
    77       * rendered?
    78       */
    79      protected String size = null;
    80  
    81      /**
    82       * The value to compare with for marking an option selected.
    83       */
    84      protected String value = null;
    85  
    86      public String getMultiple() {
    87          return (this.multiple);
    88      }
    89  
    90      public void setMultiple(String multiple) {
    91          this.multiple = multiple;
    92      }
    93  
    94      public String getName() {
    95          return (this.name);
    96      }
    97  
    98      public void setName(String name) {
    99          this.name = name;
    100     }
    101 
    102     public String getSize() {
    103         return (this.size);
    104     }
    105 
    106     public void setSize(String size) {
    107         this.size = size;
    108     }
    109 
    110     // ------------------------------------------------------------- Properties
    111 
    112     /**
    113      * Does the specified value match one of those we are looking for?
    114      *
    115      * @param value Value to be compared.
    116      */
    117     public boolean isMatched(String value) {
    118         if ((this.match == null) || (value == null)) {
    119             return false;
    120         }
    121 
    122         for (int i = 0; i < this.match.length; i++) {
    123             if (value.equals(this.match[i])) {
    124                 return true;
    125             }
    126         }
    127 
    128         return false;
    129     }
    130 
    131     /**
    132      * Return the property name.
    133      */
    134     public String getProperty() {
    135         return (this.property);
    136     }
    137 
    138     /**
    139      * Set the property name.
    140      *
    141      * @param property The new property name
    142      */
    143     public void setProperty(String property) {
    144         this.property = property;
    145     }
    146 
    147     /**
    148      * Return the comparison value.
    149      */
    150     public String getValue() {
    151         return (this.value);
    152     }
    153 
    154     /**
    155      * Set the comparison value.
    156      *
    157      * @param value The new comparison value
    158      */
    159     public void setValue(String value) {
    160         this.value = value;
    161     }
    162 
    163     // --------------------------------------------------------- Public Methods
    164 
    165     /**
    166      * Render the beginning of this select tag. <p> Support for indexed
    167      * property since Struts 1.1
    168      *
    169      * @throws JspException if a JSP exception has occurred
    170      */
    171     public int doStartTag() throws JspException {
    172         TagUtils.getInstance().write(pageContext, renderSelectStartElement());
    173 
    174         // Store this tag itself as a page attribute
    175         pageContext.setAttribute(Constants.SELECT_KEY, this);
    176 
    177         this.calculateMatchValues();
    178 
    179         return (EVAL_BODY_TAG);
    180     }
    181 
    182     /**
    183      * Create an appropriate select start element based on our parameters.
    184      *
    185      * @throws JspException
    186      * @since Struts 1.1
    187      */
    188     protected String renderSelectStartElement()
    189         throws JspException {
    190         StringBuffer results = new StringBuffer("<select");
    191 
    192         prepareAttribute(results, "name", prepareName());
    193         prepareAttribute(results, "accesskey", getAccesskey());
    194 
    195         if (multiple != null) {
    196             results.append(" multiple=\"multiple\"");
    197         }
    198 
    199         prepareAttribute(results, "size", getSize());
    200         prepareAttribute(results, "tabindex", getTabindex());
    201         results.append(prepareEventHandlers());
    202         results.append(prepareStyles());
    203         prepareOtherAttributes(results);
    204         results.append(">");
    205 
    206         return results.toString();
    207     }
    208 
    209     /**
    210      * Calculate the match values we will actually be using.
    211      *
    212      * @throws JspException
    213      */
    214     private void calculateMatchValues()
    215         throws JspException {
    216         if (this.value != null) {
    217             this.match = new String[1];
    218             this.match[0] = this.value;
    219         } else {
    220             Object bean =
    221                 TagUtils.getInstance().lookup(pageContext, name, null);
    222 
    223             if (bean == null) {
    224                 JspException e =
    225                     new JspException(messages.getMessage("getter.bean", name));
    226 
    227                 TagUtils.getInstance().saveException(pageContext, e);
    228                 throw e;
    229             }
    230 
    231             try {
    232                 this.match = BeanUtils.getArrayProperty(bean, property);
    233 
    234                 if (this.match == null) {
    235                     this.match = new String[0];
    236                 }
    237             } catch (IllegalAccessException e) {
    238                 TagUtils.getInstance().saveException(pageContext, e);
    239                 throw new JspException(messages.getMessage("getter.access",
    240                         property, name));
    241             } catch (InvocationTargetException e) {
    242                 Throwable t = e.getTargetException();
    243 
    244                 TagUtils.getInstance().saveException(pageContext, t);
    245                 throw new JspException(messages.getMessage("getter.result",
    246                         property, t.toString()));
    247             } catch (NoSuchMethodException e) {
    248                 TagUtils.getInstance().saveException(pageContext, e);
    249                 throw new JspException(messages.getMessage("getter.method",
    250                         property, name));
    251             }
    252         }
    253     }
    254 
    255     /**
    256      * Save any body content of this tag, which will generally be the
    257      * option(s) representing the values displayed to the user.
    258      *
    259      * @throws JspException if a JSP exception has occurred
    260      */
    261     public int doAfterBody() throws JspException {
    262         if (bodyContent != null) {
    263             String value = bodyContent.getString();
    264 
    265             if (value == null) {
    266                 value = "";
    267             }
    268 
    269             this.saveBody = value.trim();
    270         }
    271 
    272         return (SKIP_BODY);
    273     }
    274 
    275     /**
    276      * Render the end of this form.
    277      *
    278      * @throws JspException if a JSP exception has occurred
    279      */
    280     public int doEndTag() throws JspException {
    281         // Remove the page scope attributes we created
    282         pageContext.removeAttribute(Constants.SELECT_KEY);
    283 
    284         // Render a tag representing the end of our current form
    285         StringBuffer results = new StringBuffer();
    286 
    287         if (saveBody != null) {
    288             results.append(saveBody);
    289             saveBody = null;
    290         }
    291 
    292         results.append("</select>");
    293 
    294         TagUtils.getInstance().write(pageContext, results.toString());
    295 
    296         return (EVAL_PAGE);
    297     }
    298 
    299     /**
    300      * Prepare the name element
    301      *
    302      * @return The element name.
    303      */
    304     protected String prepareName()
    305         throws JspException {
    306         if (property == null) {
    307             return null;
    308         }
    309 
    310         // * @since Struts 1.1
    311         if (indexed) {
    312             StringBuffer results = new StringBuffer();
    313 
    314             prepareIndex(results, name);
    315             results.append(property);
    316 
    317             return results.toString();
    318         }
    319 
    320         return property;
    321     }
    322 
    323     /**
    324      * Release any acquired resources.
    325      */
    326     public void release() {
    327         super.release();
    328         match = null;
    329         multiple = null;
    330         name = Constants.BEAN_KEY;
    331         property = null;
    332         saveBody = null;
    333         size = null;
    334         value = null;
    335     }
    336 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
