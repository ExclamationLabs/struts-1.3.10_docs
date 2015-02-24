[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/commands/TilesPreProcessor.html.md)


    1   /*
    2    * $Id: TilesPreProcessor.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.tiles.commands;
    22  
    23  import java.io.IOException;
    24  
    25  import javax.servlet.RequestDispatcher;
    26  import javax.servlet.ServletException;
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.http.HttpServletResponse;
    29  
    30  import org.apache.commons.chain.Command;
    31  import org.apache.commons.chain.Context;
    32  import org.apache.commons.logging.Log;
    33  import org.apache.commons.logging.LogFactory;
    34  import org.apache.struts.chain.contexts.ServletActionContext;
    35  import org.apache.struts.config.ForwardConfig;
    36  import org.apache.struts.tiles.ComponentContext;
    37  import org.apache.struts.tiles.ComponentDefinition;
    38  import org.apache.struts.tiles.Controller;
    39  import org.apache.struts.tiles.DefinitionsUtil;
    40  import org.apache.struts.tiles.FactoryNotFoundException;
    41  import org.apache.struts.tiles.NoSuchDefinitionException;
    42  import org.apache.struts.tiles.TilesUtil;
    43  import org.apache.struts.upload.MultipartRequestWrapper;
    44  
    45  
    46  /**
    47   * <p>Command class intended to perform responsibilities of the
    48   * TilesRequestProcessor in Struts 1.1.  Does not actually dispatch requests,
    49   * but simply prepares the chain context for a later forward as
    50   * appropriate.  Should be added to a chain before something which
    51   * would handle a conventional ForwardConfig.</p>
    52   *
    53   * <p>This class will never have any effect on the chain unless a
    54   * <code>TilesDefinitionFactory</code> can be found; however it does not
    55   * consider the absence of a definition factory to be a fatal error; the
    56   * command simply returns false and lets the chain continue.</p>
    57   *
    58   * <p>To initialize the <code>TilesDefinitionFactory</code>, use
    59   * <code>org.apache.struts.chain.commands.legacy.TilesPlugin</code>.  This class
    60   * is a simple extension to <code>org.apache.struts.tiles.TilesPlugin</code>
    61   * which simply does not interfere with your choice of <code>RequestProcessor</code>
    62   * implementation.
    63   *  </p>
    64   *
    65   *
    66   */
    67  public class TilesPreProcessor implements Command
    68  {
    69  
    70  
    71      // ------------------------------------------------------ Instance Variables
    72  
    73  
    74      private static final Log log = LogFactory.getLog(TilesPreProcessor.class);
    75  
    76      // ---------------------------------------------------------- Public Methods
    77  
    78  
    79      /**
    80       * <p>If the current <code>ForwardConfig</code> is using "tiles",
    81       * perform necessary pre-processing to set up the <code>TilesContext</code>
    82       * and substitute a new <code>ForwardConfig</code> which is understandable
    83       * to a <code>RequestDispatcher</code>.</p>
    84       *
    85       * <p>Note that if the command finds a previously existing
    86       * <code>ComponentContext</code> in the request, then it
    87       * infers that it has been called from within another tile,
    88       * so instead of changing the <code>ForwardConfig</code> in the chain
    89       * <code>Context</code>, the command uses <code>RequestDispatcher</code>
    90       * to <em>include</em> the tile, and returns true, indicating that the processing
    91       * chain is complete.</p>
    92       *
    93       * @param context The <code>Context</code> for the current request
    94       *
    95       * @return <code>false</code> in most cases, but true if we determine
    96       * that we're processing in "include" mode.
    97       */
    98      public boolean execute(Context context) throws Exception {
    99  
    100         // Is there a Tiles Definition to be processed?
    101         ServletActionContext sacontext = (ServletActionContext) context;
    102         ForwardConfig forwardConfig = sacontext.getForwardConfig();
    103         if (forwardConfig == null || forwardConfig.getPath() == null)
    104         {
    105             log.debug("No forwardConfig or no path, so pass to next command.");
    106             return (false);
    107         }
    108 
    109 
    110         ComponentDefinition definition = null;
    111         try
    112         {
    113             definition = TilesUtil.getDefinition(forwardConfig.getPath(),
    114                     sacontext.getRequest(),
    115                     sacontext.getContext());
    116         }
    117         catch (FactoryNotFoundException ex)
    118         {
    119             // this is not a serious error, so log at low priority
    120             log.debug("Tiles DefinitionFactory not found, so pass to next command.");
    121             return false;
    122         }
    123         catch (NoSuchDefinitionException ex)
    124         {
    125             // ignore not found
    126             log.debug("NoSuchDefinitionException " + ex.getMessage());
    127         }
    128 
    129         // Do we do a forward (original behavior) or an include ?
    130         boolean doInclude = false;
    131         ComponentContext tileContext = null;
    132 
    133         // Get current tile context if any.
    134         // If context exists, or if the response has already been committed we will do an include
    135         tileContext = ComponentContext.getContext(sacontext.getRequest());
    136         doInclude = (tileContext != null || sacontext.getResponse().isCommitted());
    137 
    138         // Controller associated to a definition, if any
    139         Controller controller = null;
    140 
    141         // Computed uri to include
    142         String uri = null;
    143 
    144         if (definition != null)
    145         {
    146             // We have a "forward config" definition.
    147             // We use it to complete missing attribute in context.
    148             // We also get uri, controller.
    149             uri = definition.getPath();
    150             controller = definition.getOrCreateController();
    151 
    152             if (tileContext == null) {
    153                 tileContext =
    154                         new ComponentContext(definition.getAttributes());
    155                 ComponentContext.setContext(tileContext, sacontext.getRequest());
    156 
    157             } else {
    158                 tileContext.addMissing(definition.getAttributes());
    159             }
    160         }
    161 
    162         // Process definition set in Action, if any.  This may override the
    163         // values for uri or controller found using the ForwardConfig, and
    164         // may augment the tileContext with additional attributes.
    165         // :FIXME: the class DefinitionsUtil is deprecated, but I can't find
    166         // the intended alternative to use.
    167         definition = DefinitionsUtil.getActionDefinition(sacontext.getRequest());
    168         if (definition != null) { // We have a definition.
    169                 // We use it to complete missing attribute in context.
    170                 // We also overload uri and controller if set in definition.
    171                 if (definition.getPath() != null) {
    172                     log.debug("Override forward uri "
    173                               + uri
    174                               + " with action uri "
    175                               + definition.getPath());
    176                         uri = definition.getPath();
    177                 }
    178 
    179                 if (definition.getOrCreateController() != null) {
    180                     log.debug("Override forward controller with action controller");
    181                         controller = definition.getOrCreateController();
    182                 }
    183 
    184                 if (tileContext == null) {
    185                         tileContext =
    186                                 new ComponentContext(definition.getAttributes());
    187                         ComponentContext.setContext(tileContext, sacontext.getRequest());
    188                 } else {
    189                         tileContext.addMissing(definition.getAttributes());
    190                 }
    191         }
    192 
    193 
    194         if (uri == null) {
    195             log.debug("no uri computed, so pass to next command");
    196             return false;
    197         }
    198 
    199         // Execute controller associated to definition, if any.
    200         if (controller != null) {
    201             log.trace("Execute controller: " + controller);
    202             controller.execute(
    203                     tileContext,
    204                     sacontext.getRequest(),
    205                     sacontext.getResponse(),
    206                     sacontext.getContext());
    207         }
    208 
    209         // If request comes from a previous Tile, do an include.
    210         // This allows to insert an action in a Tile.
    211 
    212         if (doInclude) {
    213             log.info("Tiles process complete; doInclude with " + uri);
    214             doInclude(sacontext, uri);
    215         } else {
    216             log.info("Tiles process complete; forward to " + uri);
    217             doForward(sacontext, uri);
    218         }
    219 
    220         log.debug("Tiles processed, so clearing forward config from context.");
    221         sacontext.setForwardConfig( null );
    222         return (false);
    223     }
    224 
    225 
    226     // ------------------------------------------------------- Protected Methods
    227 
    228     /**
    229      * <p>Do an include of specified URI using a <code>RequestDispatcher</code>.</p>
    230      *
    231      * @param context a chain servlet/web context
    232      * @param uri Context-relative URI to include
    233      */
    234     protected void doInclude(
    235         ServletActionContext context,
    236         String uri)
    237         throws IOException, ServletException {
    238 
    239         RequestDispatcher rd = getRequiredDispatcher(context, uri);
    240 
    241         if (rd != null) {
    242             rd.include(context.getRequest(), context.getResponse());
    243         }
    244     }
    245 
    246     /**
    247      * <p>Do an include of specified URI using a <code>RequestDispatcher</code>.</p>
    248      *
    249      * @param context a chain servlet/web context
    250      * @param uri Context-relative URI to include
    251      */
    252     protected void doForward(
    253         ServletActionContext context,
    254         String uri)
    255         throws IOException, ServletException {
    256 
    257         RequestDispatcher rd = getRequiredDispatcher(context, uri);
    258 
    259         if (rd != null) {
    260             rd.forward(context.getRequest(), context.getResponse());
    261         }
    262     }
    263 
    264     /**
    265      * <p>Get the <code>RequestDispatcher</code> for the specified <code>uri</code>.  If it is not found,
    266      * send a 500 error as a response and return null;
    267      *
    268      * @param context the current <code>ServletActionContext</code>
    269      * @param uri the ServletContext-relative URI of the request dispatcher to find.
    270      * @return the <code>RequestDispatcher</code>, or null if none is returned from the <code>ServletContext</code>.
    271      * @throws IOException if <code>getRequestDispatcher(uri)</code> has an error.
    272      */
    273     private RequestDispatcher getRequiredDispatcher(ServletActionContext context, String uri) throws IOException {
    274         RequestDispatcher rd = context.getContext().getRequestDispatcher(uri);
    275         if (rd == null) {
    276             log.debug("No request dispatcher found for " + uri);
    277             HttpServletResponse response = context.getResponse();
    278             response.sendError(
    279                 HttpServletResponse.SC_INTERNAL_SERVER_ERROR,
    280                 "Error getting RequestDispatcher for " + uri);
    281         }
    282         return rd;
    283     }
    284 
    285 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
