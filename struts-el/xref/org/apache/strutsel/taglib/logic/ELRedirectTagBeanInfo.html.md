[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/logic/ELRedirectTagBeanInfo.html.md)


    1   /*
    2    * $Id: ELRedirectTagBeanInfo.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.logic;
    22  
    23  import java.beans.IntrospectionException;
    24  import java.beans.PropertyDescriptor;
    25  import java.beans.SimpleBeanInfo;
    26  
    27  import java.util.ArrayList;
    28  
    29  /**
    30   * This is the <code>BeanInfo</code> descriptor for the
    31   * <code>org.apache.strutsel.taglib.logic.ELRedirectTag</code> class.  It is
    32   * needed to override the default mapping of custom tag attribute names to
    33   * class attribute names. <p> This is because the value of the unevaluated EL
    34   * expression has to be kept separately from the evaluated value, which is
    35   * stored in the base class. This is related to the fact that the JSP compiler
    36   * can choose to reuse different tag instances if they received the same
    37   * original attribute values, and the JSP compiler can choose to not re-call
    38   * the setter methods, because it can assume the same values are already set.
    39   */
    40  public class ELRedirectTagBeanInfo extends SimpleBeanInfo {
    41      public PropertyDescriptor[] getPropertyDescriptors() {
    42          ArrayList proplist = new ArrayList();
    43  
    44          try {
    45              proplist.add(new PropertyDescriptor("action", ELRedirectTag.class,
    46                      null, "setActionExpr"));
    47          } catch (IntrospectionException ex) {
    48          }
    49  
    50          try {
    51              proplist.add(new PropertyDescriptor("anchor", ELRedirectTag.class,
    52                      null, "setAnchorExpr"));
    53          } catch (IntrospectionException ex) {
    54          }
    55  
    56          try {
    57              proplist.add(new PropertyDescriptor("forward", ELRedirectTag.class,
    58                      null, "setForwardExpr"));
    59          } catch (IntrospectionException ex) {
    60          }
    61  
    62          try {
    63              proplist.add(new PropertyDescriptor("href", ELRedirectTag.class,
    64                      null, "setHrefExpr"));
    65          } catch (IntrospectionException ex) {
    66          }
    67  
    68          try {
    69              proplist.add(new PropertyDescriptor("name", ELRedirectTag.class,
    70                      null, "setNameExpr"));
    71          } catch (IntrospectionException ex) {
    72          }
    73  
    74          try {
    75              proplist.add(new PropertyDescriptor("page", ELRedirectTag.class,
    76                      null, "setPageExpr"));
    77          } catch (IntrospectionException ex) {
    78          }
    79  
    80          try {
    81              proplist.add(new PropertyDescriptor("paramId", ELRedirectTag.class,
    82                      null, "setParamIdExpr"));
    83          } catch (IntrospectionException ex) {
    84          }
    85  
    86          try {
    87              proplist.add(new PropertyDescriptor("paramName",
    88                      ELRedirectTag.class, null, "setParamNameExpr"));
    89          } catch (IntrospectionException ex) {
    90          }
    91  
    92          try {
    93              proplist.add(new PropertyDescriptor("paramProperty",
    94                      ELRedirectTag.class, null, "setParamPropertyExpr"));
    95          } catch (IntrospectionException ex) {
    96          }
    97  
    98          try {
    99              proplist.add(new PropertyDescriptor("paramScope",
    100                     ELRedirectTag.class, null, "setParamScopeExpr"));
    101         } catch (IntrospectionException ex) {
    102         }
    103 
    104         try {
    105             proplist.add(new PropertyDescriptor("property",
    106                     ELRedirectTag.class, null, "setPropertyExpr"));
    107         } catch (IntrospectionException ex) {
    108         }
    109 
    110         try {
    111             proplist.add(new PropertyDescriptor("scope", ELRedirectTag.class,
    112                     null, "setScopeExpr"));
    113         } catch (IntrospectionException ex) {
    114         }
    115 
    116         try {
    117             proplist.add(new PropertyDescriptor("transaction",
    118                     ELRedirectTag.class, null, "setTransactionExpr"));
    119         } catch (IntrospectionException ex) {
    120         }
    121 
    122         try {
    123             proplist.add(new PropertyDescriptor("useLocalEncoding",
    124                     ELRedirectTag.class, null, "setUseLocalEncodingExpr"));
    125         } catch (IntrospectionException ex) {
    126         }
    127 
    128         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    129 
    130         return ((PropertyDescriptor[]) proplist.toArray(result));
    131     }
    132 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
