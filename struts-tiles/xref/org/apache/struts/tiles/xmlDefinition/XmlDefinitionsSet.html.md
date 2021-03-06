[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/xmlDefinition/XmlDefinitionsSet.html.md)


    1   /*
    2    * $Id: XmlDefinitionsSet.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.util.HashMap;
    25  import java.util.Iterator;
    26  import java.util.Map;
    27  
    28  import org.apache.struts.tiles.NoSuchDefinitionException;
    29  
    30  /**
    31   * A set of definitions read from XML definitions file.
    32  */
    33  public class XmlDefinitionsSet
    34  {
    35      /** Defined definitions. */
    36    protected Map definitions;
    37  
    38       /**
    39        * Constructor.
    40        */
    41    public XmlDefinitionsSet()
    42     {
    43     definitions = new HashMap();
    44     }
    45  
    46    /**
    47     * Put definition in set.
    48     * @param definition Definition to add.
    49     */
    50    public void putDefinition(XmlDefinition definition)
    51    {
    52    definitions.put( definition.getName(), definition );
    53    }
    54  
    55    /**
    56     * Get requested definition.
    57     * @param name Definition name.
    58     */
    59    public XmlDefinition getDefinition(String name)
    60    {
    61    return (XmlDefinition)definitions.get( name );
    62    }
    63  
    64    /**
    65     * Get definitions map.
    66     */
    67    public Map getDefinitions()
    68    {
    69    return definitions;
    70    }
    71  
    72    /**
    73     * Resolve extended instances.
    74     */
    75    public void resolveInheritances() throws NoSuchDefinitionException
    76      {
    77        // Walk through all definitions and resolve individual inheritance
    78      Iterator i = definitions.values().iterator();
    79      while( i.hasNext() )
    80        {
    81        XmlDefinition definition = (XmlDefinition)i.next();
    82        definition.resolveInheritance( this );
    83        }  // end loop
    84      }
    85  
    86    /**
    87     * Add definitions from specified child definitions set.
    88     * For each definition in child, look if it already exists in this set.
    89     * If not, add it, if yes, overload parent's definition with child definition.
    90     * @param child Definition used to overload this object.
    91     */
    92    public void extend( XmlDefinitionsSet child )
    93      {
    94      if(child==null)
    95        return;
    96      Iterator i = child.getDefinitions().values().iterator();
    97      while( i.hasNext() )
    98        {
    99        XmlDefinition childInstance = (XmlDefinition)i.next();
    100       XmlDefinition parentInstance = getDefinition(childInstance.getName() );
    101       if( parentInstance != null )
    102         {
    103         parentInstance.overload( childInstance );
    104         }
    105        else
    106         putDefinition( childInstance );
    107       } // end loop
    108     }
    109     /**
    110      * Get String representation.
    111      */
    112   public String toString()
    113     {
    114     return "definitions=" + definitions.toString() ;
    115     }
    116 
    117 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
