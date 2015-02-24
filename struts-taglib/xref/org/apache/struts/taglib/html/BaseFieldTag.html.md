[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/BaseFieldTag.html)


    1   /*
    2    * $Id: BaseFieldTag.java 684305 2008-08-09 17:43:00Z niallp $
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
    24  
    25  import javax.servlet.jsp.JspException;
    26  
    27  /**
    28   * Convenience base class for the various input tags for text fields.
    29   *
    30   * @version $Rev: 684305 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    31   *          $
    32   */
    33  public abstract class BaseFieldTag extends BaseInputTag {
    34      // ----------------------------------------------------- Instance Variables
    35  
    36      /**
    37       * Comma-delimited list of content types that a server processing this
    38       * form will handle correctly.  This property is defined only for the
    39       * <code>file</code> tag, but is implemented here because it affects the
    40       * rendered HTML of the corresponding &lt;input&gt; tag.
    41       */
    42      protected String accept = null;
    43  
    44      /**
    45       * The "redisplay contents" flag (used only on <code>password</code>).
    46       */
    47      protected boolean redisplay = true;
    48  
    49      /**
    50       * The type of input field represented by this tag (text, password, or
    51       * hidden).
    52       */
    53      protected String type = null;
    54  
    55      public String getAccept() {
    56          return (this.accept);
    57      }
    58  
    59      public void setAccept(String accept) {
    60          this.accept = accept;
    61      }
    62  
    63      public boolean getRedisplay() {
    64          return (this.redisplay);
    65      }
    66  
    67      public void setRedisplay(boolean redisplay) {
    68          this.redisplay = redisplay;
    69      }
    70  
    71      // --------------------------------------------------------- Public Methods
    72  
    73      /**
    74       * Generate the required input tag. <p> Support for indexed property since
    75       * Struts 1.1
    76       *
    77       * @throws JspException if a JSP exception has occurred
    78       */
    79      public int doStartTag() throws JspException {
    80          TagUtils.getInstance().write(this.pageContext, this.renderInputElement());
    81  
    82          return (EVAL_BODY_TAG);
    83      }
    84  
    85      /**
    86       * Renders a fully formed &lt;input&gt; element.
    87       *
    88       * @throws JspException
    89       * @since Struts 1.2
    90       */
    91      protected String renderInputElement()
    92          throws JspException {
    93          StringBuffer results = new StringBuffer("<input");
    94  
    95          prepareAttribute(results, "type", this.type);
    96          prepareAttribute(results, "name", prepareName());
    97          prepareAttribute(results, "accesskey", getAccesskey());
    98          prepareAttribute(results, "accept", getAccept());
    99          prepareAttribute(results, "maxlength", getMaxlength());
    100         prepareAttribute(results, "size", getCols());
    101         prepareAttribute(results, "tabindex", getTabindex());
    102         prepareValue(results);
    103         results.append(this.prepareEventHandlers());
    104         results.append(this.prepareStyles());
    105         if (!is.html.md()) {
    106             prepareAttribute(results, "autocomplete", getAutocomplete());
    107         }
    108         prepareOtherAttributes(results);
    109         results.append(this.getElementClose());
    110 
    111         return results.toString();
    112     }
    113 
    114     /**
    115      * Render the value element
    116      *
    117      * @param results The StringBuffer that output will be appended to.
    118      */
    119     protected void prepareValue(StringBuffer results)
    120         throws JspException {
    121         results.append(" value=\"");
    122 
    123         if (value != null) {
    124             results.append(this.formatValue(value));
    125         } else if (redisplay || !"password".equals(type)) {
    126             Object value =
    127                 TagUtils.getInstance().lookup(pageContext, name, property, null);
    128 
    129             results.append(this.formatValue(value));
    130         }
    131 
    132         results.append('"');
    133     }
    134 
    135     /**
    136      * Return the given value as a formatted <code>String</code>.  This
    137      * implementation escapes potentially harmful HTML characters.
    138      *
    139      * @param value The value to be formatted. <code>null</code> values will
    140      *              be returned as the empty String "".
    141      * @throws JspException if a JSP exception has occurred
    142      * @since Struts 1.2
    143      */
    144     protected String formatValue(Object value)
    145         throws JspException {
    146         if (value == null) {
    147             return "";
    148         }
    149 
    150         return TagUtils.getInstance().filter(value.toString());
    151     }
    152 
    153     /**
    154      * Release any acquired resources.
    155      */
    156     public void release() {
    157         super.release();
    158         accept = null;
    159         name = Constants.BEAN_KEY;
    160         redisplay = true;
    161     }
    162 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
