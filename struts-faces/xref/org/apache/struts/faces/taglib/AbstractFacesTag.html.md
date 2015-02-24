[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/taglib/AbstractFacesTag.html.md)


    1   /*
    2    * $Id: AbstractFacesTag.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import javax.faces.el.ValueBinding;
    27  import javax.faces.webapp.UIComponentTag;
    28  
    29  
    30  /**
    31   * <p>Abstract base class for custom component tags for the
    32   * <em>Struts-Faces Integration Library</em>.</p>
    33   *
    34   *
    35   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    36   */
    37  
    38  public abstract class AbstractFacesTag extends UIComponentTag {
    39  
    40  
    41      // ---------------------------------------------------------- Tag Attributes
    42  
    43  
    44      /**
    45       * <p>The servlet context attribute under which our
    46       * <code>MessageResources</code> bundle is stored.</p>
    47       */
    48      protected String bundle = null;
    49  
    50      public void setBundle(String bundle) {
    51          this.bundle = bundle;
    52      }
    53  
    54  
    55      /**
    56       * <p>The CSS style(s) used to render this component.</p>
    57       */
    58      protected String style = null;
    59  
    60      public void setStyle(String style) {
    61          this.style = style;
    62      }
    63  
    64  
    65      /**
    66       * <p>The CSS style class(es) used to render this component.</p>
    67       */
    68      protected String styleClass = null;
    69  
    70      public void setStyleClass(String styleClass) {
    71          this.styleClass = styleClass;
    72      }
    73  
    74  
    75      /**
    76       * <p>The literal value to be rendered.</p>
    77       */
    78      protected String value = null;
    79  
    80      public void setValue(String value) {
    81          this.value = value;
    82      }
    83  
    84  
    85      // ---------------------------------------------------------- Public Methods
    86  
    87  
    88      /**
    89       * <p>Return the component type of the component to be created for
    90       * this tag.</p>
    91       */
    92      public abstract String getComponentType();
    93  
    94  
    95      /**
    96       * <p>Return the <code>rendererType</code> to be used for rendering
    97       * our component.</p>
    98       */
    99      public abstract String getRendererType();
    100 
    101 
    102     /**
    103      * <p>Release any variables allocated during use of this tag instance.</p>
    104      */
    105     public void release() {
    106 
    107         super.release();
    108         this.bundle = null;
    109         this.style = null;
    110         this.styleClass = null;
    111         this.value = null;
    112 
    113     }
    114 
    115 
    116     // -------------------------------------------------- UIComponentTag Methods
    117 
    118 
    119     /**
    120      * <p>Override attributes set on this tag instance.</p>
    121      *
    122      * @param component Component whose attributes should be overridden
    123      */
    124     protected void setProperties(UIComponent component) {
    125 
    126         super.setProperties(component);
    127         setStringAttribute(component, "bundle", bundle);
    128         setStringAttribute(component, "style", style);
    129         setStringAttribute(component, "styleClass", styleClass);
    130         setStringAttribute(component, "value", value);
    131 
    132     }
    133 
    134 
    135     // ------------------------------------------------------- Protected Methods
    136 
    137 
    138     /**
    139      * <p>If the specified attribute value is not <code>null</code>
    140      * use it to either store a value binding expression for the
    141      * specified attribute name, or store it as the literal value
    142      * of the attribute.</p>
    143      *
    144      * @param component <code>UIComponent</code> whose attribute
    145      *  is to be set
    146      * @param name Attribute name
    147      * @param value Attribute value (or <code>null</code>)
    148      *
    149      * @exception NumberFormatException if the value does not
    150      *  contain a parsable integer
    151      * @exception ReferenceSyntaxException if the expression has
    152      *  invalid syntax
    153      */
    154     protected void setBooleanAttribute(UIComponent component,
    155                                        String name, String value) {
    156 
    157         if (value == null) {
    158             return;
    159         }
    160         if (isValueReference(value)) {
    161             ValueBinding vb =
    162                 getFacesContext().getApplication().createValueBinding(value);
    163             component.setValueBinding(name, vb);
    164         } else {
    165             component.getAttributes().put(name, Boolean.valueOf(value));
    166         }
    167 
    168     }
    169 
    170 
    171     /**
    172      * <p>If the specified attribute value is not <code>null</code>
    173      * use it to either store a value binding expression for the
    174      * specified attribute name, or store it as the literal value
    175      * of the attribute.</p>
    176      *
    177      * @param component <code>UIComponent</code> whose attribute
    178      *  is to be set
    179      * @param name Attribute name
    180      * @param value Attribute value (or <code>null</code>)
    181      *
    182      * @exception NumberFormatException if the value does not
    183      *  contain a parsable integer
    184      * @exception ReferenceSyntaxException if the expression has
    185      *  invalid syntax
    186      */
    187     protected void setIntegerAttribute(UIComponent component,
    188                                        String name, String value) {
    189 
    190         if (value == null) {
    191             return;
    192         }
    193         if (isValueReference(value)) {
    194             ValueBinding vb =
    195                 getFacesContext().getApplication().createValueBinding(value);
    196             component.setValueBinding(name, vb);
    197         } else {
    198             component.getAttributes().put(name, Integer.valueOf(value));
    199         }
    200 
    201     }
    202 
    203 
    204     /**
    205      * <p>If the specified attribute value is not <code>null</code>
    206      * use it to either store a value binding expression for the
    207      * specified attribute name, or store it as the literal value
    208      * of the attribute.</p>
    209      *
    210      * @param component <code>UIComponent</code> whose attribute
    211      *  is to be set
    212      * @param name Attribute name
    213      * @param value Attribute value (or <code>null</code>)
    214      *
    215      * @exception ReferenceSyntaxException if the expression has
    216      *  invalid syntax
    217      */
    218     protected void setStringAttribute(UIComponent component,
    219                                       String name, String value) {
    220 
    221         if (value == null) {
    222             return;
    223         }
    224         if (isValueReference(value)) {
    225             ValueBinding vb =
    226                 getFacesContext().getApplication().createValueBinding(value);
    227             component.setValueBinding(name, vb);
    228         } else {
    229             component.getAttributes().put(name, value);
    230         }
    231 
    232     }
    233 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
