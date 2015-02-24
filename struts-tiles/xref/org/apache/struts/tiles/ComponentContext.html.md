[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/ComponentContext.html.md)


    1   /*
    2    * $Id: ComponentContext.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles;
    23  
    24  import java.io.Serializable;
    25  import java.util.Collections;
    26  import java.util.HashMap;
    27  import java.util.Iterator;
    28  import java.util.Map;
    29  import java.util.Set;
    30  
    31  import javax.servlet.ServletRequest;
    32  import javax.servlet.jsp.PageContext;
    33  
    34  import org.apache.struts.tiles.taglib.ComponentConstants;
    35  
    36  /**
    37   * Component context.
    38   */
    39  public class ComponentContext implements Serializable {
    40  
    41      /**
    42       * Component attributes.
    43       */
    44      private Map attributes=null;
    45  
    46      /**
    47       * Constructor.
    48       */
    49      public ComponentContext() {
    50          super();
    51      }
    52  
    53      /**
    54       * Constructor.
    55       * Create a context and set specified attributes.
    56       * @param attributes Attributes to initialize context.
    57       */
    58      public ComponentContext(Map attributes) {
    59          if (attributes != null) {
    60              this.attributes = new HashMap(attributes);
    61          }
    62      }
    63  
    64      /**
    65       * Add all attributes to this context.
    66       * Copies all of the mappings from the specified attribute map to this context.
    67       * New attribute mappings will replace any mappings that this context had for any of the keys
    68       * currently in the specified attribute map.
    69       * @param newAttributes Attributes to add.
    70       */
    71      public void addAll(Map newAttributes) {
    72          if (attributes == null) {
    73              attributes = new HashMap(newAttributes);
    74              return;
    75          }
    76  
    77          attributes.putAll(newAttributes);
    78      }
    79  
    80      /**
    81       * Add all missing attributes to this context.
    82       * Copies all of the mappings from the specified attributes map to this context.
    83       * New attribute mappings will be added only if they don't already exist in
    84       * this context.
    85       * @param defaultAttributes Attributes to add.
    86       */
    87      public void addMissing(Map defaultAttributes) {
    88          if (defaultAttributes == null) {
    89              return;
    90          }
    91  
    92          if (attributes == null) {
    93              attributes = new HashMap(defaultAttributes);
    94              return;
    95          }
    96  
    97          Set entries = defaultAttributes.entrySet();
    98          Iterator iterator = entries.iterator();
    99          while (iterator.hasNext()) {
    100             Map.Entry entry = (Map.Entry) iterator.next();
    101             if (!attributes.containsKey(entry.getKey())) {
    102                 attributes.put(entry.getKey(), entry.getValue());
    103             }
    104         }
    105     }
    106 
    107     /**
    108      * Get an attribute from context.
    109      * @param name Name of the attribute.
    110      * @return <{Object}>
    111      */
    112     public Object getAttribute(String name) {
    113         if (attributes == null){
    114             return null;
    115         }
    116 
    117         return attributes.get(name);
    118     }
    119 
    120     /**
    121      * Get names of all attributes.
    122      * @return <{Object}>
    123      */
    124     public Iterator getAttributeNames() {
    125         if (attributes == null) {
    126             return Collections.EMPTY_LIST.iterator();
    127         }
    128 
    129         return attributes.keySet().iterator();
    130     }
    131 
    132     /**
    133      * Put a new attribute to context.
    134      * @param name Name of the attribute.
    135      * @param value Value of the attribute.
    136      */
    137     public void putAttribute(String name, Object value) {
    138         if (attributes == null) {
    139             attributes = new HashMap();
    140         }
    141 
    142         attributes.put(name, value);
    143     }
    144 
    145     /**
    146      * Find object in one of the contexts.
    147      * Order : component then pageContext.findAttribute()
    148      * @param beanName Name of the bean to find.
    149      * @param pageContext Page context.
    150      * @return Requested bean or <code>null</code> if not found.
    151      */
    152     public Object findAttribute(String beanName, PageContext pageContext) {
    153         Object attribute = getAttribute(beanName);
    154         if (attribute == null) {
    155             attribute = pageContext.findAttribute(beanName);
    156         }
    157 
    158         return attribute;
    159     }
    160 
    161     /**
    162      * Get object from requested context.
    163      * Context can be 'component'.
    164      * @param beanName Name of the bean to find.
    165      * @param scope Search scope (see {@link PageContext}).
    166      * @param pageContext Page context.
    167      * @return requested bean or <code>null</code> if not found.
    168      */
    169     public Object getAttribute(
    170         String beanName,
    171         int scope,
    172         PageContext pageContext) {
    173 
    174         if (scope == ComponentConstants.COMPONENT_SCOPE){
    175             return getAttribute(beanName);
    176         }
    177 
    178         return pageContext.getAttribute(beanName, scope);
    179     }
    180 
    181     /**
    182      * Get component context from request.
    183      * @param request ServletRequest.
    184      * @return ComponentContext or null if context is not found or an
    185      * jspException is present in the request.
    186      */
    187     static public ComponentContext getContext(ServletRequest request) {
    188        if (request.getAttribute("javax.servlet.jsp.jspException") != null) {
    189            return null;
    190         }        return (ComponentContext) request.getAttribute(
    191             ComponentConstants.COMPONENT_CONTEXT);
    192     }
    193 
    194     /**
    195      * Store component context into request.
    196      * @param context ComponentContext to store.
    197      * @param request Request to store ComponentContext.
    198      */
    199     static public void setContext(
    200         ComponentContext context,
    201         ServletRequest request) {
    202 
    203         request.setAttribute(ComponentConstants.COMPONENT_CONTEXT, context);
    204     }
    205 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
