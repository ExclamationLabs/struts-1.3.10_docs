[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/component/HtmlComponent.html.md)


    1   /*
    2    * $Id: HtmlComponent.java 471754 2006-11-06 14:55:09Z husted $
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
    32   * <code>&lt.html.md:html&gt;</code> tag.</p>
    33   */
    34  
    35  public class HtmlComponent extends UIOutput {
    36  
    37  
    38      // ------------------------------------------------------------ Constructors
    39  
    40  
    41      /**
    42       * <p>Create a new {@link HtmlComponent} with default properties.</p>
    43       */
    44      public HtmlComponent() {
    45  
    46          super();
    47          setRendererType("org.apache.struts.faces.Html");
    48  
    49      }
    50  
    51  
    52      // ------------------------------------------------------ Instance Variables
    53  
    54  
    55      /**
    56       * <p>Flag indicating we should create a locale.</p>
    57       */
    58      private boolean locale = true;
    59      private boolean localeSet = false;
    60  
    61  
    62      /**
    63       * <p>Flag indicating we should render XHTML output.</p>
    64       */
    65      private boolean .html.md = false;
    66      private boolean .html.mdSet = false;
    67  
    68  
    69      // ---------------------------------------------------- Component Properties
    70  
    71  
    72      /**
    73       * <p>Return the component family to which this component belongs.</p>
    74       */
    75      public String getFamily() {
    76  
    77          return "org.apache.struts.faces.Html";
    78  
    79      }
    80  
    81  
    82      /**
    83       * <p>Return a flag indicating whether a locale should be created.</p>
    84       */
    85      public boolean isLocale() {
    86  
    87          if (localeSet) {
    88              return locale;
    89          }
    90          ValueBinding vb = getValueBinding("locale");
    91          if (vb != null) {
    92              Boolean value = (Boolean) vb.getValue(getFacesContext());
    93              if (null == value) {
    94                  return locale;
    95              }
    96              return value.booleanValue();
    97          } else {
    98              return locale;
    99          }
    100 
    101     }
    102 
    103 
    104     /**
    105      * <p>Set the flag indicating whether a locale should be created.</p>
    106      *
    107      * @param locale The new flag
    108      */
    109     public void setLocale(boolean locale) {
    110 
    111         this.locale = locale;
    112         this.localeSet = true;
    113 
    114     }
    115 
    116 
    117     /**
    118      * <p>Return a flag indicating whether .html.md should be created.</p>
    119      */
    120     public boolean is.html.md() {
    121 
    122         if (.html.mdSet) {
    123             return .html.md;
    124         }
    125         ValueBinding vb = getValueBinding(".html.md");
    126         if (vb != null) {
    127             Boolean value = (Boolean) vb.getValue(getFacesContext());
    128             if (null == value) {
    129                 return .html.md;
    130             }
    131             return value.booleanValue();
    132         } else {
    133             return .html.md;
    134         }
    135 
    136     }
    137 
    138 
    139     /**
    140      * <p>Set the flag indicating whether .html.md should be created.</p>
    141      *
    142      * @param .html.md The new flag
    143      */
    144     public void set.html.md(boolean xhtml) {
    145 
    146         this..html.md = xhtml;
    147         this..html.mdSet = true;
    148 
    149     }
    150 
    151 
    152     // ---------------------------------------------------- StateManager Methods
    153 
    154 
    155     /**
    156      * <p>Restore the state of this component.</p>
    157      *
    158      * @param context <code>FacesContext</code> for the current request
    159      * @param state State object from which to restore our state
    160      */
    161     public void restoreState(FacesContext context, Object state) {
    162 
    163         Object values[] = (Object[]) state;
    164         super.restoreState(context, values[0]);
    165         locale = ((Boolean) values[1]).booleanValue();
    166         localeSet = ((Boolean) values[2]).booleanValue();
    167         .html.md = ((Boolean) values[3]).booleanValue();
    168         .html.mdSet = ((Boolean) values[4]).booleanValue();
    169 
    170     }
    171 
    172 
    173     /**
    174      * <p>Save the state of this component.</p>
    175      *
    176      * @param context <code>FacesContext</code> for the current request
    177      */
    178     public Object saveState(FacesContext context) {
    179 
    180         Object values[] = new Object[5];
    181         values[0] = super.saveState(context);
    182         values[1] = locale ? Boolean.TRUE : Boolean.FALSE;
    183         values[2] = localeSet ? Boolean.TRUE : Boolean.FALSE;
    184         values[3] = .html.md ? Boolean.TRUE : Boolean.FALSE;
    185         values[4] = .html.mdSet ? Boolean.TRUE : Boolean.FALSE;
    186         return values;
    187 
    188     }
    189 
    190 
    191 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
