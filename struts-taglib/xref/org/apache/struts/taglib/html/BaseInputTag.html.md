[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/BaseInputTag.html)


    1   /*
    2    * $Id: BaseInputTag.java 684382 2008-08-10 00:11:59Z niallp $
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
    23  import org.apache.struts.util.MessageResources;
    24  
    25  import javax.servlet.jsp.JspException;
    26  
    27  /**
    28   * Abstract base class for the various input tags.
    29   *
    30   * @version $Rev: 684382 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    31   *          $
    32   */
    33  public abstract class BaseInputTag extends BaseHandlerTag {
    34      /**
    35       * The message resources for this package.
    36       */
    37      protected static MessageResources messages =
    38          MessageResources.getMessageResources(Constants.Package
    39              + ".LocalStrings");
    40  
    41      // ----------------------------------------------------- Instance Variables
    42  
    43      /**
    44       * Autocomplete non standard attribute
    45       */
    46      private String autocomplete = null;
    47  
    48      /**
    49       * The number of character columns for this field, or negative for no
    50       * limit.
    51       */
    52      protected String cols = null;
    53  
    54      /**
    55       * The maximum number of characters allowed, or negative for no limit.
    56       */
    57      protected String maxlength = null;
    58  
    59      /**
    60       * The name of the field (and associated property) being processed.
    61       */
    62      protected String property = null;
    63  
    64      /**
    65       * The number of rows for this field, or negative for no limit.
    66       */
    67      protected String rows = null;
    68  
    69      /**
    70       * The value for this field, or <code>null</code> to retrieve the
    71       * corresponding property from our associated bean.
    72       */
    73      protected String value = null;
    74  
    75      /**
    76       * The name of the bean containing our underlying property.
    77       */
    78      protected String name = Constants.BEAN_KEY;
    79  
    80      // ------------------------------------------------------------- Properties
    81  
    82      /**
    83       * Return autocomplete
    84       * @since 1.3.10
    85       */
    86      public String getAutocomplete() {
    87          return autocomplete;
    88      }
    89  
    90      /**
    91       * Activate/disactivate autocompletion (on/off)
    92       * @since 1.3.10
    93       */
    94      public void setAutocomplete(String autocomplete) {
    95          this.autocomplete = autocomplete;
    96      }
    97  
    98      public String getName() {
    99          return (this.name);
    100     }
    101 
    102     public void setName(String name) {
    103         this.name = name;
    104     }
    105 
    106     /**
    107      * Return the number of columns for this field.
    108      */
    109     public String getCols() {
    110         return (this.cols);
    111     }
    112 
    113     /**
    114      * Set the number of columns for this field.
    115      *
    116      * @param cols The new number of columns
    117      */
    118     public void setCols(String cols) {
    119         this.cols = cols;
    120     }
    121 
    122     /**
    123      * Return the maximum length allowed.
    124      */
    125     public String getMaxlength() {
    126         return (this.maxlength);
    127     }
    128 
    129     /**
    130      * Set the maximum length allowed.
    131      *
    132      * @param maxlength The new maximum length
    133      */
    134     public void setMaxlength(String maxlength) {
    135         this.maxlength = maxlength;
    136     }
    137 
    138     /**
    139      * Return the property name.
    140      */
    141     public String getProperty() {
    142         return (this.property);
    143     }
    144 
    145     /**
    146      * Set the property name.
    147      *
    148      * @param property The new property name
    149      */
    150     public void setProperty(String property) {
    151         this.property = property;
    152     }
    153 
    154     /**
    155      * Return the number of rows for this field.
    156      */
    157     public String getRows() {
    158         return (this.rows);
    159     }
    160 
    161     /**
    162      * Set the number of rows for this field.
    163      *
    164      * @param rows The new number of rows
    165      */
    166     public void setRows(String rows) {
    167         this.rows = rows;
    168     }
    169 
    170     /**
    171      * Return the size of this field (synonym for <code>getCols()</code>).
    172      */
    173     public String getSize() {
    174         return (getCols());
    175     }
    176 
    177     /**
    178      * Set the size of this field (synonym for <code>setCols()</code>).
    179      *
    180      * @param size The new size
    181      */
    182     public void setSize(String size) {
    183         setCols(size);
    184     }
    185 
    186     /**
    187      * Return the field value (if any).
    188      */
    189     public String getValue() {
    190         return (this.value);
    191     }
    192 
    193     /**
    194      * Set the field value (if any).
    195      *
    196      * @param value The new field value, or <code>null</code> to retrieve the
    197      *              corresponding property from the bean
    198      */
    199     public void setValue(String value) {
    200         this.value = value;
    201     }
    202 
    203     // --------------------------------------------------------- Public Methods
    204 
    205     /**
    206      * Process the start of this tag.  The default implementation does
    207      * nothing.
    208      *
    209      * @throws JspException if a JSP exception has occurred
    210      */
    211     public int doStartTag() throws JspException {
    212         return (EVAL_BODY_TAG);
    213     }
    214 
    215     /**
    216      * Process the end of this tag.  The default implementation does nothing.
    217      *
    218      * @throws JspException if a JSP exception has occurred
    219      */
    220     public int doEndTag() throws JspException {
    221         return (EVAL_PAGE);
    222     }
    223 
    224     /**
    225      * Prepare the name element
    226      *
    227      * @return The element name.
    228      */
    229     protected String prepareName()
    230         throws JspException {
    231         if (property == null) {
    232             return null;
    233         }
    234 
    235         // * @since Struts 1.1
    236         if (indexed) {
    237             StringBuffer results = new StringBuffer();
    238 
    239             prepareIndex(results, name);
    240             results.append(property);
    241 
    242             return results.toString();
    243         }
    244 
    245         return property;
    246     }
    247 
    248     /**
    249      * Release any acquired resources.
    250      */
    251     public void release() {
    252         super.release();
    253         autocomplete = null;
    254         name = Constants.BEAN_KEY;
    255         cols = null;
    256         maxlength = null;
    257         property = null;
    258         rows = null;
    259         value = null;
    260     }
    261 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
