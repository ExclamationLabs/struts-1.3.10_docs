[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELRadioTagBeanInfo.html)


    1   /*
    2    * $Id: ELRadioTagBeanInfo.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELRadioTag</code> class.  It is
    32   * needed to override the default mapping of custom tag attribute names to
    33   * class attribute names. <p> This is because the value of the unevaluated EL
    34   * expression has to be kept separately from the evaluated value, which is
    35   * stored in the base class. This is related to the fact that the JSP compiler
    36   * can choose to reuse different tag instances if they received the same
    37   * original attribute values, and the JSP compiler can choose to not re-call
    38   * the setter methods, because it can assume the same values are already set.
    39   */
    40  public class ELRadioTagBeanInfo extends SimpleBeanInfo {
    41      public PropertyDescriptor[] getPropertyDescriptors() {
    42          ArrayList proplist = new ArrayList();
    43  
    44          try {
    45              proplist.add(new PropertyDescriptor("accesskey", ELRadioTag.class,
    46                      null, "setAccesskeyExpr"));
    47          } catch (IntrospectionException ex) {
    48          }
    49  
    50          try {
    51              proplist.add(new PropertyDescriptor("alt", ELRadioTag.class, null,
    52                      "setAltExpr"));
    53          } catch (IntrospectionException ex) {
    54          }
    55  
    56          try {
    57              proplist.add(new PropertyDescriptor("altKey", ELRadioTag.class,
    58                      null, "setAltKeyExpr"));
    59          } catch (IntrospectionException ex) {
    60          }
    61  
    62          try {
    63              proplist.add(new PropertyDescriptor("bundle", ELRadioTag.class,
    64                      null, "setBundleExpr"));
    65          } catch (IntrospectionException ex) {
    66          }
    67  
    68          try {
    69              proplist.add(new PropertyDescriptor("dir", ELRadioTag.class,
    70                      null, "setDirExpr"));
    71          } catch (IntrospectionException ex) {
    72          }
    73  
    74          try {
    75              proplist.add(new PropertyDescriptor("disabled", ELRadioTag.class,
    76                      null, "setDisabledExpr"));
    77          } catch (IntrospectionException ex) {
    78          }
    79  
    80          try {
    81              proplist.add(new PropertyDescriptor("errorKey", ELRadioTag.class,
    82                      null, "setErrorKeyExpr"));
    83          } catch (IntrospectionException ex) {
    84          }
    85  
    86          try {
    87              proplist.add(new PropertyDescriptor("errorStyle", ELRadioTag.class,
    88                      null, "setErrorStyleExpr"));
    89          } catch (IntrospectionException ex) {
    90          }
    91  
    92          try {
    93              proplist.add(new PropertyDescriptor("errorStyleClass",
    94                      ELRadioTag.class, null, "setErrorStyleClassExpr"));
    95          } catch (IntrospectionException ex) {
    96          }
    97  
    98          try {
    99              proplist.add(new PropertyDescriptor("errorStyleId",
    100                     ELRadioTag.class, null, "setErrorStyleIdExpr"));
    101         } catch (IntrospectionException ex) {
    102         }
    103 
    104         try {
    105             proplist.add(new PropertyDescriptor("indexed", ELRadioTag.class,
    106                     null, "setIndexedExpr"));
    107         } catch (IntrospectionException ex) {
    108         }
    109 
    110         try {
    111             proplist.add(new PropertyDescriptor("lang", ELRadioTag.class,
    112                     null, "setLangExpr"));
    113         } catch (IntrospectionException ex) {
    114         }
    115 
    116         try {
    117             proplist.add(new PropertyDescriptor("name", ELRadioTag.class, null,
    118                     "setNameExpr"));
    119         } catch (IntrospectionException ex) {
    120         }
    121 
    122         try {
    123             proplist.add(new PropertyDescriptor("onblur", ELRadioTag.class,
    124                     null, "setOnblurExpr"));
    125         } catch (IntrospectionException ex) {
    126         }
    127 
    128         try {
    129             proplist.add(new PropertyDescriptor("onchange", ELRadioTag.class,
    130                     null, "setOnchangeExpr"));
    131         } catch (IntrospectionException ex) {
    132         }
    133 
    134         try {
    135             proplist.add(new PropertyDescriptor("onclick", ELRadioTag.class,
    136                     null, "setOnclickExpr"));
    137         } catch (IntrospectionException ex) {
    138         }
    139 
    140         try {
    141             proplist.add(new PropertyDescriptor("ondblclick", ELRadioTag.class,
    142                     null, "setOndblclickExpr"));
    143         } catch (IntrospectionException ex) {
    144         }
    145 
    146         try {
    147             proplist.add(new PropertyDescriptor("onfocus", ELRadioTag.class,
    148                     null, "setOnfocusExpr"));
    149         } catch (IntrospectionException ex) {
    150         }
    151 
    152         try {
    153             proplist.add(new PropertyDescriptor("onkeydown", ELRadioTag.class,
    154                     null, "setOnkeydownExpr"));
    155         } catch (IntrospectionException ex) {
    156         }
    157 
    158         try {
    159             proplist.add(new PropertyDescriptor("onkeypress", ELRadioTag.class,
    160                     null, "setOnkeypressExpr"));
    161         } catch (IntrospectionException ex) {
    162         }
    163 
    164         try {
    165             proplist.add(new PropertyDescriptor("onkeyup", ELRadioTag.class,
    166                     null, "setOnkeyupExpr"));
    167         } catch (IntrospectionException ex) {
    168         }
    169 
    170         try {
    171             proplist.add(new PropertyDescriptor("onmousedown",
    172                     ELRadioTag.class, null, "setOnmousedownExpr"));
    173         } catch (IntrospectionException ex) {
    174         }
    175 
    176         try {
    177             proplist.add(new PropertyDescriptor("onmousemove",
    178                     ELRadioTag.class, null, "setOnmousemoveExpr"));
    179         } catch (IntrospectionException ex) {
    180         }
    181 
    182         try {
    183             proplist.add(new PropertyDescriptor("onmouseout", ELRadioTag.class,
    184                     null, "setOnmouseoutExpr"));
    185         } catch (IntrospectionException ex) {
    186         }
    187 
    188         try {
    189             proplist.add(new PropertyDescriptor("onmouseover",
    190                     ELRadioTag.class, null, "setOnmouseoverExpr"));
    191         } catch (IntrospectionException ex) {
    192         }
    193 
    194         try {
    195             proplist.add(new PropertyDescriptor("onmouseup", ELRadioTag.class,
    196                     null, "setOnmouseupExpr"));
    197         } catch (IntrospectionException ex) {
    198         }
    199 
    200         try {
    201             proplist.add(new PropertyDescriptor("property", ELRadioTag.class,
    202                     null, "setPropertyExpr"));
    203         } catch (IntrospectionException ex) {
    204         }
    205 
    206         try {
    207             proplist.add(new PropertyDescriptor("style", ELRadioTag.class,
    208                     null, "setStyleExpr"));
    209         } catch (IntrospectionException ex) {
    210         }
    211 
    212         try {
    213             proplist.add(new PropertyDescriptor("styleClass", ELRadioTag.class,
    214                     null, "setStyleClassExpr"));
    215         } catch (IntrospectionException ex) {
    216         }
    217 
    218         try {
    219             proplist.add(new PropertyDescriptor("styleId", ELRadioTag.class,
    220                     null, "setStyleIdExpr"));
    221         } catch (IntrospectionException ex) {
    222         }
    223 
    224         try {
    225             proplist.add(new PropertyDescriptor("tabindex", ELRadioTag.class,
    226                     null, "setTabindexExpr"));
    227         } catch (IntrospectionException ex) {
    228         }
    229 
    230         try {
    231             proplist.add(new PropertyDescriptor("title", ELRadioTag.class,
    232                     null, "setTitleExpr"));
    233         } catch (IntrospectionException ex) {
    234         }
    235 
    236         try {
    237             proplist.add(new PropertyDescriptor("titleKey", ELRadioTag.class,
    238                     null, "setTitleKeyExpr"));
    239         } catch (IntrospectionException ex) {
    240         }
    241 
    242         try {
    243             proplist.add(new PropertyDescriptor("value", ELRadioTag.class,
    244                     null, "setValueExpr"));
    245         } catch (IntrospectionException ex) {
    246         }
    247 
    248         try {
    249             proplist.add(new PropertyDescriptor("idName", ELRadioTag.class,
    250                     null, "setIdNameExpr"));
    251         } catch (IntrospectionException ex) {
    252         }
    253 
    254         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    255 
    256         return ((PropertyDescriptor[]) proplist.toArray(result));
    257     }
    258 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
