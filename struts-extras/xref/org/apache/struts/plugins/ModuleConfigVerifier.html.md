[View Javadoc](../../../../../apidocs/org/apache/struts/plugins/ModuleConfigVerifier.html.md)


    1   /*
    2    * $Id: ModuleConfigVerifier.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.action.ActionServlet;
    24  import org.apache.struts.action.PlugIn;
    25  import org.apache.struts.config.ForwardConfig;
    26  import org.apache.struts.config.MessageResourcesConfig;
    27  import org.apache.struts.config.ModuleConfig;
    28  import org.apache.struts.config.PlugInConfig;
    29  import org.apache.struts.util.RequestUtils;
    30  import org.apache.commons.logging.Log;
    31  import org.apache.commons.logging.LogFactory;
    32  
    33  import javax.servlet.ServletException;
    34  
    35  /**
    36   * <p>Convenient implementation of {@link PlugIn} that performs as many
    37   * verification tests on the information stored in the {@link ModuleConfig}
    38   * for this module as is practical.  Based on the setting of the
    39   * <code>fatal</code> property (which defaults to <code>true</code>), the
    40   * detection of any such errors will cause a <code>ServletException</code> to
    41   * be thrown from the <code>init</code> method, which will ultimately cause
    42   * the initialization of your Struts controller servlet to fail.</p>
    43   *
    44   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    45   * @since Struts 1.1
    46   */
    47  public class ModuleConfigVerifier implements PlugIn {
    48  
    49      /**
    50       * Commons Logging instance.
    51       */
    52      private static Log LOG = LogFactory.getLog(ModuleConfigVerifier.class);
    53  
    54      // ----------------------------------------------------- Instance Variables
    55  
    56      /**
    57       * <p>The {@link ModuleConfig} instance for our module.</p>
    58       */
    59      protected ModuleConfig config = null;
    60  
    61      /**
    62       * <p>The {@link ActionServlet} instance we are associated with.</p>
    63       */
    64      protected ActionServlet servlet = null;
    65  
    66      // ------------------------------------------------------------- Properties
    67  
    68      /**
    69       * <p>Should the existence of configuration errors be fatal.</p>
    70       */
    71      private boolean fatal = true;
    72  
    73      /**
    74       * <p>Return the "configuation errors are fatal" flag.</p>
    75       */
    76      public boolean isFatal() {
    77          return (this.fatal);
    78      }
    79  
    80      /**
    81       * <p>Set the "configuration errors are fatal" flag.</p>
    82       *
    83       * @param fatal The new flag value
    84       */
    85      public void setFatal(boolean fatal) {
    86          this.fatal = fatal;
    87      }
    88  
    89      // --------------------------------------------------------- Public Methods
    90  
    91      /**
    92       * <p>Receive notification that our owning module is being shut down.</p>
    93       */
    94      public void destroy() {
    95          ; // No action required
    96      }
    97  
    98      // See interface for Javadoc.
    99      public void init(ActionServlet servlet, ModuleConfig config)
    100         throws ServletException {
    101         this.servlet = servlet;
    102         this.config = config;
    103 
    104         boolean ok = true;
    105 
    106         LOG.info(servlet.getInternal().getMessage("configVerifying"));
    107 
    108         // Perform detailed validations of each portion of ModuleConfig
    109         // :TODO: Complete methods to verify Action, Controller, et al, configurations.
    110 
    111         /*
    112         if (!verifyActionConfigs()) {
    113             ok = false;
    114         }
    115         */
    116         if (!verifyActionMappingClass()) {
    117             ok = false;
    118         }
    119 
    120         /*
    121         if (!verifyControllerConfig()) {
    122             ok = false;
    123         }
    124         if (!verifyExceptionConfigs()) {
    125             ok = false;
    126         }
    127         if (!verifyFormBeanConfigs()) {
    128             ok = false;
    129         }
    130         */
    131         if (!verifyForwardConfigs()) {
    132             ok = false;
    133         }
    134 
    135         if (!verifyMessageResourcesConfigs()) {
    136             ok = false;
    137         }
    138 
    139         if (!verifyPlugInConfigs()) {
    140             ok = false;
    141         }
    142 
    143         // Throw an exception on a fatal error
    144         LOG.info(servlet.getInternal().getMessage("configCompleted"));
    145 
    146         if (!ok && isFatal()) {
    147             throw new ServletException(servlet.getInternal().getMessage("configFatal"));
    148         }
    149     }
    150 
    151     // ------------------------------------------------------ Protected Methods
    152 
    153     /**
    154      * <p>Return <code>true</code> if information returned by
    155      * <code>config.getActionMappingClass</code> is all valid; otherwise, log
    156      * error messages and return <code>false</code>.</p>
    157      */
    158     protected boolean verifyActionMappingClass() {
    159         String amcName = config.getActionMappingClass();
    160 
    161         if (amcName == null) {
    162             LOG.error(servlet.getInternal().getMessage("verifyActionMappingClass.missing"));
    163 
    164             return (false);
    165         }
    166 
    167         try {
    168             Class amcClass = RequestUtils.applicationClass(amcName);
    169         } catch (ClassNotFoundException e) {
    170             LOG.error(servlet.getInternal().getMessage("verifyActionMappingClass.invalid",
    171                     amcName));
    172 
    173             return (false);
    174         }
    175 
    176         return (true);
    177     }
    178 
    179     /**
    180      * <p>Return <code>true</code> if information returned by
    181      * <code>config.findForwardConfigs</code> is all valid; otherwise, log
    182      * error messages and return <code>false</code>.</p>
    183      */
    184     protected boolean verifyForwardConfigs() {
    185         boolean ok = true;
    186         ForwardConfig[] fcs = config.findForwardConfigs();
    187 
    188         for (int i = 0; i < fcs.length; i++) {
    189             String path = fcs[i].getPath();
    190 
    191             if (path == null) {
    192                 LOG.error(servlet.getInternal().getMessage("verifyForwardConfigs.missing",
    193                         fcs[i].getName()));
    194                 ok = false;
    195             } else if (!path.startsWith("/")) {
    196                 LOG.error(servlet.getInternal().getMessage("verifyForwardConfigs.invalid",
    197                         path, fcs[i].getName()));
    198             }
    199         }
    200 
    201         return (ok);
    202     }
    203 
    204     /**
    205      * <p>Return <code>true</code> if information returned by
    206      * <code>config.findMessageResourcesConfigs</code> is all valid;
    207      * otherwise, log error messages and return <code>false</code>.</p>
    208      */
    209     protected boolean verifyMessageResourcesConfigs() {
    210         boolean ok = true;
    211         MessageResourcesConfig[] mrcs = config.findMessageResourcesConfigs();
    212 
    213         for (int i = 0; i < mrcs.length; i++) {
    214             String factory = mrcs[i].getFactory();
    215 
    216             if (factory == null) {
    217                 LOG.error(servlet.getInternal().getMessage("verifyMessageResourcesConfigs.missing"));
    218                 ok = false;
    219             } else {
    220                 try {
    221                     Class clazz = RequestUtils.applicationClass(factory);
    222                 } catch (ClassNotFoundException e) {
    223                     LOG.error(servlet.getInternal().getMessage("verifyMessageResourcesConfigs.invalid",
    224                             factory));
    225                     ok = false;
    226                 }
    227             }
    228 
    229             String key = mrcs[i].getKey();
    230 
    231             if (key == null) {
    232                 LOG.error(servlet.getInternal().getMessage("verifyMessageResourcesConfigs.key"));
    233             }
    234         }
    235 
    236         return (ok);
    237     }
    238 
    239     /**
    240      * <p>Return <code>true</code> if information returned by
    241      * <code>config.findPluginConfigs</code> is all valid; otherwise, log
    242      * error messages and return <code>false</code>.</p>
    243      */
    244     protected boolean verifyPlugInConfigs() {
    245         boolean ok = true;
    246         PlugInConfig[] pics = config.findPlugInConfigs();
    247 
    248         for (int i = 0; i < pics.length; i++) {
    249             String className = pics[i].getClassName();
    250 
    251             if (className == null) {
    252                 LOG.error(servlet.getInternal().getMessage("verifyPlugInConfigs.missing"));
    253                 ok = false;
    254             } else {
    255                 try {
    256                     Class clazz = RequestUtils.applicationClass(className);
    257                 } catch (ClassNotFoundException e) {
    258                     LOG.error(servlet.getInternal().getMessage("verifyPlugInConfigs.invalid",
    259                             className));
    260                     ok = false;
    261                 }
    262             }
    263         }
    264 
    265         return (ok);
    266     }
    267 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
