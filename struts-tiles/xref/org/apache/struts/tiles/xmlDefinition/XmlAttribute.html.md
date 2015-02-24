[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/xmlDefinition/XmlAttribute.html.md)


    1   /*
    2    * $Id: XmlAttribute.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  package org.apache.struts.tiles.xmlDefinition;
    23  
    24  import org.apache.struts.tiles.DefinitionNameAttribute;
    25  import org.apache.struts.tiles.DirectStringAttribute;
    26  import org.apache.struts.tiles.PathAttribute;
    27  import org.apache.struts.tiles.UntypedAttribute;
    28  
    29  /**
    30   * A property key-value pair.  This class is used to read configuration files.
    31   */
    32  public class XmlAttribute {
    33  
    34      /**
    35       * Attribute name or key.
    36       */
    37      private String name = null;
    38  
    39      /**
    40       * Attribute value.
    41       * Value read from description file.
    42       */
    43      private Object value = null;
    44  
    45      /**
    46       * Attribute value.
    47       */
    48      private String direct = null;
    49  
    50      /**
    51       * Attribute value.
    52       */
    53      private String valueType = null;
    54  
    55      /**
    56       * Attribute value.
    57       */
    58      private String role = null;
    59  
    60      /**
    61       * Real attribute value.
    62       * Real value is the value after processing of valueType.
    63       * I.e. if a type is defined, realValue contains wrapper for this type.
    64       */
    65      private Object realValue = null;
    66  
    67      /**
    68       * Constructor.
    69       */
    70      public XmlAttribute() {
    71          super();
    72      }
    73  
    74      /**
    75       * Constructor.
    76       */
    77      public XmlAttribute(String name, Object value) {
    78          this.name = name;
    79          this.value = value;
    80      }
    81  
    82      /**
    83       * Access method for the name property.
    84       *
    85       * @return The current value of the name property.
    86       */
    87      public String getName() {
    88          return name;
    89      }
    90  
    91      /**
    92       * Sets the value of the name property.
    93       *
    94       * @param role the new value of the name property
    95       */
    96      public void setRole(String role) {
    97          this.role = role;
    98      }
    99  
    100     /**
    101      * Access method for the name property.
    102      *
    103      * @return The current value of the name property.
    104      */
    105     public String getRole() {
    106         return role;
    107     }
    108 
    109     /**
    110      * Sets the value of the name property.
    111      *
    112      * @param aName the new value of the name property.
    113      */
    114     public void setName(String aName) {
    115         name = aName;
    116     }
    117 
    118     /**
    119      * Another access method for the name property.
    120      *
    121      * @return   the current value of the name property
    122      */
    123     public String getAttribute() {
    124         return name;
    125     }
    126 
    127     /**
    128      * Sets the value of the name property.
    129      *
    130      * @param aName the new value of the name property
    131      */
    132     public void setAttribute(String aName) {
    133         name = aName;
    134     }
    135 
    136     /**
    137      * Access method for the value property. Return the value or a
    138      * QualifiedAttribute containing the value if 'direct' is set.
    139      *
    140      * @return The current value of the value property.
    141      */
    142     public Object getValue() {
    143         // Compatibility with JSP Template
    144         if (this.realValue == null) {
    145             this.realValue = this.computeRealValue();
    146         }
    147 
    148         return this.realValue;
    149     }
    150 
    151     /**
    152      * Sets the value of the value property.
    153      *
    154      * @param aValue the new value of the value property
    155      */
    156     public void setValue(Object aValue) {
    157         realValue = null;
    158         value = aValue;
    159     }
    160 
    161     /**
    162      * Sets the value of the value property.
    163      *
    164      * @param aValue the new value of the value property
    165      */
    166     public void setContent(Object aValue) {
    167         setValue(aValue);
    168     }
    169 
    170     /**
    171      * Sets the value of the value property.
    172      *
    173      * @param body the new value of the value property
    174      */
    175     public void setBody(String body) {
    176         if (body.length() == 0) {
    177             return;
    178         }
    179 
    180         setValue(body);
    181     }
    182 
    183     /**
    184      * Sets the value of the value property.
    185      *
    186      * @param value the new value of the value property
    187      */
    188     public void setDirect(String value) {
    189         this.direct = value;
    190     }
    191 
    192     /**
    193      * Sets the value of the value property.
    194      *
    195      * @param value the new value of the value property
    196      */
    197     public void setType(String value) {
    198         this.valueType = value;
    199     }
    200 
    201     /**
    202      * Compute  real value from attributes setting.
    203      */
    204     protected Object computeRealValue() {
    205         Object realValue = value;
    206         // Is there a type set ?
    207         // First check direct attribute, and translate it to a valueType.
    208         // Then, evaluate valueType, and create requested typed attribute.
    209         if (direct != null) {
    210             this.valueType =
    211                 Boolean.valueOf(direct).booleanValue() ? "string" : "path";
    212         }
    213 
    214         if (value != null && valueType != null) {
    215             String strValue = value.toString();
    216 
    217             if (valueType.equalsIgnoreCase("string")) {
    218                 realValue = new DirectStringAttribute(strValue);
    219 
    220             } else if (valueType.equalsIgnoreCase("page")) {
    221                 realValue = new PathAttribute(strValue);
    222 
    223             } else if (valueType.equalsIgnoreCase("template")) {
    224                 realValue = new PathAttribute(strValue);
    225 
    226             } else if (valueType.equalsIgnoreCase("instance")) {
    227                 realValue = new DefinitionNameAttribute(strValue);
    228             }
    229 
    230             // Set realValue's role value if needed
    231             if (role != null) {
    232                 ((UntypedAttribute) realValue).setRole(role);
    233             }
    234         }
    235 
    236         // Create attribute wrapper to hold role if role is set and no type
    237         // specified
    238         if (role != null && value != null && valueType == null) {
    239             realValue = new UntypedAttribute(value.toString(), role);
    240         }
    241 
    242         return realValue;
    243     }
    244 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
