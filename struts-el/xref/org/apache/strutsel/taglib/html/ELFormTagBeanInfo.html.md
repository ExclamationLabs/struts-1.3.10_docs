[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELFormTagBeanInfo.html)


    1   /*
    2    * $Id: ELFormTagBeanInfo.java 479637 2006-11-27 14:35:06Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELFormTag</code> class.  It is needed
    32   * to override the default mapping of custom tag attribute names to class
    33   * attribute names.
    34   */
    35  public class ELFormTagBeanInfo extends SimpleBeanInfo {
    36      public PropertyDescriptor[] getPropertyDescriptors() {
    37          ArrayList proplist = new ArrayList();
    38  
    39          try {
    40              proplist.add(new PropertyDescriptor("action", ELFormTag.class,
    41                      null, "setActionExpr"));
    42          } catch (IntrospectionException ex) {
    43          }
    44  
    45          try {
    46              proplist.add(new PropertyDescriptor("dir", ELFormTag.class,
    47                      null, "setDirExpr"));
    48          } catch (IntrospectionException ex) {
    49          }
    50  
    51          try {
    52              proplist.add(new PropertyDescriptor("disabled", ELFormTag.class,
    53                      null, "setDisabledExpr"));
    54          } catch (IntrospectionException ex) {
    55          }
    56  
    57          try {
    58              proplist.add(new PropertyDescriptor("enctype", ELFormTag.class,
    59                      null, "setEnctypeExpr"));
    60          } catch (IntrospectionException ex) {
    61          }
    62  
    63          try {
    64              proplist.add(new PropertyDescriptor("focus", ELFormTag.class, null,
    65                      "setFocusExpr"));
    66          } catch (IntrospectionException ex) {
    67          }
    68  
    69          try {
    70              proplist.add(new PropertyDescriptor("focusIndex", ELFormTag.class,
    71                      null, "setFocusIndexExpr"));
    72          } catch (IntrospectionException ex) {
    73          }
    74  
    75          try {
    76              proplist.add(new PropertyDescriptor("lang", ELFormTag.class,
    77                      null, "setLangExpr"));
    78          } catch (IntrospectionException ex) {
    79          }
    80  
    81          try {
    82              proplist.add(new PropertyDescriptor("method", ELFormTag.class,
    83                      null, "setMethodExpr"));
    84          } catch (IntrospectionException ex) {
    85          }
    86  
    87          try {
    88              proplist.add(new PropertyDescriptor("name", ELFormTag.class, null,
    89                      "setNameExpr"));
    90          } catch (IntrospectionException ex) {
    91          }
    92  
    93          try {
    94              proplist.add(new PropertyDescriptor("onreset", ELFormTag.class,
    95                      null, "setOnresetExpr"));
    96          } catch (IntrospectionException ex) {
    97          }
    98  
    99          try {
    100             proplist.add(new PropertyDescriptor("onsubmit", ELFormTag.class,
    101                     null, "setOnsubmitExpr"));
    102         } catch (IntrospectionException ex) {
    103         }
    104 
    105         try {
    106             proplist.add(new PropertyDescriptor("readonly", ELFormTag.class,
    107                     null, "setReadonlyExpr"));
    108         } catch (IntrospectionException ex) {
    109         }
    110 
    111         try {
    112             proplist.add(new PropertyDescriptor("scope", ELFormTag.class, null,
    113                     "setScopeExpr"));
    114         } catch (IntrospectionException ex) {
    115         }
    116 
    117         try {
    118             proplist.add(new PropertyDescriptor("scriptLanguage",
    119                     ELFormTag.class, null, "setScriptLanguageExpr"));
    120         } catch (IntrospectionException ex) {
    121         }
    122 
    123         try {
    124             proplist.add(new PropertyDescriptor("style", ELFormTag.class, null,
    125                     "setStyleExpr"));
    126         } catch (IntrospectionException ex) {
    127         }
    128 
    129         try {
    130             proplist.add(new PropertyDescriptor("styleClass", ELFormTag.class,
    131                     null, "setStyleClassExpr"));
    132         } catch (IntrospectionException ex) {
    133         }
    134 
    135         try {
    136             proplist.add(new PropertyDescriptor("styleId", ELFormTag.class,
    137                     null, "setStyleIdExpr"));
    138         } catch (IntrospectionException ex) {
    139         }
    140 
    141         try {
    142             proplist.add(new PropertyDescriptor("target", ELFormTag.class,
    143                     null, "setTargetExpr"));
    144         } catch (IntrospectionException ex) {
    145         }
    146 
    147         try {
    148             proplist.add(new PropertyDescriptor("type", ELFormTag.class, null,
    149                     "setTypeExpr"));
    150         } catch (IntrospectionException ex) {
    151         }
    152 
    153         try {
    154             proplist.add(new PropertyDescriptor("acceptCharset",
    155                     ELFormTag.class, null, "setAcceptCharsetExpr"));
    156         } catch (IntrospectionException ex) {
    157         }
    158 
    159         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    160 
    161         return ((PropertyDescriptor[]) proplist.toArray(result));
    162     }
    163 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
