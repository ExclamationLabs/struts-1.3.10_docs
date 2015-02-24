[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/UseAttributeTag.html.md)


    1   /*
    2    * $Id: UseAttributeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import javax.servlet.jsp.PageContext;
    26  import javax.servlet.jsp.tagext.TagSupport;
    27  
    28  import org.apache.struts.tiles.taglib.util.TagUtils;
    29  import org.apache.struts.tiles.ComponentContext;
    30  
    31  
    32  /**
    33   * Custom tag exposing a component attribute to page.
    34   *
    35   */
    36  public class UseAttributeTag extends TagSupport {
    37  
    38  
    39      // ----------------------------------------------------- Instance Variables
    40  
    41  
    42      /**
    43       * Class name of object.
    44       */
    45      private String  classname = null;
    46  
    47  
    48      /**
    49       * The scope name.
    50       */
    51      private String scopeName = null;
    52  
    53      /**
    54       * The scope value.
    55       */
    56      private int scope = PageContext.PAGE_SCOPE;
    57  
    58  
    59  
    60      /**
    61       * The attribute name to be exposed.
    62       */
    63      private String attributeName = null;
    64  
    65      /**
    66       * Are errors ignored. This is the property for attribute 'ignore'.
    67       * Default value is <code>false</code>, which throws an exception.
    68       * Only "attribute not found" - errors are ignored.
    69       */
    70    protected boolean isErrorIgnored = false;
    71  
    72  
    73      // ------------------------------------------------------------- Properties
    74  
    75  
    76      /**
    77       * Release all allocated resources.
    78       */
    79      public void release() {
    80  
    81          super.release();
    82          attributeName = null;
    83          classname = null;
    84          scope = PageContext.PAGE_SCOPE;
    85          scopeName = null;
    86          isErrorIgnored = false;
    87            // Parent doesn't clear id, so we do it
    88            // bug reported by Heath Chiavettone on 18 Mar 2002
    89          id = null;
    90      }
    91  
    92      /**
    93       * Get class name.
    94       */
    95      public String getClassname() {
    96  
    97    return (this.classname);
    98  
    99      }
    100 
    101 
    102     /**
    103      * Set the class name.
    104      *
    105      * @param name The new class name.
    106      */
    107     public void setClassname(String name) {
    108 
    109   this.classname = name;
    110 
    111     }
    112 
    113     /**
    114      * Set name.
    115      */
    116   public void setName(String value){
    117     this.attributeName = value;
    118   }
    119 
    120     /**
    121      * Get name.
    122      */
    123   public String getName()
    124   {
    125   return attributeName;
    126   }
    127 
    128     /**
    129      * Set the scope.
    130      *
    131      * @param scope The new scope.
    132      */
    133     public void setScope(String scope) {
    134   this.scopeName = scope;
    135     }
    136 
    137     /**
    138      * Get scope.
    139      */
    140   public String getScope()
    141   {
    142   return scopeName;
    143   }
    144 
    145     /**
    146      * Set ignore.
    147      */
    148   public void setIgnore(boolean ignore)
    149     {
    150     this.isErrorIgnored = ignore;
    151     }
    152 
    153     /**
    154      * Get ignore.
    155      */
    156   public boolean getIgnore()
    157   {
    158   return isErrorIgnored;
    159   }
    160 
    161     // --------------------------------------------------------- Public Methods
    162 
    163 
    164     /**
    165      * Expose the requested attribute from component context.
    166      *
    167      * @exception JspException if a JSP exception has occurred
    168      */
    169   public int doStartTag() throws JspException
    170     {
    171       // Do a local copy of id
    172     String localId=this.id;
    173     if( localId==null )
    174       localId=attributeName;
    175 
    176     ComponentContext compContext = (ComponentContext)pageContext.getAttribute( ComponentConstants.COMPONENT_CONTEXT, PageContext.REQUEST_SCOPE);
    177     if( compContext == null )
    178       throw new JspException ( "Error - tag useAttribute : no tiles context found." );
    179 
    180     Object value = compContext.getAttribute(attributeName);
    181         // Check if value exists and if we must send a runtime exception
    182     if( value == null )
    183       if(!isErrorIgnored)
    184         throw new JspException ( "Error - tag useAttribute : attribute '"+ attributeName + "' not found in context. Check tag syntax" );
    185        else
    186         return SKIP_BODY;
    187 
    188     if( scopeName != null )
    189       {
    190       scope = TagUtils.getScope( scopeName, PageContext.PAGE_SCOPE );
    191       if(scope!=ComponentConstants.COMPONENT_SCOPE)
    192         pageContext.setAttribute(localId, value, scope);
    193       }
    194      else
    195       pageContext.setAttribute(localId, value);
    196 
    197       // Continue processing this page
    198     return SKIP_BODY;
    199     }
    200 
    201 
    202 
    203 
    204     /**
    205      * Clean up after processing this enumeration.
    206      *
    207      * @exception JspException if a JSP exception has occurred
    208      */
    209   public int doEndTag() throws JspException
    210     {
    211     return (EVAL_PAGE);
    212     }
    213 
    214 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
