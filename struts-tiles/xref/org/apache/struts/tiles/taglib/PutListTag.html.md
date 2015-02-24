[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/PutListTag.html.md)


    1   /*
    2    * $Id: PutListTag.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles.taglib;
    23  
    24  import java.util.ArrayList;
    25  import java.util.List;
    26  
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  import org.apache.struts.tiles.AttributeDefinition;
    31  import org.apache.struts.tiles.UntypedAttribute;
    32  
    33  /**
    34   * PutList tag implementation.
    35   */
    36  public class PutListTag
    37      extends TagSupport
    38      implements ComponentConstants, AddTagParent, PutListTagParent {
    39  
    40      /**
    41       * Name of this attribute.
    42       */
    43      private String attributeName = null;
    44  
    45      /**
    46       * The list itself.
    47       */
    48      private List list = null;
    49  
    50      /**
    51       * Role attribute.
    52       */
    53      private String role = null;
    54  
    55      /**
    56       * Default constructor.
    57       */
    58      public PutListTag() {
    59          super();
    60      }
    61  
    62      /**
    63       * Release all allocated resources.
    64       */
    65      public void release() {
    66          super.release();
    67          attributeName = null;
    68          role = null;
    69      }
    70  
    71      /**
    72       * Release all internal resources.
    73       */
    74      protected void releaseInternal() {
    75          list = null;
    76      }
    77  
    78      /**
    79       * Set property.
    80       */
    81      public void setName(String name) {
    82          this.attributeName = name;
    83      }
    84  
    85      /**
    86       * Get property.
    87       */
    88      public String getName() {
    89          return attributeName;
    90      }
    91  
    92      /**
    93       * Set role attribute.
    94       * @param role The role the user must be in to store content.
    95       */
    96      public void setRole(String role) {
    97          this.role = role;
    98      }
    99  
    100     /**
    101      * Get role attribute.
    102      */
    103     public String getRole() {
    104         return role;
    105     }
    106 
    107     /**
    108      * Get list defined in tag.
    109      */
    110     public List getList() {
    111         return list;
    112     }
    113 
    114     /**
    115      * Set property.
    116      */
    117     public void addElement(Object value) {
    118         if (list == null) {
    119             list = new ArrayList();
    120         }
    121 
    122         list.add(value);
    123     }
    124 
    125     /**
    126      * Process nested &lg;putList&gt; tag.
    127      * Method calls by nested &lg;putList&gt; tags.
    128      * Nested list is added to current list.
    129      * If role is defined, nested attribute is wrapped into an untypped definition
    130      * containing attribute value and role.
    131      */
    132     public void processNestedTag(PutListTag nestedTag) throws JspException {
    133         // Get real value and check role
    134         // If role is set, add it in attribute definition if any.
    135         // If no attribute definition, create untyped one, and set role.
    136         Object attributeValue = nestedTag.getList();
    137 
    138         if (nestedTag.getRole() != null) {
    139             AttributeDefinition def = new UntypedAttribute(attributeValue);
    140             def.setRole(nestedTag.getRole());
    141             attributeValue = def;
    142         }
    143 
    144         // now add attribute to enclosing parent (i.e. : this object)
    145         addElement(attributeValue);
    146     }
    147 
    148     /**
    149      * Process nested &lg;add&gt; tag.
    150      * Method calls by nested &lg;add&gt; tags.
    151      * Nested attribute is added to current list.
    152      * If role is defined, nested attribute is wrapped into an untypped definition
    153      * containing attribute value and role.
    154      */
    155     public void processNestedTag(AddTag nestedTag) throws JspException {
    156         // Get real value and check role
    157         // If role is set, add it in attribute definition if any.
    158         // If no attribute definition, create untyped one, and set role.
    159         Object attributeValue = nestedTag.getRealValue();
    160         AttributeDefinition def;
    161 
    162         if (nestedTag.getRole() != null) {
    163             try {
    164                 def = ((AttributeDefinition) attributeValue);
    165             } catch (ClassCastException ex) {
    166                 def = new UntypedAttribute(attributeValue);
    167             }
    168             def.setRole(nestedTag.getRole());
    169             attributeValue = def;
    170         }
    171 
    172         // now add attribute to enclosing parent (i.e. : this object)
    173         addElement(attributeValue);
    174     }
    175 
    176     /**
    177      * Do start tag.
    178      */
    179     public int doStartTag() throws JspException {
    180         return EVAL_BODY_INCLUDE;
    181     }
    182 
    183     /**
    184      * Do end tag.
    185      */
    186     public int doEndTag() throws JspException {
    187         PutListTagParent enclosingParent = findEnclosingParent();
    188         enclosingParent.processNestedTag(this);
    189         // Clear list to avoid reuse
    190         releaseInternal();
    191         return EVAL_PAGE;
    192     }
    193 
    194     /**
    195      * Find enclosing parent tag accepting this tag.
    196      * @throws JspException If we can't find an appropriate enclosing tag.
    197      */
    198     protected PutListTagParent findEnclosingParent() throws JspException {
    199         try {
    200             PutListTagParent parent =
    201                 (PutListTagParent) findAncestorWithClass(this,
    202                     PutListTagParent.class);
    203 
    204             if (parent == null) {
    205                 throw new JspException("Error - tag putList : enclosing tag doesn't accept 'putList' tag.");
    206             }
    207 
    208             return parent;
    209 
    210         } catch (ClassCastException ex) {
    211             throw new JspException("Error - tag putList : enclosing tag doesn't accept 'putList' tag.", ex);
    212         }
    213     }
    214 
    215 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
