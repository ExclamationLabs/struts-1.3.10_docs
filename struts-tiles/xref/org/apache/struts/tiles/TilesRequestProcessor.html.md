[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/TilesRequestProcessor.html.md)


    1   /*
    2    * $Id: TilesRequestProcessor.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import java.io.IOException;
    25  
    26  import javax.servlet.ServletException;
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.http.HttpServletResponse;
    29  
    30  import org.apache.commons.logging.Log;
    31  import org.apache.commons.logging.LogFactory;
    32  import org.apache.struts.action.ActionServlet;
    33  import org.apache.struts.action.RequestProcessor;
    34  import org.apache.struts.config.ForwardConfig;
    35  import org.apache.struts.config.ModuleConfig;
    36  
    37  /**
    38   * <p><strong>RequestProcessor</strong> contains the processing logic that
    39   * the Struts controller servlet performs as it receives each servlet request
    40   * from the container.</p>
    41   * <p>This processor subclasses the Struts RequestProcessor in order to intercept calls to forward
    42   * or include. When such calls are done, the Tiles processor checks if the specified URI
    43   * is a definition name. If true, the definition is retrieved and included. If
    44   * false, the original URI is included or a forward is performed.
    45   * <p>
    46   * Actually, catching is done by overloading the following methods:
    47   * <ul>
    48   * <li>{@link #processForwardConfig(HttpServletRequest,HttpServletResponse,ForwardConfig)}</li>
    49   * <li>{@link #internalModuleRelativeForward(String, HttpServletRequest , HttpServletResponse)}</li>
    50   * <li>{@link #internalModuleRelativeInclude(String, HttpServletRequest , HttpServletResponse)}</li>
    51   * </ul>
    52   * </p>
    53   * @since Struts 1.1
    54   */
    55  public class TilesRequestProcessor extends RequestProcessor {
    56  
    57      /**
    58       * Definitions factory.
    59       */
    60      protected DefinitionsFactory definitionsFactory = null;
    61  
    62      /**
    63       * Commons Logging instance.
    64       */
    65      protected static Log log = LogFactory.getLog(TilesRequestProcessor.class);
    66  
    67      /**
    68       * Initialize this request processor instance.
    69       *
    70       * @param servlet The ActionServlet we are associated with.
    71       * @param moduleConfig The ModuleConfig we are associated with.
    72       * @throws ServletException If an error occurs during initialization.
    73       */
    74      public void init(ActionServlet servlet, ModuleConfig moduleConfig)
    75          throws ServletException {
    76  
    77          super.init(servlet, moduleConfig);
    78          this.initDefinitionsMapping();
    79      }
    80  
    81      /**
    82       * Read component instance mapping configuration file.
    83       * This is where we read files properties.
    84       */
    85      protected void initDefinitionsMapping() throws ServletException {
    86          // Retrieve and set factory for this modules
    87          definitionsFactory =
    88              (
    89                  (TilesUtilStrutsImpl) TilesUtil
    90                      .getTilesUtil())
    91                      .getDefinitionsFactory(
    92                  getServletContext(),
    93                  moduleConfig);
    94  
    95          if (definitionsFactory == null) { // problem !
    96  
    97              log.info(
    98                  "Definition Factory not found for module '"
    99                      + moduleConfig.getPrefix()
    100                     + "'. "
    101                     + "Have you declared the appropriate plugin in struts-config.xml ?");
    102 
    103             return;
    104         }
    105 
    106         log.info(
    107             "Tiles definition factory found for request processor '"
    108                 + moduleConfig.getPrefix()
    109                 + "'.");
    110 
    111     }
    112 
    113     /**
    114      * Process a Tile definition name.
    115      * This method tries to process the parameter <code>definitionName</code>
    116      * as a definition name.
    117      * It returns <code>true</code> if a definition has been processed, or
    118      * <code>false</code> otherwise.
    119      * This method is deprecated; the method without the
    120      * <code>contextRelative</code> parameter should be used instead.
    121      *
    122      * @param definitionName Definition name to insert.
    123      * @param contextRelative Is the definition marked contextRelative ?
    124      * @param request Current page request.
    125      * @param response Current page response.
    126      * @return <code>true</code> if the method has processed uri as a
    127      * definition name, <code>false</code> otherwise.
    128      * @deprecated use processTilesDefinition(definitionName, request, response)
    129      *  instead.  This method will be removed in a version after 1.3.0.
    130      */
    131     protected boolean processTilesDefinition(
    132         String definitionName,
    133         boolean contextRelative,
    134         HttpServletRequest request,
    135         HttpServletResponse response)
    136         throws IOException, ServletException {
    137 
    138         return processTilesDefinition(definitionName, request, response);
    139 
    140     }
    141 
    142     /**
    143      * Process a Tile definition name.
    144      * This method tries to process the parameter <code>definitionName</code>
    145      * as a definition name.
    146      * It returns <code>true</code> if a definition has been processed, or
    147      * <code>false</code> otherwise.
    148      *
    149      * @param definitionName Definition name to insert.
    150      * @param request Current page request.
    151      * @param response Current page response.
    152      * @return <code>true</code> if the method has processed uri as a
    153      * definition name, <code>false</code> otherwise.
    154      */
    155     protected boolean processTilesDefinition(
    156         String definitionName,
    157         HttpServletRequest request,
    158         HttpServletResponse response)
    159         throws IOException, ServletException {
    160 
    161         // Do we do a forward (original behavior) or an include ?
    162         boolean doInclude = false;
    163 
    164         // Controller associated to a definition, if any
    165         Controller controller = null;
    166 
    167         // Computed uri to include
    168         String uri = null;
    169 
    170         ComponentContext tileContext = null;
    171 
    172         try {
    173             // Get current tile context if any.
    174             // If context exist, we will do an include
    175             tileContext = ComponentContext.getContext(request);
    176             doInclude = (tileContext != null);
    177             ComponentDefinition definition = null;
    178 
    179             // Process tiles definition names only if a definition factory exist,
    180             // and definition is found.
    181             if (definitionsFactory != null) {
    182                 // Get definition of tiles/component corresponding to uri.
    183                 try {
    184                     definition =
    185                         definitionsFactory.getDefinition(
    186                             definitionName,
    187                             request,
    188                             getServletContext());
    189                 } catch (NoSuchDefinitionException ex) {
    190                     // Ignore not found
    191                     log.debug("NoSuchDefinitionException " + ex.getMessage());
    192                 }
    193                 if (definition != null) { // We have a definition.
    194                     // We use it to complete missing attribute in context.
    195                     // We also get uri, controller.
    196                     uri = definition.getPath();
    197                     controller = definition.getOrCreateController();
    198 
    199                     if (tileContext == null) {
    200                         tileContext =
    201                             new ComponentContext(definition.getAttributes());
    202                         ComponentContext.setContext(tileContext, request);
    203 
    204                     } else {
    205                         tileContext.addMissing(definition.getAttributes());
    206                     }
    207                 }
    208             }
    209 
    210             // Process definition set in Action, if any.
    211             definition = DefinitionsUtil.getActionDefinition(request);
    212             if (definition != null) { // We have a definition.
    213                 // We use it to complete missing attribute in context.
    214                 // We also overload uri and controller if set in definition.
    215                 if (definition.getPath() != null) {
    216                     uri = definition.getPath();
    217                 }
    218 
    219                 if (definition.getOrCreateController() != null) {
    220                     controller = definition.getOrCreateController();
    221                 }
    222 
    223                 if (tileContext == null) {
    224                     tileContext =
    225                         new ComponentContext(definition.getAttributes());
    226                     ComponentContext.setContext(tileContext, request);
    227                 } else {
    228                     tileContext.addMissing(definition.getAttributes());
    229                 }
    230             }
    231 
    232         } catch (java.lang.InstantiationException ex) {
    233 
    234             log.error("Can't create associated controller", ex);
    235 
    236             throw new ServletException(
    237                 "Can't create associated controller",
    238                 ex);
    239         } catch (DefinitionsFactoryException ex) {
    240             throw new ServletException(ex);
    241         }
    242 
    243         // Have we found a definition ?
    244         if (uri == null) {
    245             return false;
    246         }
    247 
    248         // Execute controller associated to definition, if any.
    249         if (controller != null) {
    250             try {
    251                 controller.execute(
    252                     tileContext,
    253                     request,
    254                     response,
    255                     getServletContext());
    256 
    257             } catch (Exception e) {
    258                 throw new ServletException(e);
    259             }
    260         }
    261 
    262         // If request comes from a previous Tile, do an include.
    263         // This allows to insert an action in a Tile.
    264         if (log.isDebugEnabled()) {
    265             log.debug("uri=" + uri + " doInclude=" + doInclude);
    266         }
    267 
    268         if (doInclude) {
    269             doInclude(uri, request, response);
    270         } else {
    271             doForward(uri, request, response); // original behavior
    272         }
    273 
    274         return true;
    275     }
    276 
    277     /**
    278      * Do a forward using request dispatcher.
    279      * Uri is a valid uri. If response has already been commited, do an include
    280      * instead.
    281      * @param uri Uri or Definition name to forward.
    282      * @param request Current page request.
    283      * @param response Current page response.
    284      */
    285     protected void doForward(
    286         String uri,
    287         HttpServletRequest request,
    288         HttpServletResponse response)
    289         throws IOException, ServletException {
    290 
    291         if (response.isCommitted()) {
    292             this.doInclude(uri, request, response);
    293 
    294         } else {
    295             super.doForward(uri, request, response);
    296         }
    297     }
    298 
    299     /**
    300      * Overloaded method from Struts' RequestProcessor.
    301      * Forward or redirect to the specified destination by the specified
    302      * mechanism.
    303      * This method catches the Struts' actionForward call. It checks if the
    304      * actionForward is done on a Tiles definition name. If true, process the
    305      * definition and insert it. If false, call the original parent's method.
    306      * @param request The servlet request we are processing.
    307      * @param response The servlet response we are creating.
    308      * @param forward The ActionForward controlling where we go next.
    309      *
    310      * @exception IOException if an input/output error occurs.
    311      * @exception ServletException if a servlet exception occurs.
    312      */
    313     protected void processForwardConfig(
    314         HttpServletRequest request,
    315         HttpServletResponse response,
    316         ForwardConfig forward)
    317         throws IOException, ServletException {
    318 
    319         // Required by struts contract
    320         if (forward == null) {
    321             return;
    322         }
    323 
    324         if (log.isDebugEnabled()) {
    325             log.debug(
    326                 "processForwardConfig("
    327                     + forward.getPath()
    328                     + ")");
    329         }
    330 
    331         // Try to process the definition.
    332         if (processTilesDefinition(forward.getPath(),
    333             request,
    334             response)) {
    335             if (log.isDebugEnabled()) {
    336                 log.debug(
    337                     "  '" + forward.getPath() + "' - processed as definition");
    338             }
    339             return;
    340         }
    341 
    342         if (log.isDebugEnabled()) {
    343             log.debug("  '" + forward.getPath() + "' - processed as uri");
    344         }
    345 
    346         // forward doesn't contain a definition, let parent do processing
    347         super.processForwardConfig(request, response, forward);
    348     }
    349 
    350     /**
    351      * Catch the call to a module relative forward.
    352      * If the specified uri is a tiles definition name, insert it.
    353      * Otherwise, parent processing is called.
    354      * Do a module relative forward to specified uri using request dispatcher.
    355      * Uri is relative to the current module. The real uri is computed by
    356      * prefixing the module name.
    357      * <strong>This method is used internally and is not part of the public
    358      * API. It is advised to not use it in subclasses.</strong>
    359      * @param uri Module-relative URI to forward to.
    360      * @param request Current page request.
    361      * @param response Current page response.
    362      * @since Struts 1.1
    363      */
    364     protected void internalModuleRelativeForward(
    365         String uri,
    366         HttpServletRequest request,
    367         HttpServletResponse response)
    368         throws IOException, ServletException {
    369 
    370         if (processTilesDefinition(uri, request, response)) {
    371             return;
    372         }
    373 
    374         super.internalModuleRelativeForward(uri, request, response);
    375     }
    376 
    377     /**
    378      * Do a module relative include to specified uri using request dispatcher.
    379      * Uri is relative to the current module. The real uri is computed by
    380      * prefixing the module name.
    381      * <strong>This method is used internally and is not part of the public
    382      * API. It is advised to not use it in subclasses.</strong>
    383      * @param uri Module-relative URI to forward to.
    384      * @param request Current page request.
    385      * @param response Current page response.
    386      * @since Struts 1.1
    387      */
    388     protected void internalModuleRelativeInclude(
    389         String uri,
    390         HttpServletRequest request,
    391         HttpServletResponse response)
    392         throws IOException, ServletException {
    393 
    394         if (processTilesDefinition(uri, request, response)) {
    395             return;
    396         }
    397 
    398         super.internalModuleRelativeInclude(uri, request, response);
    399     }
    400 
    401     /**
    402      * Get associated definition factory.
    403      */
    404     public DefinitionsFactory getDefinitionsFactory() {
    405         return definitionsFactory;
    406     }
    407 
    408 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
