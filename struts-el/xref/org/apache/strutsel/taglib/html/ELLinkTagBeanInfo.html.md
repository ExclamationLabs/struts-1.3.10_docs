[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELLinkTagBeanInfo.html)


    1   /*
    2    * $Id: ELLinkTagBeanInfo.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELLinkTag</code> class.  It is needed
    32   * to override the default mapping of custom tag attribute names to class
    33   * attribute names. <p> This is because the value of the unevaluated EL
    34   * expression has to be kept separately from the evaluated value, which is
    35   * stored in the base class. This is related to the fact that the JSP compiler
    36   * can choose to reuse different tag instances if they received the same
    37   * original attribute values, and the JSP compiler can choose to not re-call
    38   * the setter methods, because it can assume the same values are already set.
    39   */
    40  public class ELLinkTagBeanInfo extends SimpleBeanInfo {
    41      public PropertyDescriptor[] getPropertyDescriptors() {
    42          ArrayList proplist = new ArrayList();
    43  
    44          try {
    45              proplist.add(new PropertyDescriptor("accesskey", ELLinkTag.class,
    46                      null, "setAccesskeyExpr"));
    47          } catch (IntrospectionException ex) {
    48          }
    49  
    50          try {
    51              proplist.add(new PropertyDescriptor("action", ELLinkTag.class,
    52                      null, "setActionExpr"));
    53          } catch (IntrospectionException ex) {
    54          }
    55  
    56          try {
    57              proplist.add(new PropertyDescriptor("module", ELLinkTag.class,
    58                      null, "setModuleExpr"));
    59          } catch (IntrospectionException ex) {
    60          }
    61  
    62          try {
    63              proplist.add(new PropertyDescriptor("anchor", ELLinkTag.class,
    64                      null, "setAnchorExpr"));
    65          } catch (IntrospectionException ex) {
    66          }
    67  
    68          try {
    69              proplist.add(new PropertyDescriptor("bundle", ELLinkTag.class,
    70                      null, "setBundleExpr"));
    71          } catch (IntrospectionException ex) {
    72          }
    73  
    74          try {
    75              proplist.add(new PropertyDescriptor("forward", ELLinkTag.class,
    76                      null, "setForwardExpr"));
    77          } catch (IntrospectionException ex) {
    78          }
    79  
    80          try {
    81              proplist.add(new PropertyDescriptor("dir", ELLinkTag.class,
    82                      null, "setDirExpr"));
    83          } catch (IntrospectionException ex) {
    84          }
    85  
    86          try {
    87              proplist.add(new PropertyDescriptor("href", ELLinkTag.class, null,
    88                      "setHrefExpr"));
    89          } catch (IntrospectionException ex) {
    90          }
    91  
    92          try {
    93              proplist.add(new PropertyDescriptor("indexed", ELLinkTag.class,
    94                      null, "setIndexedExpr"));
    95          } catch (IntrospectionException ex) {
    96          }
    97  
    98          try {
    99              proplist.add(new PropertyDescriptor("indexId", ELLinkTag.class,
    100                     null, "setIndexIdExpr"));
    101         } catch (IntrospectionException ex) {
    102         }
    103 
    104         try {
    105             proplist.add(new PropertyDescriptor("lang", ELLinkTag.class,
    106                     null, "setLangExpr"));
    107         } catch (IntrospectionException ex) {
    108         }
    109 
    110         try {
    111             proplist.add(new PropertyDescriptor("linkName", ELLinkTag.class,
    112                     null, "setLinkNameExpr"));
    113         } catch (IntrospectionException ex) {
    114         }
    115 
    116         try {
    117             proplist.add(new PropertyDescriptor("name", ELLinkTag.class, null,
    118                     "setNameExpr"));
    119         } catch (IntrospectionException ex) {
    120         }
    121 
    122         try {
    123             proplist.add(new PropertyDescriptor("onblur", ELLinkTag.class,
    124                     null, "setOnblurExpr"));
    125         } catch (IntrospectionException ex) {
    126         }
    127 
    128         try {
    129             proplist.add(new PropertyDescriptor("onclick", ELLinkTag.class,
    130                     null, "setOnclickExpr"));
    131         } catch (IntrospectionException ex) {
    132         }
    133 
    134         try {
    135             proplist.add(new PropertyDescriptor("ondblclick", ELLinkTag.class,
    136                     null, "setOndblclickExpr"));
    137         } catch (IntrospectionException ex) {
    138         }
    139 
    140         try {
    141             proplist.add(new PropertyDescriptor("onfocus", ELLinkTag.class,
    142                     null, "setOnfocusExpr"));
    143         } catch (IntrospectionException ex) {
    144         }
    145 
    146         try {
    147             proplist.add(new PropertyDescriptor("onkeydown", ELLinkTag.class,
    148                     null, "setOnkeydownExpr"));
    149         } catch (IntrospectionException ex) {
    150         }
    151 
    152         try {
    153             proplist.add(new PropertyDescriptor("onkeypress", ELLinkTag.class,
    154                     null, "setOnkeypressExpr"));
    155         } catch (IntrospectionException ex) {
    156         }
    157 
    158         try {
    159             proplist.add(new PropertyDescriptor("onkeyup", ELLinkTag.class,
    160                     null, "setOnkeyupExpr"));
    161         } catch (IntrospectionException ex) {
    162         }
    163 
    164         try {
    165             proplist.add(new PropertyDescriptor("onmousedown", ELLinkTag.class,
    166                     null, "setOnmousedownExpr"));
    167         } catch (IntrospectionException ex) {
    168         }
    169 
    170         try {
    171             proplist.add(new PropertyDescriptor("onmousemove", ELLinkTag.class,
    172                     null, "setOnmousemoveExpr"));
    173         } catch (IntrospectionException ex) {
    174         }
    175 
    176         try {
    177             proplist.add(new PropertyDescriptor("onmouseout", ELLinkTag.class,
    178                     null, "setOnmouseoutExpr"));
    179         } catch (IntrospectionException ex) {
    180         }
    181 
    182         try {
    183             proplist.add(new PropertyDescriptor("onmouseover", ELLinkTag.class,
    184                     null, "setOnmouseoverExpr"));
    185         } catch (IntrospectionException ex) {
    186         }
    187 
    188         try {
    189             proplist.add(new PropertyDescriptor("onmouseup", ELLinkTag.class,
    190                     null, "setOnmouseupExpr"));
    191         } catch (IntrospectionException ex) {
    192         }
    193 
    194         try {
    195             proplist.add(new PropertyDescriptor("page", ELLinkTag.class, null,
    196                     "setPageExpr"));
    197         } catch (IntrospectionException ex) {
    198         }
    199 
    200         try {
    201             proplist.add(new PropertyDescriptor("paramId", ELLinkTag.class,
    202                     null, "setParamIdExpr"));
    203         } catch (IntrospectionException ex) {
    204         }
    205 
    206         try {
    207             proplist.add(new PropertyDescriptor("paramName", ELLinkTag.class,
    208                     null, "setParamNameExpr"));
    209         } catch (IntrospectionException ex) {
    210         }
    211 
    212         try {
    213             proplist.add(new PropertyDescriptor("paramProperty",
    214                     ELLinkTag.class, null, "setParamPropertyExpr"));
    215         } catch (IntrospectionException ex) {
    216         }
    217 
    218         try {
    219             proplist.add(new PropertyDescriptor("paramScope", ELLinkTag.class,
    220                     null, "setParamScopeExpr"));
    221         } catch (IntrospectionException ex) {
    222         }
    223 
    224         try {
    225             proplist.add(new PropertyDescriptor("property", ELLinkTag.class,
    226                     null, "setPropertyExpr"));
    227         } catch (IntrospectionException ex) {
    228         }
    229 
    230         try {
    231             proplist.add(new PropertyDescriptor("scope", ELLinkTag.class, null,
    232                     "setScopeExpr"));
    233         } catch (IntrospectionException ex) {
    234         }
    235 
    236         try {
    237             proplist.add(new PropertyDescriptor("style", ELLinkTag.class, null,
    238                     "setStyleExpr"));
    239         } catch (IntrospectionException ex) {
    240         }
    241 
    242         try {
    243             proplist.add(new PropertyDescriptor("styleClass", ELLinkTag.class,
    244                     null, "setStyleClassExpr"));
    245         } catch (IntrospectionException ex) {
    246         }
    247 
    248         try {
    249             proplist.add(new PropertyDescriptor("styleId", ELLinkTag.class,
    250                     null, "setStyleIdExpr"));
    251         } catch (IntrospectionException ex) {
    252         }
    253 
    254         try {
    255             proplist.add(new PropertyDescriptor("tabindex", ELLinkTag.class,
    256                     null, "setTabindexExpr"));
    257         } catch (IntrospectionException ex) {
    258         }
    259 
    260         try {
    261             proplist.add(new PropertyDescriptor("target", ELLinkTag.class,
    262                     null, "setTargetExpr"));
    263         } catch (IntrospectionException ex) {
    264         }
    265 
    266         try {
    267             proplist.add(new PropertyDescriptor("title", ELLinkTag.class, null,
    268                     "setTitleExpr"));
    269         } catch (IntrospectionException ex) {
    270         }
    271 
    272         try {
    273             proplist.add(new PropertyDescriptor("titleKey", ELLinkTag.class,
    274                     null, "setTitleKeyExpr"));
    275         } catch (IntrospectionException ex) {
    276         }
    277 
    278         try {
    279             proplist.add(new PropertyDescriptor("transaction", ELLinkTag.class,
    280                     null, "setTransactionExpr"));
    281         } catch (IntrospectionException ex) {
    282         }
    283 
    284         try {
    285             proplist.add(new PropertyDescriptor("useLocalEncoding",
    286                     ELLinkTag.class, null, "setUseLocalEncodingExpr"));
    287         } catch (IntrospectionException ex) {
    288         }
    289 
    290         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    291 
    292         return ((PropertyDescriptor[]) proplist.toArray(result));
    293     }
    294 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
