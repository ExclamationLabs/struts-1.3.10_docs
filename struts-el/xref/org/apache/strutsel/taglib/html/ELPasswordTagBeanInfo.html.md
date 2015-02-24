[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELPasswordTagBeanInfo.html)


    1   /*
    2    * $Id: ELPasswordTagBeanInfo.java 558599 2007-07-23 04:36:07Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELPasswordTag</code> class.  It is
    32   * needed to override the default mapping of custom tag attribute names to
    33   * class attribute names. <p> This is because the value of the unevaluated EL
    34   * expression has to be kept separately from the evaluated value, which is
    35   * stored in the base class. This is related to the fact that the JSP compiler
    36   * can choose to reuse different tag instances if they received the same
    37   * original attribute values, and the JSP compiler can choose to not re-call
    38   * the setter methods, because it can assume the same values are already set.
    39   */
    40  public class ELPasswordTagBeanInfo extends SimpleBeanInfo {
    41      public PropertyDescriptor[] getPropertyDescriptors() {
    42          ArrayList proplist = new ArrayList();
    43  
    44          try {
    45              proplist.add(new PropertyDescriptor("accesskey",
    46                      ELPasswordTag.class, null, "setAccesskeyExpr"));
    47          } catch (IntrospectionException ex) {
    48          }
    49  
    50          try {
    51              proplist.add(new PropertyDescriptor("alt", ELPasswordTag.class,
    52                      null, "setAltExpr"));
    53          } catch (IntrospectionException ex) {
    54          }
    55  
    56          try {
    57              proplist.add(new PropertyDescriptor("altKey", ELPasswordTag.class,
    58                      null, "setAltKeyExpr"));
    59          } catch (IntrospectionException ex) {
    60          }
    61  
    62          try {
    63              proplist.add(new PropertyDescriptor("bundle", ELPasswordTag.class,
    64                      null, "setBundleExpr"));
    65          } catch (IntrospectionException ex) {
    66          }
    67  
    68          try {
    69              proplist.add(new PropertyDescriptor("dir", ELPasswordTag.class,
    70                      null, "setDirExpr"));
    71          } catch (IntrospectionException ex) {
    72          }
    73  
    74          try {
    75              proplist.add(new PropertyDescriptor("disabled",
    76                      ELPasswordTag.class, null, "setDisabledExpr"));
    77          } catch (IntrospectionException ex) {
    78          }
    79  
    80          try {
    81              proplist.add(new PropertyDescriptor("errorKey",
    82                      ELPasswordTag.class, null, "setErrorKeyExpr"));
    83          } catch (IntrospectionException ex) {
    84          }
    85  
    86          try {
    87              proplist.add(new PropertyDescriptor("errorStyle",
    88                      ELPasswordTag.class, null, "setErrorStyleExpr"));
    89          } catch (IntrospectionException ex) {
    90          }
    91  
    92          try {
    93              proplist.add(new PropertyDescriptor("errorStyleClass",
    94                      ELPasswordTag.class, null, "setErrorStyleClassExpr"));
    95          } catch (IntrospectionException ex) {
    96          }
    97  
    98          try {
    99              proplist.add(new PropertyDescriptor("errorStyleId",
    100                     ELPasswordTag.class, null, "setErrorStyleIdExpr"));
    101         } catch (IntrospectionException ex) {
    102         }
    103 
    104         try {
    105             proplist.add(new PropertyDescriptor("indexed", ELPasswordTag.class,
    106                     null, "setIndexedExpr"));
    107         } catch (IntrospectionException ex) {
    108         }
    109 
    110         try {
    111             proplist.add(new PropertyDescriptor("lang", ELPasswordTag.class,
    112                     null, "setLangExpr"));
    113         } catch (IntrospectionException ex) {
    114         }
    115 
    116         try {
    117             proplist.add(new PropertyDescriptor("maxlength",
    118                     ELPasswordTag.class, null, "setMaxlengthExpr"));
    119         } catch (IntrospectionException ex) {
    120         }
    121 
    122         try {
    123             proplist.add(new PropertyDescriptor("name", ELPasswordTag.class,
    124                     null, "setNameExpr"));
    125         } catch (IntrospectionException ex) {
    126         }
    127 
    128         try {
    129             proplist.add(new PropertyDescriptor("onblur", ELPasswordTag.class,
    130                     null, "setOnblurExpr"));
    131         } catch (IntrospectionException ex) {
    132         }
    133 
    134         try {
    135             proplist.add(new PropertyDescriptor("onchange",
    136                     ELPasswordTag.class, null, "setOnchangeExpr"));
    137         } catch (IntrospectionException ex) {
    138         }
    139 
    140         try {
    141             proplist.add(new PropertyDescriptor("onclick", ELPasswordTag.class,
    142                     null, "setOnclickExpr"));
    143         } catch (IntrospectionException ex) {
    144         }
    145 
    146         try {
    147             proplist.add(new PropertyDescriptor("ondblclick",
    148                     ELPasswordTag.class, null, "setOndblclickExpr"));
    149         } catch (IntrospectionException ex) {
    150         }
    151 
    152         try {
    153             proplist.add(new PropertyDescriptor("onfocus", ELPasswordTag.class,
    154                     null, "setOnfocusExpr"));
    155         } catch (IntrospectionException ex) {
    156         }
    157 
    158         try {
    159             proplist.add(new PropertyDescriptor("onkeydown",
    160                     ELPasswordTag.class, null, "setOnkeydownExpr"));
    161         } catch (IntrospectionException ex) {
    162         }
    163 
    164         try {
    165             proplist.add(new PropertyDescriptor("onkeypress",
    166                     ELPasswordTag.class, null, "setOnkeypressExpr"));
    167         } catch (IntrospectionException ex) {
    168         }
    169 
    170         try {
    171             proplist.add(new PropertyDescriptor("onkeyup", ELPasswordTag.class,
    172                     null, "setOnkeyupExpr"));
    173         } catch (IntrospectionException ex) {
    174         }
    175 
    176         try {
    177             proplist.add(new PropertyDescriptor("onmousedown",
    178                     ELPasswordTag.class, null, "setOnmousedownExpr"));
    179         } catch (IntrospectionException ex) {
    180         }
    181 
    182         try {
    183             proplist.add(new PropertyDescriptor("onmousemove",
    184                     ELPasswordTag.class, null, "setOnmousemoveExpr"));
    185         } catch (IntrospectionException ex) {
    186         }
    187 
    188         try {
    189             proplist.add(new PropertyDescriptor("onmouseout",
    190                     ELPasswordTag.class, null, "setOnmouseoutExpr"));
    191         } catch (IntrospectionException ex) {
    192         }
    193 
    194         try {
    195             proplist.add(new PropertyDescriptor("onmouseover",
    196                     ELPasswordTag.class, null, "setOnmouseoverExpr"));
    197         } catch (IntrospectionException ex) {
    198         }
    199 
    200         try {
    201             proplist.add(new PropertyDescriptor("onmouseup",
    202                     ELPasswordTag.class, null, "setOnmouseupExpr"));
    203         } catch (IntrospectionException ex) {
    204         }
    205 
    206         try {
    207             proplist.add(new PropertyDescriptor("onselect", 
    208                     ELPasswordTag.class, null, "setOnselectExpr"));
    209         } catch (IntrospectionException ex) {
    210         }
    211 
    212         try {
    213             proplist.add(new PropertyDescriptor("property",
    214                     ELPasswordTag.class, null, "setPropertyExpr"));
    215         } catch (IntrospectionException ex) {
    216         }
    217 
    218         try {
    219             proplist.add(new PropertyDescriptor("readonly",
    220                     ELPasswordTag.class, null, "setReadonlyExpr"));
    221         } catch (IntrospectionException ex) {
    222         }
    223 
    224         try {
    225             proplist.add(new PropertyDescriptor("redisplay",
    226                     ELPasswordTag.class, null, "setRedisplayExpr"));
    227         } catch (IntrospectionException ex) {
    228         }
    229 
    230         try {
    231             proplist.add(new PropertyDescriptor("style", ELPasswordTag.class,
    232                     null, "setStyleExpr"));
    233         } catch (IntrospectionException ex) {
    234         }
    235 
    236         try {
    237             proplist.add(new PropertyDescriptor("styleClass",
    238                     ELPasswordTag.class, null, "setStyleClassExpr"));
    239         } catch (IntrospectionException ex) {
    240         }
    241 
    242         try {
    243             proplist.add(new PropertyDescriptor("styleId", ELPasswordTag.class,
    244                     null, "setStyleIdExpr"));
    245         } catch (IntrospectionException ex) {
    246         }
    247 
    248         try {
    249             proplist.add(new PropertyDescriptor("size", ELPasswordTag.class,
    250                     null, "setSizeExpr"));
    251         } catch (IntrospectionException ex) {
    252         }
    253 
    254         try {
    255             proplist.add(new PropertyDescriptor("tabindex",
    256                     ELPasswordTag.class, null, "setTabindexExpr"));
    257         } catch (IntrospectionException ex) {
    258         }
    259 
    260         try {
    261             proplist.add(new PropertyDescriptor("title", ELPasswordTag.class,
    262                     null, "setTitleExpr"));
    263         } catch (IntrospectionException ex) {
    264         }
    265 
    266         try {
    267             proplist.add(new PropertyDescriptor("titleKey",
    268                     ELPasswordTag.class, null, "setTitleKeyExpr"));
    269         } catch (IntrospectionException ex) {
    270         }
    271 
    272         try {
    273             proplist.add(new PropertyDescriptor("value", ELPasswordTag.class,
    274                     null, "setValueExpr"));
    275         } catch (IntrospectionException ex) {
    276         }
    277 
    278         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    279 
    280         return ((PropertyDescriptor[]) proplist.toArray(result));
    281     }
    282 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
