[View Javadoc](../../../../../apidocs/org/apache/struts/util/LabelValueBean.html.md)


    1   /*
    2    * $Id: LabelValueBean.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import java.io.Serializable;
    24  
    25  import java.util.Comparator;
    26  
    27  /**
    28   * A simple JavaBean to represent label-value pairs. This is most commonly
    29   * used when constructing user interface elements which have a label to be
    30   * displayed to the user, and a corresponding value to be returned to the
    31   * server. One example is the <code>&lt.html.md:options&gt;</code> tag.
    32   *
    33   * <p> Note: this class has a natural ordering that is inconsistent with
    34   * equals. </p>
    35   *
    36   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    37   *          $
    38   */
    39  public class LabelValueBean implements Comparable, Serializable {
    40      /**
    41       * Comparator that can be used for a case insensitive sort of
    42       * <code>LabelValueBean</code> objects.
    43       */
    44      public static final Comparator CASE_INSENSITIVE_ORDER =
    45          new Comparator() {
    46              public int compare(Object o1, Object o2) {
    47                  String label1 = ((LabelValueBean) o1).getLabel();
    48                  String label2 = ((LabelValueBean) o2).getLabel();
    49  
    50                  return label1.compareToIgnoreCase(label2);
    51              }
    52          };
    53  
    54      // ------------------------------------------------------------- Properties
    55  
    56      /**
    57       * The property which supplies the option label visible to the end user.
    58       */
    59      private String label = null;
    60  
    61      /**
    62       * The property which supplies the value returned to the server.
    63       */
    64      private String value = null;
    65  
    66      // ----------------------------------------------------------- Constructors
    67  
    68      /**
    69       * Default constructor.
    70       */
    71      public LabelValueBean() {
    72          super();
    73      }
    74  
    75      /**
    76       * Construct an instance with the supplied property values.
    77       *
    78       * @param label The label to be displayed to the user.
    79       * @param value The value to be returned to the server.
    80       */
    81      public LabelValueBean(String label, String value) {
    82          this.label = label;
    83          this.value = value;
    84      }
    85  
    86      public String getLabel() {
    87          return this.label;
    88      }
    89  
    90      public void setLabel(String label) {
    91          this.label = label;
    92      }
    93  
    94      public String getValue() {
    95          return this.value;
    96      }
    97  
    98      public void setValue(String value) {
    99          this.value = value;
    100     }
    101 
    102     // --------------------------------------------------------- Public Methods
    103 
    104     /**
    105      * Compare LabelValueBeans based on the label, because that's the human
    106      * viewable part of the object.
    107      *
    108      * @see Comparable
    109      */
    110     public int compareTo(Object o) {
    111         // Implicitly tests for the correct type, throwing
    112         // ClassCastException as required by interface
    113         String otherLabel = ((LabelValueBean) o).getLabel();
    114 
    115         return this.getLabel().compareTo(otherLabel);
    116     }
    117 
    118     /**
    119      * Return a string representation of this object.
    120      */
    121     public String toString() {
    122         StringBuffer sb = new StringBuffer("LabelValueBean[");
    123 
    124         sb.append(this.label);
    125         sb.append(", ");
    126         sb.append(this.value);
    127         sb.append("]");
    128 
    129         return (sb.toString());
    130     }
    131 
    132     /**
    133      * LabelValueBeans are equal if their values are both null or equal.
    134      *
    135      * @see Object#equals(Object)
    136      */
    137     public boolean equals(Object obj) {
    138         if (obj == this) {
    139             return true;
    140         }
    141 
    142         if (!(obj instanceof LabelValueBean)) {
    143             return false;
    144         }
    145 
    146         LabelValueBean bean = (LabelValueBean) obj;
    147         int nil = (this.getValue() == null) ? 1 : 0;
    148 
    149         nil += ((bean.getValue() == null) ? 1 : 0);
    150 
    151         if (nil == 2) {
    152             return true;
    153         } else if (nil == 1) {
    154             return false;
    155         } else {
    156             return this.getValue().equals(bean.getValue());
    157         }
    158     }
    159 
    160     /**
    161      * The hash code is based on the object's value.
    162      *
    163      * @see Object#hashCode()
    164      */
    165     public int hashCode() {
    166         return (this.getValue() == null) ? 17 : this.getValue().hashCode();
    167     }
    168 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
