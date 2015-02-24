[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/GetAttributeTag.html.md)


    1   /*
    2    * $Id: GetAttributeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import java.io.IOException;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.PageContext;
    30  import javax.servlet.jsp.tagext.TagSupport;
    31  
    32  import org.apache.struts.tiles.ComponentContext;
    33  
    34    /**
    35     * Retrieve the value of the specified component/template attribute property,
    36     * and render it to the current JspWriter as a String.
    37     * The usual toString() conversion is applied on the found value.
    38     */
    39  public class GetAttributeTag extends TagSupport implements ComponentConstants {
    40  
    41    private String attribute = null;
    42      /** Role attribute */
    43    private String role = null;
    44      /**
    45       * Do we ignore error if attribute is not found.
    46       * Default value is <code>false</code>, which will throw an exception.
    47       */
    48    private boolean isErrorIgnored = false;
    49  
    50    /**
    51     * Default constructor.
    52     */
    53    public GetAttributeTag() {
    54      super();
    55    }
    56  
    57      /**
    58       * Release all allocated resources.
    59       */
    60      public void release() {
    61  
    62          super.release();
    63          attribute = null;
    64          role = null;
    65          isErrorIgnored = false;
    66      }
    67  
    68      /**
    69       * Set attribute.
    70       * @param attribute Attribute.
    71       */
    72    public void setAttribute(String attribute){
    73      this.attribute = attribute;
    74    }
    75  
    76      /**
    77       * Get attribute.
    78       * @return Attribute.
    79       */
    80    public String getAttribute()
    81    {
    82    return attribute;
    83    }
    84  
    85      /**
    86       * Set Name.
    87       * Same as setAttribute().
    88       * @param value Attribute.
    89       */
    90    public void setName(String value)
    91      {
    92      this.attribute = value;
    93      }
    94  
    95      /**
    96       * Get Name.
    97       * Set as getAttribute().
    98       * @return Attribute.
    99       */
    100   public String getName()
    101   {
    102   return attribute;
    103   }
    104 
    105     /**
    106      * Set ignoring flag when attribute is not found.
    107      * @param ignore default: <code>false</code>: Exception is thrown when attribute is not found, set to <code>
    108      * true</code> to ignore missing attributes silently
    109      */
    110   public void setIgnore(boolean ignore)
    111     {
    112     this.isErrorIgnored = ignore;
    113     }
    114 
    115     /**
    116      * Get ignore flag.
    117      * @return <code>false</code>: Exception is thrown when attribute is not found, set to <code>
    118      * true</code> to ignore missing attributes silently
    119      */
    120   public boolean getIgnore()
    121   {
    122   return isErrorIgnored;
    123   }
    124 
    125     /**
    126      * Set role.
    127      * @param role The role the user must be in to store content.
    128      */
    129    public void setRole(String role) {
    130       this.role = role;
    131    }
    132 
    133     /**
    134      * Get role.
    135      * @return Role.
    136      */
    137   public String getRole()
    138   {
    139   return role;
    140   }
    141 
    142     /**
    143      * Close tag.
    144      * @throws JspException On error processing tag.
    145      */
    146   public int doEndTag() throws JspException {
    147 
    148       // Check role
    149     if(role != null && !((HttpServletRequest)pageContext.getRequest()).isUserInRole(role) )
    150       {
    151       return EVAL_PAGE;
    152       } // end if
    153 
    154       // Get context
    155     ComponentContext compContext = (ComponentContext)pageContext.getAttribute( ComponentConstants.COMPONENT_CONTEXT, PageContext.REQUEST_SCOPE);
    156 
    157     if( compContext == null )
    158       throw new JspException ( "Error - tag.getAsString : component context is not defined. Check tag syntax" );
    159 
    160     Object value = compContext.getAttribute(attribute);
    161     if( value == null)
    162       { // no value : throw error or fail silently according to ignore
    163       if(isErrorIgnored == false )
    164         throw new JspException ( "Error - tag.getAsString : attribute '"+ attribute + "' not found in context. Check tag syntax" );
    165        else
    166         return EVAL_PAGE;
    167       } // end if
    168 
    169 
    170     try
    171       {
    172       pageContext.getOut().print( value );
    173       }
    174      catch( IOException ex )
    175       {
    176       ex.printStackTrace();
    177       throw new JspException ( "Error - tag.getProperty : IOException ", ex);
    178       }
    179 
    180     return EVAL_PAGE;
    181   }
    182 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
