[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/component/MessageComponent.html.md)


    1   /*
    2    * $Id: MessageComponent.java 471754 2006-11-06 14:55:09Z husted $
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
    32   * <code>&lt.html.md:message&gt;</code> tag.</p>
    33   */
    34  
    35  public class MessageComponent extends UIOutput {
    36  
    37  
    38      // ------------------------------------------------------------ Constructors
    39  
    40  
    41      /**
    42       * <p>Create a new {@link MessageComponent} with default properties.</p>
    43       */
    44      public MessageComponent() {
    45  
    46          super();
    47          setRendererType("org.apache.struts.faces.Message");
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
    62       * <p>Flag indicating whether output should be filtered.</p>
    63       */
    64      private boolean filter = true;
    65      private boolean filterSet = false;
    66  
    67  
    68      /**
    69       * <p>Message key to use for message lookup.</p>
    70       */
    71      private String key = null;
    72  
    73  
    74      /**
    75       * <p>CSS style(s) to be rendered for this component.</p>
    76       */
    77      private String style = null;
    78  
    79  
    80      /**
    81       * <p>CSS style class(es) to be rendered for this component.</p>
    82       */
    83      private String styleClass = null;
    84  
    85  
    86      // ---------------------------------------------------- Component Properties
    87  
    88  
    89      /**
    90       * <p>Return the MessageResources key.</p>
    91       */
    92      public String getBundle() {
    93  
    94          ValueBinding vb = getValueBinding("bundle");
    95          if (vb != null) {
    96              return (String) vb.getValue(getFacesContext());
    97          } else {
    98              return bundle;
    99          }
    100 
    101     }
    102 
    103 
    104     /**
    105      * <p>Set the MessageResources key.</p>
    106      *
    107      * @param bundle The new key
    108      */
    109     public void setBundle(String bundle) {
    110 
    111         this.bundle = bundle;
    112 
    113     }
    114 
    115 
    116     /**
    117      * <p>Return the component family to which this component belongs.</p>
    118      */
    119     public String getFamily() {
    120 
    121         return "org.apache.struts.faces.Message";
    122 
    123     }
    124 
    125 
    126     /**
    127      * <p>Return a flag indicating whether filtering should take place.</p>
    128      */
    129     public boolean isFilter() {
    130 
    131         if (filterSet) {
    132             return filter;
    133         }
    134         ValueBinding vb = getValueBinding("filter");
    135         if (vb != null) {
    136             Boolean value = (Boolean) vb.getValue(getFacesContext());
    137             if (null == value) {
    138                 return filter;
    139             }
    140             return value.booleanValue();
    141         } else {
    142             return filter;
    143         }
    144 
    145     }
    146 
    147 
    148     /**
    149      * <p>Set the flag indicating that the output value should be filtered.</p>
    150      *
    151      * @param filter The new filter flag
    152      */
    153     public void setFilter(boolean filter) {
    154 
    155         this.filter = filter;
    156         this.filterSet = true;
    157 
    158     }
    159 
    160 
    161     /**
    162      * <p>Return the message key.</p>
    163      */
    164     public String getKey() {
    165 
    166         ValueBinding vb = getValueBinding("key");
    167         if (vb != null) {
    168             return (String) vb.getValue(getFacesContext());
    169         } else {
    170             return key;
    171         }
    172 
    173     }
    174 
    175 
    176     /**
    177      * <p>Set the message key.</p>
    178      *
    179      * @param key The new key
    180      */
    181     public void setKey(String key) {
    182 
    183         this.key = key;
    184 
    185     }
    186 
    187 
    188     /**
    189      * <p>Return the CSS style(s) to be rendered for this component.</p>
    190      */
    191     public String getStyle() {
    192 
    193         ValueBinding vb = getValueBinding("style");
    194         if (vb != null) {
    195             return (String) vb.getValue(getFacesContext());
    196         } else {
    197             return style;
    198         }
    199 
    200     }
    201 
    202 
    203     /**
    204      * <p>Set the CSS style(s) to be rendered for this component.</p>
    205      *
    206      * @param style The new CSS style(s)
    207      */
    208     public void setStyle(String style) {
    209 
    210         this.style = style;
    211 
    212     }
    213 
    214 
    215     /**
    216      * <p>Return the CSS style class(es) to be rendered for this component.</p>
    217      */
    218     public String getStyleClass() {
    219 
    220         ValueBinding vb = getValueBinding("styleClass");
    221         if (vb != null) {
    222             return (String) vb.getValue(getFacesContext());
    223         } else {
    224             return styleClass;
    225         }
    226 
    227     }
    228 
    229 
    230     /**
    231      * <p>Set the CSS style class(es) to be rendered for this component.</p>
    232      *
    233      * @param styleClass The new CSS style class(es)
    234      */
    235     public void setStyleClass(String styleClass) {
    236 
    237         this.styleClass = styleClass;
    238 
    239     }
    240 
    241 
    242     // ---------------------------------------------------- StateManager Methods
    243 
    244 
    245     /**
    246      * <p>Restore the state of this component.</p>
    247      *
    248      * @param context <code>FacesContext</code> for the current request
    249      * @param state State object from which to restore our state
    250      */
    251     public void restoreState(FacesContext context, Object state) {
    252 
    253         Object values[] = (Object[]) state;
    254         super.restoreState(context, values[0]);
    255         bundle = (String) values[1];
    256         filter = ((Boolean) values[2]).booleanValue();
    257         filterSet = ((Boolean) values[3]).booleanValue();
    258         key = (String) values[4];
    259         style = (String) values[5];
    260         styleClass = (String) values[6];
    261 
    262     }
    263 
    264 
    265     /**
    266      * <p>Save the state of this component.</p>
    267      *
    268      * @param context <code>FacesContext</code> for the current request
    269      */
    270     public Object saveState(FacesContext context) {
    271 
    272         Object values[] = new Object[7];
    273         values[0] = super.saveState(context);
    274         values[1] = bundle;
    275         values[2] = filter ? Boolean.TRUE : Boolean.FALSE;
    276         values[3] = filterSet ? Boolean.TRUE : Boolean.FALSE;
    277         values[4] = key;
    278         values[5] = style;
    279         values[6] = styleClass;
    280         return values;
    281 
    282     }
    283 
    284 
    285 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
