[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELJavascriptValidatorTagBeanInfo.html)


    1   /*
    2    * $Id: ELJavascriptValidatorTagBeanInfo.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.html.md;
    22  
    23  import java.beans.IntrospectionException;
    24  import java.beans.PropertyDescriptor;
    25  import java.beans.SimpleBeanInfo;
    26  
    27  import java.util.ArrayList;
    28  
    29  /**
    30   * This is the <code>BeanInfo</code> descriptor for the
    31   * <code>org.apache.strutsel.taglib.html.md.ELJavascriptValidatorTag</code>
    32   * class. It is needed to override the default mapping of custom tag attribute
    33   * names to class attribute names. <p> This is because the value of the
    34   * unevaluated EL expression has to be kept separately from the evaluated
    35   * value, which is stored in the base class. This is related to the fact that
    36   * the JSP compiler can choose to reuse different tag instances if they
    37   * received the same original attribute values, and the JSP compiler can
    38   * choose to not re-call the setter methods, because it can assume the same
    39   * values are already set.
    40   */
    41  public class ELJavascriptValidatorTagBeanInfo extends SimpleBeanInfo {
    42      public PropertyDescriptor[] getPropertyDescriptors() {
    43          ArrayList proplist = new ArrayList();
    44  
    45          try {
    46              proplist.add(new PropertyDescriptor("cdata",
    47                      ELJavascriptValidatorTag.class, null, "setCdataExpr"));
    48          } catch (IntrospectionException ex) {
    49          }
    50  
    51          try {
    52              proplist.add(new PropertyDescriptor("dynamicJavascript",
    53                      ELJavascriptValidatorTag.class, null,
    54                      "setDynamicJavascriptExpr"));
    55          } catch (IntrospectionException ex) {
    56          }
    57  
    58          try {
    59              proplist.add(new PropertyDescriptor("formName",
    60                      ELJavascriptValidatorTag.class, null, "setFormNameExpr"));
    61          } catch (IntrospectionException ex) {
    62          }
    63  
    64          try {
    65              proplist.add(new PropertyDescriptor("method",
    66                      ELJavascriptValidatorTag.class, null, "setMethodExpr"));
    67          } catch (IntrospectionException ex) {
    68          }
    69  
    70          try {
    71              proplist.add(new PropertyDescriptor("page",
    72                      ELJavascriptValidatorTag.class, null, "setPageExpr"));
    73          } catch (IntrospectionException ex) {
    74          }
    75  
    76          try {
    77              proplist.add(new PropertyDescriptor("scriptLanguage",
    78                      ELJavascriptValidatorTag.class, null,
    79                      "setScriptLanguageExpr"));
    80          } catch (IntrospectionException ex) {
    81          }
    82  
    83          try {
    84              proplist.add(new PropertyDescriptor("src",
    85                      ELJavascriptValidatorTag.class, null, "setSrcExpr"));
    86          } catch (IntrospectionException ex) {
    87          }
    88  
    89          try {
    90              proplist.add(new PropertyDescriptor("staticJavascript",
    91                      ELJavascriptValidatorTag.class, null,
    92                      "setStaticJavascriptExpr"));
    93          } catch (IntrospectionException ex) {
    94          }
    95  
    96          try {
    97              proplist.add(new PropertyDescriptor(.html.mdComment",
    98                      ELJavascriptValidatorTag.class, null, "setHtmlCommentExpr"));
    99          } catch (IntrospectionException ex) {
    100         }
    101 
    102         try {
    103             proplist.add(new PropertyDescriptor("bundle",
    104                     ELJavascriptValidatorTag.class, null, "setBundleExpr"));
    105         } catch (IntrospectionException ex) {
    106         }
    107 
    108         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    109 
    110         return ((PropertyDescriptor[]) proplist.toArray(result));
    111     }
    112 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
