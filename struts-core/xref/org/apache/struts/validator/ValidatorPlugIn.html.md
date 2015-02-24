[View Javadoc](../../../../../apidocs/org/apache/struts/validator/ValidatorPlugIn.html.md)


    1   /*
    2    * $Id: ValidatorPlugIn.java 483039 2006-12-06 11:34:28Z niallp $
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
    21  package org.apache.struts.validator;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.commons.validator.ValidatorResources;
    26  import org.apache.struts.action.ActionServlet;
    27  import org.apache.struts.action.PlugIn;
    28  import org.apache.struts.config.ModuleConfig;
    29  import org.xml.sax.SAXException;
    30  
    31  import javax.servlet.ServletException;
    32  import javax.servlet.UnavailableException;
    33  
    34  import java.io.IOException;
    35  
    36  import java.net.URL;
    37  
    38  import java.util.ArrayList;
    39  import java.util.List;
    40  import java.util.StringTokenizer;
    41  
    42  /**
    43   * Loads <code>ValidatorResources</code> based on configuration in the
    44   * struts-config.xml file.
    45   *
    46   * @version $Rev: 483039 $ $Date: 2005-08-30 00:22:27 -0400 (Tue, 30 Aug 2005)
    47   *          $
    48   * @since Struts 1.1
    49   */
    50  public class ValidatorPlugIn implements PlugIn {
    51      /**
    52       * Commons Logging instance.
    53       */
    54      private static Log log = LogFactory.getLog(ValidatorPlugIn.class);
    55  
    56      /**
    57       * Delimitter for Validator resources.
    58       */
    59      private final static String RESOURCE_DELIM = ",";
    60  
    61      /**
    62       * Application scope key that <code>ValidatorResources</code> is stored
    63       * under.
    64       */
    65      public final static String VALIDATOR_KEY =
    66          "org.apache.commons.validator.VALIDATOR_RESOURCES";
    67  
    68      /**
    69       * Application scope key that <code>StopOnError</code> is stored under.
    70       *
    71       * @since Struts 1.2
    72       */
    73      public final static String STOP_ON_ERROR_KEY =
    74          "org.apache.struts.validator.STOP_ON_ERROR";
    75  
    76      /**
    77       * The module configuration for our owning module.
    78       */
    79      private ModuleConfig config = null;
    80  
    81      /**
    82       * The {@link ActionServlet} owning this application.
    83       */
    84      private ActionServlet servlet = null;
    85  
    86      /**
    87       * The set of Form instances that have been created and initialized, keyed
    88       * by the struts form name.
    89       */
    90      protected ValidatorResources resources = null;
    91  
    92      // ------------------------------------------------------------- Properties
    93  
    94      /**
    95       * A comma delimitted list of Validator resource.
    96       */
    97      private String pathnames = null;
    98  
    99      /**
    100      * Informs the Validators if it has to stop validation when finding the
    101      * first error or if it should continue.  Default to <code>true</code> to
    102      * keep Struts 1.1 backwards compatibility.
    103      */
    104     private boolean stopOnFirstError = true;
    105 
    106     /**
    107      * Gets a comma delimitted list of Validator resources.
    108      *
    109      * @return comma delimited list of Validator resource path names
    110      */
    111     public String getPathnames() {
    112         return pathnames;
    113     }
    114 
    115     /**
    116      * Sets a comma delimitted list of Validator resources.
    117      *
    118      * @param pathnames delimited list of Validator resource path names
    119      */
    120     public void setPathnames(String pathnames) {
    121         this.pathnames = pathnames;
    122     }
    123 
    124     /**
    125      * Gets the value for stopOnFirstError.
    126      *
    127      * @return A boolean indicating whether JavaScript validation should stop
    128      *         when it finds the first error (Struts 1.1 behaviour) or
    129      *         continue validation.
    130      * @since Struts 1.2
    131      */
    132     public boolean isStopOnFirstError() {
    133         return this.stopOnFirstError;
    134     }
    135 
    136     /**
    137      * Sets the value for stopOnFirstError.
    138      *
    139      * @param stopOnFirstError A boolean indicating whether JavaScript
    140      *                         validation should stop when it finds the first
    141      *                         error (Struts 1.1 behaviour) or continue
    142      *                         validation.
    143      * @since Struts 1.2
    144      */
    145     public void setStopOnFirstError(boolean stopOnFirstError) {
    146         this.stopOnFirstError = stopOnFirstError;
    147     }
    148 
    149     /**
    150      * Initialize and load our resources.
    151      *
    152      * @param servlet The ActionServlet for our application
    153      * @param config  The ModuleConfig for our owning module
    154      * @throws ServletException if we cannot configure ourselves correctly
    155      */
    156     public void init(ActionServlet servlet, ModuleConfig config)
    157         throws ServletException {
    158         // Remember our associated configuration and servlet
    159         this.config = config;
    160         this.servlet = servlet;
    161 
    162         // Load our database from persistent storage
    163         try {
    164             this.initResources();
    165 
    166             servlet.getServletContext().setAttribute(VALIDATOR_KEY
    167                 + config.getPrefix(), resources);
    168 
    169             servlet.getServletContext().setAttribute(STOP_ON_ERROR_KEY + '.'
    170                 + config.getPrefix(),
    171                 (this.stopOnFirstError ? Boolean.TRUE : Boolean.FALSE));
    172         } catch (Exception e) {
    173             log.error(e.getMessage(), e);
    174             throw new UnavailableException(
    175                 "Cannot load a validator resource from '" + pathnames + "'");
    176         }
    177     }
    178 
    179     /**
    180      * Gracefully shut down, releasing any resources that were allocated at
    181      * initialization.
    182      */
    183     public void destroy() {
    184         if (log.isDebugEnabled()) {
    185             log.debug("Destroying ValidatorPlugin");
    186         }
    187 
    188         servlet = null;
    189         config = null;
    190 
    191         destroyResources();
    192     }
    193 
    194     /**
    195      * Initialize the validator resources for this module.
    196      *
    197      * @throws IOException      if an input/output error is encountered
    198      * @throws ServletException if we cannot initialize these resources
    199      */
    200     protected void initResources()
    201         throws IOException, ServletException {
    202         if ((pathnames == null) || (pathnames.length() <= 0)) {
    203             return;
    204         }
    205 
    206         StringTokenizer st = new StringTokenizer(pathnames, RESOURCE_DELIM);
    207 
    208         List urlList = new ArrayList();
    209 
    210         try {
    211             while (st.hasMoreTokens()) {
    212                 String validatorRules = st.nextToken().trim();
    213 
    214                 if (log.isInfoEnabled()) {
    215                     log.info("Loading validation rules file from '"
    216                         + validatorRules + "'");
    217                 }
    218 
    219                 URL input =
    220                     servlet.getServletContext().getResource(validatorRules);
    221 
    222                 // If the config isn't in the servlet context, try the class
    223                 // loader which allows the config files to be stored in a jar
    224                 if (input == null) {
    225                     input = getClass().getResource(validatorRules);
    226                 }
    227 
    228                 if (input != null) {
    229                     urlList.add(input);
    230                 } else {
    231                     throw new ServletException(
    232                         "Skipping validation rules file from '"
    233                         + validatorRules + "'.  No url could be located.");
    234                 }
    235             }
    236 
    237             int urlSize = urlList.size();
    238             URL[] urlArray = new URL[urlSize];
    239 
    240             for (int urlIndex = 0; urlIndex < urlSize; urlIndex++) {
    241                 urlArray[urlIndex] = (URL) urlList.get(urlIndex);
    242             }
    243 
    244             this.resources = new ValidatorResources(urlArray);
    245         } catch (SAXException sex) {
    246             log.error("Skipping all validation", sex);
    247             throw new ServletException(sex);
    248         }
    249     }
    250 
    251     /**
    252      * Destroy <code>ValidatorResources</code>.
    253      */
    254     protected void destroyResources() {
    255         resources = null;
    256     }
    257 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
