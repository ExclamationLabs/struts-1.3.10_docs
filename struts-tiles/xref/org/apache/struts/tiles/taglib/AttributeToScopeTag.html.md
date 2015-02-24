[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/AttributeToScopeTag.html.md)


    1   /*
    2    * $Id: AttributeToScopeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    33    *  Custom  tag  that  puts  component's  attributes  in  a  scope  (request,  page,  ...).
    34    *  @deprecated  Is  it  still  in  use  ?
    35    */
    36  public  final  class  AttributeToScopeTag  extends  TagSupport  {
    37  
    38  
    39          //  ----------------------------------------------------- Instance Variables
    40  
    41  
    42      /**
    43       * The scope name.
    44       */
    45      private String scopeName = null;
    46  
    47      /**
    48       * The scope value.
    49       */
    50      private int scope = PageContext.PAGE_SCOPE;
    51  
    52  
    53  
    54      /**
    55       * The property name to be exposed.
    56       */
    57      private String property = null;
    58  
    59  
    60      // ------------------------------------------------------------- Properties
    61  
    62  
    63  
    64      /**
    65       * Return the property name.
    66       */
    67      public String getProperty()
    68      {
    69      return  (this.property);
    70      }
    71  
    72  
    73       /**
    74         *  Set  the  property  name.
    75         *
    76         *  @param  property  The  property  name
    77         */
    78      public  void  setProperty(String  property)
    79      {
    80      this.property  =  property;
    81      }
    82  
    83      /**
    84        *  Set  the  scope.
    85        *
    86        *  @param  scope  The  new  scope
    87        */
    88      public  void  setScope(String  scope)
    89      {
    90      this.scopeName  =  scope;
    91      }
    92  
    93          //  ---------------------------------------------------------  Public  Methods
    94  
    95  
    96          /**
    97            *  Expose  the  requested  property  from  component  context.
    98            *
    99            *  @exception  JspException  if  a  JSP  exception  has  occurred
    100           */
    101     public  int  doStartTag()  throws  JspException
    102         {
    103         if(  id==null  )
    104             id=property;
    105 
    106         ComponentContext  compContext  =  (ComponentContext)pageContext.getAttribute(  ComponentConstants.COMPONENT_CONTEXT,  PageContext.REQUEST_SCOPE);
    107 
    108         if(  compContext  ==  null  )
    109             throw  new  JspException  (  "Error  -  tag.useProperty  :  component  context  is  not  defined.  Check  tag  syntax"  );
    110 
    111         Object  value  =  compContext.getAttribute(property);
    112         if(  value  ==  null  )
    113             throw  new  JspException  (  "Error  -  tag.useProperty  :  property  '"+  property  +  "'  not  found  in  context.  Check  tag  syntax"  );
    114 
    115         if(  scopeName  !=  null  )
    116             {
    117             scope  =  TagUtils.getScope(  scopeName,  PageContext.PAGE_SCOPE  );
    118             pageContext.setAttribute(id,  value,  scope);
    119             }
    120           else
    121             pageContext.setAttribute(id,  value);
    122 
    123           //  Continue  processing  this  page
    124         return  SKIP_BODY;
    125         }
    126 
    127 
    128 
    129 
    130         /**
    131           *  Clean  up  after  processing  this  enumeration.
    132           *
    133           *  @exception  JspException  if  a  JSP  exception  has  occurred
    134           */
    135     public  int  doEndTag()  throws  JspException
    136         {
    137         return  (EVAL_PAGE);
    138         }
    139 
    140         /**
    141           *  Release  all  allocated  resources.
    142           */
    143         public  void  release()  {
    144 
    145                 super.release();
    146                 property  =  null;
    147                 scopeName  =  null;
    148                 scope  =  PageContext.PAGE_SCOPE;
    149         }
    150 
    151 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
