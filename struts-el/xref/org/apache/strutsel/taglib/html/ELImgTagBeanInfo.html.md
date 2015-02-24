[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELImgTagBeanInfo.html)


    1   /*
    2    * $Id: ELImgTagBeanInfo.java 479635 2006-11-27 14:27:18Z pbenedict $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELImgTag</code> class.  It is needed
    32   * to override the default mapping of custom tag attribute names to class
    33   * attribute names.
    34   */
    35  public class ELImgTagBeanInfo extends SimpleBeanInfo {
    36      public PropertyDescriptor[] getPropertyDescriptors() {
    37          ArrayList proplist = new ArrayList();
    38  
    39          try {
    40              proplist.add(new PropertyDescriptor("action", ELImgTag.class, null,
    41                      "setActionExpr"));
    42          } catch (IntrospectionException ex) {
    43          }
    44  
    45          try {
    46              proplist.add(new PropertyDescriptor("module", ELImgTag.class, null,
    47                      "setModuleExpr"));
    48          } catch (IntrospectionException ex) {
    49          }
    50  
    51          try {
    52              proplist.add(new PropertyDescriptor("align", ELImgTag.class, null,
    53                      "setAlignExpr"));
    54          } catch (IntrospectionException ex) {
    55          }
    56  
    57          try {
    58              proplist.add(new PropertyDescriptor("alt", ELImgTag.class, null,
    59                      "setAltExpr"));
    60          } catch (IntrospectionException ex) {
    61          }
    62  
    63          try {
    64              proplist.add(new PropertyDescriptor("altKey", ELImgTag.class, null,
    65                      "setAltKeyExpr"));
    66          } catch (IntrospectionException ex) {
    67          }
    68  
    69          try {
    70              proplist.add(new PropertyDescriptor("border", ELImgTag.class, null,
    71                      "setBorderExpr"));
    72          } catch (IntrospectionException ex) {
    73          }
    74  
    75          try {
    76              proplist.add(new PropertyDescriptor("bundle", ELImgTag.class, null,
    77                      "setBundleExpr"));
    78          } catch (IntrospectionException ex) {
    79          }
    80  
    81          try {
    82              proplist.add(new PropertyDescriptor("dir", ELImgTag.class,
    83                      null, "setDirExpr"));
    84          } catch (IntrospectionException ex) {
    85          }
    86  
    87          try {
    88              proplist.add(new PropertyDescriptor("height", ELImgTag.class, null,
    89                      "setHeightExpr"));
    90          } catch (IntrospectionException ex) {
    91          }
    92  
    93          try {
    94              proplist.add(new PropertyDescriptor("hspace", ELImgTag.class, null,
    95                      "setHspaceExpr"));
    96          } catch (IntrospectionException ex) {
    97          }
    98  
    99          try {
    100             proplist.add(new PropertyDescriptor("imageName", ELImgTag.class,
    101                     null, "setImageNameExpr"));
    102         } catch (IntrospectionException ex) {
    103         }
    104 
    105         try {
    106             proplist.add(new PropertyDescriptor("ismap", ELImgTag.class, null,
    107                     "setIsmapExpr"));
    108         } catch (IntrospectionException ex) {
    109         }
    110 
    111         try {
    112             proplist.add(new PropertyDescriptor("lang", ELImgTag.class,
    113                     null, "setLangExpr"));
    114         } catch (IntrospectionException ex) {
    115         }
    116 
    117         try {
    118             proplist.add(new PropertyDescriptor("locale", ELImgTag.class, null,
    119                     "setLocaleExpr"));
    120         } catch (IntrospectionException ex) {
    121         }
    122 
    123         try {
    124             proplist.add(new PropertyDescriptor("name", ELImgTag.class, null,
    125                     "setNameExpr"));
    126         } catch (IntrospectionException ex) {
    127         }
    128 
    129         try {
    130             proplist.add(new PropertyDescriptor("onclick", ELImgTag.class,
    131                     null, "setOnclickExpr"));
    132         } catch (IntrospectionException ex) {
    133         }
    134 
    135         try {
    136             proplist.add(new PropertyDescriptor("ondblclick", ELImgTag.class,
    137                     null, "setOndblclickExpr"));
    138         } catch (IntrospectionException ex) {
    139         }
    140 
    141         try {
    142             proplist.add(new PropertyDescriptor("onkeydown", ELImgTag.class,
    143                     null, "setOnkeydownExpr"));
    144         } catch (IntrospectionException ex) {
    145         }
    146 
    147         try {
    148             proplist.add(new PropertyDescriptor("onkeypress", ELImgTag.class,
    149                     null, "setOnkeypressExpr"));
    150         } catch (IntrospectionException ex) {
    151         }
    152 
    153         try {
    154             proplist.add(new PropertyDescriptor("onkeyup", ELImgTag.class,
    155                     null, "setOnkeyupExpr"));
    156         } catch (IntrospectionException ex) {
    157         }
    158 
    159         try {
    160             proplist.add(new PropertyDescriptor("onmousedown", ELImgTag.class,
    161                     null, "setOnmousedownExpr"));
    162         } catch (IntrospectionException ex) {
    163         }
    164 
    165         try {
    166             proplist.add(new PropertyDescriptor("onmousemove", ELImgTag.class,
    167                     null, "setOnmousemoveExpr"));
    168         } catch (IntrospectionException ex) {
    169         }
    170 
    171         try {
    172             proplist.add(new PropertyDescriptor("onmouseout", ELImgTag.class,
    173                     null, "setOnmouseoutExpr"));
    174         } catch (IntrospectionException ex) {
    175         }
    176 
    177         try {
    178             proplist.add(new PropertyDescriptor("onmouseover", ELImgTag.class,
    179                     null, "setOnmouseoverExpr"));
    180         } catch (IntrospectionException ex) {
    181         }
    182 
    183         try {
    184             proplist.add(new PropertyDescriptor("onmouseup", ELImgTag.class,
    185                     null, "setOnmouseupExpr"));
    186         } catch (IntrospectionException ex) {
    187         }
    188 
    189         try {
    190             proplist.add(new PropertyDescriptor("paramId", ELImgTag.class,
    191                     null, "setParamIdExpr"));
    192         } catch (IntrospectionException ex) {
    193         }
    194 
    195         try {
    196             proplist.add(new PropertyDescriptor("page", ELImgTag.class, null,
    197                     "setPageExpr"));
    198         } catch (IntrospectionException ex) {
    199         }
    200 
    201         try {
    202             proplist.add(new PropertyDescriptor("pageKey", ELImgTag.class,
    203                     null, "setPageKeyExpr"));
    204         } catch (IntrospectionException ex) {
    205         }
    206 
    207         try {
    208             proplist.add(new PropertyDescriptor("paramName", ELImgTag.class,
    209                     null, "setParamNameExpr"));
    210         } catch (IntrospectionException ex) {
    211         }
    212 
    213         try {
    214             proplist.add(new PropertyDescriptor("paramProperty",
    215                     ELImgTag.class, null, "setParamPropertyExpr"));
    216         } catch (IntrospectionException ex) {
    217         }
    218 
    219         try {
    220             proplist.add(new PropertyDescriptor("paramScope", ELImgTag.class,
    221                     null, "setParamScopeExpr"));
    222         } catch (IntrospectionException ex) {
    223         }
    224 
    225         try {
    226             proplist.add(new PropertyDescriptor("property", ELImgTag.class,
    227                     null, "setPropertyExpr"));
    228         } catch (IntrospectionException ex) {
    229         }
    230 
    231         try {
    232             proplist.add(new PropertyDescriptor("scope", ELImgTag.class, null,
    233                     "setScopeExpr"));
    234         } catch (IntrospectionException ex) {
    235         }
    236 
    237         try {
    238             proplist.add(new PropertyDescriptor("src", ELImgTag.class, null,
    239                     "setSrcExpr"));
    240         } catch (IntrospectionException ex) {
    241         }
    242 
    243         try {
    244             proplist.add(new PropertyDescriptor("srcKey", ELImgTag.class, null,
    245                     "setSrcKeyExpr"));
    246         } catch (IntrospectionException ex) {
    247         }
    248 
    249         try {
    250             proplist.add(new PropertyDescriptor("style", ELImgTag.class, null,
    251                     "setStyleExpr"));
    252         } catch (IntrospectionException ex) {
    253         }
    254 
    255         try {
    256             proplist.add(new PropertyDescriptor("styleClass", ELImgTag.class,
    257                     null, "setStyleClassExpr"));
    258         } catch (IntrospectionException ex) {
    259         }
    260 
    261         try {
    262             proplist.add(new PropertyDescriptor("styleId", ELImgTag.class,
    263                     null, "setStyleIdExpr"));
    264         } catch (IntrospectionException ex) {
    265         }
    266 
    267         try {
    268             proplist.add(new PropertyDescriptor("title", ELImgTag.class, null,
    269                     "setTitleExpr"));
    270         } catch (IntrospectionException ex) {
    271         }
    272 
    273         try {
    274             proplist.add(new PropertyDescriptor("titleKey", ELImgTag.class,
    275                     null, "setTitleKeyExpr"));
    276         } catch (IntrospectionException ex) {
    277         }
    278 
    279         try {
    280             proplist.add(new PropertyDescriptor("useLocalEncoding",
    281                     ELImgTag.class, null, "setUseLocalEncodingExpr"));
    282         } catch (IntrospectionException ex) {
    283         }
    284 
    285         try {
    286             proplist.add(new PropertyDescriptor("usemap", ELImgTag.class, null,
    287                     "setUsemapExpr"));
    288         } catch (IntrospectionException ex) {
    289         }
    290 
    291         try {
    292             proplist.add(new PropertyDescriptor("vspace", ELImgTag.class, null,
    293                     "setVspaceExpr"));
    294         } catch (IntrospectionException ex) {
    295         }
    296 
    297         try {
    298             proplist.add(new PropertyDescriptor("width", ELImgTag.class, null,
    299                     "setWidthExpr"));
    300         } catch (IntrospectionException ex) {
    301         }
    302 
    303         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    304 
    305         return ((PropertyDescriptor[]) proplist.toArray(result));
    306     }
    307 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
