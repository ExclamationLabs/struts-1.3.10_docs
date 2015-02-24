[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/xmlDefinition/XmlDefinition.html.md)


    1   /*
    2    * $Id: XmlDefinition.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles.xmlDefinition;
    23  
    24  import java.util.Iterator;
    25  
    26  import org.apache.commons.logging.Log;
    27  import org.apache.commons.logging.LogFactory;
    28  import org.apache.struts.tiles.ComponentDefinition;
    29  import org.apache.struts.tiles.NoSuchDefinitionException;
    30  
    31  /**
    32    *A definition read from an XML definitions file.
    33    */
    34  public class XmlDefinition extends ComponentDefinition
    35  {
    36    /**
    37     * Extends attribute value.
    38     */
    39    private String inherit;
    40  
    41      /** Commons Logging instance. */
    42     protected static Log log = LogFactory.getLog(XmlDefinition.class);
    43  
    44    /**
    45     * Used for resolving inheritance.
    46     */
    47    private boolean isVisited=false;
    48  
    49  
    50       /**
    51        * Constructor.
    52        */
    53     public XmlDefinition()
    54     {
    55     super();
    56     //if(debug)
    57       //System.out.println( "create definition" );
    58     }
    59  
    60    /**
    61     * Add an attribute to this component.
    62     *
    63     * @param attribute Attribute to add.
    64     */
    65    public void addAttribute( XmlAttribute attribute)
    66      {
    67      putAttribute( attribute.getName(), attribute.getValue() );
    68      }
    69  
    70    /**
    71     * Set extends.
    72     *
    73     * @param name Name of the extended definition.
    74     */
    75    public void setExtends(String name)
    76      {
    77      inherit = name;
    78      }
    79  
    80    /**
    81     * Get extends.
    82     *
    83     * @return Name of the extended definition.
    84     */
    85    public String getExtends()
    86      {
    87      return inherit;
    88      }
    89  
    90    /**
    91     * Get extends flag.
    92     *
    93     */
    94    public boolean isExtending( )
    95      {
    96      return inherit!=null;
    97      }
    98  
    99    /**
    100    * Set isVisited.
    101    *
    102    */
    103   public void setIsVisited( boolean isVisited )
    104     {
    105     this.isVisited = isVisited;
    106     }
    107 
    108     /**
    109      * Resolve inheritance.
    110      * First, resolve parent's inheritance, then set path to the parent's path.
    111      * Also copy attributes setted in parent, and not set in child
    112      * If instance doesn't extend anything, do nothing.
    113      * @throws NoSuchDefinitionException If an inheritance can not be solved.
    114      */
    115   public void resolveInheritance( XmlDefinitionsSet definitionsSet )
    116     throws NoSuchDefinitionException
    117     {
    118       // Already done, or not needed ?
    119     if( isVisited || !isExtending() )
    120       return;
    121 
    122     if(log.isDebugEnabled())
    123       log.debug( "Resolve definition for child name='" + getName()
    124               + "' extends='" + getExtends() + "'.");
    125 
    126       // Set as visited to avoid endless recurisvity.
    127     setIsVisited( true );
    128 
    129       // Resolve parent before itself.
    130     XmlDefinition parent = definitionsSet.getDefinition( getExtends() );
    131     if( parent == null )
    132       { // error
    133       String msg = "Error while resolving definition inheritance: child '"
    134                            + getName() +    "' can't find its ancestor '"
    135                            + getExtends() +
    136                            "'. Please check your description file.";
    137       log.error( msg );
    138         // to do : find better exception
    139       throw new NoSuchDefinitionException( msg );
    140       }
    141 
    142     parent.resolveInheritance( definitionsSet );
    143 
    144       // Iterate on each parent's attribute and add it if not defined in child.
    145     Iterator parentAttributes = parent.getAttributes().keySet().iterator();
    146     while( parentAttributes.hasNext() )
    147       {
    148       String name = (String)parentAttributes.next();
    149       if( !getAttributes().containsKey(name) )
    150         putAttribute( name, parent.getAttribute(name) );
    151       }
    152       // Set path and role if not setted
    153     if( path == null )
    154       setPath( parent.getPath() );
    155     if( role == null )
    156       setRole( parent.getRole() );
    157     if( controller==null )
    158       {
    159       setController( parent.getController());
    160       setControllerType( parent.getControllerType());
    161       }
    162     }
    163 
    164   /**
    165    * Overload this definition with passed child.
    166    * All attributes from child are copied to this definition. Previous
    167    * attributes with same name are disguarded.
    168    * Special attribute 'path','role' and 'extends' are overloaded if defined
    169    * in child.
    170    * @param child Child used to overload this definition.
    171    */
    172   public void overload( XmlDefinition child )
    173     {
    174     if( child.getPath() != null )
    175       {
    176       path = child.getPath();
    177       }
    178     if( child.getExtends() != null )
    179       {
    180       inherit = child.getExtends();
    181       }
    182     if( child.getRole() != null )
    183       {
    184       role = child.getRole();
    185       }
    186     if( child.getController()!=null )
    187       {
    188       controller = child.getController();
    189       controllerType =  child.getControllerType();
    190       }
    191       // put all child attributes in parent.
    192     attributes.putAll( child.getAttributes());
    193     }
    194 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
