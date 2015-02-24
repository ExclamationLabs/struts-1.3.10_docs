[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionRedirect.html.md)


    1   /*
    2    * $Id: ActionRedirect.java 513602 2007-03-02 02:50:23Z pbenedict $
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
    21  package org.apache.struts.action;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.config.ForwardConfig;
    26  import org.apache.struts.util.ResponseUtils;
    27  
    28  import java.util.ArrayList;
    29  import java.util.Arrays;
    30  import java.util.HashMap;
    31  import java.util.Iterator;
    32  import java.util.List;
    33  import java.util.Map;
    34  
    35  /**
    36   * <p> A subclass of {@link ActionForward} which is designed for use in
    37   * redirecting requests, with support for adding parameters at runtime. <br/>
    38   * An {@link ForwardConfig} (or subclass) can be passed to the constructor to
    39   * copy its configuration: </p> <p>
    40   * <pre>
    41   * public ActionForward execute(ActionMapping mapping,
    42   *                              ActionForm form,
    43   *                              HttpServletRequest request,
    44   *                              HttpServletResponse response)
    45   *         throws Exception {
    46   *     ActionRedirect redirect =
    47   *             new ActionRedirect(mapping.findForward("doRedirect"));
    48   *     redirect.addParameter("param1","value1");
    49   *     redirect.addParameter("param2","2");
    50   *     redirect.addParameter("param3","3.0");
    51   *     return redirect;
    52   * }
    53   * </pre>
    54   * </p>
    55   *
    56   * @version $Rev: 513602 $ $Date: 2007-03-01 20:50:23 -0600 (Thu, 01 Mar 2007) $
    57   */
    58  public class ActionRedirect extends ActionForward {
    59      // ----------------------------------------------------- Manifest constants
    60  
    61      /**
    62       * <p>Default allocation size for string buffers.</p>
    63       */
    64      private static final int DEFAULT_BUFFER_SIZE = 256;
    65  
    66      // ----------------------------------------------------- Static variables
    67  
    68      /**
    69       * <p>Commons logging instance.</p>
    70       */
    71      protected static final Log LOG = LogFactory.getLog(ActionRedirect.class);
    72  
    73      // ----------------------------------------------------- Instance variables
    74  
    75      /**
    76       * <p>Holds the redirect parameters. Each entry is either a String or a
    77       * String[] depending on whether it has one or more entries.</p>
    78       */
    79      protected Map parameterValues = null;
    80  
    81      /**
    82       * <p>Holds the anchor value.</p>
    83       */
    84      protected String anchorValue = null;
    85  
    86      // ----------------------------------------------------- Constructors
    87  
    88      /**
    89       * <p>Construct a new instance with redirect set to true and initialize
    90       * parameter lists.</p>
    91       */
    92      public ActionRedirect() {
    93          setRedirect(true);
    94          initializeParameters();
    95      }
    96  
    97      /**
    98       * <p>Construct a new instance with the specified path and initialize
    99       * parameter lists.</p>
    100      *
    101      * @param path Path for this instance
    102      */
    103     public ActionRedirect(String path) {
    104         super(path);
    105         setRedirect(true);
    106         initializeParameters();
    107     }
    108 
    109     /**
    110      * <p>Construct a new instance with the specified values and initialize
    111      * parameter lists.</p>
    112      *
    113      * @param name   Name of this instance
    114      * @param path   Path for this instance
    115      * @param module Module prefix, if any
    116      */
    117     public ActionRedirect(String name, String path, String module) {
    118         super(name, path, true);
    119         setModule(module);
    120         initializeParameters();
    121     }
    122 
    123     /**
    124      * <p>Construct a new instance with a {@link ForwardConfig} object to copy
    125      * name, path, contextRelative, and arbitrary property values from.</p>
    126      *
    127      * @param baseConfig the {@link ForwardConfig} to copy configuration
    128      *                   values from
    129      */
    130     public ActionRedirect(ForwardConfig baseConfig) {
    131         setName(baseConfig.getName());
    132         setPath(baseConfig.getPath());
    133         setModule(baseConfig.getModule());
    134         setRedirect(true);
    135         inheritProperties(baseConfig);
    136         initializeParameters();
    137     }
    138 
    139     // ----------------------------------------------------- Private methods
    140 
    141     /**
    142      * <p>Initializes the internal objects used to hold parameter values.</p>
    143      */
    144     private void initializeParameters() {
    145         parameterValues = new HashMap();
    146     }
    147 
    148     // ----------------------------------------------------- Public methods
    149 
    150     /**
    151      * <p>Adds the object's toString() to the list of parameters if it's not
    152      * null, or an empty string with the given fieldName if it is.</p>
    153      *
    154      * @param fieldName the name to use for the parameter
    155      * @param valueObj  the value for this parameter
    156      * @return The ActionRedirect instance this method is called on
    157      */
    158     public ActionRedirect addParameter(String fieldName, Object valueObj) {
    159         String value = (valueObj != null) ? valueObj.toString() : "";
    160 
    161         if (parameterValues == null) {
    162             initializeParameters();
    163         }
    164 
    165         //try {
    166         value = ResponseUtils.encodeURL(value);
    167 
    168         //} catch (UnsupportedEncodingException uce) {
    169         // this shouldn't happen since UTF-8 is the W3C Recommendation
    170         //     String errorMsg = "UTF-8 Character Encoding not supported";
    171         //     LOG.error(errorMsg, uce);
    172         //     throw new RuntimeException(errorMsg, uce);
    173         // }
    174         Object currentValue = parameterValues.get(fieldName);
    175 
    176         if (currentValue == null) {
    177             // there's no value for this param yet; add it to the map
    178             parameterValues.put(fieldName, value);
    179         } else if (currentValue instanceof String) {
    180             // there's already a value; let's use an array for these parameters
    181             String[] newValue = new String[2];
    182 
    183             newValue[0] = (String) currentValue;
    184             newValue[1] = value;
    185             parameterValues.put(fieldName, newValue);
    186         } else if (currentValue instanceof String[]) {
    187             // add the value to the list of existing values
    188             List newValues =
    189                 new ArrayList(Arrays.asList((Object[]) currentValue));
    190 
    191             newValues.add(value);
    192             parameterValues.put(fieldName,
    193                 newValues.toArray(new String[newValues.size()]));
    194         }
    195         return this;
    196     }
    197 
    198     /**
    199      * <p>Adds an anchor to the path.  Technically, the anchor value is
    200      * just stored for later and will be added to the path in getPath().
    201      * Note that this is a considerably simpler method than the
    202      * addParmaeter method because aside from encoding the value, there
    203      * isn't really anything to do.  Passing in null is fine because that
    204      * is the value that will be checked for later to determine whether
    205      * to append an anchor to the path or not.</p>
    206      *
    207      * @param anchorValue The anchor to append to the path
    208      * @return The ActionRefirect instance this method is called on
    209      */
    210     public ActionRedirect setAnchor(String anchorValue) {
    211         this.anchorValue = ResponseUtils.encodeURL(anchorValue);
    212         return this;
    213     }
    214 
    215     /**
    216      * <p>Get the original path without the parameters added at runtime.</p>
    217      *
    218      * @return the original path as configured.
    219      */
    220     public String getOriginalPath() {
    221         return super.getPath();
    222     }
    223 
    224     /**
    225      * <p>Get the path for this object, including any parameters that may have
    226      * been added at runtime.</p>
    227      *
    228      * @return The path for this object.
    229      */
    230     public String getPath() {
    231         // get the original path and the parameter string that was formed
    232         String originalPath = getOriginalPath();
    233         String parameterString = getParameterString();
    234         String anchorString = getAnchorString();
    235 
    236         StringBuffer result = new StringBuffer(originalPath);
    237 
    238         if ((parameterString != null) && (parameterString.length() > 0)) {
    239             // the parameter separator we're going to use
    240             String paramSeparator = "?";
    241 
    242             // true if we need to use a parameter separator after originalPath
    243             boolean needsParamSeparator = true;
    244 
    245             // does the original path already have a "?"?
    246             int paramStartIndex = originalPath.indexOf("?");
    247 
    248             if (paramStartIndex > 0) {
    249                 // did the path end with "?"?
    250                 needsParamSeparator = (paramStartIndex != (originalPath.length()
    251                     - 1));
    252 
    253                 if (needsParamSeparator) {
    254                     paramSeparator = "&";
    255                 }
    256             }
    257 
    258             if (needsParamSeparator) {
    259                 result.append(paramSeparator);
    260             }
    261 
    262             result.append(parameterString);
    263         }
    264 
    265         // append anchor string (or blank if none was set)
    266         result.append(anchorString);
    267 
    268 
    269         return result.toString();
    270     }
    271 
    272     /**
    273      * <p>Forms the string containing the parameters
    274      *  passed onto this object thru calls to addParameter().</p>
    275      *
    276      * @return a string which can be appended to the URLs.  The
    277      *    return string includes a leading hash
    278      *    mark (#).
    279      */
    280     public String getAnchorString() {
    281         String retVal = "";
    282         if (anchorValue != null) {
    283             retVal = "#" + anchorValue;
    284         }
    285         return retVal;
    286     }
    287 
    288     /**
    289      * <p>Forms the string containing the parameters passed onto this object
    290      * thru calls to addParameter().</p>
    291      *
    292      * @return a string which can be appended to the URLs.  The return string
    293      *         does not include a leading question mark (?).
    294      */
    295     public String getParameterString() {
    296         StringBuffer strParam = new StringBuffer(DEFAULT_BUFFER_SIZE);
    297 
    298         // loop through all parameters
    299         Iterator iterator = parameterValues.keySet().iterator();
    300 
    301         while (iterator.hasNext()) {
    302             // get the parameter name
    303             String paramName = (String) iterator.next();
    304 
    305             // get the value for this parameter
    306             Object value = parameterValues.get(paramName);
    307 
    308             if (value instanceof String) {
    309                 // just one value for this param
    310                 strParam.append(paramName).append("=").append(value);
    311             } else if (value instanceof String[]) {
    312                 // loop through all values for this param
    313                 String[] values = (String[]) value;
    314 
    315                 for (int i = 0; i < values.length; i++) {
    316                     strParam.append(paramName).append("=").append(values[i]);
    317 
    318                     if (i < (values.length - 1)) {
    319                         strParam.append("&");
    320                     }
    321                 }
    322             }
    323 
    324             if (iterator.hasNext()) {
    325                 strParam.append("&");
    326             }
    327         }
    328 
    329         return strParam.toString();
    330     }
    331 
    332     // ----------------------------------------------------- toString()
    333 
    334     /**
    335      * <p>Return a string description of this object.</p>
    336      *
    337      * @return a string containing the original path for this object and the
    338      *         parameters it currently holds
    339      */
    340     public String toString() {
    341         StringBuffer result = new StringBuffer(DEFAULT_BUFFER_SIZE);
    342 
    343         result.append("ActionRedirect [");
    344         result.append("originalPath=").append(getOriginalPath()).append(";");
    345         result.append("parameterString=").append(getParameterString()).append("]");
    346         result.append("anchorString=").append(getAnchorString()).append("]");
    347 
    348         return result.toString();
    349     }
    350 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
