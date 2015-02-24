[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib.html.md/ELMultiboxTagBeanInfo.html)


    1   /*
    2    * $Id: ELMultiboxTagBeanInfo.java 471754 2006-11-06 14:55:09Z husted $
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
    31   * <code>org.apache.strutsel.taglib.html.md.ELMultiboxTag</code> class.  It is
    32   * needed to override the default mapping of custom tag attribute names to
    33   * class attribute names. <p> In particular, it provides for the mapping of
    34   * the custom tag attribute <code>disabled</code> to the instance variable
    35   * <code>disabledExpr</code>. <p> This is because the value of the unevaluated
    36   * EL expression has to be kept separately from the evaluated value, which is
    37   * stored in the base class. This is related to the fact that the JSP compiler
    38   * can choose to reuse different tag instances if they received the same
    39   * original attribute values, and the JSP compiler can choose to not re-call
    40   * the setter methods, because it can assume the same values are already set.
    41   */
    42  public class ELMultiboxTagBeanInfo extends SimpleBeanInfo {
    43      public PropertyDescriptor[] getPropertyDescriptors() {
    44          ArrayList proplist = new ArrayList();
    45  
    46          try {
    47              proplist.add(new PropertyDescriptor("accesskey",
    48                      ELMultiboxTag.class, null, "setAccesskeyExpr"));
    49          } catch (IntrospectionException ex) {
    50          }
    51  
    52          try {
    53              proplist.add(new PropertyDescriptor("alt", ELMultiboxTag.class,
    54                      null, "setAltExpr"));
    55          } catch (IntrospectionException ex) {
    56          }
    57  
    58          try {
    59              proplist.add(new PropertyDescriptor("altKey", ELMultiboxTag.class,
    60                      null, "setAltKeyExpr"));
    61          } catch (IntrospectionException ex) {
    62          }
    63  
    64          try {
    65              proplist.add(new PropertyDescriptor("bundle", ELMultiboxTag.class,
    66                      null, "setBundleExpr"));
    67          } catch (IntrospectionException ex) {
    68          }
    69  
    70          try {
    71              proplist.add(new PropertyDescriptor("disabled",
    72                      ELMultiboxTag.class, null, "setDisabledExpr"));
    73          } catch (IntrospectionException ex) {
    74          }
    75  
    76          try {
    77              proplist.add(new PropertyDescriptor("errorKey",
    78                      ELMultiboxTag.class, null, "setErrorKeyExpr"));
    79          } catch (IntrospectionException ex) {
    80          }
    81  
    82          try {
    83              proplist.add(new PropertyDescriptor("errorStyle",
    84                      ELMultiboxTag.class, null, "setErrorStyleExpr"));
    85          } catch (IntrospectionException ex) {
    86          }
    87  
    88          try {
    89              proplist.add(new PropertyDescriptor("errorStyleClass",
    90                      ELMultiboxTag.class, null, "setErrorStyleClassExpr"));
    91          } catch (IntrospectionException ex) {
    92          }
    93  
    94          try {
    95              proplist.add(new PropertyDescriptor("errorStyleId",
    96                      ELMultiboxTag.class, null, "setErrorStyleIdExpr"));
    97          } catch (IntrospectionException ex) {
    98          }
    99  
    100         try {
    101             proplist.add(new PropertyDescriptor("name", ELMultiboxTag.class,
    102                     null, "setNameExpr"));
    103         } catch (IntrospectionException ex) {
    104         }
    105 
    106         try {
    107             proplist.add(new PropertyDescriptor("onblur", ELMultiboxTag.class,
    108                     null, "setOnblurExpr"));
    109         } catch (IntrospectionException ex) {
    110         }
    111 
    112         try {
    113             proplist.add(new PropertyDescriptor("onchange",
    114                     ELMultiboxTag.class, null, "setOnchangeExpr"));
    115         } catch (IntrospectionException ex) {
    116         }
    117 
    118         try {
    119             proplist.add(new PropertyDescriptor("onclick", ELMultiboxTag.class,
    120                     null, "setOnclickExpr"));
    121         } catch (IntrospectionException ex) {
    122         }
    123 
    124         try {
    125             proplist.add(new PropertyDescriptor("ondblclick",
    126                     ELMultiboxTag.class, null, "setOndblclickExpr"));
    127         } catch (IntrospectionException ex) {
    128         }
    129 
    130         try {
    131             proplist.add(new PropertyDescriptor("onfocus", ELMultiboxTag.class,
    132                     null, "setOnfocusExpr"));
    133         } catch (IntrospectionException ex) {
    134         }
    135 
    136         try {
    137             proplist.add(new PropertyDescriptor("onkeydown",
    138                     ELMultiboxTag.class, null, "setOnkeydownExpr"));
    139         } catch (IntrospectionException ex) {
    140         }
    141 
    142         try {
    143             proplist.add(new PropertyDescriptor("onkeypress",
    144                     ELMultiboxTag.class, null, "setOnkeypressExpr"));
    145         } catch (IntrospectionException ex) {
    146         }
    147 
    148         try {
    149             proplist.add(new PropertyDescriptor("onkeyup", ELMultiboxTag.class,
    150                     null, "setOnkeyupExpr"));
    151         } catch (IntrospectionException ex) {
    152         }
    153 
    154         try {
    155             proplist.add(new PropertyDescriptor("onmousedown",
    156                     ELMultiboxTag.class, null, "setOnmousedownExpr"));
    157         } catch (IntrospectionException ex) {
    158         }
    159 
    160         try {
    161             proplist.add(new PropertyDescriptor("onmousemove",
    162                     ELMultiboxTag.class, null, "setOnmousemoveExpr"));
    163         } catch (IntrospectionException ex) {
    164         }
    165 
    166         try {
    167             proplist.add(new PropertyDescriptor("onmouseout",
    168                     ELMultiboxTag.class, null, "setOnmouseoutExpr"));
    169         } catch (IntrospectionException ex) {
    170         }
    171 
    172         try {
    173             proplist.add(new PropertyDescriptor("onmouseover",
    174                     ELMultiboxTag.class, null, "setOnmouseoverExpr"));
    175         } catch (IntrospectionException ex) {
    176         }
    177 
    178         try {
    179             proplist.add(new PropertyDescriptor("onmouseup",
    180                     ELMultiboxTag.class, null, "setOnmouseupExpr"));
    181         } catch (IntrospectionException ex) {
    182         }
    183 
    184         try {
    185             proplist.add(new PropertyDescriptor("property",
    186                     ELMultiboxTag.class, null, "setPropertyExpr"));
    187         } catch (IntrospectionException ex) {
    188         }
    189 
    190         try {
    191             proplist.add(new PropertyDescriptor("style", ELMultiboxTag.class,
    192                     null, "setStyleExpr"));
    193         } catch (IntrospectionException ex) {
    194         }
    195 
    196         try {
    197             proplist.add(new PropertyDescriptor("styleClass",
    198                     ELMultiboxTag.class, null, "setStyleClassExpr"));
    199         } catch (IntrospectionException ex) {
    200         }
    201 
    202         try {
    203             proplist.add(new PropertyDescriptor("styleId", ELMultiboxTag.class,
    204                     null, "setStyleIdExpr"));
    205         } catch (IntrospectionException ex) {
    206         }
    207 
    208         try {
    209             proplist.add(new PropertyDescriptor("tabindex",
    210                     ELMultiboxTag.class, null, "setTabindexExpr"));
    211         } catch (IntrospectionException ex) {
    212         }
    213 
    214         try {
    215             proplist.add(new PropertyDescriptor("title", ELMultiboxTag.class,
    216                     null, "setTitleExpr"));
    217         } catch (IntrospectionException ex) {
    218         }
    219 
    220         try {
    221             proplist.add(new PropertyDescriptor("titleKey",
    222                     ELMultiboxTag.class, null, "setTitleKeyExpr"));
    223         } catch (IntrospectionException ex) {
    224         }
    225 
    226         try {
    227             proplist.add(new PropertyDescriptor("value", ELMultiboxTag.class,
    228                     null, "setValueExpr"));
    229         } catch (IntrospectionException ex) {
    230         }
    231 
    232         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    233 
    234         return ((PropertyDescriptor[]) proplist.toArray(result));
    235     }
    236 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
