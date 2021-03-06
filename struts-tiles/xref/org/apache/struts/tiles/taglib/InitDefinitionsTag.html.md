[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/InitDefinitionsTag.html.md)


    1   /*
    2    * $Id: InitDefinitionsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import javax.servlet.jsp.JspException;
    26  import javax.servlet.jsp.tagext.TagSupport;
    27  
    28  import org.apache.struts.tiles.DefinitionsFactory;
    29  import org.apache.struts.tiles.DefinitionsFactoryConfig;
    30  import org.apache.struts.tiles.DefinitionsFactoryException;
    31  import org.apache.struts.tiles.TilesUtil;
    32  
    33    /**
    34     * Init definitions factory.
    35     */
    36  public class InitDefinitionsTag extends TagSupport
    37      implements ComponentConstants {
    38  
    39  
    40    private String filename = null;
    41    private String classname = null;
    42  
    43    /**
    44     * Default constructor.
    45     */
    46    public InitDefinitionsTag() {
    47      super();
    48    }
    49  
    50      /**
    51       * Release all allocated resources.
    52       */
    53      public void release() {
    54  
    55          super.release();
    56          filename = null;
    57      }
    58  
    59      /**
    60       * Set file.
    61       */
    62    public void setFile(String name){
    63      this.filename = name;
    64    }
    65  
    66      /**
    67       * Set classname.
    68       */
    69    public void setClassname(String classname){
    70      this.classname = classname;
    71    }
    72  
    73      /**
    74       * Do start tag.
    75       */
    76    public int doStartTag() throws JspException
    77    {
    78    DefinitionsFactory factory =
    79        TilesUtil.getDefinitionsFactory(pageContext.getRequest(),
    80            pageContext.getServletContext());
    81    if(factory != null )
    82      return SKIP_BODY;
    83  
    84    DefinitionsFactoryConfig factoryConfig = new DefinitionsFactoryConfig();
    85    factoryConfig.setFactoryClassname( classname );
    86    factoryConfig.setDefinitionConfigFiles( filename );
    87  
    88    try
    89      {
    90      factory = TilesUtil.createDefinitionsFactory(
    91          pageContext.getServletContext(), factoryConfig);
    92      }
    93     catch( DefinitionsFactoryException ex )
    94        {
    95        ex.printStackTrace();
    96        throw new JspException( ex );
    97        }
    98    return SKIP_BODY;
    99    }
    100 
    101     /**
    102      * Do end tag.
    103      */
    104   public int doEndTag() throws JspException {
    105     return EVAL_PAGE;
    106   }
    107 
    108 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
