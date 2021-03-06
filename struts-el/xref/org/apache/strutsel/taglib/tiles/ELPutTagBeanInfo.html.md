[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/tiles/ELPutTagBeanInfo.html.md)


    1   /*
    2    * $Id: ELPutTagBeanInfo.java 471754 2006-11-06 14:55:09Z husted $
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
    31   * <code>org.apache.strutsel.taglib.tiles.ELPutTag</code> class.  It is needed
    32   * to override the default mapping of custom tag attribute names to class
    33   * attribute names.
    34   */
    35  public class ELPutTagBeanInfo extends SimpleBeanInfo {
    36      public PropertyDescriptor[] getPropertyDescriptors() {
    37          ArrayList proplist = new ArrayList();
    38  
    39          try {
    40              proplist.add(new PropertyDescriptor("name", ELPutTag.class, null,
    41                      "setNameExpr"));
    42          } catch (IntrospectionException ex) {
    43          }
    44  
    45          try {
    46              proplist.add(new PropertyDescriptor("value", ELPutTag.class, null,
    47                      "setValueExpr"));
    48          } catch (IntrospectionException ex) {
    49          }
    50  
    51          try {
    52              proplist.add(new PropertyDescriptor("content", ELPutTag.class,
    53                      null, "setContentExpr"));
    54          } catch (IntrospectionException ex) {
    55          }
    56  
    57          try {
    58              proplist.add(new PropertyDescriptor("direct", ELPutTag.class, null,
    59                      "setDirectExpr"));
    60          } catch (IntrospectionException ex) {
    61          }
    62  
    63          try {
    64              proplist.add(new PropertyDescriptor("type", ELPutTag.class, null,
    65                      "setTypeExpr"));
    66          } catch (IntrospectionException ex) {
    67          }
    68  
    69          try {
    70              proplist.add(new PropertyDescriptor("beanName", ELPutTag.class,
    71                      null, "setBeanNameExpr"));
    72          } catch (IntrospectionException ex) {
    73          }
    74  
    75          try {
    76              proplist.add(new PropertyDescriptor("beanProperty", ELPutTag.class,
    77                      null, "setBeanPropertyExpr"));
    78          } catch (IntrospectionException ex) {
    79          }
    80  
    81          try {
    82              proplist.add(new PropertyDescriptor("beanScope", ELPutTag.class,
    83                      null, "setBeanScopeExpr"));
    84          } catch (IntrospectionException ex) {
    85          }
    86  
    87          try {
    88              proplist.add(new PropertyDescriptor("role", ELPutTag.class, null,
    89                      "setRoleExpr"));
    90          } catch (IntrospectionException ex) {
    91          }
    92  
    93          PropertyDescriptor[] result = new PropertyDescriptor[proplist.size()];
    94  
    95          return ((PropertyDescriptor[]) proplist.toArray(result));
    96      }
    97  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
