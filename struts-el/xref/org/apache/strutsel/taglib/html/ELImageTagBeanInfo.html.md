[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELImageTagBeanInfo.html)


    1   /*
    2    * $Id: ELImageTagBeanInfo.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELImageTag</code> class.  It is
    32   * needed to override the default mapping of custom tag attribute names to
    33   * class attribute names. <p> This is because the value of the unevaluated EL
    34   * expression has to be kept separately from the evaluated value, which is
    35   * stored in the base class. This is related to the fact that the JSP compiler
    36   * can choose to reuse different tag instances if they received the same
    37   * original attribute values, and the JSP compiler can choose to not re-call
    38   * the setter methods, because it can assume the same values are already set.
    39   */
    40  public class ELImageTagBeanInfo extends SimpleBeanInfo {
    41      public PropertyDescriptor[] getPropertyDescriptors() {
    42          ArrayList proplist = new ArrayList();
    43  
    44          try {
    45              proplist.add(new PropertyDescriptor("accesskey", ELImageTag.class,
    46                      null, "setAccesskeyExpr"));
    47          } catch (IntrospectionException ex) {
    48          }
    49  
    50          try {
    51              proplist.add(new PropertyDescriptor("align", ELImageTag.class,
    52                      null, "setAlignExpr"));
    53          } catch (IntrospectionException ex) {
    54          }
    55  
    56          try {
    57              proplist.add(new PropertyDescriptor("alt", ELImageTag.class, null,
    58                      "setAltExpr"));
    59          } catch (IntrospectionException ex) {
    60          }
    61  
    62          try {
    63              proplist.add(new PropertyDescriptor("altKey", ELImageTag.class,
    64                      null, "setAltKeyExpr"));
    65          } catch (IntrospectionException ex) {
    66          }
    67  
    68          try {
    69              proplist.add(new PropertyDescriptor("border", ELImageTag.class,
    70                      null, "setBorderExpr"));
    71          } catch (IntrospectionException ex) {
    72          }
    73  
    74          try {
    75              proplist.add(new PropertyDescriptor("bundle", ELImageTag.class,
    76                      null, "setBundleExpr"));
    77          } catch (IntrospectionException ex) {
    78          }
    79  
    80          try {
    81              proplist.add(new PropertyDescriptor("dir", ELImageTag.class,
    82                      null, "setDirExpr"));
    83          } catch (IntrospectionException ex) {
    84          }
    85  
    86          try {
    87              proplist.add(new PropertyDescriptor("disabled", ELImageTag.class,
    88                      null, "setDisabledExpr"));
    89          } catch (IntrospectionException ex) {
    90          }
    91  
    92          try {
    93              proplist.add(new PropertyDescriptor("indexed", ELImageTag.class,
    94                      null, "setIndexedExpr"));
    95          } catch (IntrospectionException ex) {
    96          }
    97  
    98          try {
    99              proplist.add(new PropertyDescriptor("lang", ELImageTag.class,
    100                     null, "setLangExpr"));
    101         } catch (IntrospectionException ex) {
    102         }
    103 
    104         try {
    105             proplist.add(new PropertyDescriptor("locale", ELImageTag.class,
    106                     null, "setLocaleExpr"));
    107         } catch (IntrospectionException ex) {
    108         }
    109 
    110         try {
    111             proplist.add(new PropertyDescriptor("module", ELImageTag.class,
    112                     null, "setModuleExpr"));
    113         } catch (IntrospectionException ex) {
    114         }
    115 
    116         try {
    117             proplist.add(new PropertyDescriptor("onblur", ELImageTag.class,
    118                     null, "setOnblurExpr"));
    119         } catch (IntrospectionException ex) {
    120         }
    121 
    122         try {
    123             proplist.add(new PropertyDescriptor("onchange", ELImageTag.class,
    124                     null, "setOnchangeExpr"));
    125         } catch (IntrospectionException ex) {
    126         }
    127 
    128         try {
    129             proplist.add(new PropertyDescriptor("onclick", ELImageTag.class,
    130                     null, "setOnclickExpr"));
    131         } catch (IntrospectionException ex) {
    132         }
    133 
    134         try {
    135             proplist.add(new PropertyDescriptor("ondblclick", ELImageTag.class,
    136                     null, "setOndblclickExpr"));
    137         } catch (IntrospectionException ex) {
    138         }
    139 
    140         try {
    141             proplist.add(new PropertyDescriptor("onfocus", ELImageTag.class,
    142                     null, "setOnfocusExpr"));
    143         } catch (IntrospectionException ex) {
    144         }
    145 
    146         try {
    147             proplist.add(new PropertyDescriptor("onkeydown", ELImageTag.class,
    148                     null, "setOnkeydownExpr"));
    149         } catch (IntrospectionException ex) {
    150         }
    151 
    152         try {
    153             proplist.add(new PropertyDescriptor("onkeypress", ELImageTag.class,
    154                     null, "setOnkeypressExpr"));
    155         } catch (IntrospectionException ex) {
    156         }
    157 
    158         try {
    159             proplist.add(new PropertyDescriptor("onkeyup", ELImageTag.class,
    160                     null, "setOnkeyupExpr"));
    161         } catch (IntrospectionException ex) {
    162         }
    163 
    164         try {
    165             proplist.add(new PropertyDescriptor("onmousedown",
    166                     ELImageTag.class, null, "setOnmousedownExpr"));
    167         } catch (IntrospectionException ex) {
    168         }
    169 
    170         try {
    171             proplist.add(new PropertyDescriptor("onmousemove",
    172                     ELImageTag.class, null, "setOnmousemoveExpr"));
    173         } catch (IntrospectionException ex) {
    174         }
    175 
    176         try {
    177             proplist.add(new PropertyDescriptor("onmouseout", ELImageTag.class,
    178                     null, "setOnmouseoutExpr"));
    179         } catch (IntrospectionException ex) {
    180         }
    181 
    182         try {
    183             proplist.add(new PropertyDescriptor("onmouseover",
    184                     ELImageTag.class, null, "setOnmouseoverExpr"));
    185         } catch (IntrospectionException ex) {
    186         }
    187 
    188         try {
    189             proplist.add(new PropertyDescriptor("onmouseup", ELImageTag.class,
    190                     null, "setOnmouseupExpr"));
    191         } catch (IntrospectionException ex) {
    192         }
    193 
    194         try {
    195             proplist.add(new PropertyDescriptor("page", ELImageTag.class, null,
    196                     "setPageExpr"));
    197         } catch (IntrospectionException ex) {
    198         }
    199 
    200         try {
    201             proplist.add(new PropertyDescriptor("pageKey", ELImageTag.class,
    202                     null, "setPageKeyExpr"));
    203         } catch (IntrospectionException ex) {
    204         }
    205 
    206         try {
    207             proplist.add(new PropertyDescriptor("property", ELImageTag.class,
    208                     null, "setPropertyExpr"));
    209         } catch (IntrospectionException ex) {
    210         }
    211 
    212         try {
    213             proplist.add(new PropertyDescriptor("src", ELImageTag.class, null,
    214                     "setSrcExpr"));
    215         } catch (IntrospectionException ex) {
    216         }
    217 
    218         try {
    219             proplist.add(new PropertyDescriptor("srcKey", ELImageTag.class,
    220                     null, "setSrcKeyExpr"));
    221         } catch (IntrospectionException ex) {
    222         }
    223 
    224         try {
    225             proplist.add(new PropertyDescriptor("style", ELImageTag.class,
    226                     null, "setStyleExpr"));
    227         } catch (IntrospectionException ex) {
    228         }
    229 
    230         try {
    231             proplist.add(new PropertyDescriptor("styleClass", ELImageTag.class,
    232                     null, "setStyleClassExpr"));
    233         } catch (IntrospectionException ex) {
    234         }
    235 
    236         try {
    237             proplist.add(new PropertyDescriptor("styleId", ELImageTag.class,
    238                     null, "setStyleIdExpr"));
    239         } catch (IntrospectionException ex) {
    240         }
    241 
    242         try {
    243             proplist.add(new PropertyDescriptor("tabindex", ELImageTag.class,
    244                     null, "setTabindexExpr"));
    245         } catch (IntrospectionException ex) {
    246         }
    247 
    248         try {
    249             proplist.add(new PropertyDescriptor("title", ELImageTag.class,
    250                     null, "setTitleExpr"));
    251         } catch (IntrospectionException ex) {
    252         }
    253 
    254         try {
    255             proplist.add(new PropertyDescriptor("titleKey", ELImageTag.class,
    256                     null, "setTitleKeyExpr"));
    257         } catch (IntrospectionException ex) {
    258         }
    259 
    260         try {
    261             proplist.add(new PropertyDescriptor("value", ELImageTag.class,
    262                     null, "setValueExpr"));
    263         } catch (IntrospectionException ex) {
    264         }
    265 
    266         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    267 
    268         return ((PropertyDescriptor[]) proplist.toArray(result));
    269     }
    270 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
