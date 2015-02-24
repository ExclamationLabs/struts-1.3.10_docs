[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/DefinitionsFactoryConfig.html.md)


    1   /*
    2    * $Id: DefinitionsFactoryConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.io.Serializable;
    25  import java.lang.reflect.InvocationTargetException;
    26  import java.util.HashMap;
    27  import java.util.Iterator;
    28  import java.util.Map;
    29  import java.util.Set;
    30  
    31  import org.apache.commons.beanutils.BeanUtils;
    32  
    33  /**
    34   * A TilesFactoryConfig object hold configuration attributes for a tile
    35   * definition factory.
    36   *
    37   * @since Struts 1.1
    38   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    39   */
    40  public class DefinitionsFactoryConfig implements Serializable {
    41  
    42      /**
    43       * Fully qualified classname of the factory to create.
    44       * If no classname is set, a default factory is created
    45       * (of class "org.apache.struts.tiles.xmlDefinition.I18nFactorySet").
    46       */
    47      protected String factoryClassname =
    48          "org.apache.struts.tiles.xmlDefinition.I18nFactorySet";
    49  
    50      /**
    51       * Specifies whether the parser will validate configuration files.
    52       * Default value is true.
    53       */
    54      protected boolean parserValidate = true;
    55  
    56      /**
    57       * Definition configuration file specified by user.
    58       */
    59      protected String definitionConfigFiles = null;
    60  
    61      /**
    62       * Specifies whether the factory is "module-aware".
    63       */
    64      protected boolean moduleAware = true;
    65  
    66      /**
    67       * The name associated to this factory.
    68       * <br>
    69       * With Struts 1.1, this name is the module name to which this factory
    70       * belong. It is set by the system.
    71       * <br>
    72       * In prior versions, this property is not used.
    73       */
    74      protected String factoryName;
    75  
    76      /**
    77       * Alternate name for parser debug details properties in configuration file.
    78       * @deprecated This will be removed in a release after Struts 1.2.
    79       */
    80      public static final String PARSER_DETAILS_PARAMETER_NAME =
    81          "definitions-parser-details";
    82  
    83      /**
    84       * Alternate name for parser validate properties in configuration file.
    85       */
    86      public static final String PARSER_VALIDATE_PARAMETER_NAME =
    87          "definitions-parser-validate";
    88  
    89      /**
    90       * Alternate name for factory classname properties in configuration file.
    91       */
    92      public static final String FACTORY_CLASSNAME_PARAMETER_NAME =
    93          "definitions-factory-class";
    94  
    95      /**
    96       * Alternate name for definition files properties in configuration file.
    97       */
    98      public static final String DEFINITIONS_CONFIG_PARAMETER_NAME =
    99          "definitions-config";
    100 
    101     /**
    102      * Alternate name for definition debug details properties in configuration file.
    103      * @deprecated This will be removed in a release after Struts 1.2.
    104      */
    105     public static final String TILES_DETAILS_PARAMETER_NAME = "definitions-debug";
    106 
    107     /**
    108      * Map of extra attribute available.
    109      */
    110     private Map extraAttributes = new HashMap();
    111 
    112     /**
    113      * Default constructor.
    114      */
    115     public DefinitionsFactoryConfig() {
    116         super();
    117     }
    118 
    119     /**
    120      * Constructor.
    121      * Create configuration object, and initialize it with parameters from Map.
    122      * Parameters corresponding to an attribute are filtered and stored in appropriate
    123      * attribute.
    124      * @param initParameters Map.
    125      */
    126     public DefinitionsFactoryConfig(Map initParameters) {
    127         super();
    128     }
    129 
    130     /**
    131      * Get the module aware flag.
    132      * @return <code>true</code>: user wants a single factory instance,
    133      * <code>false</code>: user wants multiple factory instances (one per module with Struts)
    134      */
    135     public boolean isModuleAware() {
    136         return moduleAware;
    137     }
    138     /**
    139      * Set the module aware flag.
    140      * @param moduleAware <code>true</code>: user wants a single factory instance,
    141      * <code>false</code>: user wants multiple factory instances (one per module with Struts)
    142      */
    143     public void setModuleAware(boolean moduleAware) {
    144         this.moduleAware = moduleAware;
    145     }
    146 
    147     /**
    148      * Get the classname of the factory.
    149      * @return Classname.
    150      */
    151     public String getFactoryClassname() {
    152         return factoryClassname;
    153     }
    154 
    155     /**
    156      * Set the classname of the factory..
    157      * @param aFactoryClassname Classname of the factory.
    158      */
    159     public void setFactoryClassname(String aFactoryClassname) {
    160         factoryClassname = aFactoryClassname;
    161     }
    162 
    163     /**
    164      * Determines if the parser is validating.
    165      * @return <code>true<code> when in validating mode.
    166      */
    167     public boolean getParserValidate() {
    168         return parserValidate;
    169     }
    170 
    171     /**
    172      * Set the validating mode for the parser.
    173      * @param aParserValidate <code>true</code> for validation, <code>false</code> otherwise
    174      */
    175     public void setParserValidate(boolean aParserValidate) {
    176         parserValidate = aParserValidate;
    177     }
    178 
    179     /**
    180      * Get the definition config files.
    181      * @return Defition config files.
    182      */
    183     public String getDefinitionConfigFiles() {
    184         return definitionConfigFiles;
    185     }
    186 
    187     /**
    188      * Set the definition config files.
    189      * @param aDefinitionConfigFiles Definition config files.
    190      */
    191     public void setDefinitionConfigFiles(String aDefinitionConfigFiles) {
    192         definitionConfigFiles = aDefinitionConfigFiles;
    193     }
    194 
    195     /**
    196      * Set value of an additional attribute.
    197      * @param name Name of the attribute.
    198      * @param value Value of the attribute.
    199      */
    200     public void setAttribute(String name, Object value) {
    201         extraAttributes.put(name, value);
    202     }
    203 
    204     /**
    205      * Get value of an additional attribute.
    206      * @param name Name of the attribute.
    207      * @return Value of the attribute, or null if not found.
    208      */
    209     public Object getAttribute(String name) {
    210         return extraAttributes.get(name);
    211     }
    212 
    213     /**
    214      * Get additional attributes as a Map.
    215      * @return Map A Map containing attribute name - value pairs.
    216      */
    217     public Map getAttributes() {
    218         Map map = new HashMap(extraAttributes);
    219         // Add property attributes using old names
    220         /*
    221           map.put(DEFINITIONS_CONFIG_PARAMETER_NAME, getDefinitionConfigFiles());
    222           map.put(TILES_DETAILS_PARAMETER_NAME, Integer.toString(getDebugLevel()) );
    223           map.put(PARSER_DETAILS_PARAMETER_NAME, Integer.toString(getParserDebugLevel()) );
    224           map.put(PARSER_VALIDATE_PARAMETER_NAME, new Boolean(getParserValidate()).toString() );
    225 
    226           if( ! "org.apache.struts.tiles.xmlDefinition.I18nFactorySet".equals(getFactoryClassname()) )
    227           map.put(FACTORY_CLASSNAME_PARAMETER_NAME, getFactoryClassname());
    228         */
    229         return map;
    230     }
    231 
    232     /**
    233      * Populate this config object from properties map, based on
    234      * the specified name/value pairs.  This method uses the populate() method from
    235      * org.apache.commons.beanutils.BeanUtil.
    236      * <p>
    237      * Properties keys are scanned for old property names, and linked to the new name
    238      * if necessary. This modifies the properties map.
    239      * <p>
    240      * The particular setter method to be called for each property is
    241      * determined using the usual JavaBeans introspection mechanisms.  Thus,
    242      * you may identify custom setter methods using a BeanInfo class that is
    243      * associated with the class of the bean itself.  If no such BeanInfo
    244      * class is available, the standard method name conversion ("set" plus
    245      * the capitalized name of the property in question) is used.
    246      * <p>
    247      * <strong>NOTE</strong>:  It is contrary to the JavaBeans Specification
    248      * to have more than one setter method (with different argument
    249      * signatures) for the same property.
    250      *
    251      * @param properties Map keyed by property name, with the
    252      *  corresponding (String or String[]) value(s) to be set.
    253      *
    254      * @exception IllegalAccessException if the caller does not have
    255      *  access to the property accessor method.
    256      * @exception InvocationTargetException if the property accessor method
    257      *  throws an exception.
    258      * @see org.apache.commons.beanutils.BeanUtils
    259      */
    260     public void populate(Map properties)
    261         throws IllegalAccessException, InvocationTargetException {
    262 
    263         // link old parameter names for backward compatibility
    264         linkOldPropertyNames(properties);
    265         BeanUtils.populate(this, properties);
    266     }
    267 
    268     /**
    269      * Link old property names to new property names.
    270      * This modifies the map.
    271      * @param properties Map keyed by property name, with the
    272      *  corresponding (String or String[]) value(s) to be set.
    273      */
    274     static public void linkOldPropertyNames(Map properties) {
    275         Set entries = properties.entrySet();
    276         Map toAdd = new HashMap();
    277         Iterator i = entries.iterator();
    278         while (i.hasNext()) {
    279             Map.Entry entry = (Map.Entry) i.next();
    280 
    281             if (DEFINITIONS_CONFIG_PARAMETER_NAME.equals(entry.getKey())) {
    282                 toAdd.put("definitionConfigFiles", entry.getValue());
    283 
    284             } else if (FACTORY_CLASSNAME_PARAMETER_NAME.equals(entry.getKey())) {
    285                 toAdd.put("factoryClassname", entry.getValue());
    286 
    287             } else if (PARSER_DETAILS_PARAMETER_NAME.equals(entry.getKey())) {
    288                 toAdd.put("parserDebugLevel", entry.getValue());
    289 
    290             } else if (PARSER_VALIDATE_PARAMETER_NAME.equals(entry.getKey())) {
    291                 toAdd.put("parserValidate", entry.getValue());
    292 
    293             } else if (TILES_DETAILS_PARAMETER_NAME.equals(entry.getKey())) {
    294                 toAdd.put("debugLevel", entry.getValue());
    295             }
    296         }
    297 
    298         if (toAdd.size() > 0) {
    299             properties.putAll(toAdd);
    300         }
    301     }
    302 
    303     /**
    304      * Get the factory name.
    305      */
    306     public String getFactoryName() {
    307         return factoryName;
    308     }
    309     /**
    310      * Set the factory name.
    311      * @param factoryName Name of the factory.
    312      */
    313     public void setFactoryName(String factoryName) {
    314         this.factoryName = factoryName;
    315     }
    316 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
