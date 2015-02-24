[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/ComponentDefinition.html.md)


    1   /*
    2    * $Id: ComponentDefinition.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import java.util.HashMap;
    26  import java.util.Map;
    27  
    28  import org.apache.commons.logging.Log;
    29  import org.apache.commons.logging.LogFactory;
    30  import org.apache.struts.tiles.xmlDefinition.XmlDefinition;
    31  import org.apache.struts.util.RequestUtils;
    32  
    33  /**
    34   * Definition of a template / component attributes.
    35   * Attributes of a component can be defined with the help of this class.
    36   * An instance of this class can be used as a bean, and passed to 'insert' tag.
    37   */
    38  public class ComponentDefinition implements Serializable {
    39  
    40      /**
    41       * Commons Logging instance.
    42       */
    43      protected static Log log = LogFactory.getLog(ComponentDefinition.class);
    44  
    45      /**
    46       * Definition name
    47       */
    48      protected String name = null;
    49  
    50      /**
    51       * Component / template path (URL).
    52       */
    53      protected String path = null;
    54  
    55      /**
    56       * Attributes defined for the component.
    57       */
    58      protected Map attributes = null;
    59  
    60      /**
    61       * Role associated to definition.
    62       */
    63      protected String role = null;
    64  
    65      /** Associated Controller URL or classname, if defined */
    66      protected String controller = null;
    67  
    68      /**
    69       * Associated Controller typename, if controllerName defined.
    70       * Can be CONTROLLER, ACTION or URL, or null.
    71       */
    72      protected String controllerType = null;
    73  
    74      /**
    75       * Controller name type.
    76       */
    77      public static final String URL = "url";
    78  
    79      /**
    80       * Controller name type.
    81       */
    82      public static final String CONTROLLER = "controller";
    83  
    84      /**
    85       * Controller name type.
    86       */
    87      public static final String ACTION = "action";
    88  
    89      /**
    90       * Controller associated to Definition.
    91       * Lazy creation : only on first request
    92       */
    93      private Controller controllerInstance = null;
    94  
    95      /**
    96       * Constructor.
    97       */
    98      public ComponentDefinition() {
    99          attributes = new HashMap();
    100     }
    101 
    102     /**
    103      * Copy Constructor.
    104      * Create a new definition initialized with parent definition.
    105      * Do a shallow copy : attributes are shared between copies, but not the Map
    106      * containing attributes.
    107      */
    108     public ComponentDefinition(ComponentDefinition definition) {
    109         attributes = new HashMap(definition.getAttributes());
    110         this.name = definition.getName();
    111         this.path = definition.getPath();
    112         this.role = definition.getRole();
    113         this.controllerInstance = definition.getControllerInstance();
    114         this.controller = definition.getController();
    115         this.controllerType = definition.getControllerType();
    116     }
    117 
    118     /**
    119      * Constructor.
    120      * Create a new definition initialized from a RawDefinition.
    121      * Raw definitions are used to read definition from a data source (xml file, db, ...).
    122      * A RawDefinition mainly contains properties of type String, while Definition
    123      * contains more complex type (ex : Controller).
    124      * Do a shallow copy : attributes are shared between objects, but not the Map
    125      * containing attributes.
    126      * OO Design issues : Actually RawDefinition (XmlDefinition) extends ComponentDefinition.
    127      * This must not be the case. I have do it because I am lazy.
    128      * @throws InstantiationException if an error occur while instanciating Controller :
    129      * (classname can't be instanciated, Illegal access with instanciated class,
    130      * Error while instanciating class, classname can't be instanciated.
    131      */
    132     public ComponentDefinition(XmlDefinition definition) {
    133 
    134         this((ComponentDefinition) definition);
    135     }
    136 
    137     /**
    138      * Constructor.
    139      */
    140     public ComponentDefinition(String name, String path, Map attributes) {
    141         this.name = name;
    142         this.path = path;
    143         this.attributes = attributes;
    144     }
    145 
    146     /**
    147      * Access method for the name property.
    148      *
    149      * @return   the current value of the name property
    150      */
    151     public String getName() {
    152         return name;
    153     }
    154 
    155     /**
    156      * Sets the value of the name property.
    157      *
    158      * @param aName the new value of the name property
    159      */
    160     public void setName(String aName) {
    161         name = aName;
    162     }
    163 
    164     /**
    165      * Access method for the path property.
    166      *
    167      * @return The current value of the path property.
    168      */
    169     public String getPage() {
    170         return path;
    171     }
    172 
    173     /**
    174      * Sets the value of the path property.
    175      *
    176      * @param page the new value of the path property
    177      */
    178     public void setPage(String page) {
    179         path = page;
    180     }
    181 
    182     /**
    183      * Access method for the path property.
    184      *
    185      * @return   the current value of the path property
    186      */
    187     public String getPath() {
    188         return path;
    189     }
    190 
    191     /**
    192      * Sets the value of the path property.
    193      *
    194      * @param aPath the new value of the path property
    195      */
    196     public void setPath(String aPath) {
    197         path = aPath;
    198     }
    199 
    200     /**
    201      * Access method for the template property.
    202      * Same as getPath()
    203      * @return   the current value of the template property
    204      */
    205     public String getTemplate() {
    206         return path;
    207     }
    208 
    209     /**
    210      * Sets the value of the template property.
    211      * Same as setPath()
    212      *
    213      * @param template the new value of the path property
    214      */
    215     public void setTemplate(String template) {
    216         path = template;
    217     }
    218 
    219     /**
    220      * Access method for the role property.
    221      * @return   the current value of the role property
    222      */
    223     public String getRole() {
    224         return role;
    225     }
    226 
    227     /**
    228      * Sets the value of the role property.
    229      *
    230      * @param role the new value of the path property
    231      */
    232     public void setRole(String role) {
    233         this.role = role;
    234     }
    235 
    236     /**
    237      * Access method for the attributes property.
    238      * If there is no attributes, return an empty map.
    239      * @return   the current value of the attributes property
    240      */
    241     public Map getAttributes() {
    242         return attributes;
    243     }
    244 
    245     /**
    246      * Returns the value of the named attribute as an Object, or null if no
    247      * attribute of the given name exists.
    248      *
    249      * @return   requested attribute or null if not found
    250      */
    251     public Object getAttribute(String key) {
    252         return attributes.get(key);
    253     }
    254 
    255     /**
    256      * Put a new attribute in this component
    257      *
    258      * @param key String key for attribute
    259      * @param value Attibute value.
    260      */
    261     public void putAttribute(String key, Object value) {
    262         attributes.put(key, value);
    263     }
    264 
    265     /**
    266      * Put an attribute in component / template definition.
    267      * Attribute can be used as content for tag get.
    268      * @param name Attribute name
    269      * @param content Attribute value
    270      */
    271     public void put(String name, Object content) {
    272         put(name, content, false, null);
    273     }
    274 
    275     /**
    276      * Put an attribute in template definition.
    277      * Attribute can be used as content for tag get.
    278      * @param name Attribute name
    279      * @param content Attribute value ï¿½
    280      * @param direct Determines how content is handled by get tag: true means content is printed directly; false, the default, means content is included
    281      */
    282     public void put(String name, Object content, boolean direct) {
    283         put(name, content, direct, null);
    284     }
    285 
    286     /**
    287      * Put an attribute in template definition.
    288      * Attribute can be used as content for tag get.
    289      * @param name Attribute name
    290      * @param content Attribute value
    291      * @param direct Determines how content is handled by get tag: true means content is printed directly; false, the default, means content is included
    292      * @param role Determine if content is used by get tag. If user is in role, content is used.
    293      */
    294     public void put(String name, Object content, boolean direct, String role) {
    295         if (direct == true) { // direct String
    296             put(name, content, "string", role);
    297         } else {
    298             put(name, content, "template", role);
    299         }
    300 
    301     }
    302 
    303     /**
    304      * Put an attribute in template definition.
    305      * Attribute can be used as content for tag get.
    306      * @param name Attribute name
    307      * @param content Attribute value
    308      * @param type attribute type: template, string, definition
    309      * @param role Determine if content is used by get tag. If user is in role, content is used.
    310      */
    311     public void put(String name, Object content, String type, String role) {
    312         // Is there a type set ?
    313         // First check direct attribute, and translate it to a valueType.
    314         // Then, evaluate valueType, and create requested typed attribute.
    315         AttributeDefinition attribute = null;
    316 
    317         if (content != null
    318             && type != null
    319             && !(content instanceof AttributeDefinition)) {
    320 
    321             String strValue = content.toString();
    322             if (type.equalsIgnoreCase("string")) {
    323                 attribute = new DirectStringAttribute(strValue);
    324 
    325             } else if (type.equalsIgnoreCase("page")) {
    326                 attribute = new PathAttribute(strValue);
    327 
    328             } else if (type.equalsIgnoreCase("template")) {
    329                 attribute = new PathAttribute(strValue);
    330 
    331             } else if (type.equalsIgnoreCase("instance")) {
    332                 attribute = new DefinitionNameAttribute(strValue);
    333 
    334             } else if (type.equalsIgnoreCase("definition")) {
    335                 attribute = new DefinitionNameAttribute(strValue);
    336             }
    337         }
    338 
    339         putAttribute(name, attribute);
    340     }
    341 
    342     /**
    343      * Returns a description of the attributes.
    344      */
    345     public String toString() {
    346         return "{name="
    347             + name
    348             + ", path="
    349             + path
    350             + ", role="
    351             + role
    352             + ", controller="
    353             + controller
    354             + ", controllerType="
    355             + controllerType
    356             + ", controllerInstance="
    357             + controllerInstance
    358             + ", attributes="
    359             + attributes
    360             + "}\n";
    361     }
    362 
    363     /**
    364      * Get associated controller type.
    365      * Type denote a fully qualified classname.
    366      */
    367     public String getControllerType() {
    368         return controllerType;
    369     }
    370 
    371     /**
    372      * Set associated controller type.
    373      * Type denote a fully qualified classname.
    374      * @param controllerType Typeof associated controller
    375      */
    376     public void setControllerType(String controllerType) {
    377         this.controllerType = controllerType;
    378     }
    379 
    380     /**
    381      * Set associated controller name as an url, and controller
    382      * type as "url".
    383      * Name must be an url (not checked).
    384      * Convenience method.
    385      * @param controller Controller url
    386      */
    387     public void setControllerUrl(String controller) {
    388         setController(controller);
    389         setControllerType("url");
    390     }
    391 
    392     /**
    393      * Set associated controller name as a classtype, and controller
    394      * type as "classname".
    395      * Name denote a fully qualified classname
    396      * Convenience method.
    397      * @param controller Controller classname.
    398      */
    399     public void setControllerClass(String controller) {
    400         setController(controller);
    401         setControllerType("classname");
    402     }
    403 
    404     /**
    405      * Get associated controller local URL.
    406      * URL should be local to webcontainer in order to allow request context followup.
    407      * URL comes as a string.
    408      */
    409     public String getController() {
    410         return controller;
    411     }
    412 
    413     /**
    414      * Set associated controller URL.
    415      * URL should be local to webcontainer in order to allow request context followup.
    416      * URL is specified as a string.
    417      * @param url Url called locally
    418      */
    419     public void setController(String url) {
    420         this.controller = url;
    421     }
    422 
    423     /**
    424      * Get controller instance.
    425      * @return controller instance.
    426      */
    427     public Controller getControllerInstance() {
    428         return controllerInstance;
    429     }
    430 
    431     /**
    432      * Get or create controller.
    433      * Get controller, create it if necessary.
    434      * @return controller if controller or controllerType is set, null otherwise.
    435      * @throws InstantiationException if an error occur while instanciating Controller :
    436      * (classname can't be instanciated, Illegal access with instanciated class,
    437      * Error while instanciating class, classname can't be instanciated.
    438      */
    439     public Controller getOrCreateController() throws InstantiationException {
    440 
    441         if (controllerInstance != null) {
    442             return controllerInstance;
    443         }
    444 
    445         // Do we define a controller ?
    446         if (controller == null && controllerType == null) {
    447             return null;
    448         }
    449 
    450         // check parameters
    451         if (controllerType != null && controller == null) {
    452             throw new InstantiationException("Controller name should be defined if controllerType is set");
    453         }
    454 
    455         controllerInstance = createController(controller, controllerType);
    456 
    457         return controllerInstance;
    458     }
    459 
    460     /**
    461      * Set controller.
    462      */
    463     public void setControllerInstance(Controller controller) {
    464         this.controllerInstance = controller;
    465     }
    466 
    467     /**
    468      * Create a new instance of controller named in parameter.
    469      * If controllerType is specified, create controller accordingly.
    470      * Otherwise, if name denote a classname, create an instance of it. If class is
    471      *  subclass of org.apache.struts.action.Action, wrap controller
    472      * appropriately.
    473      * Otherwise, consider name as an url.
    474      * @param name Controller name (classname, url, ...)
    475      * @param controllerType Expected Controller type
    476      * @return org.apache.struts.tiles.Controller
    477      * @throws InstantiationException if an error occur while instanciating Controller :
    478      * (classname can't be instanciated, Illegal access with instanciated class,
    479      * Error while instanciating class, classname can't be instanciated.
    480      */
    481     public static Controller createController(String name, String controllerType)
    482         throws InstantiationException {
    483 
    484         if (log.isDebugEnabled()) {
    485             log.debug("Create controller name=" + name + ", type=" + controllerType);
    486         }
    487 
    488         Controller controller = null;
    489 
    490         if (controllerType == null) { // first try as a classname
    491             try {
    492                 return createControllerFromClassname(name);
    493 
    494             } catch (InstantiationException ex) { // ok, try something else
    495                 controller = new UrlController(name);
    496             }
    497 
    498         } else if ("url".equalsIgnoreCase(controllerType)) {
    499             controller = new UrlController(name);
    500 
    501         } else if ("classname".equalsIgnoreCase(controllerType)) {
    502             controller = createControllerFromClassname(name);
    503         }
    504 
    505         return controller;
    506     }
    507 
    508     /**
    509      * Create a controller from specified classname
    510      * @param classname Controller classname.
    511      * @return org.apache.struts.tiles.Controller
    512      * @throws InstantiationException if an error occur while instanciating Controller :
    513      * (classname can't be instanciated, Illegal access with instanciated class,
    514      * Error while instanciating class, classname can't be instanciated.
    515      */
    516     public static Controller createControllerFromClassname(String classname)
    517         throws InstantiationException {
    518 
    519         try {
    520             Class requestedClass = RequestUtils.applicationClass(classname);
    521             Object instance = requestedClass.newInstance();
    522 
    523             if (log.isDebugEnabled()) {
    524                 log.debug("Controller created : " + instance);
    525             }
    526             return (Controller) instance;
    527 
    528         } catch (java.lang.ClassNotFoundException ex) {
    529             throw new InstantiationException(
    530                 "Error - Class not found :" + ex.getMessage());
    531 
    532         } catch (java.lang.IllegalAccessException ex) {
    533             throw new InstantiationException(
    534                 "Error - Illegal class access :" + ex.getMessage());
    535 
    536         } catch (java.lang.InstantiationException ex) {
    537             throw ex;
    538 
    539         } catch (java.lang.ClassCastException ex) {
    540             throw new InstantiationException(
    541                 "Controller of class '"
    542                     + classname
    543                     + "' should implements 'Controller' or extends 'Action'");
    544         }
    545     }
    546 
    547 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
