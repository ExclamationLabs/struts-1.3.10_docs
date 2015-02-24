[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/taglib/FormTag.html.md)


    1   /*
    2    * $Id: FormTag.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.taglib;
    23  
    24  
    25  import javax.faces.component.UIComponent;
    26  
    27  
    28  /**
    29   * <p>Render an input form that is submitted to a Struts <code>Action</code>,
    30   * for the <em>Struts-Faces Integration Library</em>.</p>
    31   *
    32   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    33   */
    34  
    35  public class FormTag extends AbstractFacesTag {
    36  
    37  
    38      // ---------------------------------------------------------- Tag Attributes
    39  
    40  
    41      /**
    42       * <p>The <code>path</code> of the Struts <code>Action</code> to which
    43       * this form should be submitted.  This property is analogous to the
    44       * <code>formName</code> property on the form tag in the standard
    45       * HTML RenderKit.</p>
    46       */
    47      protected String action = null;
    48  
    49      public void setAction(String action) {
    50          this.action = action;
    51      }
    52  
    53  
    54      /**
    55       * <p>The content encoding type to use.</p>
    56       */
    57      protected String enctype = null;
    58  
    59      public void setEnctype(String enctype) {
    60          this.enctype = enctype;
    61      }
    62  
    63  
    64      /**
    65       * <p>The name of the field to which focus should be set when this
    66       * form is displayed.</p>
    67       */
    68      protected String focus = null;
    69  
    70      public void setFocus(String focus) {
    71          this.focus = focus;
    72      }
    73  
    74  
    75      /**
    76       * <p>The subscript of the focus field array to receive focus.</p>
    77       */
    78      protected String focusIndex = null;
    79  
    80      public void setFocusIndex(String focusIndex) {
    81          this.focusIndex = focusIndex;
    82      }
    83  
    84  
    85      /**
    86       * <p>The JavaScript reset event handler.</p>
    87       */
    88      protected String onreset = null;
    89  
    90      public void setOnreset(String onreset) {
    91          this.onreset = onreset;
    92      }
    93  
    94  
    95      /**
    96       * <p>The JavaScript submit event handler.</p>
    97       */
    98      protected String onsubmit = null;
    99  
    100     public void setOnsubmit(String onsubmit) {
    101         this.onsubmit = onsubmit;
    102     }
    103 
    104 
    105     /**
    106      * <p>The window target for this submit.</p>
    107      */
    108     protected String target = null;
    109 
    110     public void setTarget(String target) {
    111         this.target = target;
    112     }
    113 
    114 
    115     // ------------------------------------------------------------- Tag Methods
    116 
    117 
    118     /**
    119      * <p>Release any allocated resources.</p>
    120      */
    121     public void release() {
    122 
    123         super.release();
    124         action = null;
    125         enctype = null;
    126         focus = null;
    127         focusIndex = null;
    128         onreset = null;
    129         onsubmit = null;
    130         target = null;
    131 
    132     }
    133 
    134 
    135     // ---------------------------------------------------------- Public Methods
    136 
    137 
    138     /**
    139      * <p>Return the type of component to be created for this tag.</p>
    140      */
    141     public String getComponentType() {
    142 
    143         return ("org.apache.struts.faces.Form");
    144 
    145     }
    146 
    147 
    148     /**
    149      * <p>Return the <code>rendererType</code> to be used for rendering
    150      * our component.</p>
    151      */
    152     public String getRendererType() {
    153 
    154         return ("org.apache.struts.faces.Form");
    155 
    156     }
    157 
    158 
    159     // ------------------------------------------------------- Protected Methods
    160 
    161 
    162     /**
    163      * <p>Override attributes set on this tag instance.</p>
    164      *
    165      * @param component Component whose attributes should be overridden
    166      */
    167     protected void setProperties(UIComponent component) {
    168 
    169         super.setProperties(component);
    170         setStringAttribute(component, "action", action);
    171         setStringAttribute(component, "enctype", enctype);
    172         setStringAttribute(component, "focus", focus);
    173         setStringAttribute(component, "focusIndex", focusIndex);
    174         setStringAttribute(component, "onreset", onreset);
    175         setStringAttribute(component, "onsubmit", onsubmit);
    176         setStringAttribute(component, "target", target);
    177 
    178     }
    179 
    180 
    181 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
