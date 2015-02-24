[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/component/WriteComponent.html.md)


    1   /*
    2    * $Id: WriteComponent.java 471754 2006-11-06 14:55:09Z husted $
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
    32   * <code>&lt.html.md:write&gt;</code> tag.</p>
    33   */
    34  
    35  public class WriteComponent extends UIOutput {
    36  
    37  
    38      // ------------------------------------------------------------ Constructors
    39  
    40  
    41      /**
    42       * <p>Create a new {@link WriteComponent} with default properties.</p>
    43       */
    44      public WriteComponent() {
    45  
    46          super();
    47          setRendererType("org.apache.struts.faces.Write");
    48  
    49      }
    50  
    51  
    52      // ------------------------------------------------------ Instance Variables
    53  
    54  
    55      /**
    56       * <p>Flag indicating whether output should be filtered.</p>
    57       */
    58      private boolean filter = true;
    59      private boolean filterSet = false;
    60  
    61  
    62      /**
    63       * <p>CSS style(s) to be rendered for this component.</p>
    64       */
    65      private String style = null;
    66  
    67  
    68      /**
    69       * <p>CSS style class(es) to be rendered for this component.</p>
    70       */
    71      private String styleClass = null;
    72  
    73  
    74      // ---------------------------------------------------- Component Properties
    75  
    76  
    77      /**
    78       * <p>Return the component family to which this component belongs.</p>
    79       */
    80      public String getFamily() {
    81  
    82          return "org.apache.struts.faces.Write";
    83  
    84      }
    85  
    86  
    87      /**
    88       * <p>Return a flag indicating whether filtering should take place.</p>
    89       */
    90      public boolean isFilter() {
    91  
    92          if (filterSet) {
    93              return filter;
    94          }
    95          ValueBinding vb = getValueBinding("filter");
    96          if (vb != null) {
    97              Boolean value = (Boolean) vb.getValue(getFacesContext());
    98              if (null == value) {
    99                  return filter;
    100             }
    101             return value.booleanValue();
    102         } else {
    103             return filter;
    104         }
    105 
    106     }
    107 
    108 
    109     /**
    110      * <p>Set the flag indicating that the output value should be filtered.</p>
    111      *
    112      * @param filter The new filter flag
    113      */
    114     public void setFilter(boolean filter) {
    115 
    116         this.filter = filter;
    117         this.filterSet = true;
    118 
    119     }
    120 
    121 
    122     /**
    123      * <p>Return the CSS style(s) to be rendered for this component.</p>
    124      */
    125     public String getStyle() {
    126 
    127         ValueBinding vb = getValueBinding("style");
    128         if (vb != null) {
    129             return (String) vb.getValue(getFacesContext());
    130         } else {
    131             return style;
    132         }
    133 
    134     }
    135 
    136 
    137     /**
    138      * <p>Set the CSS style(s) to be rendered for this component.</p>
    139      *
    140      * @param style The new CSS style(s)
    141      */
    142     public void setStyle(String style) {
    143 
    144         this.style = style;
    145 
    146     }
    147 
    148 
    149     /**
    150      * <p>Return the CSS style class(es) to be rendered for this component.</p>
    151      */
    152     public String getStyleClass() {
    153 
    154         ValueBinding vb = getValueBinding("styleClass");
    155         if (vb != null) {
    156             return (String) vb.getValue(getFacesContext());
    157         } else {
    158             return styleClass;
    159         }
    160 
    161     }
    162 
    163 
    164     /**
    165      * <p>Set the CSS style class(es) to be rendered for this component.</p>
    166      *
    167      * @param styleClass The new CSS style class(es)
    168      */
    169     public void setStyleClass(String styleClass) {
    170 
    171         this.styleClass = styleClass;
    172 
    173     }
    174 
    175 
    176     // ---------------------------------------------------- StateManager Methods
    177 
    178 
    179     /**
    180      * <p>Restore the state of this component.</p>
    181      *
    182      * @param context <code>FacesContext</code> for the current request
    183      * @param state State object from which to restore our state
    184      */
    185     public void restoreState(FacesContext context, Object state) {
    186 
    187         Object values[] = (Object[]) state;
    188         super.restoreState(context, values[0]);
    189         filter = ((Boolean) values[1]).booleanValue();
    190         filterSet = ((Boolean) values[2]).booleanValue();
    191         style = (String) values[3];
    192         styleClass = (String) values[4];
    193 
    194     }
    195 
    196 
    197     /**
    198      * <p>Save the state of this component.</p>
    199      *
    200      * @param context <code>FacesContext</code> for the current request
    201      */
    202     public Object saveState(FacesContext context) {
    203 
    204         Object values[] = new Object[5];
    205         values[0] = super.saveState(context);
    206         values[1] = filter ? Boolean.TRUE : Boolean.FALSE;
    207         values[2] = filterSet ? Boolean.TRUE : Boolean.FALSE;
    208         values[3] = style;
    209         values[4] = styleClass;
    210         return values;
    211 
    212     }
    213 
    214 
    215 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
