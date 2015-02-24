[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/DefinitionsUtil.html.md)


    1   /*
    2    * $Id: DefinitionsUtil.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles;
    23  
    24  import java.lang.reflect.InvocationTargetException;
    25  import java.util.Enumeration;
    26  import java.util.HashMap;
    27  import java.util.Map;
    28  
    29  import javax.servlet.ServletConfig;
    30  import javax.servlet.ServletContext;
    31  import javax.servlet.ServletRequest;
    32  
    33  import org.apache.commons.logging.Log;
    34  import org.apache.commons.logging.LogFactory;
    35  import org.apache.struts.tiles.taglib.ComponentConstants;
    36  
    37  /**
    38   * Utilities class for definitions factory.
    39   * Also define userDebugLevel property (TODO to be moved from this class ?).
    40   * @deprecated Use {@link TilesUtil#createDefinitionsFactory(ServletContext, DefinitionsFactoryConfig)}
    41   */
    42  public class DefinitionsUtil extends TilesUtil implements ComponentConstants {
    43  
    44      /**
    45       * Commons Logging instance.
    46       */
    47      protected static Log log = LogFactory.getLog(DefinitionsUtil.class);
    48  
    49      /**
    50       * Global user defined debug level.
    51       * @deprecated This will be removed in a release after Struts 1.2.
    52       */
    53      public static int userDebugLevel = 0;
    54  
    55      /**
    56       * User Debug level.
    57       * @deprecated This will be removed in a release after Struts 1.2.
    58       */
    59      public static final int NO_DEBUG = 0;
    60  
    61      /**
    62       * Name of init property carrying debug level.
    63       */
    64      public static final String DEFINITIONS_CONFIG_USER_DEBUG_LEVEL =
    65          "definitions-debug";
    66  
    67      /**
    68       * Name of init property carrying factory class name.
    69       */
    70      public static final String DEFINITIONS_FACTORY_CLASSNAME =
    71          "definitions-factory-class";
    72  
    73      /**
    74       * Constant name used to store factory in context.
    75       */
    76      public static final String DEFINITIONS_FACTORY =
    77          "org.apache.struts.tiles.DEFINITIONS_FACTORY";
    78  
    79      /**
    80       * Constant name used to store definition in jsp context.
    81       * Used to pass definition from a Struts action to servlet forward.
    82       */
    83      public static final String ACTION_DEFINITION =
    84          "org.apache.struts.tiles.ACTION_DEFINITION";
    85  
    86      /**
    87       * Create Definition factory.
    88       * If a factory class name is provided, a factory of this class is created. Otherwise,
    89       * default factory is created.
    90       * @param classname Class name of the factory to create.
    91       * @param servletContext Servlet Context passed to newly created factory.
    92       * @param properties Map of name/property used to initialize factory configuration object.
    93       * @return newly created factory.
    94       * @throws DefinitionsFactoryException If an error occur while initializing factory
    95       * @deprecated Use createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)
    96       */
    97      public static DefinitionsFactory createDefinitionsFactory(
    98          ServletContext servletContext,
    99          Map properties,
    100         String classname)
    101         throws DefinitionsFactoryException {
    102 
    103         // Create config object
    104         DefinitionsFactoryConfig factoryConfig = new DefinitionsFactoryConfig();
    105         // populate it from map.
    106         try {
    107             factoryConfig.populate(properties);
    108 
    109         } catch (Exception ex) {
    110             throw new DefinitionsFactoryException(
    111                 "Error - createDefinitionsFactory : Can't populate config object from properties map",
    112                 ex);
    113         }
    114 
    115         // Add classname
    116         if (classname != null)
    117             factoryConfig.setFactoryClassname(classname);
    118 
    119         // Create factory using config object
    120         return createDefinitionsFactory(servletContext, factoryConfig);
    121     }
    122 
    123     /**
    124      * Create default Definition factory.
    125      * @param servletContext Servlet Context passed to newly created factory.
    126      * @param properties Map of name/property used to initialize factory configuration object.
    127      * @return newly created factory of type ConfigurableDefinitionsFactory.
    128      * @throws DefinitionsFactoryException If an error occur while initializing factory
    129      */
    130     public static DefinitionsFactory createDefinitionsFactory(
    131         ServletContext servletContext,
    132         Map properties)
    133         throws DefinitionsFactoryException {
    134 
    135         return createDefinitionsFactory(servletContext, properties, null);
    136     }
    137 
    138     /**
    139      * Create Definition factory.
    140      * Create configuration object from servlet web.xml file, then create
    141      * ConfigurableDefinitionsFactory and initialized it with object.
    142      * <p>
    143      * Convenience method. Calls createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)
    144      *
    145      * @param servletContext Servlet Context passed to newly created factory.
    146      * @param servletConfig Servlet config containing parameters to be passed to factory configuration object.
    147      * @return newly created factory of type ConfigurableDefinitionsFactory.
    148      * @throws DefinitionsFactoryException If an error occur while initializing factory
    149      */
    150     public static DefinitionsFactory createDefinitionsFactory(
    151         ServletContext servletContext,
    152         ServletConfig servletConfig)
    153         throws DefinitionsFactoryException {
    154 
    155         DefinitionsFactoryConfig factoryConfig = readFactoryConfig(servletConfig);
    156 
    157         return createDefinitionsFactory(servletContext, factoryConfig);
    158     }
    159 
    160     /**
    161      * Create Definition factory.
    162      * Create configuration object from servlet web.xml file, then create
    163      * ConfigurableDefinitionsFactory and initialized it with object.
    164      * <p>
    165      * If checkIfExist is true, start by checking if factory already exist. If yes,
    166      * return it. If no, create a new one.
    167      * <p>
    168      * If checkIfExist is false, factory is always created.
    169      * <p>
    170      * Convenience method. Calls createDefinitionsFactory(ServletContext servletContext, DefinitionsFactoryConfig factoryConfig)
    171      *
    172      * @param servletContext Servlet Context passed to newly created factory.
    173      * @param servletConfig Servlet config containing parameters to be passed to factory configuration object.
    174      * @param checkIfExist Check if factory already exist. If true and factory exist, return it.
    175      * If true and factory doesn't exist, create it. If false, create it in all cases.
    176      * @return newly created factory of type ConfigurableDefinitionsFactory.
    177      * @throws DefinitionsFactoryException If an error occur while initializing factory
    178      */
    179     public static DefinitionsFactory createDefinitionsFactory(
    180         ServletContext servletContext,
    181         ServletConfig servletConfig,
    182         boolean checkIfExist)
    183         throws DefinitionsFactoryException {
    184 
    185         if (checkIfExist) {
    186             // Check if already exist in context
    187             DefinitionsFactory factory = getDefinitionsFactory(servletContext);
    188             if (factory != null)
    189                 return factory;
    190         }
    191 
    192         return createDefinitionsFactory(servletContext, servletConfig);
    193     }
    194 
    195     /**
    196      * Get definition factory from appropriate servlet context.
    197      * @return Definitions factory or null if not found.
    198      * @deprecated Use {@link TilesUtil#getDefinitionsFactory(ServletRequest, ServletContext)}
    199      * @since 20020708
    200      */
    201     public static DefinitionsFactory getDefinitionsFactory(ServletContext servletContext) {
    202         return (DefinitionsFactory) servletContext.getAttribute(DEFINITIONS_FACTORY);
    203     }
    204 
    205     /**
    206      * Get Definition stored in jsp context by an action.
    207      * @return ComponentDefinition or null if not found.
    208      */
    209     public static ComponentDefinition getActionDefinition(ServletRequest request) {
    210         return (ComponentDefinition) request.getAttribute(ACTION_DEFINITION);
    211     }
    212 
    213     /**
    214      * Store definition in jsp context.
    215      * Mainly used by Struts to pass a definition defined in an Action to the forward.
    216      */
    217     public static void setActionDefinition(
    218         ServletRequest request,
    219         ComponentDefinition definition) {
    220 
    221         request.setAttribute(ACTION_DEFINITION, definition);
    222     }
    223 
    224     /**
    225      * Remove Definition stored in jsp context.
    226      * Mainly used by Struts to pass a definition defined in an Action to the forward.
    227      */
    228     public static void removeActionDefinition(
    229         ServletRequest request,
    230         ComponentDefinition definition) {
    231 
    232         request.removeAttribute(ACTION_DEFINITION);
    233     }
    234 
    235     /**
    236      * Populate Definition Factory Config from web.xml properties.
    237      * @param factoryConfig Definition Factory Config to populate.
    238      * @param servletConfig Current servlet config containing web.xml properties.
    239      * @exception IllegalAccessException if the caller does not have
    240      *  access to the property accessor method
    241      * @exception java.lang.reflect.InvocationTargetException if the property accessor method
    242      *  throws an exception
    243      * @see org.apache.commons.beanutils.BeanUtils
    244      * @since tiles 20020708
    245      */
    246     public static void populateDefinitionsFactoryConfig(
    247         DefinitionsFactoryConfig factoryConfig,
    248         ServletConfig servletConfig)
    249         throws IllegalAccessException, InvocationTargetException {
    250 
    251         Map properties = new DefinitionsUtil.ServletPropertiesMap(servletConfig);
    252         factoryConfig.populate(properties);
    253     }
    254 
    255     /**
    256      * Create FactoryConfig and initialize it from web.xml.
    257      *
    258      * @param servletConfig ServletConfig for the module with which
    259      *  this plug in is associated
    260      * @exception DefinitionsFactoryException if this <code>PlugIn</code> cannot
    261      *  be successfully initialized
    262      */
    263     protected static DefinitionsFactoryConfig readFactoryConfig(ServletConfig servletConfig)
    264         throws DefinitionsFactoryException {
    265 
    266         // Create tiles definitions config object
    267         DefinitionsFactoryConfig factoryConfig = new DefinitionsFactoryConfig();
    268 
    269         // Get init parameters from web.xml files
    270         try {
    271             DefinitionsUtil.populateDefinitionsFactoryConfig(
    272                 factoryConfig,
    273                 servletConfig);
    274 
    275         } catch (Exception ex) {
    276             ex.printStackTrace();
    277             throw new DefinitionsFactoryException(
    278                 "Can't populate DefinitionsFactoryConfig class from 'web.xml'.",
    279                 ex);
    280         }
    281 
    282         return factoryConfig;
    283     }
    284 
    285     /**
    286      * Inner class.
    287      * Wrapper for ServletContext init parameters.
    288      * Object of this class is an hashmap containing parameters and values
    289      * defined in the servlet config file (web.xml).
    290      */
    291     static class ServletPropertiesMap extends HashMap {
    292         /**
    293          * Constructor.
    294          */
    295         ServletPropertiesMap(ServletConfig config) {
    296             // This implementation is very simple.
    297             // It is possible to avoid creation of a new structure, but this need
    298             // imply writing all Map interface.
    299             Enumeration e = config.getInitParameterNames();
    300             while (e.hasMoreElements()) {
    301                 String key = (String) e.nextElement();
    302                 put(key, config.getInitParameter(key));
    303             }
    304         }
    305     } // end inner class
    306 
    307 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
