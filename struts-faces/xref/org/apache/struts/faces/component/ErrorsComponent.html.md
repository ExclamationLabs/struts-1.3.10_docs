[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/component/ErrorsComponent.html.md)


    1   /*
    2    * $Id: ErrorsComponent.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.component;
    23  
    24  
    25  import javax.faces.component.UIOutput;
    26  import javax.faces.context.FacesContext;
    27  import javax.faces.el.ValueBinding;
    28  
    29  
    30  /**
    31   * <p>Custom component that replaces the Struts
    32   * <code>&lt.html.md:errors&gt;</code> tag.</p>
    33   */
    34  
    35  public class ErrorsComponent extends UIOutput {
    36  
    37  
    38      // ------------------------------------------------------------ Constructors
    39  
    40  
    41      /**
    42       * <p>Create a new {@link ErrorsComponent} with default properties.</p>
    43       */
    44      public ErrorsComponent() {
    45  
    46          super();
    47          setRendererType("org.apache.struts.faces.Errors");
    48  
    49      }
    50  
    51  
    52      // ------------------------------------------------------ Instance Variables
    53  
    54  
    55      /**
    56       * <p>MessageResources attribute key to use for message lookup.</p>
    57       */
    58      private String bundle = null;
    59  
    60  
    61      /**
    62       * <p>Property name of the property to report errors for.</p>
    63       */
    64      private String property = null;
    65  
    66  
    67      // ---------------------------------------------------- Component Properties
    68  
    69  
    70      /**
    71       * <p>Return the MessageResources key.</p>
    72       */
    73      public String getBundle() {
    74  
    75          ValueBinding vb = getValueBinding("bundle");
    76          if (vb != null) {
    77              return (String) vb.getValue(getFacesContext());
    78          } else {
    79              return bundle;
    80          }
    81  
    82      }
    83  
    84  
    85      /**
    86       * <p>Set the MessageResources key.</p>
    87       *
    88       * @param bundle The new key
    89       */
    90      public void setBundle(String bundle) {
    91  
    92          this.bundle = bundle;
    93  
    94      }
    95  
    96  
    97      /**
    98       * <p>Return the component family to which this component belongs.</p>
    99       */
    100     public String getFamily() {
    101 
    102         return "org.apache.struts.faces.Errors";
    103 
    104     }
    105 
    106 
    107     /**
    108      * <p>Return the property name for which to report errors.</p>
    109      */
    110     public String getProperty() {
    111 
    112         ValueBinding vb = getValueBinding("property");
    113         if (vb != null) {
    114             return (String) vb.getValue(getFacesContext());
    115         } else {
    116             return property;
    117         }
    118 
    119     }
    120 
    121 
    122     /**
    123      * <p>Set the property name for which to report errors.</p>
    124      *
    125      * @param property The new property name
    126      */
    127     public void setProperty(String property) {
    128 
    129         this.property = property;
    130 
    131     }
    132 
    133 
    134     // ---------------------------------------------------- StateManager Methods
    135 
    136 
    137     /**
    138      * <p>Restore the state of this component.</p>
    139      *
    140      * @param context <code>FacesContext</code> for the current request
    141      * @param state State object from which to restore our state
    142      */
    143     public void restoreState(FacesContext context, Object state) {
    144 
    145         Object values[] = (Object[]) state;
    146         super.restoreState(context, values[0]);
    147         bundle = (String) values[1];
    148         property = (String) values[2];
    149 
    150     }
    151 
    152 
    153     /**
    154      * <p>Save the state of this component.</p>
    155      *
    156      * @param context <code>FacesContext</code> for the current request
    157      */
    158     public Object saveState(FacesContext context) {
    159 
    160         Object values[] = new Object[3];
    161         values[0] = super.saveState(context);
    162         values[1] = bundle;
    163         values[2] = property;
    164         return values;
    165 
    166     }
    167 
    168 
    169 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
