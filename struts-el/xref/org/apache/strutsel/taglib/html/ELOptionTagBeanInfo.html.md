[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELOptionTagBeanInfo.html)


    1   /*
    2    * $Id: ELOptionTagBeanInfo.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELOptionTag</code> class.  It is
    32   * needed to override the default mapping of custom tag attribute names to
    33   * class attribute names. <p> This is because the value of the unevaluated EL
    34   * expression has to be kept separately from the evaluated value, which is
    35   * stored in the base class. This is related to the fact that the JSP compiler
    36   * can choose to reuse different tag instances if they received the same
    37   * original attribute values, and the JSP compiler can choose to not re-call
    38   * the setter methods, because it can assume the same values are already set.
    39   */
    40  public class ELOptionTagBeanInfo extends SimpleBeanInfo {
    41      public PropertyDescriptor[] getPropertyDescriptors() {
    42          ArrayList proplist = new ArrayList();
    43  
    44          try {
    45              proplist.add(new PropertyDescriptor("bundle", ELOptionTag.class,
    46                      null, "setBundleExpr"));
    47          } catch (IntrospectionException ex) {
    48          }
    49  
    50          try {
    51              proplist.add(new PropertyDescriptor("dir", ELOptionTag.class,
    52                      null, "setDirExpr"));
    53          } catch (IntrospectionException ex) {
    54          }
    55  
    56          try {
    57              proplist.add(new PropertyDescriptor("disabled", ELOptionTag.class,
    58                      null, "setDisabledExpr"));
    59          } catch (IntrospectionException ex) {
    60          }
    61  
    62          try {
    63              proplist.add(new PropertyDescriptor("filter", ELOptionTag.class, null,
    64                      "setFilterExpr"));
    65          } catch (IntrospectionException ex) {
    66          }
    67  
    68          try {
    69              proplist.add(new PropertyDescriptor("lang", ELOptionTag.class,
    70                      null, "setLangExpr"));
    71          } catch (IntrospectionException ex) {
    72          }
    73  
    74          try {
    75              proplist.add(new PropertyDescriptor("key", ELOptionTag.class, null,
    76                      "setKeyExpr"));
    77          } catch (IntrospectionException ex) {
    78          }
    79  
    80          try {
    81              proplist.add(new PropertyDescriptor("locale", ELOptionTag.class,
    82                      null, "setLocaleExpr"));
    83          } catch (IntrospectionException ex) {
    84          }
    85  
    86          try {
    87              proplist.add(new PropertyDescriptor("style", ELOptionTag.class,
    88                      null, "setStyleExpr"));
    89          } catch (IntrospectionException ex) {
    90          }
    91  
    92          try {
    93              proplist.add(new PropertyDescriptor("styleClass",
    94                      ELOptionTag.class, null, "setStyleClassExpr"));
    95          } catch (IntrospectionException ex) {
    96          }
    97  
    98          try {
    99              proplist.add(new PropertyDescriptor("styleId", ELOptionTag.class,
    100                     null, "setStyleIdExpr"));
    101         } catch (IntrospectionException ex) {
    102         }
    103 
    104         try {
    105             proplist.add(new PropertyDescriptor("value", ELOptionTag.class,
    106                     null, "setValueExpr"));
    107         } catch (IntrospectionException ex) {
    108         }
    109 
    110         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    111 
    112         return ((PropertyDescriptor[]) proplist.toArray(result));
    113     }
    114 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
