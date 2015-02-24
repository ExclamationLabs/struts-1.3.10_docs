[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/definition/ComponentDefinitionsFactoryWrapper.html.md)


    1   /*
    2    * $Id: ComponentDefinitionsFactoryWrapper.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.util.HashMap;
    25  import java.util.Map;
    26  
    27  import javax.servlet.ServletContext;
    28  import javax.servlet.ServletRequest;
    29  
    30  import org.apache.struts.tiles.ComponentDefinition;
    31  import org.apache.struts.tiles.ComponentDefinitionsFactory;
    32  import org.apache.struts.tiles.DefinitionsFactory;
    33  import org.apache.struts.tiles.DefinitionsFactoryConfig;
    34  import org.apache.struts.tiles.DefinitionsFactoryException;
    35  import org.apache.struts.tiles.NoSuchDefinitionException;
    36  import org.apache.struts.util.RequestUtils;
    37  
    38  /**
    39   * Wrapper from new definition factory interface to old interface.
    40   * This class provides mapping from the old interface's life cycle to the new life cycle.
    41   * @since 20020708
    42   */
    43  public class ComponentDefinitionsFactoryWrapper implements DefinitionsFactory {
    44  
    45      /**
    46       * The underlying factory.
    47       */
    48      private ComponentDefinitionsFactory factory = null;
    49  
    50      /**
    51       * Factory configuration,
    52       */
    53      private DefinitionsFactoryConfig config = null;
    54  
    55      /**
    56       * Constructor.
    57       * Create new wrapper for specified factory.
    58       * @param factory The factory to create a wrapper for.
    59       */
    60      public ComponentDefinitionsFactoryWrapper(ComponentDefinitionsFactory factory) {
    61          this.factory = factory;
    62      }
    63  
    64      /**
    65       * Constructor.
    66       * Create new wrapper.
    67       * The config object passed to init method should reference a factory implementing
    68       * {@link ComponentDefinitionsFactory}.
    69       */
    70      public ComponentDefinitionsFactoryWrapper() {
    71          super();
    72      }
    73  
    74      /**
    75       * Get requested definition.
    76       * @param name Name of the definition.
    77       * @param request The request we are processing.
    78       * @param servletContext Our servlet context.
    79       * @return ComponentDefition
    80       */
    81      public ComponentDefinition getDefinition(
    82          String name,
    83          ServletRequest request,
    84          ServletContext servletContext)
    85          throws NoSuchDefinitionException, DefinitionsFactoryException {
    86  
    87          return factory.getDefinition(name, request, servletContext);
    88      }
    89  
    90      /**
    91       * Call underlying factory init method.
    92       * @param config DefinitionsFactoryConfig.
    93       * @param servletContext Our servlet context.
    94       */
    95      public void init(DefinitionsFactoryConfig config, ServletContext servletContext)
    96          throws DefinitionsFactoryException {
    97  
    98          this.config = config;
    99  
    100         // create factory and initialize it
    101         if (factory == null) {
    102             factory = createFactoryInstance(config.getFactoryClassname());
    103         }
    104 
    105         factory.initFactory(servletContext, createConfigMap(config));
    106     }
    107 
    108     /**
    109      * Do nothing because old life cycle has no equivalent.
    110      */
    111     public void destroy() {
    112         factory = null;
    113     }
    114 
    115     /**
    116      * Set underlying factory configuration.
    117      * @param config DefinitionsFactoryConfig to use.
    118      * @param servletContext Our servlet context.
    119      *
    120      */
    121     public void setConfig(
    122         DefinitionsFactoryConfig config,
    123         ServletContext servletContext)
    124         throws DefinitionsFactoryException {
    125 
    126         ComponentDefinitionsFactory newFactory =
    127             createFactoryInstance(config.getFactoryClassname());
    128 
    129         newFactory.initFactory(servletContext, createConfigMap(config));
    130         factory = newFactory;
    131     }
    132 
    133     /**
    134      * Get underlying factory configuration.
    135      * @return DefinitionsFactoryConfig.
    136      */
    137     public DefinitionsFactoryConfig getConfig() {
    138         return config;
    139     }
    140 
    141     /**
    142      * Get internal factory.
    143      * @return The internal ComponentDefitionsFactory.
    144      */
    145     public ComponentDefinitionsFactory getInternalFactory() {
    146         return factory;
    147     }
    148 
    149     /**
    150      * Create Definition factory from provided classname which must implement {@link ComponentDefinitionsFactory}.
    151      * Factory class must extend {@link DefinitionsFactory}.
    152      * @param classname Class name of the factory to create.
    153      * @return newly created factory.
    154      * @throws DefinitionsFactoryException If an error occur while initializing factory
    155      */
    156     protected ComponentDefinitionsFactory createFactoryInstance(String classname)
    157         throws DefinitionsFactoryException {
    158 
    159         try {
    160             Class factoryClass = RequestUtils.applicationClass(classname);
    161             Object factory = factoryClass.newInstance();
    162             return (ComponentDefinitionsFactory) factory;
    163 
    164         } catch (ClassCastException ex) { // Bad classname
    165             throw new DefinitionsFactoryException(
    166                 "Error - createDefinitionsFactory : Factory class '"
    167                     + classname
    168                     + " must implement 'DefinitionsFactory'.",
    169                 ex);
    170 
    171         } catch (ClassNotFoundException ex) { // Bad classname
    172             throw new DefinitionsFactoryException(
    173                 "Error - createDefinitionsFactory : Bad class name '"
    174                     + classname
    175                     + "'.",
    176                 ex);
    177 
    178         } catch (InstantiationException ex) { // Bad constructor or error
    179             throw new DefinitionsFactoryException(ex);
    180 
    181         } catch (IllegalAccessException ex) {
    182             throw new DefinitionsFactoryException(ex);
    183         }
    184 
    185     }
    186 
    187     /**
    188      * Return String representation.
    189      * Calls toString() on underlying factory.
    190      * @return String representation.
    191      */
    192     public String toString() {
    193         return getInternalFactory().toString();
    194     }
    195 
    196     /**
    197      * Create map of configuration attributes from configuration object.
    198      * Mapping is done between old names and new names.
    199      * @param config The DefinitionsFactoryConfig to use.
    200      * @return Map Map of name/value pairs.
    201      */
    202     public static Map createConfigMap(DefinitionsFactoryConfig config) {
    203         Map map = new HashMap(config.getAttributes());
    204         // Add property attributes using old names
    205         map.put(
    206             DefinitionsFactoryConfig.DEFINITIONS_CONFIG_PARAMETER_NAME,
    207             config.getDefinitionConfigFiles());
    208 
    209         map.put(
    210             DefinitionsFactoryConfig.PARSER_VALIDATE_PARAMETER_NAME,
    211             (config.getParserValidate() ? Boolean.TRUE.toString() : Boolean.FALSE.toString()));
    212 
    213         if (!"org.apache.struts.tiles.xmlDefinition.I18nFactorySet"
    214             .equals(config.getFactoryClassname())) {
    215 
    216             map.put(
    217                 DefinitionsFactoryConfig.FACTORY_CLASSNAME_PARAMETER_NAME,
    218                 config.getFactoryClassname());
    219         }
    220 
    221         return map;
    222     }
    223 
    224 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
