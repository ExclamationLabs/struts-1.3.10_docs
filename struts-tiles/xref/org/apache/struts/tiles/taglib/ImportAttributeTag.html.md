[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/ImportAttributeTag.html.md)


    1   /*
    2    * $Id: ImportAttributeTag.java 504721 2007-02-07 22:22:21Z bayard $
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
    22  
    23  package org.apache.struts.tiles.taglib;
    24  
    25  import java.util.Iterator;
    26  
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.PageContext;
    29  import javax.servlet.jsp.tagext.TagSupport;
    30  
    31  import org.apache.struts.tiles.taglib.util.TagUtils;
    32  import org.apache.struts.tiles.ComponentContext;
    33  
    34  
    35  /**
    36    *  Import attribute from component to requested scope.
    37    *  Attribute name and scope are optional. If not specified, all component
    38    *  attributes are imported in page scope.
    39   */
    40  
    41  public class ImportAttributeTag extends TagSupport {
    42  
    43      /**
    44       * Class name of object.
    45       */
    46      private String  name = null;
    47  
    48  
    49      /**
    50       * The scope name.
    51       */
    52      private String scopeName = null;
    53  
    54      /**
    55       * The scope value.
    56       */
    57      private int scope = PageContext.PAGE_SCOPE;
    58      /**
    59       * Are errors ignored. This is the property for attribute
    60       * <code>ignore</code>.
    61       * Default value is <code>false</code>, which throws an exception.
    62       * Only "attribute not found" - errors are ignored.
    63       */
    64    protected boolean isErrorIgnored = false;
    65  
    66  
    67      /**
    68       * Release all allocated resources.
    69       */
    70      public void release() {
    71  
    72          super.release();
    73          name = null;
    74          scopeName = null;
    75          scope = PageContext.PAGE_SCOPE;
    76          isErrorIgnored = false;
    77      }
    78  
    79      /**
    80       * Get the name.
    81       * @return Name.
    82       */
    83      public String getName()
    84       {
    85       return (this.name);
    86       }
    87  
    88  
    89      /**
    90       * Set the name.
    91       * @param name The new name
    92       */
    93      public void setName(String name)
    94       {
    95       this.name = name;
    96       }
    97  
    98      /**
    99       * Set the scope.
    100      * @param scope Scope.
    101      */
    102     public void setScope(String scope)
    103       {
    104       this.scopeName = scope;
    105       }
    106 
    107     /**
    108      * Get scope.
    109      * @return Scope.
    110      */
    111   public String getScope()
    112   {
    113   return scopeName;
    114   }
    115 
    116     /**
    117      * Set ignore flag.
    118      * @param ignore default: <code>false</code>: Exception is thrown when
    119      * attribute is not found, set to <code>
    120      * true</code> to ignore missing attributes silently
    121      */
    122   public void setIgnore(boolean ignore)
    123     {
    124     this.isErrorIgnored = ignore;
    125     }
    126 
    127     /**
    128      * Get ignore flag.
    129      * @return default: <code>false</code>: Exception is thrown when attribute
    130      * is not found, set to <code>
    131      * true</code> to ignore missing attributes silently
    132      */
    133   public boolean getIgnore()
    134   {
    135   return isErrorIgnored;
    136   }
    137 
    138     // --------------------------------------------------------- Public Methods
    139 
    140 
    141     /**
    142      * Expose the requested property from component context.
    143      *
    144      * @exception JspException On errors processing tag.
    145      */
    146 public int doStartTag() throws JspException
    147     {
    148       // retrieve component context
    149     ComponentContext compContext =
    150         (ComponentContext)pageContext.getAttribute(
    151             ComponentConstants.COMPONENT_CONTEXT, PageContext.REQUEST_SCOPE);
    152     if( compContext == null )
    153         throw new JspException ( "Error - tag importAttribute : "
    154             + "no tiles context found." );
    155 
    156       // set scope
    157     scope = TagUtils.getScope( scopeName, PageContext.PAGE_SCOPE );
    158 
    159       // push attribute in requested context.
    160     if( name != null )
    161       {
    162       Object value = compContext.getAttribute(name);
    163         // Check if value exist and if we must send a runtime exception
    164       if( value == null ) 
    165         {
    166         if(!isErrorIgnored) 
    167           {
    168           throw new JspException ( "Error - tag importAttribute : property '"+
    169               name + "' not found in context. Check tag syntax" );
    170           }
    171         }
    172        else 
    173         {
    174         pageContext.setAttribute(name, value, scope);
    175         }
    176       }
    177      else
    178       { // set all attributes
    179       Iterator names = compContext.getAttributeNames();
    180       while(names.hasNext())
    181         {
    182         String name = (String)names.next();
    183         if(name == null ) {
    184           if(!isErrorIgnored)
    185             throw new JspException ( "Error - tag importAttribute : "
    186                 + "encountered an attribute with key 'null'" );
    187           else
    188             return SKIP_BODY;
    189         }
    190 
    191         Object value = compContext.getAttribute(name);
    192         // Check if value exist and if we must send a runtime exception
    193         if( value == null ) {
    194           if(!isErrorIgnored) {
    195             throw new JspException ( "Error - tag importAttribute : property '"
    196                 + name + "' has a value of 'null'" );
    197           }
    198         }
    199         pageContext.setAttribute(name, value, scope);
    200         } // end loop
    201       } // end else
    202 
    203       // Continue processing this page
    204     return SKIP_BODY;
    205     }
    206 
    207     /**
    208      * Clean up after processing this enumeration.
    209      *
    210      * @exception JspException On errors processing tag.
    211      */
    212   public int doEndTag() throws JspException
    213     {
    214     return (EVAL_PAGE);
    215     }
    216 
    217 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
