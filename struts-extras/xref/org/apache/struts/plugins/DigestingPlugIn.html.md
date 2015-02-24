[View Javadoc](../../../../../apidocs/org/apache/struts/plugins/DigestingPlugIn.html.md)


    1   /*
    2    * $Id: DigestingPlugIn.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.plugins;
    22  
    23  import org.apache.commons.digester.Digester;
    24  import org.apache.commons.digester.RuleSet;
    25  import org.apache.commons.digester.xmlrules.DigesterLoader;
    26  import org.apache.commons.logging.Log;
    27  import org.apache.commons.logging.LogFactory;
    28  import org.apache.struts.action.ActionServlet;
    29  import org.apache.struts.action.PlugIn;
    30  import org.apache.struts.config.ModuleConfig;
    31  import org.apache.struts.util.RequestUtils;
    32  import org.xml.sax.SAXException;
    33  
    34  import javax.servlet.ServletException;
    35  
    36  import java.io.File;
    37  import java.io.IOException;
    38  
    39  import java.net.URL;
    40  import java.net.URLConnection;
    41  
    42  /**
    43   * <p>An implementation of <code>PlugIn</code> which can be configured to
    44   * instantiate a graph of objects using the Commons Digester and place the
    45   * root object of that graph into the Application context.</p>
    46   *
    47   * @version $Rev: 471754 $
    48   * @see org.apache.struts.action.PlugIn
    49   * @since Struts 1.2
    50   */
    51  public class DigestingPlugIn implements PlugIn {
    52      /**
    53       * Commons Logging instance.
    54       */
    55      private static Log log = LogFactory.getLog(DigestingPlugIn.class);
    56      protected static final String SOURCE_CLASSPATH = "classpath";
    57      protected static final String SOURCE_FILE = "file";
    58      protected static final String SOURCE_SERVLET = "servlet";
    59      protected String configPath = null;
    60      protected String configSource = SOURCE_SERVLET;
    61      protected String digesterPath = null;
    62      protected String digesterSource = SOURCE_SERVLET;
    63      protected String key = null;
    64      protected ModuleConfig moduleConfig = null;
    65      protected String rulesets = null;
    66      protected ActionServlet servlet = null;
    67      protected boolean push = false;
    68  
    69      /**
    70       * Constructor for DigestingPlugIn.
    71       */
    72      public DigestingPlugIn() {
    73          super();
    74      }
    75  
    76      /**
    77       * Receive notification that our owning module is being shut down.
    78       */
    79      public void destroy() {
    80          this.servlet = null;
    81          this.moduleConfig = null;
    82      }
    83  
    84      /**
    85       * <p>Initialize a <code>Digester</code> and use it to parse a
    86       * configuration file, resulting in a root object which will be placed
    87       * into the ServletContext.</p>
    88       *
    89       * @param servlet ActionServlet that is managing all the modules in this
    90       *                web application
    91       * @param config  ModuleConfig for the module with which this plug-in is
    92       *                associated
    93       * @throws ServletException if this <code>PlugIn</code> cannot be
    94       *                          successfully initialized
    95       */
    96      public void init(ActionServlet servlet, ModuleConfig config)
    97          throws ServletException {
    98          this.servlet = servlet;
    99          this.moduleConfig = config;
    100 
    101         Object obj = null;
    102 
    103         Digester digester = this.initializeDigester();
    104 
    105         if (this.push) {
    106             log.debug("push == true; pushing plugin onto digester stack");
    107             digester.push(this);
    108         }
    109 
    110         try {
    111             log.debug("XML data file: [path: " + this.configPath + ", source: "
    112                 + this.configSource + "]");
    113 
    114             URL configURL =
    115                 this.getConfigURL(this.configPath, this.configSource);
    116 
    117             if (configURL == null) {
    118                 throw new ServletException(
    119                     "Unable to locate XML data file at [path: "
    120                     + this.configPath + ", source: " + this.configSource + "]");
    121             }
    122 
    123             URLConnection conn = configURL.openConnection();
    124 
    125             conn.setUseCaches(false);
    126             conn.connect();
    127             obj = digester.parse(conn.getInputStream());
    128         } catch (IOException e) {
    129             // TODO Internationalize msg
    130             log.error("Exception processing config", e);
    131             throw new ServletException(e);
    132         } catch (SAXException e) {
    133             // TODO Internationalize msg
    134             log.error("Exception processing config", e);
    135             throw new ServletException(e);
    136         }
    137 
    138         this.storeGeneratedObject(obj);
    139     }
    140 
    141     /**
    142      * Initialize the <code>Digester</code> which will be used to process the
    143      * main configuration.
    144      *
    145      * @return a Digester, ready to use.
    146      * @throws ServletException
    147      */
    148     protected Digester initializeDigester()
    149         throws ServletException {
    150         Digester digester = null;
    151 
    152         if ((this.digesterPath != null) && (this.digesterSource != null)) {
    153             try {
    154                 log.debug("Initialize digester from XML [path: "
    155                     + this.digesterPath + "; source: " + this.digesterSource
    156                     + "]");
    157                 digester =
    158                     this.digesterFromXml(this.digesterPath, this.digesterSource);
    159             } catch (IOException e) {
    160                 // TODO Internationalize msg
    161                 log.error("Exception instantiating digester from XML ", e);
    162                 throw new ServletException(e);
    163             }
    164         } else {
    165             log.debug("No XML rules for digester; call newDigesterInstance()");
    166             digester = this.newDigesterInstance();
    167         }
    168 
    169         this.applyRuleSets(digester);
    170 
    171         return digester;
    172     }
    173 
    174     /**
    175      * <p>Instantiate a <code>Digester</code>.</p> <p>Subclasses may wish to
    176      * override this to provide a subclass of Digester, or to configure the
    177      * Digester using object methods.</p>
    178      *
    179      * @return a basic instance of <code>org.apache.commons.digester.Digester</code>
    180      */
    181     protected Digester newDigesterInstance() {
    182         return new Digester();
    183     }
    184 
    185     /**
    186      * <p>Instantiate a Digester from an XML input stream using the Commons
    187      * <code>DigesterLoader</code>.</p>
    188      *
    189      * @param path   the path to the digester rules XML to be found using
    190      *               <code>source</code>
    191      * @param source a string indicating the lookup method to be used with
    192      *               <code>path</code>
    193      * @return a configured Digester
    194      * @throws FileNotFoundException
    195      * @throws MalformedURLException
    196      * @see #getConfigURL(String, String)
    197      */
    198     protected Digester digesterFromXml(String path, String source)
    199         throws IOException {
    200         URL configURL = this.getConfigURL(path, source);
    201 
    202         if (configURL == null) {
    203             throw new NullPointerException("No resource '" + path
    204                 + "' found in '" + source + "'");
    205         }
    206 
    207         return DigesterLoader.createDigester(configURL);
    208     }
    209 
    210     /**
    211      * Instantiate any <code>RuleSet</code> classes defined in the
    212      * <code>rulesets</code> property and use them to add rules to our
    213      * <code>Digester</code>.
    214      *
    215      * @param digester the Digester instance to add RuleSet objects to.
    216      * @throws ServletException
    217      */
    218     protected void applyRuleSets(Digester digester)
    219         throws ServletException {
    220         if ((this.rulesets == null) || (this.rulesets.trim().length() == 0)) {
    221             return;
    222         }
    223 
    224         rulesets = rulesets.trim();
    225 
    226         String ruleSet = null;
    227 
    228         while (rulesets.length() > 0) {
    229             int comma = rulesets.indexOf(",");
    230 
    231             if (comma < 0) {
    232                 ruleSet = rulesets.trim();
    233                 rulesets = "";
    234             } else {
    235                 ruleSet = rulesets.substring(0, comma).trim();
    236                 rulesets = rulesets.substring(comma + 1).trim();
    237             }
    238 
    239             if (log.isDebugEnabled()) {
    240                 // TODO Internationalize msg
    241                 log.debug("Configuring custom Digester Ruleset of type "
    242                     + ruleSet);
    243             }
    244 
    245             try {
    246                 RuleSet instance =
    247                     (RuleSet) RequestUtils.applicationInstance(ruleSet);
    248 
    249                 digester.addRuleSet(instance);
    250             } catch (Exception e) {
    251                 // TODO Internationalize msg
    252                 log.error("Exception configuring custom Digester RuleSet", e);
    253                 throw new ServletException(e);
    254             }
    255         }
    256     }
    257 
    258     /**
    259      * <p>Look up a resource path using one of a set of known path resolution
    260      * mechanisms and return a URL to the resource.</p>
    261      *
    262      * @param path   a String which is meaningful to one of the known
    263      *               resolution mechanisms.
    264      * @param source one of the known path resolution mechanisms:
    265      *
    266      *               <ul>
    267      *
    268      *               <li>file - the path is a fully-qualified filesystem
    269      *               path.</li>
    270      *
    271      *               <li>servlet - the path is a servlet-context relative
    272      *               path.</li>
    273      *
    274      *               <li>classpath - the path is a classpath-relative
    275      *               path.</li>
    276      *
    277      *               </ul>
    278      * @return a URL pointing to the given path in the given mechanism.
    279      * @throws java.io.FileNotFoundException
    280      * @throws java.net.MalformedURLException
    281      */
    282     protected URL getConfigURL(String path, String source)
    283         throws IOException {
    284         if (SOURCE_CLASSPATH.equals(source)) {
    285             return this.getClassPathURL(path);
    286         }
    287 
    288         if (SOURCE_FILE.equals(source)) {
    289             return this.getFileURL(path);
    290         }
    291 
    292         if (SOURCE_SERVLET.equals(source)) {
    293             return this.getServletContextURL(path);
    294         }
    295 
    296         // TODO Internationalize msg
    297         throw new IllegalArgumentException("ConfigSource " + source
    298             + " is not recognized");
    299     }
    300 
    301     /**
    302      * Given a string, return a URL to a classpath resource of that name.
    303      *
    304      * @param path a Classpath-relative string identifying a resource.
    305      * @return a URL identifying the resource on the classpath. TODO Do we
    306      *         need to be smarter about ClassLoaders?
    307      */
    308     protected URL getClassPathURL(String path) {
    309         return getClass().getClassLoader().getResource(path);
    310     }
    311 
    312     /**
    313      * Given a string, return a URL to a Servlet Context resource of that
    314      * name.
    315      *
    316      * @param path a Classpath-relative string identifying a resource.
    317      * @return a URL identifying the resource in the Servlet Context
    318      * @throws MalformedURLException
    319      */
    320     protected URL getServletContextURL(String path)
    321         throws IOException {
    322         return this.servlet.getServletContext().getResource(path);
    323     }
    324 
    325     /**
    326      * Given a string, return a URL to a Filesystem resource of that name.
    327      *
    328      * @param path a path to a file.
    329      * @return a URL identifying the resource in the in the file system.
    330      * @throws MalformedURLException
    331      * @throws FileNotFoundException
    332      */
    333     protected URL getFileURL(String path)
    334         throws IOException {
    335         File file = new File(path);
    336 
    337         return file.toURL();
    338     }
    339 
    340     /**
    341      * @param configPath the path to configuration information for this
    342      *                   PlugIn.
    343      * @see #configSource
    344      */
    345     public void setConfigPath(String configPath) {
    346         this.configPath = configPath;
    347     }
    348 
    349     /**
    350      * @return the configPath property
    351      * @see #configSource
    352      */
    353     public String getConfigPath() {
    354         return configPath;
    355     }
    356 
    357     /**
    358      * Set the source of the config file.  Should be one of the following:
    359      * <ul> <li> "classpath" - indicates that the configPath will be resolved
    360      * by the ClassLoader. </li> <li> "file" - indicates that the configPath
    361      * is a fully-qualified filesystem path. </li> <li> "servlet" - indicates
    362      * that the configPath will be found by the ServletContext. </li> </ul>
    363      *
    364      * @param configSource the source (lookup method) for the config file.
    365      * @see #configPath
    366      */
    367     public void setConfigSource(String configSource) {
    368         this.configSource = configSource;
    369     }
    370 
    371     /**
    372      * @return the string describing which access method should be used to
    373      *         resolve configPath.
    374      * @see #configPath
    375      */
    376     public String getConfigSource() {
    377         return configSource;
    378     }
    379 
    380     /**
    381      * This method is called after the Digester runs to store the generated
    382      * object somewhere.  This implementation places the given object into the
    383      * ServletContext under the attribute name as defined in
    384      * <code>key</code>.
    385      *
    386      * @param obj The object to save.
    387      */
    388     protected void storeGeneratedObject(Object obj) {
    389         log.debug("Put [" + obj + "] into application context [key:" + this.key
    390             + "]");
    391         this.servlet.getServletContext().setAttribute(this.getKey(), obj);
    392     }
    393 
    394     /**
    395      * @param key The ServletContext attribute name to store the generated
    396      *            object under.
    397      */
    398     public void setKey(String key) {
    399         this.key = key;
    400     }
    401 
    402     /**
    403      * @return The ServletContext attribute name the generated object is
    404      *         stored under.
    405      */
    406     public String getKey() {
    407         return key;
    408     }
    409 
    410     /**
    411      * <p>A comma-delimited list of one or more classes which implement
    412      * <code>org.apache.commons.digester.RuleSet</code>. (Optional)</p>
    413      */
    414     public void setRulesets(String ruleSets) {
    415         this.rulesets = ruleSets;
    416     }
    417 
    418     /**
    419      * @return The configured list of <code>RuleSet</code> classes.
    420      */
    421     public String getRulesets() {
    422         return this.rulesets;
    423     }
    424 
    425     /**
    426      * <p>The path to a Digester XML configuration file, relative to the
    427      * <code>digesterSource</code> property. (Optional)</p>
    428      *
    429      * @see #digesterSource
    430      * @see #getConfigURL(String, String)
    431      */
    432     public void setDigesterPath(String digesterPath) {
    433         this.digesterPath = digesterPath;
    434     }
    435 
    436     /**
    437      * @return the configured path to a Digester XML config file, or null.
    438      * @see #digesterSource
    439      * @see #getConfigURL(String, String)
    440      */
    441     public String getDigesterPath() {
    442         return digesterPath;
    443     }
    444 
    445     /**
    446      * <p>The lookup mechanism to be used to resolve <code>digesterPath</code>
    447      * (optional). </p>
    448      *
    449      * @param digesterSource
    450      * @see #getConfigURL(String, String)
    451      */
    452     public void setDigesterSource(String digesterSource) {
    453         this.digesterSource = digesterSource;
    454     }
    455 
    456     /**
    457      * @return the configured lookup mechanism for resolving
    458      *         <code>digesterPath</code>.
    459      * @see #getConfigURL(String, String)
    460      */
    461     public String getDigesterSource() {
    462         return this.digesterSource;
    463     }
    464 
    465     /**
    466      * <p>If set to <code>true</code>, this PlugIn will be pushed onto the
    467      * Digester stack before the digester <code>parse</code> method is
    468      * called.</p> <p>Defaults to <code>false</code></p>
    469      *
    470      * @param push
    471      */
    472     public void setPush(boolean push) {
    473         this.push = push;
    474     }
    475 
    476     /**
    477      * @return Whether or not this <code>PlugIn</code> instance will be pushed
    478      *         onto the <code>Digester</code> stack before
    479      *         <code>digester.parse()</code> is called.
    480      */
    481     public boolean getPush() {
    482         return this.push;
    483     }
    484 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
