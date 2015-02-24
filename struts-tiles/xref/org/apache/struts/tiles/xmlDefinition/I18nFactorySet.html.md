[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/xmlDefinition/I18nFactorySet.html.md)


    1   /*
    2    * $Id: I18nFactorySet.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.io.FileNotFoundException;
    25  import java.io.IOException;
    26  import java.io.InputStream;
    27  import java.util.ArrayList;
    28  import java.util.HashMap;
    29  import java.util.Iterator;
    30  import java.util.List;
    31  import java.util.Locale;
    32  import java.util.Map;
    33  import java.util.StringTokenizer;
    34  
    35  import javax.servlet.ServletContext;
    36  import javax.servlet.ServletRequest;
    37  import javax.servlet.http.HttpServletRequest;
    38  import javax.servlet.http.HttpSession;
    39  
    40  import org.apache.commons.logging.Log;
    41  import org.apache.commons.logging.LogFactory;
    42  import org.apache.struts.tiles.taglib.ComponentConstants;
    43  import org.apache.struts.tiles.DefinitionsFactoryException;
    44  import org.apache.struts.tiles.FactoryNotFoundException;
    45  import org.xml.sax.SAXException;
    46  
    47  /**
    48   * Definitions factory.
    49   * This implementation allows to have a set of definition factories.
    50   * There is a main factory and one factory for each file associated to a Locale.
    51   *
    52   * To retrieve a definition, we first search for the appropriate factory using
    53   * the Locale found in session context. If no factory is found, use the
    54   * default one. Then we ask the factory for the definition.
    55   *
    56   * A definition factory file is loaded using main filename extended with locale code
    57   * (ex : <code>templateDefinitions_fr.xml</code>). If no file is found under this name, use default file.
    58   */
    59  public class I18nFactorySet extends FactorySet {
    60  
    61      /**
    62       * Commons Logging instance.
    63       */
    64      protected static Log log = LogFactory.getLog(I18nFactorySet.class);
    65  
    66      /**
    67       * Config file parameter name.
    68       */
    69      public static final String DEFINITIONS_CONFIG_PARAMETER_NAME =
    70          "definitions-config";
    71  
    72      /**
    73       * Config file parameter name.
    74       */
    75      public static final String PARSER_DETAILS_PARAMETER_NAME =
    76          "definitions-parser-details";
    77  
    78      /**
    79       * Config file parameter name.
    80       */
    81      public static final String PARSER_VALIDATE_PARAMETER_NAME =
    82          "definitions-parser-validate";
    83  
    84      /**
    85       * Possible definition filenames.
    86       */
    87      public static final String DEFAULT_DEFINITION_FILENAMES[] =
    88          {
    89              "/WEB-INF/tileDefinitions.xml",
    90              "/WEB-INF/componentDefinitions.xml",
    91              "/WEB-INF/instanceDefinitions.xml" };
    92  
    93      /**
    94       * Default filenames extension.
    95       */
    96      public static final String FILENAME_EXTENSION = ".xml";
    97  
    98      /**
    99       * Default factory.
    100      */
    101     protected DefinitionsFactory defaultFactory = null;
    102 
    103     /**
    104      * XML parser used.
    105      * Attribute is transient to allow serialization. In this implementaiton,
    106      * xmlParser is created each time we need it ;-(.
    107      */
    108     protected transient XmlParser xmlParser;
    109 
    110     /**
    111      * Do we want validating parser. Default is <code>false</code>.
    112      * Can be set from servlet config file.
    113      */
    114     protected boolean isValidatingParser = false;
    115 
    116     /**
    117      * Parser detail level. Default is 0.
    118      * Can be set from servlet config file.
    119      */
    120     protected int parserDetailLevel = 0;
    121 
    122     /**
    123      * Names of files containing instances descriptions.
    124      */
    125     private List filenames = null;
    126 
    127     /**
    128      * Collection of already loaded definitions set, referenced by their suffix.
    129      */
    130     private Map loaded = null;
    131 
    132     /**
    133      * Parameterless Constructor.
    134      * Method {@link #initFactory} must be called prior to any use of created factory.
    135      */
    136     public I18nFactorySet() {
    137         super();
    138     }
    139 
    140     /**
    141      * Constructor.
    142      * Init the factory by reading appropriate configuration file.
    143      * @param servletContext Servlet context.
    144      * @param properties Map containing all properties.
    145      * @throws FactoryNotFoundException Can't find factory configuration file.
    146      */
    147     public I18nFactorySet(ServletContext servletContext, Map properties)
    148         throws DefinitionsFactoryException {
    149 
    150         initFactory(servletContext, properties);
    151     }
    152 
    153     /**
    154      * Initialization method.
    155      * Init the factory by reading appropriate configuration file.
    156      * This method is called exactly once immediately after factory creation in
    157      * case of internal creation (by DefinitionUtil).
    158      * @param servletContext Servlet Context passed to newly created factory.
    159      * @param properties Map of name/property passed to newly created factory. Map can contains
    160      * more properties than requested.
    161      * @throws DefinitionsFactoryException An error occur during initialization.
    162      */
    163     public void initFactory(ServletContext servletContext, Map properties)
    164         throws DefinitionsFactoryException {
    165 
    166         // Set some property values
    167         String value = (String) properties.get(PARSER_VALIDATE_PARAMETER_NAME);
    168         if (value != null) {
    169             isValidatingParser = Boolean.valueOf(value).booleanValue();
    170         }
    171 
    172         value = (String) properties.get(PARSER_DETAILS_PARAMETER_NAME);
    173         if (value != null) {
    174             try {
    175                 parserDetailLevel = Integer.valueOf(value).intValue();
    176 
    177             } catch (NumberFormatException ex) {
    178                 log.error(
    179                     "Bad format for parameter '"
    180                         + PARSER_DETAILS_PARAMETER_NAME
    181                         + "'. Integer expected.");
    182             }
    183         }
    184 
    185         // init factory withappropriate configuration file
    186         // Try to use provided filename, if any.
    187         // If no filename are provided, try to use default ones.
    188         String filename = (String) properties.get(DEFINITIONS_CONFIG_PARAMETER_NAME);
    189         if (filename != null) { // Use provided filename
    190             try {
    191                 initFactory(servletContext, filename);
    192                 if (log.isDebugEnabled()) {
    193                     log.debug("Factory initialized from file '" + filename + "'.");
    194                 }
    195 
    196             } catch (FileNotFoundException ex) { // A filename is specified, throw appropriate error.
    197                 log.error(ex.getMessage() + " : Can't find file '" + filename + "'");
    198                 throw new FactoryNotFoundException(
    199                     ex.getMessage() + " : Can't find file '" + filename + "'");
    200             }
    201 
    202         } else { // try each default file names
    203             for (int i = 0; i < DEFAULT_DEFINITION_FILENAMES.length; i++) {
    204                 filename = DEFAULT_DEFINITION_FILENAMES[i];
    205                 try {
    206                     initFactory(servletContext, filename);
    207                     if (log.isInfoEnabled()) {
    208                         log.info(
    209                             "Factory initialized from file '" + filename + "'.");
    210                     }
    211                 } catch (FileNotFoundException ex) {
    212                     // Do nothing
    213                 }
    214             }
    215         }
    216 
    217     }
    218 
    219     /**
    220      * Initialization method.
    221      * Init the factory by reading appropriate configuration file.
    222      * This method is called exactly once immediately after factory creation in
    223      * case of internal creation (by DefinitionUtil).
    224      * @param servletContext Servlet Context passed to newly created factory.
    225      * @param proposedFilename File names, comma separated, to use as  base file names.
    226      * @throws DefinitionsFactoryException An error occur during initialization.
    227      */
    228     protected void initFactory(
    229         ServletContext servletContext,
    230         String proposedFilename)
    231         throws DefinitionsFactoryException, FileNotFoundException {
    232 
    233         // Init list of filenames
    234         StringTokenizer tokenizer = new StringTokenizer(proposedFilename, ",");
    235         this.filenames = new ArrayList(tokenizer.countTokens());
    236         while (tokenizer.hasMoreTokens()) {
    237             this.filenames.add(tokenizer.nextToken().trim());
    238         }
    239 
    240         loaded = new HashMap();
    241         defaultFactory = createDefaultFactory(servletContext);
    242         if (log.isDebugEnabled())
    243             log.debug("default factory:" + defaultFactory);
    244     }
    245 
    246     /**
    247      * Get default factory.
    248      * @return Default factory
    249      */
    250     protected DefinitionsFactory getDefaultFactory() {
    251         return defaultFactory;
    252     }
    253 
    254     /**
    255      * Create default factory .
    256      * Create InstancesMapper for specified Locale.
    257      * If creation failes, use default mapper and log error message.
    258      * @param servletContext Current servlet context. Used to open file.
    259      * @return Created default definition factory.
    260      * @throws DefinitionsFactoryException If an error occur while creating factory.
    261      * @throws FileNotFoundException if factory can't be loaded from filenames.
    262      */
    263     protected DefinitionsFactory createDefaultFactory(ServletContext servletContext)
    264         throws DefinitionsFactoryException, FileNotFoundException {
    265 
    266         XmlDefinitionsSet rootXmlConfig = parseXmlFiles(servletContext, "", null);
    267         if (rootXmlConfig == null) {
    268             throw new FileNotFoundException();
    269         }
    270 
    271         rootXmlConfig.resolveInheritances();
    272 
    273         if (log.isDebugEnabled()) {
    274             log.debug(rootXmlConfig);
    275         }
    276 
    277         DefinitionsFactory factory = new DefinitionsFactory(rootXmlConfig);
    278         if (log.isDebugEnabled()) {
    279             log.debug("factory loaded : " + factory);
    280         }
    281 
    282         return factory;
    283     }
    284 
    285     /**
    286      * Extract key that will be used to get the sub factory.
    287      * @param name Name of requested definition
    288      * @param request Current servlet request.
    289      * @param servletContext Current servlet context.
    290      * @return the key or <code>null</code> if not found.
    291      */
    292     protected Object getDefinitionsFactoryKey(
    293         String name,
    294         ServletRequest request,
    295         ServletContext servletContext) {
    296 
    297         Locale locale = null;
    298         try {
    299             HttpSession session = ((HttpServletRequest) request).getSession(false);
    300             if (session != null) {
    301                 locale = (Locale) session.getAttribute(ComponentConstants.LOCALE_KEY);
    302             }
    303 
    304         } catch (ClassCastException ex) {
    305             log.error("I18nFactorySet.getDefinitionsFactoryKey");
    306             ex.printStackTrace();
    307         }
    308 
    309         return locale;
    310     }
    311 
    312     /**
    313      * Create a factory for specified key.
    314     * If creation failes, return default factory and log an error message.
    315     * @param key The key.
    316     * @param request Servlet request.
    317     * @param servletContext Servlet context.
    318     * @return Definition factory for specified key.
    319     * @throws DefinitionsFactoryException If an error occur while creating factory.
    320      */
    321     protected DefinitionsFactory createFactory(
    322         Object key,
    323         ServletRequest request,
    324         ServletContext servletContext)
    325         throws DefinitionsFactoryException {
    326 
    327         if (key == null) {
    328             return getDefaultFactory();
    329         }
    330 
    331         // Build possible postfixes
    332         List possiblePostfixes = calculateSuffixes((Locale) key);
    333 
    334         // Search last postix corresponding to a config file to load.
    335         // First check if something is loaded for this postfix.
    336         // If not, try to load its config.
    337         XmlDefinitionsSet lastXmlFile = null;
    338         DefinitionsFactory factory = null;
    339         String curPostfix = null;
    340         int i = 0;
    341 
    342         for (i = possiblePostfixes.size() - 1; i >= 0; i--) {
    343             curPostfix = (String) possiblePostfixes.get(i);
    344 
    345             // Already loaded ?
    346             factory = (DefinitionsFactory) loaded.get(curPostfix);
    347             if (factory != null) { // yes, stop search
    348                 return factory;
    349             }
    350 
    351             // Try to load it. If success, stop search
    352             lastXmlFile = parseXmlFiles(servletContext, curPostfix, null);
    353             if (lastXmlFile != null) {
    354                 break;
    355             }
    356         }
    357 
    358         // Have we found a description file ?
    359         // If no, return default one
    360         if (lastXmlFile == null) {
    361             return getDefaultFactory();
    362         }
    363 
    364         // We found something. Need to load base and intermediate files
    365         String lastPostfix = curPostfix;
    366         XmlDefinitionsSet rootXmlConfig = parseXmlFiles(servletContext, "", null);
    367         for (int j = 0; j < i; j++) {
    368             curPostfix = (String) possiblePostfixes.get(j);
    369             parseXmlFiles(servletContext, curPostfix, rootXmlConfig);
    370         }
    371 
    372         rootXmlConfig.extend(lastXmlFile);
    373         rootXmlConfig.resolveInheritances();
    374 
    375         factory = new DefinitionsFactory(rootXmlConfig);
    376         loaded.put(lastPostfix, factory);
    377 
    378         if (log.isDebugEnabled()) {
    379             log.debug("factory loaded : " + factory);
    380         }
    381 
    382         // return last available found !
    383         return factory;
    384     }
    385 
    386     /**
    387      * Calculate the suffixes based on the locale.
    388      * @param locale the locale
    389      */
    390     private List calculateSuffixes(Locale locale) {
    391 
    392         List suffixes = new ArrayList(3);
    393         String language = locale.getLanguage();
    394         String country  = locale.getCountry();
    395         String variant  = locale.getVariant();
    396 
    397         StringBuffer suffix = new StringBuffer();
    398         suffix.append('_');
    399         suffix.append(language);
    400         if (language.length() > 0) {
    401             suffixes.add(suffix.toString());
    402         }
    403 
    404         suffix.append('_');
    405         suffix.append(country);
    406         if (country.length() > 0) {
    407             suffixes.add(suffix.toString());
    408         }
    409 
    410         suffix.append('_');
    411         suffix.append(variant);
    412         if (variant.length() > 0) {
    413             suffixes.add(suffix.toString());
    414         }
    415 
    416         return suffixes;
    417 
    418     }
    419 
    420     /**
    421      * Parse files associated to postix if they exist.
    422      * For each name in filenames, append postfix before file extension,
    423      * then try to load the corresponding file.
    424      * If file doesn't exist, try next one. Each file description is added to
    425      * the XmlDefinitionsSet description.
    426      * The XmlDefinitionsSet description is created only if there is a definition file.
    427      * Inheritance is not resolved in the returned XmlDefinitionsSet.
    428      * If no description file can be opened and no definiion set is provided, return <code>null</code>.
    429      * @param postfix Postfix to add to each description file.
    430      * @param xmlDefinitions Definitions set to which definitions will be added. If <code>null</code>, a definitions
    431      * set is created on request.
    432      * @return XmlDefinitionsSet The definitions set created or passed as parameter.
    433      * @throws DefinitionsFactoryException On errors parsing file.
    434      */
    435     protected XmlDefinitionsSet parseXmlFiles(
    436         ServletContext servletContext,
    437         String postfix,
    438         XmlDefinitionsSet xmlDefinitions)
    439         throws DefinitionsFactoryException {
    440 
    441         if (postfix != null && postfix.length() == 0) {
    442             postfix = null;
    443         }
    444 
    445         // Iterate throw each file name in list
    446         Iterator i = filenames.iterator();
    447         while (i.hasNext()) {
    448             String filename = concatPostfix((String) i.next(), postfix);
    449             xmlDefinitions = parseXmlFile(servletContext, filename, xmlDefinitions);
    450         }
    451 
    452         return xmlDefinitions;
    453     }
    454 
    455     /**
    456      * Parse specified xml file and add definition to specified definitions set.
    457      * This method is used to load several description files in one instances list.
    458      * If filename exists and definition set is <code>null</code>, create a new set. Otherwise, return
    459      * passed definition set (can be <code>null</code>).
    460      * @param servletContext Current servlet context. Used to open file.
    461      * @param filename Name of file to parse.
    462      * @param xmlDefinitions Definitions set to which definitions will be added. If null, a definitions
    463      * set is created on request.
    464      * @return XmlDefinitionsSet The definitions set created or passed as parameter.
    465      * @throws DefinitionsFactoryException On errors parsing file.
    466      */
    467     protected XmlDefinitionsSet parseXmlFile(
    468         ServletContext servletContext,
    469         String filename,
    470         XmlDefinitionsSet xmlDefinitions)
    471         throws DefinitionsFactoryException {
    472 
    473         try {
    474             InputStream input = servletContext.getResourceAsStream(filename);
    475             // Try to load using real path.
    476             // This allow to load config file under websphere 3.5.x
    477             // Patch proposed Houston, Stephen (LIT) on 5 Apr 2002
    478             if (null == input) {
    479                 try {
    480                     input =
    481                         new java.io.FileInputStream(
    482                             servletContext.getRealPath(filename));
    483                 } catch (Exception e) {
    484                 }
    485             }
    486 
    487             // If the config isn't in the servlet context, try the class loader
    488             // which allows the config files to be stored in a jar
    489             if (input == null) {
    490                 input = getClass().getResourceAsStream(filename);
    491             }
    492 
    493             // If still nothing found, this mean no config file is associated
    494             if (input == null) {
    495                 if (log.isDebugEnabled()) {
    496                     log.debug("Can't open file '" + filename + "'");
    497                 }
    498                 return xmlDefinitions;
    499             }
    500 
    501             // Check if parser already exist.
    502             // Doesn't seem to work yet.
    503             //if( xmlParser == null )
    504             if (true) {
    505                 xmlParser = new XmlParser();
    506                 xmlParser.setValidating(isValidatingParser);
    507             }
    508 
    509             // Check if definition set already exist.
    510             if (xmlDefinitions == null) {
    511                 xmlDefinitions = new XmlDefinitionsSet();
    512             }
    513 
    514             xmlParser.parse(input, xmlDefinitions);
    515 
    516         } catch (SAXException ex) {
    517             if (log.isDebugEnabled()) {
    518                 log.debug("Error while parsing file '" + filename + "'.");
    519                 ex.printStackTrace();
    520             }
    521             throw new DefinitionsFactoryException(
    522                 "Error while parsing file '" + filename + "'. " + ex.getMessage(),
    523                 ex);
    524 
    525         } catch (IOException ex) {
    526             throw new DefinitionsFactoryException(
    527                 "IO Error while parsing file '" + filename + "'. " + ex.getMessage(),
    528                 ex);
    529         }
    530 
    531         return xmlDefinitions;
    532     }
    533 
    534     /**
    535      * Concat postfix to the name. Take care of existing filename extension.
    536      * Transform the given name "name.ext" to have "name" + "postfix" + "ext".
    537      * If there is no ext, return "name" + "postfix".
    538      * @param name Filename.
    539      * @param postfix Postfix to add.
    540      * @return Concatenated filename.
    541      */
    542     private String concatPostfix(String name, String postfix) {
    543         if (postfix == null) {
    544             return name;
    545         }
    546 
    547         // Search file name extension.
    548         // take care of Unix files starting with .
    549         int dotIndex = name.lastIndexOf(".");
    550         int lastNameStart = name.lastIndexOf(java.io.File.pathSeparator);
    551         if (dotIndex < 1 || dotIndex < lastNameStart) {
    552             return name + postfix;
    553         }
    554 
    555         String ext = name.substring(dotIndex);
    556         name = name.substring(0, dotIndex);
    557         return name + postfix + ext;
    558     }
    559 
    560     /**
    561      * Return String representation.
    562      * @return String representation.
    563      */
    564     public String toString() {
    565         StringBuffer buff = new StringBuffer("I18nFactorySet : \n");
    566         buff.append("--- default factory ---\n");
    567         buff.append(defaultFactory.toString());
    568         buff.append("\n--- other factories ---\n");
    569         Iterator i = factories.values().iterator();
    570         while (i.hasNext()) {
    571             buff.append(i.next().toString()).append("---------- \n");
    572         }
    573         return buff.toString();
    574     }
    575 
    576 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
