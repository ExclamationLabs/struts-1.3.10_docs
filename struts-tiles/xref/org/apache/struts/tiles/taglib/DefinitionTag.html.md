[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/DefinitionTag.html.md)


    1   /*
    2    * $Id: DefinitionTag.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import javax.servlet.jsp.JspException;
    25  
    26  import org.apache.struts.tiles.taglib.util.TagUtils;
    27  import org.apache.struts.tiles.AttributeDefinition;
    28  import org.apache.struts.tiles.ComponentDefinition;
    29  import org.apache.struts.tiles.UntypedAttribute;
    30  
    31  /**
    32   * This is the tag handler for &lt;tiles:definition&gt;, which defines
    33   * a tiles (or template / component). Definition is put in requested context and can be
    34   * used in &lt;tiles:insert&gt.
    35   *
    36   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    37   */
    38  public class DefinitionTag
    39      extends DefinitionTagSupport
    40      implements PutTagParent, PutListTagParent {
    41  
    42      /* JSP Tag attributes */
    43      /**
    44       * Definition identifier.
    45       */
    46      private String id = null;
    47  
    48      /**
    49       * Scope into which definition will be saved.
    50       */
    51      private String scope = null;
    52  
    53      /**
    54       * Extends attribute value.
    55       */
    56      private String extendsDefinition = null;
    57  
    58      /* Internal properties */
    59      /**
    60       * Template definition
    61       */
    62      private ComponentDefinition definition = null;
    63  
    64      /**
    65       * Reset member values for reuse. This method calls super.release(),
    66       * which invokes TagSupport.release(), which typically does nothing.
    67       */
    68      public void release() {
    69          super.release();
    70          id = null;
    71          page = null;
    72          scope = null;
    73          role = null;
    74          extendsDefinition = null;
    75      }
    76  
    77      /**
    78       * Release internal references.
    79       */
    80      protected void releaseInternal() {
    81          definition = null;
    82      }
    83  
    84      /**
    85       * This method is a convenience for other tags for
    86       * putting content into the tile definition.
    87       * Content is already typed by caller.
    88       */
    89      public void putAttribute(String name, Object content) {
    90          definition.putAttribute(name, content);
    91      }
    92  
    93      /**
    94       * Process nested &lg;put&gt; tag.
    95       * Method is called from nested &lg;put&gt; tags.
    96       * Nested list is added to current list.
    97       * If role is defined, nested attribute is wrapped into an untyped definition
    98       * containing attribute value and role.
    99       */
    100     public void processNestedTag(PutTag nestedTag) throws JspException {
    101         // Get real value and check role
    102         // If role is set, add it in attribute definition if any.
    103         // If no attribute definition, create untyped one and set role.
    104         Object attributeValue = nestedTag.getRealValue();
    105         AttributeDefinition def;
    106 
    107         if (nestedTag.getRole() != null) {
    108             try {
    109                 def = ((AttributeDefinition) attributeValue);
    110             } catch (ClassCastException ex) {
    111                 def = new UntypedAttribute(attributeValue);
    112             }
    113             def.setRole(nestedTag.getRole());
    114             attributeValue = def;
    115         }
    116 
    117         // now add attribute to enclosing parent (i.e. : this object)
    118         putAttribute(nestedTag.getName(), attributeValue);
    119     }
    120 
    121     /**
    122      * Process nested &lg;putList&gt; tag.
    123      * Method is called from nested &lg;putList&gt; tags.
    124      * Nested list is added to current list.
    125      * If role is defined, nested attribute is wrapped into an untyped definition
    126      * containing attribute value and role.
    127      */
    128     public void processNestedTag(PutListTag nestedTag) throws JspException {
    129         // Get real value and check role
    130         // If role is set, add it in attribute definition if any.
    131         // If no attribute definition, create untyped one and set role.
    132         Object attributeValue = nestedTag.getList();
    133 
    134         if (nestedTag.getRole() != null) {
    135             AttributeDefinition def = new UntypedAttribute(attributeValue);
    136             def.setRole(nestedTag.getRole());
    137             attributeValue = def;
    138         }
    139 
    140         // Check if a name is defined
    141         if (nestedTag.getName() == null) {
    142             throw new JspException("Error - PutList : attribute name is not defined. It is mandatory as the list is added to a 'definition'.");
    143         }
    144 
    145         // now add attribute to enclosing parent (i.e. : this object).
    146         putAttribute(nestedTag.getName(), attributeValue);
    147     }
    148 
    149     /**
    150      * Get the ID.
    151      * @return ID
    152      */
    153     public String getId() {
    154         return id;
    155     }
    156 
    157     /**
    158      * Set the ID.
    159      * @param id New ID.
    160      */
    161     public void setId(String id) {
    162         this.id = id;
    163     }
    164 
    165     /**
    166      * Get the scope.
    167      * @return Scope.
    168      */
    169     public String getScope() {
    170         return scope;
    171     }
    172 
    173     /**
    174      * Set the scope.
    175      * @param aScope Scope.
    176      */
    177     public void setScope(String aScope) {
    178         scope = aScope;
    179     }
    180 
    181     /**
    182      * Set <code>extends</code> (parent) definition name.
    183      * @param definitionName Name of parent definition.
    184      */
    185     public void setExtends(String definitionName) {
    186         this.extendsDefinition = definitionName;
    187     }
    188 
    189     /**
    190      * Get <code>extends</code> (parent) definition name.
    191      * @return Name of parent definition.
    192      */
    193     public String getExtends() {
    194         return extendsDefinition;
    195     }
    196 
    197     /**
    198      * Process the start tag by creating a new definition.
    199      * @throws JspException On errors processing tag.
    200      */
    201     public int doStartTag() throws JspException {
    202         // Do we extend a definition ?
    203         if (extendsDefinition != null && !extendsDefinition.equals("")) {
    204             ComponentDefinition parentDef =
    205                 TagUtils.getComponentDefinition(extendsDefinition, pageContext);
    206 
    207             definition = new ComponentDefinition(parentDef);
    208 
    209         } else {
    210             definition = new ComponentDefinition();
    211         }
    212 
    213         // Set definitions attributes
    214         if (page != null) {
    215             definition.setTemplate(page);
    216         }
    217 
    218         if (role != null) {
    219             definition.setRole(role);
    220         }
    221 
    222         return EVAL_BODY_INCLUDE;
    223     }
    224 
    225     /**
    226      * Process the end tag by putting the definition in appropriate context.
    227      * @throws JspException On errors processing tag.
    228      */
    229     public int doEndTag() throws JspException {
    230         TagUtils.setAttribute(pageContext, id, definition, scope);
    231 
    232         releaseInternal();
    233         return EVAL_PAGE;
    234     }
    235 
    236 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
