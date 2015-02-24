[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/xmlDefinition/FactorySet.html.md)


    1   /*
    2    * $Id: FactorySet.java 471754 2006-11-06 14:55:09Z husted $
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
    28  import javax.servlet.ServletContext;
    29  import javax.servlet.ServletRequest;
    30  
    31  import org.apache.struts.tiles.ComponentDefinition;
    32  import org.apache.struts.tiles.ComponentDefinitionsFactory;
    33  import org.apache.struts.tiles.DefinitionsFactoryException;
    34  import org.apache.struts.tiles.FactoryNotFoundException;
    35  import org.apache.struts.tiles.NoSuchDefinitionException;
    36  
    37  /**
    38   * Component Definitions factory.
    39   * This factory contains several factories identified by a key. The
    40   * getDefinition() method first looks for the factory key, retrieves or creates this
    41   * factory and then calls its getDefinition().
    42   */
    43  public abstract class FactorySet implements ComponentDefinitionsFactory
    44  {
    45  
    46      /** Loaded factories */
    47    protected Map factories=null;
    48  
    49    /**
    50     * Extract key that will be used to get the sub factory.
    51     * @param name Name of requested definition.
    52     * @param request Current servlet request.
    53     * @param servletContext Current servlet context.
    54     * @return Object.
    55     */
    56    abstract protected Object getDefinitionsFactoryKey(String name, ServletRequest request, ServletContext servletContext);
    57  
    58    /**
    59     * Get default factory.
    60     * @return Default factory.
    61     */
    62    abstract protected DefinitionsFactory getDefaultFactory();
    63  
    64    /**
    65     * Get a factory by its key.
    66     * If key is <code>null</code>, return defaultFactory.
    67     * Search in loaded factories. If not found, create factory and store return value in
    68     * loaded factories.
    69     * @param key Key of requested definition.
    70     * @param request Current servlet request.
    71     * @param servletContext Current servlet context.
    72     * @throws DefinitionsFactoryException If an error occur while creating factory.
    73     */
    74    protected DefinitionsFactory getFactory(Object key, ServletRequest request, ServletContext servletContext)
    75      throws DefinitionsFactoryException
    76    {
    77    if(key == null )
    78      return getDefaultFactory();
    79  
    80    Object factory = factories.get( key );
    81    if( factory == null )
    82      {
    83        // synchronize creation to avoid double creation by separate threads.
    84        // Also, check if factory hasn't been created while waiting for synchronized
    85        // section.
    86      synchronized(factories)
    87        {
    88        factory = factories.get( key );
    89        if( factory == null )
    90          {
    91          factory = createFactory( key, request, servletContext);
    92          factories.put( key, factory );
    93          } // end if
    94        } // end synchronized
    95      } // end if
    96    return (DefinitionsFactory)factory;
    97    }
    98  
    99    /**
    100    * Get a definition by its name.
    101    *
    102    * @param name Name of requested definition.
    103    * @param request Current servlet request.
    104    * @param servletContext Current servlet context.
    105    * @throws NoSuchDefinitionException No definition found for specified name
    106    * @throws DefinitionsFactoryException General exception
    107    */
    108   public ComponentDefinition getDefinition(String name, ServletRequest request, ServletContext servletContext)
    109     throws NoSuchDefinitionException, DefinitionsFactoryException
    110   {
    111   if( factories == null )
    112     throw new FactoryNotFoundException( "No definitions factory defined" );
    113 
    114   Object key = getDefinitionsFactoryKey( name, request, servletContext);
    115   DefinitionsFactory factory = getFactory( key, request, servletContext);
    116   return factory.getDefinition( name, request, servletContext );
    117   }
    118 
    119   /**
    120    * Create a factory for specified key.
    121    * This method is called by getFactory() when the requested factory doesn't already exist.
    122    * Must return a factory, or a default one.
    123    * Real implementation needs to provide this method.
    124    * @param key Key of requested definition.
    125    * @param request Current servlet request.
    126    * @param servletContext Current servlet context
    127    * @throws DefinitionsFactoryException If an error occur while creating factory.
    128    */
    129   abstract protected DefinitionsFactory createFactory(Object key, ServletRequest request, ServletContext servletContext)
    130           throws DefinitionsFactoryException;
    131 
    132   /**
    133    * Init factory set.
    134    * @param servletContext Current servlet context
    135    * @param properties properties used to initialized factory set;
    136    */
    137   abstract public void initFactory(ServletContext servletContext, Map properties)
    138     throws DefinitionsFactoryException;
    139 
    140   /**
    141    * Constructor.
    142    */
    143   public FactorySet()
    144   {
    145   factories = new HashMap();
    146   }
    147 
    148     /**
    149      * Return String representation.
    150      * @return String representation.
    151      */
    152   public String toString()
    153     {
    154     Iterator i = factories.values().iterator();
    155     StringBuffer buff = new StringBuffer( "all FactorySet's factory : \n" );
    156     while( i.hasNext() )
    157       {
    158       buff.append( i.next().toString() ).append("\n");
    159       }
    160     return buff.toString();
    161     }
    162 
    163 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
