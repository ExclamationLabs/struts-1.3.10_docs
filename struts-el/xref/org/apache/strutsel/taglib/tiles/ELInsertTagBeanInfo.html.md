[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELInsertTagBeanInfo.html.md)


    1   /*
    2    * $Id: ELInsertTagBeanInfo.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.tiles;
    22  
    23  import java.beans.IntrospectionException;
    24  import java.beans.PropertyDescriptor;
    25  import java.beans.SimpleBeanInfo;
    26  
    27  import java.util.ArrayList;
    28  
    29  /**
    30   * This is the <code>BeanInfo</code> descriptor for the
    31   * <code>org.apache.strutsel.taglib.tiles.ELAddTag</code> class.  It is needed
    32   * to override the default mapping of custom tag attribute names to class
    33   * attribute names.
    34   */
    35  public class ELInsertTagBeanInfo extends SimpleBeanInfo {
    36      public PropertyDescriptor[] getPropertyDescriptors() {
    37          ArrayList proplist = new ArrayList();
    38  
    39          try {
    40              proplist.add(new PropertyDescriptor("template", ELInsertTag.class,
    41                      null, "setTemplateExpr"));
    42          } catch (IntrospectionException ex) {
    43          }
    44  
    45          try {
    46              proplist.add(new PropertyDescriptor("component", ELInsertTag.class,
    47                      null, "setComponentExpr"));
    48          } catch (IntrospectionException ex) {
    49          }
    50  
    51          try {
    52              proplist.add(new PropertyDescriptor("page", ELInsertTag.class,
    53                      null, "setPageExpr"));
    54          } catch (IntrospectionException ex) {
    55          }
    56  
    57          try {
    58              proplist.add(new PropertyDescriptor("definition",
    59                      ELInsertTag.class, null, "setDefinitionExpr"));
    60          } catch (IntrospectionException ex) {
    61          }
    62  
    63          try {
    64              proplist.add(new PropertyDescriptor("attribute", ELInsertTag.class,
    65                      null, "setAttributeExpr"));
    66          } catch (IntrospectionException ex) {
    67          }
    68  
    69          try {
    70              proplist.add(new PropertyDescriptor("name", ELInsertTag.class,
    71                      null, "setNameExpr"));
    72          } catch (IntrospectionException ex) {
    73          }
    74  
    75          try {
    76              proplist.add(new PropertyDescriptor("beanName", ELInsertTag.class,
    77                      null, "setBeanNameExpr"));
    78          } catch (IntrospectionException ex) {
    79          }
    80  
    81          try {
    82              proplist.add(new PropertyDescriptor("beanProperty",
    83                      ELInsertTag.class, null, "setBeanPropertyExpr"));
    84          } catch (IntrospectionException ex) {
    85          }
    86  
    87          try {
    88              proplist.add(new PropertyDescriptor("beanScope", ELInsertTag.class,
    89                      null, "setBeanScopeExpr"));
    90          } catch (IntrospectionException ex) {
    91          }
    92  
    93          try {
    94              proplist.add(new PropertyDescriptor("flush", ELInsertTag.class,
    95                      null, "setFlushExpr"));
    96          } catch (IntrospectionException ex) {
    97          }
    98  
    99          try {
    100             proplist.add(new PropertyDescriptor("ignore", ELInsertTag.class,
    101                     null, "setIgnoreExpr"));
    102         } catch (IntrospectionException ex) {
    103         }
    104 
    105         try {
    106             proplist.add(new PropertyDescriptor("role", ELInsertTag.class,
    107                     null, "setRoleExpr"));
    108         } catch (IntrospectionException ex) {
    109         }
    110 
    111         try {
    112             proplist.add(new PropertyDescriptor("controllerUrl",
    113                     ELInsertTag.class, null, "setControllerUrlExpr"));
    114         } catch (IntrospectionException ex) {
    115         }
    116 
    117         try {
    118             proplist.add(new PropertyDescriptor("controllerClass",
    119                     ELInsertTag.class, null, "setControllerClassExpr"));
    120         } catch (IntrospectionException ex) {
    121         }
    122 
    123         PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    124 
    125         return ((PropertyDescriptor[]) proplist.toArray(result));
    126     }
    127 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
