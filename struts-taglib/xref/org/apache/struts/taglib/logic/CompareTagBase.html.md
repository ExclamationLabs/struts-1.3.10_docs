[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/CompareTagBase.html.md)


    1   /*
    2    * $Id: CompareTagBase.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.logic;
    22  
    23  import org.apache.commons.beanutils.PropertyUtils;
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.MessageResources;
    26  
    27  import javax.servlet.http.Cookie;
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.jsp.JspException;
    30  
    31  import java.lang.reflect.InvocationTargetException;
    32  
    33  /**
    34   * Abstract base class for comparison tags.  Concrete subclasses need only
    35   * define values for desired1 and desired2.
    36   *
    37   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    38   *          $
    39   */
    40  public abstract class CompareTagBase extends ConditionalTagBase {
    41      // ----------------------------------------------------- Instance Variables
    42  
    43      /**
    44       * We will do a double/float comparison.
    45       */
    46      protected static final int DOUBLE_COMPARE = 0;
    47  
    48      /**
    49       * We will do a long/int comparison.
    50       */
    51      protected static final int LONG_COMPARE = 1;
    52  
    53      /**
    54       * We will do a String comparison.
    55       */
    56      protected static final int STRING_COMPARE = 2;
    57  
    58      /**
    59       * The message resources for this package.
    60       */
    61      protected static MessageResources messages =
    62          MessageResources.getMessageResources(
    63              "org.apache.struts.taglib.logic.LocalStrings");
    64  
    65      // ------------------------------------------------------------ Properties
    66  
    67      /**
    68       * The value to which the variable specified by other attributes of this
    69       * tag will be compared.
    70       */
    71      public String value = null;
    72  
    73      public String getValue() {
    74          return (this.value);
    75      }
    76  
    77      public void setValue(String value) {
    78          this.value = value;
    79      }
    80  
    81      // --------------------------------------------------------- Public Methods
    82  
    83      /**
    84       * Release all allocated resources.
    85       */
    86      public void release() {
    87          super.release();
    88          value = null;
    89      }
    90  
    91      // ------------------------------------------------------ Protected Methods
    92  
    93      /**
    94       * Evaluate the condition that is being tested by this particular tag, and
    95       * return <code>true</code> if the nested body content of this tag should
    96       * be evaluated, or <code>false</code> if it should be skipped. This
    97       * method must be implemented by concrete subclasses.
    98       *
    99       * @throws JspException if a JSP exception occurs
    100      */
    101     protected abstract boolean condition()
    102         throws JspException;
    103 
    104     /**
    105      * Evaluate the condition that is being tested by this particular tag, and
    106      * return <code>true</code> if the nested body content of this tag should
    107      * be evaluated, or <code>false</code> if it should be skipped. This
    108      * method must be implemented by concrete subclasses.
    109      *
    110      * @param desired1 First desired value for a true result (-1, 0, +1)
    111      * @param desired2 Second desired value for a true result (-1, 0, +1)
    112      * @throws JspException if a JSP exception occurs
    113      */
    114     protected boolean condition(int desired1, int desired2)
    115         throws JspException {
    116         // Acquire the value and determine the test type
    117         int type = -1;
    118         double doubleValue = 0.0;
    119         long longValue = 0;
    120 
    121         if ((type < 0) && (value.length() > 0)) {
    122             try {
    123                 doubleValue = Double.parseDouble(value);
    124                 type = DOUBLE_COMPARE;
    125             } catch (NumberFormatException e) {
    126                 ;
    127             }
    128         }
    129 
    130         if ((type < 0) && (value.length() > 0)) {
    131             try {
    132                 longValue = Long.parseLong(value);
    133                 type = LONG_COMPARE;
    134             } catch (NumberFormatException e) {
    135                 ;
    136             }
    137         }
    138 
    139         if (type < 0) {
    140             type = STRING_COMPARE;
    141         }
    142 
    143         // Acquire the unconverted variable value
    144         Object variable = null;
    145 
    146         if (cookie != null) {
    147             Cookie[] cookies =
    148                 ((HttpServletRequest) pageContext.getRequest()).getCookies();
    149 
    150             if (cookies == null) {
    151                 cookies = new Cookie[0];
    152             }
    153 
    154             for (int i = 0; i < cookies.length; i++) {
    155                 if (cookie.equals(cookies[i].getName())) {
    156                     variable = cookies[i].getValue();
    157 
    158                     break;
    159                 }
    160             }
    161         } else if (header != null) {
    162             variable =
    163                 ((HttpServletRequest) pageContext.getRequest()).getHeader(header);
    164         } else if (name != null) {
    165             Object bean =
    166                 TagUtils.getInstance().lookup(pageContext, name, scope);
    167 
    168             if (property != null) {
    169                 if (bean == null) {
    170                     JspException e =
    171                         new JspException(messages.getMessage("logic.bean", name));
    172 
    173                     TagUtils.getInstance().saveException(pageContext, e);
    174                     throw e;
    175                 }
    176 
    177                 try {
    178                     variable = PropertyUtils.getProperty(bean, property);
    179                 } catch (InvocationTargetException e) {
    180                     Throwable t = e.getTargetException();
    181 
    182                     if (t == null) {
    183                         t = e;
    184                     }
    185 
    186                     TagUtils.getInstance().saveException(pageContext, t);
    187                     throw new JspException(messages.getMessage(
    188                             "logic.property", name, property, t.toString()));
    189                 } catch (Throwable t) {
    190                     TagUtils.getInstance().saveException(pageContext, t);
    191                     throw new JspException(messages.getMessage(
    192                             "logic.property", name, property, t.toString()));
    193                 }
    194             } else {
    195                 variable = bean;
    196             }
    197         } else if (parameter != null) {
    198             variable = pageContext.getRequest().getParameter(parameter);
    199         } else {
    200             JspException e =
    201                 new JspException(messages.getMessage("logic.selector"));
    202 
    203             TagUtils.getInstance().saveException(pageContext, e);
    204             throw e;
    205         }
    206 
    207         if (variable == null) {
    208             variable = ""; // Coerce null to a zero-length String
    209         }
    210 
    211         // Perform the appropriate comparison
    212         int result = 0;
    213 
    214         if (type == DOUBLE_COMPARE) {
    215             try {
    216                 double doubleVariable = Double.parseDouble(variable.toString());
    217 
    218                 if (doubleVariable < doubleValue) {
    219                     result = -1;
    220                 } else if (doubleVariable > doubleValue) {
    221                     result = +1;
    222                 }
    223             } catch (NumberFormatException e) {
    224                 result = variable.toString().compareTo(value);
    225             }
    226         } else if (type == LONG_COMPARE) {
    227             try {
    228                 long longVariable = Long.parseLong(variable.toString());
    229 
    230                 if (longVariable < longValue) {
    231                     result = -1;
    232                 } else if (longVariable > longValue) {
    233                     result = +1;
    234                 }
    235             } catch (NumberFormatException e) {
    236                 result = variable.toString().compareTo(value);
    237             }
    238         } else {
    239             result = variable.toString().compareTo(value);
    240         }
    241 
    242         // Normalize the result
    243         if (result < 0) {
    244             result = -1;
    245         } else if (result > 0) {
    246             result = +1;
    247         }
    248 
    249         // Return true if the result matches either desired value
    250         return ((result == desired1) || (result == desired2));
    251     }
    252 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
