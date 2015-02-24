[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/definition/ReloadableDefinitionsFactory.html.md)


    1   /*
    2    * $Id: ReloadableDefinitionsFactory.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles.definition;
    23  
    24  import java.util.Enumeration;
    25  import java.util.HashMap;
    26  import java.util.Map;
    27  
    28  import javax.servlet.ServletConfig;
    29  import javax.servlet.ServletContext;
    30  import javax.servlet.ServletRequest;
    31  import javax.servlet.http.HttpServletRequest;
    32  
    33  import org.apache.struts.tiles.ComponentDefinition;
    34  import org.apache.struts.tiles.ComponentDefinitionsFactory;
    35  import org.apache.struts.tiles.DefinitionsFactoryException;
    36  import org.apache.struts.tiles.FactoryNotFoundException;
    37  import org.apache.struts.tiles.xmlDefinition.I18nFactorySet;
    38  import org.apache.struts.util.RequestUtils;
    39  
    40  /**
    41   * A reloadable factory.
    42   * This factory is the main entrance to any factory implementation. It takes in
    43   * charge real implementation instance, and allows reloading by creating a new
    44   * instance.
    45   *
    46   * @since Struts 1.1
    47   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    48   */
    49  public class ReloadableDefinitionsFactory implements ComponentDefinitionsFactory {
    50  
    51      /**
    52       * The real factory instance.
    53       */
    54      protected ComponentDefinitionsFactory factory = null;
    55  
    56      /**
    57       * Initialization parameters.
    58       */
    59      protected Map properties = null;
    60  
    61      /**
    62       * Name of init property carrying factory class name.
    63       */
    64      public static final String DEFINITIONS_FACTORY_CLASSNAME =
    65          "definitions-factory-class";
    66  
    67      /**
    68       * Constructor.
    69       * Create a factory according to servlet settings.
    70       * @param servletContext Our servlet context.
    71       * @param servletConfig Our servlet config.
    72       * @throws DefinitionsFactoryException If factory creation fail.
    73       */
    74      public ReloadableDefinitionsFactory(
    75          ServletContext servletContext,
    76          ServletConfig servletConfig)
    77          throws DefinitionsFactoryException {
    78  
    79          properties = new ServletPropertiesMap(servletConfig);
    80          factory = createFactory(servletContext, properties);
    81      }
    82  
    83      /**
    84       * Constructor.
    85       * Create a factory according to servlet settings.
    86       * @param servletContext Our servlet context.
    87       * @param properties Map containing all properties.
    88       * @throws DefinitionsFactoryException If factory creation fail.
    89       */
    90      public ReloadableDefinitionsFactory(
    91          ServletContext servletContext,
    92          Map properties)
    93          throws DefinitionsFactoryException {
    94  
    95          this.properties = properties;
    96          factory = createFactory(servletContext, properties);
    97      }
    98  
    99      /**
    100     * Create Definition factory from provided classname.
    101     * If a factory class name is provided, a factory of this class is created. Otherwise,
    102     * a default factory is created.
    103     * Factory must have a constructor taking ServletContext and Map as parameter.
    104     * @param classname Class name of the factory to create.
    105     * @param servletContext Servlet Context passed to newly created factory.
    106     * @param properties Map of name/property passed to newly created factory.
    107     * @return newly created factory.
    108     * @throws DefinitionsFactoryException If an error occur while initializing factory
    109     */
    110     public ComponentDefinitionsFactory createFactoryFromClassname(
    111         ServletContext servletContext,
    112         Map properties,
    113         String classname)
    114         throws DefinitionsFactoryException {
    115 
    116         if (classname == null) {
    117             return createFactory(servletContext, properties);
    118         }
    119 
    120         // Try to create from classname
    121         try {
    122             Class factoryClass = RequestUtils.applicationClass(classname);
    123             ComponentDefinitionsFactory factory =
    124                 (ComponentDefinitionsFactory) factoryClass.newInstance();
    125             factory.initFactory(servletContext, properties);
    126             return factory;
    127 
    128         } catch (ClassCastException ex) { // Bad classname
    129             throw new DefinitionsFactoryException(
    130                 "Error - createDefinitionsFactory : Factory class '"
    131                     + classname
    132                     + " must implements 'ComponentDefinitionsFactory'.",
    133                 ex);
    134 
    135         } catch (ClassNotFoundException ex) { // Bad classname
    136             throw new DefinitionsFactoryException(
    137                 "Error - createDefinitionsFactory : Bad class name '"
    138                     + classname
    139                     + "'.",
    140                 ex);
    141 
    142         } catch (InstantiationException ex) { // Bad constructor or error
    143             throw new DefinitionsFactoryException(ex);
    144 
    145         } catch (IllegalAccessException ex) {
    146             throw new DefinitionsFactoryException(ex);
    147         }
    148 
    149     }
    150 
    151     /**
    152     * Create default Definition factory.
    153     * Factory must have a constructor taking ServletContext and Map as parameter.
    154     * In this implementation, default factory is of class I18nFactorySet
    155     * @param servletContext Servlet Context passed to newly created factory.
    156     * @param properties Map of name/property passed to newly created factory.
    157     * @return newly created factory.
    158     * @throws DefinitionsFactoryException If an error occur while initializing factory
    159     */
    160     public ComponentDefinitionsFactory createDefaultFactory(
    161         ServletContext servletContext,
    162         Map properties)
    163         throws DefinitionsFactoryException {
    164 
    165         ComponentDefinitionsFactory factory =
    166             new I18nFactorySet(servletContext, properties);
    167 
    168         return factory;
    169     }
    170 
    171     /**
    172     * Create Definition factory.
    173     * Convenience method. ServletConfig is wrapped into a Map allowing retrieval
    174     * of init parameters. Factory classname is also retrieved, as well as debug level.
    175     * Finally, approriate createDefinitionsFactory() is called.
    176     * @param servletContext Servlet Context passed to newly created factory.
    177     * @param properties Map containing all properties.
    178     */
    179     public ComponentDefinitionsFactory createFactory(
    180         ServletContext servletContext,
    181         Map properties)
    182         throws DefinitionsFactoryException {
    183 
    184         String classname = (String) properties.get(DEFINITIONS_FACTORY_CLASSNAME);
    185 
    186         if (classname != null) {
    187             return createFactoryFromClassname(servletContext, properties, classname);
    188         }
    189 
    190         return new I18nFactorySet(servletContext, properties);
    191     }
    192 
    193     /**
    194      * Get a definition by its name.
    195      * Call appropriate method on underlying factory instance.
    196      * Throw appropriate exception if definition or definition factory is not found.
    197      * @param definitionName Name of requested definition.
    198      * @param request Current servlet request.
    199      * @param servletContext Current servlet context.
    200      * @throws FactoryNotFoundException Can't find definition factory.
    201      * @throws DefinitionsFactoryException General error in factory while getting definition.
    202      */
    203     public ComponentDefinition getDefinition(
    204         String definitionName,
    205         ServletRequest request,
    206         ServletContext servletContext)
    207         throws FactoryNotFoundException, DefinitionsFactoryException {
    208 
    209         return factory.getDefinition(
    210             definitionName,
    211             (HttpServletRequest) request,
    212             servletContext);
    213     }
    214 
    215     /**
    216      * Reload underlying factory.
    217      * Reload is done by creating a new factory instance, and replacing the old instance
    218      * with the new one.
    219      * @param servletContext Current servlet context.
    220      * @throws DefinitionsFactoryException If factory creation fails.
    221      */
    222     public void reload(ServletContext servletContext)
    223         throws DefinitionsFactoryException {
    224 
    225         ComponentDefinitionsFactory newInstance =
    226             createFactory(servletContext, properties);
    227 
    228         factory = newInstance;
    229     }
    230 
    231     /**
    232      * Get underlying factory instance.
    233      * @return ComponentDefinitionsFactory
    234      */
    235     public ComponentDefinitionsFactory getFactory() {
    236         return factory;
    237     }
    238 
    239     /**
    240       * Init factory.
    241       * This method is required by interface ComponentDefinitionsFactory. It is
    242       * not used in this implementation, as it manages itself the underlying creation
    243       * and initialization.
    244       * @param servletContext Servlet Context passed to newly created factory.
    245       * @param properties Map of name/property passed to newly created factory.
    246       * Map can contain more properties than requested.
    247       * @throws DefinitionsFactoryException An error occur during initialization.
    248     */
    249     public void initFactory(ServletContext servletContext, Map properties)
    250         throws DefinitionsFactoryException {
    251         // do nothing
    252     }
    253 
    254     /**
    255      * Return String representation.
    256      * @return String representation.
    257      */
    258     public String toString() {
    259         return factory.toString();
    260     }
    261 
    262     /**
    263      * Inner class.
    264      * Wrapper for ServletContext init parameters.
    265      * Object of this class is an HashMap containing parameters and values
    266      * defined in the servlet config file (web.xml).
    267      */
    268     class ServletPropertiesMap extends HashMap {
    269         /**
    270          * Constructor.
    271          */
    272         ServletPropertiesMap(ServletConfig config) {
    273             // This implementation is very simple.
    274             // It is possible to avoid creation of a new structure, but this would
    275             // imply writing all of the Map interface.
    276             Enumeration e = config.getInitParameterNames();
    277             while (e.hasMoreElements()) {
    278                 String key = (String) e.nextElement();
    279                 put(key, config.getInitParameter(key));
    280             }
    281         }
    282     } // end inner class
    283 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
