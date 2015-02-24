[View Javadoc](../../../../../apidocs/org/apache/struts/scripting/ScriptAction.html.md)


    1   /*
    2    * $Id: ScriptAction.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.scripting;
    22  
    23  // util imports:
    24  import java.util.ArrayList;
    25  import java.util.Enumeration;
    26  import java.util.Hashtable;
    27  import java.util.List;
    28  import java.util.Locale;
    29  import java.util.Map;
    30  import java.util.Properties;
    31  import java.util.StringTokenizer;
    32  
    33  // io imports:
    34  import java.io.File;
    35  import java.io.FileReader;
    36  import java.io.IOException;
    37  import java.io.InputStream;
    38  
    39  // logging imports:
    40  import org.apache.commons.logging.Log;
    41  import org.apache.commons.logging.LogFactory;
    42  
    43  // struts imports:
    44  import org.apache.struts.action.Action;
    45  import org.apache.struts.action.ActionErrors;
    46  import org.apache.struts.action.ActionForm;
    47  import org.apache.struts.action.ActionForward;
    48  import org.apache.struts.action.ActionMapping;
    49  import org.apache.struts.action.ActionMessages;
    50  
    51  // misc imports:
    52  import javax.servlet.ServletContext;
    53  import javax.servlet.http.HttpServletRequest;
    54  import javax.servlet.http.HttpServletResponse;
    55  import javax.servlet.http.HttpSession;
    56  import org.apache.bsf.BSFException;
    57  import org.apache.bsf.BSFManager;
    58  import org.apache.bsf.util.IOUtils;
    59  
    60  
    61  /**
    62   *  This Action uses scripts to perform its action. The scripting framework is
    63   *  Apache's Bean Scripting Framework which allows the scripts to be written
    64   *  many of the popular scripting languages including JavaScript, Perl, Python,
    65   *  and even VBA. <br />
    66   *  <br />
    67   *  To determine what script will be executed, the "parameter" attribute of the
    68   *  action mapping should contain the name of the script relative to the web
    69   *  application root directory (i.e. http://server/app). <br />
    70   *  <br />
    71   *  Before the script completes, the next ActionForward needs to be specified.
    72   *  This can be done one of two ways:
    73   *  <ol>
    74   *    <li> Set <code>struts.forwardName</code> to the name of the forward</li>
    75   *
    76   *    <li> Set <code>struts.forward</code> to the actual ActionForward object
    77   *    </li>
    78   *  </ol>
    79   *  A number of pre-defined variables are available to the script:
    80   *  <ul>
    81   *    <li> <code>request</code> - The HTTP request</li>
    82   *    <li> <code>response</code> - The HTTP response</li>
    83   *    <li> <code>session</code> - The session</li>
    84   *    <li> <code>application</code> - The servlet context</li>
    85   *    <li> <code>struts</code> - A grouping of all Struts-related objects</li>
    86   *
    87   *    <li> <code>log</code> - A logging instance</li>
    88   *  </ul>
    89   *  You can add your own variables by creating a BSFManagerFilter and
    90   *  configuring it in struts-scripting.properties:
    91   *  <ul>
    92   *    <li> <code>struts-scripting.filters.FILTER_NAME.class=FILTER_CLASS</code>
    93   *    - The class implementing BSFManagerFilter where FILTER_NAME is the name
    94   *    you are calling the filter.</li>
    95   *    <li> <code>
    96   *     struts-scripting.filters.FILTER_NAME.PROPERTY_NAME=PROPERTY_VALUE
    97   *      </code> - A property to be used by the filter.</li>
    98   *  </ul>
    99   *  <br />
    100  *  <br />
    101  *  To use other scripting engines other than BeanShell, create a file called
    102  *  <code>struts-scripting.properties</code> and add two properties for each
    103  *  engine:
    104  *  <ul>
    105  *    <li> <code>struts-scripting.engine.ENGINE_NAME.class</code> - The class of
    106  *    the BSF engine where ENGINE_NAME is the name you are calling the engine.
    107  *    </li>
    108  *    <li> <code>struts-scripting.engine.ENGINE_NAME.extensions</code> - A
    109  *    comma-delimited list of file extensions that will be used to identify the
    110  *    engine to use to execute the script.</li>
    111  *  </ul>
    112  *  This code was originally based off code from JPublish, but has since been
    113  *  almost completely rewritten.
    114  */
    115 public class ScriptAction extends Action {
    116 
    117     /**  The logging instance. */
    118     protected static final Log LOG = LogFactory.getLog(ScriptAction.class);
    119 
    120     /**  The default path to the properties file. */
    121     protected static final String PROPS_PATH = "/struts-scripting.properties";
    122 
    123     /**  The base property for alternate BSF engines. */
    124     protected static final String ENGINE_BASE = "struts-scripting.engine.";
    125 
    126     /**  The base property for classes that put new variables in the context. */
    127     protected static final String FILTERS_BASE = "struts-scripting.filters.";
    128 
    129     /**  A list of initialized filters. */
    130     private static BSFManagerFilter[] filters = null;
    131 
    132     /**  Holds the "compiled" scripts and their information. */
    133     private Map scripts = new Hashtable();
    134 
    135     static {
    136         Properties props = new Properties();
    137         try {
    138             InputStream in =
    139                     ScriptAction.class.getClassLoader()
    140                     .getResourceAsStream(PROPS_PATH);
    141             if (in == null) {
    142                 in =
    143                         ScriptAction.class.getClassLoader().getResourceAsStream(
    144                         "/struts-bsf.properties");
    145                 if (in != null) {
    146                     LOG.warn("The struts-bsf.properties file has been "
    147                             + "deprecated.  Please use "
    148                             + "struts-scripting.properties instead.");
    149                 } else {
    150                     LOG.warn("struts-scripting.properties not found, using "
    151                              + "default engine mappings.");
    152                 }
    153             }
    154 
    155             if (in != null) {
    156                 props.load(in);
    157             }
    158         } catch (Exception ex) {
    159             LOG.warn("Unable to load struts-scripting.properties, using "
    160                      + " default engine mappings.");
    161         }
    162         int pos = ENGINE_BASE.length();
    163         for (Enumeration e = props.propertyNames(); e.hasMoreElements();) {
    164             String name = (String) e.nextElement();
    165             if (name.startsWith(ENGINE_BASE) && name.endsWith(".class")) {
    166                 String type = name.substring(pos, name.indexOf('.', pos));
    167                 String cls = props.getProperty(name);
    168                 String ext = props.getProperty(ENGINE_BASE + type
    169                          + ".extensions", "");
    170                 String[] exts = split(ext, ",");
    171                 if (LOG.isInfoEnabled()) {
    172                     LOG.info("Loading BSF engine name:" + type + " class:"
    173                              + cls + " ext:" + ext);
    174                 }
    175                 BSFManager.registerScriptingEngine(type, cls, exts);
    176             }
    177         }
    178         filters = loadFilters(props);
    179     }
    180 
    181 
    182     /**
    183      *  Executes the script.
    184      *
    185      *@param  mapping        The action mapping
    186      *@param  form           The action form
    187      *@param  request        The request object
    188      *@param  response       The response object
    189      *@return                The action forward
    190      *@exception  Exception  If something goes wrong
    191      */
    192     public ActionForward execute(ActionMapping mapping,
    193             ActionForm form,
    194             HttpServletRequest request,
    195             HttpServletResponse response)
    196              throws Exception {
    197 
    198         BSFManager bsfManager = new BSFManager();
    199 
    200         String scriptName = null;
    201         try {
    202             scriptName = parseScriptName(mapping.getParameter(), bsfManager);
    203         } catch (Exception ex) {
    204             LOG.error("Unable to parse " + mapping.getParameter(), ex);
    205             throw new Exception("Unable to parse " + mapping.getParameter());
    206         }
    207         if (scriptName == null) {
    208             LOG.error("No script specified in the parameter attribute");
    209             throw new Exception("No script specified");
    210         }
    211 
    212         if (LOG.isDebugEnabled()) {
    213             LOG.debug("Executing script: " + scriptName);
    214         }
    215 
    216         HttpSession session = request.getSession();
    217         ServletContext application = getServlet().getServletContext();
    218 
    219         Script script = loadScript(scriptName, application);
    220 
    221         bsfManager.declareBean("request", request,
    222                 HttpServletRequest.class);
    223 
    224         bsfManager.declareBean("response", response,
    225                 HttpServletResponse.class);
    226 
    227         if (session == null) {
    228             LOG.debug("HTTP session is null");
    229         } else {
    230             bsfManager.declareBean("session", session, HttpSession.class);
    231         }
    232 
    233         bsfManager.declareBean("application", application,
    234                 ServletContext.class);
    235 
    236         bsfManager.declareBean("log", LOG, Log.class);
    237         StrutsInfo struts = new StrutsInfo(this, mapping, form,
    238                 getResources(request));
    239         bsfManager.declareBean("struts", struts, StrutsInfo.class);
    240 
    241         for (int x = 0; x < filters.length; x++) {
    242             filters[x].apply(bsfManager);
    243         }
    244 
    245         bsfManager.exec(script.lang, script.file.getCanonicalPath(), 0, 0,
    246                 script.string);
    247 
    248         ActionForward af = struts.getForward();
    249         return af;
    250     }
    251 
    252 
    253     /**
    254      *  Parses the script name and puts any url parameters in the context.
    255      *
    256      *@param  url            The script url consisting of a path and optional
    257      *      parameters
    258      *@param  manager        The BSF manager to declare new parameters in
    259      *@return                The name of the script to execute
    260      *@exception  Exception  If something goes wrong
    261      */
    262     protected String parseScriptName(String url, BSFManager manager)
    263              throws Exception {
    264         if (LOG.isDebugEnabled()) {
    265             LOG.debug("Parsing " + url);
    266         }
    267         String name = null;
    268         if (url != null) {
    269             String[] parsed = split(url, "?");
    270             name = parsed[0];
    271             if (parsed.length == 2) {
    272                 if (LOG.isDebugEnabled()) {
    273                     LOG.debug("Found a query string");
    274                 }
    275                 String[] args = split(parsed[1], "&");
    276                 for (int x = 0; x < args.length; x++) {
    277                     String[] param = split(args[x], "=");
    278                     Object o = manager.lookupBean(param[0]);
    279                     if (o != null) {
    280                         LOG.warn("BSF variable " + param[0]
    281                                  + " already exists");
    282                         param[0] = "_" + param[0];
    283                     }
    284                     manager.declareBean(param[0], param[1], String.class);
    285                     if (LOG.isDebugEnabled()) {
    286                         LOG.debug("Registering param " + param[0]
    287                                  + " with value " + param[1]);
    288                     }
    289                 }
    290             } else {
    291                 if (LOG.isDebugEnabled()) {
    292                     LOG.debug("No query string:" + parsed.length);
    293                 }
    294             }
    295         }
    296         return name;
    297     }
    298 
    299 
    300     /**
    301      *  Loads the script from cache if possible. Reloads if the script has been
    302      *  recently modified.
    303      *
    304      *@param  name     The name of the script
    305      *@param  context  The servlet context
    306      *@return          The script object
    307      */
    308     protected Script loadScript(String name, ServletContext context) {
    309 
    310         Script script = (Script) scripts.get(name);
    311         if (script == null) {
    312             script = new Script();
    313             script.file = new File(context.getRealPath(name));
    314             try {
    315                 script.lang =
    316                         BSFManager.getLangFromFilename(script.file.getName());
    317             } catch (BSFException ex) {
    318                 LOG.warn(ex, ex);
    319             }
    320         }
    321 
    322         boolean reloadScript = false;
    323         long scriptLastModified = script.file.lastModified();
    324         if (scriptLastModified > script.timeLastLoaded) {
    325             if (LOG.isDebugEnabled()) {
    326                 LOG.debug("Loading updated or new script: "
    327                         + script.file.getName());
    328             }
    329             reloadScript = true;
    330         }
    331 
    332         if (reloadScript || script.string == null) {
    333             synchronized (this) {
    334                 script.timeLastLoaded = System.currentTimeMillis();
    335                 FileReader reader = null;
    336                 try {
    337                     reader = new FileReader(script.file);
    338                     script.string = IOUtils.getStringFromReader(reader);
    339                 } catch (IOException ex) {
    340                     LOG.error("Unable to load script: " + script.file, ex);
    341                 } finally {
    342                     if (reader != null) {
    343                         try {
    344                             reader.close();
    345                         } catch (IOException ex) {
    346                             LOG.debug(ex, ex);
    347                         }
    348                     }
    349                 }
    350             }
    351         }
    352 
    353         return script;
    354     }
    355 
    356 
    357     /**
    358      *  Loads and initializes the filters.
    359      *
    360      *@param  props  The properties defining the filters
    361      *@return        An array of the loaded filters
    362      */
    363     protected static BSFManagerFilter[] loadFilters(Properties props) {
    364         ArrayList list = new ArrayList();
    365         for (Enumeration e = props.propertyNames(); e.hasMoreElements();) {
    366             String prop = (String) e.nextElement();
    367             if (prop.startsWith(FILTERS_BASE) && prop.endsWith("class")) {
    368                 String type = prop.substring(FILTERS_BASE.length(),
    369                         prop.indexOf(".", FILTERS_BASE.length()));
    370                 String claz = props.getProperty(prop);
    371                 try {
    372                     Class cls = Class.forName(claz);
    373                     BSFManagerFilter f = (BSFManagerFilter) cls.newInstance();
    374                     f.init(type, props);
    375                     list.add(f);
    376                     if (LOG.isInfoEnabled()) {
    377                         LOG.info("Loaded " + type + " filter: " + claz);
    378                     }
    379                 } catch (Exception ex) {
    380                     LOG.error("Unable to load " + type + " filter: " + claz);
    381                 }
    382             }
    383         }
    384         BSFManagerFilter[] filters = new BSFManagerFilter[list.size()];
    385         filters = (BSFManagerFilter[]) list.toArray(filters);
    386         return filters;
    387     }
    388 
    389 
    390     /**
    391      *  Splits a line with the given delimiter.
    392      *
    393      *@param  line       The line to split
    394      *@param  delimiter  The string to split with
    395      *@return            An array of substrings
    396      */
    397     protected static String[] split(String line, String delimiter) {
    398         if (line == null || "".equals(line)) {
    399             return new String[]{};
    400         }
    401 
    402         List lst = new ArrayList();
    403         for (Enumeration e = new StringTokenizer(line, delimiter);
    404             e.hasMoreElements();) {
    405             lst.add(e.nextElement());
    406         }
    407         String[] ret = new String[lst.size()];
    408         return (String[]) lst.toArray(ret);
    409     }
    410 
    411 
    412     // These methods seem necessary as some scripting engines are not able to
    413     // access Action's protected methods.  Ugly? yes... any suggestions?
    414 
    415     /**
    416      *  Saves a token.
    417      *
    418      *@param  req  The request object
    419      */
    420     public void saveToken(HttpServletRequest req) {
    421         super.saveToken(req);
    422     }
    423 
    424 
    425     /**
    426      *  Checks to see if the request is cancelled.
    427      *
    428      *@param  req  The request object
    429      *@return      True if cancelled
    430      */
    431     public boolean isCancelled(HttpServletRequest req) {
    432         return super.isCancelled(req);
    433     }
    434 
    435 
    436     /**
    437      *  Checks to see if the token is valid.
    438      *
    439      *@param  req  The request object
    440      *@return      True if valid
    441      */
    442     public boolean isTokenValid(HttpServletRequest req) {
    443         return super.isTokenValid(req);
    444     }
    445 
    446 
    447     /**
    448      *  Resets the token.
    449      *
    450      *@param  req  The request object
    451      */
    452     public void resetToken(HttpServletRequest req) {
    453         super.resetToken(req);
    454     }
    455 
    456 
    457     /**
    458      *  Gets the locale.
    459      *
    460      *@param  req  The request object
    461      *@return      The locale value
    462      */
    463     public Locale getLocale(HttpServletRequest req) {
    464         return super.getLocale(req);
    465     }
    466 
    467 
    468     /**
    469      *  Saves the messages to the request.
    470      *
    471      *@param  req  The request object
    472      *@param  mes  The action messages
    473      */
    474     public void saveMessages(HttpServletRequest req, ActionMessages mes) {
    475         super.saveMessages(req, mes);
    476     }
    477 
    478 
    479     /**
    480      *  Saves the errors to the request.
    481      *
    482      *@param  req    The request object
    483      *@param  errs   The action errors
    484      *@deprecated    Use saveErrors(HttpServletRequest, ActionMessages) instead.
    485      *      This will be removed after Struts 1.2.
    486      */
    487     public void saveErrors(HttpServletRequest req, ActionErrors errs) {
    488         super.saveErrors(req, errs);
    489     }
    490 
    491 
    492     /**  Represents a saved script. */
    493     class Script {
    494 
    495         /**  The script file. */
    496         public File file;
    497 
    498         /**  The language the script is in. */
    499         public String lang = null;
    500 
    501         /**  The time when the script was last used. */
    502         public long timeLastLoaded = 0;
    503 
    504         /**  The contents of the script file. */
    505         public String string = null;
    506     }
    507 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
