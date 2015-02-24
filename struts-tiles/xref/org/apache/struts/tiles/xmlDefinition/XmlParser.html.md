[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/xmlDefinition/XmlParser.html.md)


    1   /*
    2    * $Id: XmlParser.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.io.BufferedInputStream;
    25  import java.io.FileInputStream;
    26  import java.io.IOException;
    27  import java.io.InputStream;
    28  import java.net.URL;
    29  
    30  import org.apache.commons.digester.Digester;
    31  import org.xml.sax.SAXException;
    32  
    33  /**
    34   * Parse an XML definitions file.
    35   */
    36  public class XmlParser
    37  {
    38  
    39      /** Associated digester. */
    40    protected Digester digester;
    41      /**
    42       * Should we use a validating XML parser to read the configuration file.
    43       * Default is <code>false</code>.
    44       */
    45      protected boolean validating = false;
    46      /**
    47       * The set of public identifiers, and corresponding resource names for
    48       * the versions of the configuration file DTDs we know about.  There
    49       * <strong>MUST</strong> be an even number of Strings in this list!
    50       */
    51      protected String registrations[] = {
    52          "-//Apache Software Foundation//DTD Tiles Configuration 1.1//EN",
    53          "/org/apache/struts/resources/tiles-config_1_1.dtd",
    54          "-//Apache Software Foundation//DTD Tiles Configuration 1.3//EN",
    55          "/org/apache/struts/resources/tiles-config_1_3.dtd"
    56      };
    57  
    58       /**
    59        * Constructor.
    60        * Creates a digester parser and initializes syntax rules.
    61        */
    62    public XmlParser()
    63    {
    64      digester = new Digester();
    65      digester.setValidating(validating);
    66      digester.setNamespaceAware(true);
    67      digester.setUseContextClassLoader(true);
    68      // Register our local copy of the DTDs that we can find
    69    for (int i = 0; i < registrations.length; i += 2) {
    70        URL url = this.getClass().getResource(registrations[i+1]);
    71        if (url != null)
    72            {
    73            digester.register(registrations[i], url.toString());
    74            }
    75    }
    76      // Init syntax rules
    77    initDigester( digester );
    78    }
    79  
    80      /**
    81       * Set digester validating flag.
    82       */
    83    public void setValidating( boolean validating )
    84      {
    85      digester.setValidating( validating);
    86      }
    87  
    88  
    89     /**
    90      * Init digester for components syntax.
    91      * This is an old set of rules, left for backward compatibility.
    92      * @param digester Digester instance to use.
    93      */
    94    private void initDigesterForComponentsDefinitionsSyntax( Digester digester )
    95    {
    96       // Common constants
    97    String PACKAGE_NAME = "org.apache.struts.tiles.xmlDefinition";
    98    String DEFINITION_TAG = "component-definitions/definition";
    99    String definitionHandlerClass = PACKAGE_NAME + ".XmlDefinition";
    100 
    101   String PUT_TAG  = DEFINITION_TAG + "/put";
    102   String putAttributeHandlerClass = PACKAGE_NAME + ".XmlAttribute";
    103 
    104   String LIST_TAG = DEFINITION_TAG + "/putList";
    105   String listHandlerClass     = PACKAGE_NAME + ".XmlListAttribute";
    106 
    107   String ADD_LIST_ELE_TAG = LIST_TAG + "/add";
    108 
    109     // syntax rules
    110     digester.addObjectCreate(  DEFINITION_TAG, definitionHandlerClass );
    111     digester.addSetProperties( DEFINITION_TAG);
    112     digester.addSetNext(       DEFINITION_TAG, "putDefinition", definitionHandlerClass);
    113     // put / putAttribute rules
    114     digester.addObjectCreate(  PUT_TAG, putAttributeHandlerClass);
    115     digester.addSetNext(       PUT_TAG, "addAttribute", putAttributeHandlerClass);
    116     digester.addSetProperties( PUT_TAG);
    117     digester.addCallMethod(    PUT_TAG, "setBody", 0);
    118     // list rules
    119     digester.addObjectCreate(  LIST_TAG, listHandlerClass);
    120     digester.addSetProperties( LIST_TAG);
    121     digester.addSetNext(       LIST_TAG, "addAttribute", putAttributeHandlerClass);
    122     // list elements rules
    123     // We use Attribute class to avoid rewriting a new class.
    124     // Name part can't be used in listElement attribute.
    125     digester.addObjectCreate(  ADD_LIST_ELE_TAG, putAttributeHandlerClass);
    126     digester.addSetNext(       ADD_LIST_ELE_TAG, "add", putAttributeHandlerClass);
    127     digester.addSetProperties( ADD_LIST_ELE_TAG);
    128     digester.addCallMethod(    ADD_LIST_ELE_TAG, "setBody", 0);
    129   }
    130 
    131    /**
    132     * Init digester for Tiles syntax.
    133     * Same as components, but with first element = tiles-definitions
    134     * @param digester Digester instance to use.
    135     */
    136   private void initDigesterForTilesDefinitionsSyntax( Digester digester )
    137   {
    138      // Common constants
    139   String PACKAGE_NAME = "org.apache.struts.tiles.xmlDefinition";
    140   String DEFINITION_TAG = "tiles-definitions/definition";
    141   String definitionHandlerClass = PACKAGE_NAME + ".XmlDefinition";
    142 
    143   String PUT_TAG  = DEFINITION_TAG + "/put";
    144   String putAttributeHandlerClass = PACKAGE_NAME + ".XmlAttribute";
    145 
    146   //String LIST_TAG = DEFINITION_TAG + "/putList";
    147     // List tag value
    148   String LIST_TAG = "putList";
    149   String DEF_LIST_TAG = DEFINITION_TAG + "/" + LIST_TAG;
    150   String listHandlerClass     = PACKAGE_NAME + ".XmlListAttribute";
    151     // Tag value for adding an element in a list
    152   String ADD_LIST_ELE_TAG = "*/" + LIST_TAG + "/add";
    153 
    154     // syntax rules
    155     digester.addObjectCreate(  DEFINITION_TAG, definitionHandlerClass );
    156     digester.addSetProperties( DEFINITION_TAG);
    157     digester.addSetNext(       DEFINITION_TAG, "putDefinition", definitionHandlerClass);
    158     // put / putAttribute rules
    159     // Rules for a same pattern are called in order, but rule.end() are called
    160     // in reverse order.
    161     // SetNext and CallMethod use rule.end() method. So, placing SetNext in
    162     // first position ensure it will be called last (sic).
    163     digester.addObjectCreate(  PUT_TAG, putAttributeHandlerClass);
    164     digester.addSetNext(       PUT_TAG, "addAttribute", putAttributeHandlerClass);
    165     digester.addSetProperties( PUT_TAG);
    166     digester.addCallMethod(    PUT_TAG, "setBody", 0);
    167     // Definition level list rules
    168     // This is rules for lists nested in a definition
    169     digester.addObjectCreate(  DEF_LIST_TAG, listHandlerClass);
    170     digester.addSetProperties( DEF_LIST_TAG);
    171     digester.addSetNext(       DEF_LIST_TAG, "addAttribute", putAttributeHandlerClass);
    172     // list elements rules
    173     // We use Attribute class to avoid rewriting a new class.
    174     // Name part can't be used in listElement attribute.
    175     digester.addObjectCreate(  ADD_LIST_ELE_TAG, putAttributeHandlerClass);
    176     digester.addSetNext(       ADD_LIST_ELE_TAG, "add", putAttributeHandlerClass);
    177     digester.addSetProperties( ADD_LIST_ELE_TAG);
    178     digester.addCallMethod(    ADD_LIST_ELE_TAG, "setBody", 0);
    179 
    180     // nested list elements rules
    181     // Create a list handler, and add it to parent list
    182   String NESTED_LIST = "*/" + LIST_TAG + "/" + LIST_TAG;
    183     digester.addObjectCreate(  NESTED_LIST, listHandlerClass);
    184     digester.addSetProperties( NESTED_LIST);
    185     digester.addSetNext(       NESTED_LIST, "add", putAttributeHandlerClass);
    186 
    187     // item elements rules
    188     // We use Attribute class to avoid rewriting a new class.
    189     // Name part can't be used in listElement attribute.
    190   //String ADD_WILDCARD = LIST_TAG + "/addItem";
    191   // non String ADD_WILDCARD = LIST_TAG + "/addx*";
    192   String ADD_WILDCARD = "*/item";
    193   String menuItemDefaultClass = "org.apache.struts.tiles.beans.SimpleMenuItem";
    194     digester.addObjectCreate(  ADD_WILDCARD, menuItemDefaultClass, "classtype");
    195     digester.addSetNext(       ADD_WILDCARD, "add", "java.lang.Object");
    196     digester.addSetProperties( ADD_WILDCARD);
    197 
    198     // bean elements rules
    199   String BEAN_TAG = "*/bean";
    200   String beanDefaultClass = "org.apache.struts.tiles.beans.SimpleMenuItem";
    201     digester.addObjectCreate(  BEAN_TAG, beanDefaultClass, "classtype");
    202     digester.addSetNext(       BEAN_TAG, "add", "java.lang.Object");
    203     digester.addSetProperties( BEAN_TAG);
    204 
    205     // Set properties to surrounding element
    206   digester.addSetProperty(BEAN_TAG+ "/set-property", "property", "value");
    207   }
    208 
    209    /**
    210     * Init digester in order to parse instances definition file syntax.
    211     * Instances is an old name for "definition". This method is left for
    212     * backwards compatibility.
    213     * @param digester Digester instance to use.
    214     */
    215   private void initDigesterForInstancesSyntax( Digester digester )
    216   {
    217         // Build a digester to process our configuration resource
    218   String PACKAGE_NAME = "org.apache.struts.tiles.xmlDefinition";
    219   String INSTANCE_TAG = "component-instances/instance";
    220   String instanceHandlerClass = PACKAGE_NAME + ".XmlDefinition";
    221 
    222   String PUT_TAG = INSTANCE_TAG + "/put";
    223   String PUTATTRIBUTE_TAG = INSTANCE_TAG + "/putAttribute";
    224   String putAttributeHandlerClass = PACKAGE_NAME + ".XmlAttribute";
    225 
    226   String LIST_TAG     = INSTANCE_TAG + "/putList";
    227   String listHandlerClass     = PACKAGE_NAME + ".XmlListAttribute";
    228 
    229   String ADD_LIST_ELE_TAG = LIST_TAG + "/add";
    230 
    231     // component instance rules
    232     digester.addObjectCreate(  INSTANCE_TAG, instanceHandlerClass );
    233     digester.addSetProperties( INSTANCE_TAG);
    234     digester.addSetNext(       INSTANCE_TAG, "putDefinition", instanceHandlerClass);
    235     // put / putAttribute rules
    236     digester.addObjectCreate(  PUTATTRIBUTE_TAG, putAttributeHandlerClass);
    237     digester.addSetProperties( PUTATTRIBUTE_TAG);
    238     digester.addSetNext(       PUTATTRIBUTE_TAG, "addAttribute", putAttributeHandlerClass);
    239     // put / putAttribute rules
    240     digester.addObjectCreate(  PUT_TAG, putAttributeHandlerClass);
    241     digester.addSetProperties( PUT_TAG);
    242     digester.addSetNext(       PUT_TAG, "addAttribute", putAttributeHandlerClass);
    243     // list rules
    244     digester.addObjectCreate(  LIST_TAG, listHandlerClass);
    245     digester.addSetProperties( LIST_TAG);
    246     digester.addSetNext(       LIST_TAG, "addAttribute", putAttributeHandlerClass);
    247     // list elements rules
    248     // We use Attribute class to avoid rewriting a new class.
    249     // Name part can't be used in listElement attribute.
    250     digester.addObjectCreate(  ADD_LIST_ELE_TAG, putAttributeHandlerClass);
    251     digester.addSetProperties( ADD_LIST_ELE_TAG);
    252     digester.addSetNext(       ADD_LIST_ELE_TAG, "add", putAttributeHandlerClass);
    253   }
    254 
    255    /**
    256     * Init digester.
    257     * @param digester Digester instance to use.
    258     */
    259   protected void initDigester( Digester digester )
    260   {
    261   initDigesterForTilesDefinitionsSyntax( digester );
    262   initDigesterForComponentsDefinitionsSyntax( digester );
    263   initDigesterForInstancesSyntax( digester );
    264   }
    265 
    266   /**
    267    * Parse input reader and add encountered definitions to definitions set.
    268    * @param in Input stream.
    269    * @param definitions Xml Definitions set to which encountered definition are added.
    270    * @throws IOException On errors during file parsing.
    271    * @throws SAXException On errors parsing XML.
    272    */
    273   public void parse( InputStream in, XmlDefinitionsSet definitions ) throws IOException, SAXException
    274   {
    275     try
    276     {
    277       // set first object in stack
    278     //digester.clear();
    279     digester.push(definitions);
    280       // parse
    281       digester.parse(in);
    282       in.close();
    283       }
    284   catch (SAXException e)
    285     {
    286       //throw new ServletException( "Error while parsing " + mappingConfig, e);
    287     throw e;
    288       }
    289 
    290   }
    291 
    292     /**
    293      * Main method to check file syntax.
    294      */
    295   public static void main(String[] args)
    296   {
    297   //String filename = "E:/programs/jakarta-tomcat/webapps/wtiles-struts/WEB-INF/tiles-examples-defs.xml";
    298   String filename = "E:/programs/jakarta-tomcat-4.0.3/webapps/wtiles-struts/WEB-INF/tiles-examples-defs.xml";
    299   //String filename = "E:/programs/jakarta-tomcat/webapps/wtiles-struts/WEB-INF/tilesDefinitions.xml";
    300   //String filename = "E:/programs/jakarta-tomcat/webapps/wtiles-channel/WEB-INF/componentDefinitions.xml";
    301   //String filename2 = "E:/programs/jakarta-tomcat/webapps/wtiles-tutorial/WEB-INF/componentDefinitions.xml";
    302 
    303 
    304     if( args.length > 1 )
    305       {
    306       filename = args[1];
    307       } // end if
    308 
    309   System.out.println( "Read file '" + filename  +"'" );
    310 
    311   InputStream input = null;
    312   // InputStream input2 = null;
    313     // Open file
    314     try
    315       {
    316         input = new BufferedInputStream(
    317                              new FileInputStream( filename) );
    318     //    input2 = new BufferedInputStream(
    319           //                   new FileInputStream( filename2) );
    320       }
    321      catch( IOException ex )
    322       {
    323       System.out.println( "can't open file '" + filename + "' : " + ex.getMessage() );
    324       }
    325     // Check file syntax
    326     try
    327       {
    328         XmlParser parser = new XmlParser();
    329       parser.setValidating(true);
    330       XmlDefinitionsSet definitions = new XmlDefinitionsSet();
    331         System.out.println( "  Parse file" );
    332       parser.parse( input, definitions);
    333       //  System.out.println( "  Check file 2" );
    334       //parser.parse( input2, definitions);
    335         System.out.println( "  done." );
    336       System.out.println( "  Result : " + definitions.toString() );
    337       }
    338      catch( Exception ex )
    339       {
    340       System.out.println( "Error during parsing '" + filename + "' : " + ex.getMessage() );
    341       ex.printStackTrace();
    342       }
    343   }
    344 
    345 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
