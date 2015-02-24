[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/TilesUtilStrutsModulesImpl.html.md)


    1   /*
    2    * $Id: TilesUtilStrutsModulesImpl.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import javax.servlet.ServletContext;
    27  import javax.servlet.ServletException;
    28  import javax.servlet.ServletRequest;
    29  import javax.servlet.http.HttpServletRequest;
    30  import javax.servlet.http.HttpServletResponse;
    31  
    32  import org.apache.struts.Globals;
    33  import org.apache.struts.config.ModuleConfig;
    34  import org.apache.struts.util.ModuleUtils;
    35  
    36  /**
    37   * Implementation of TilesUtil for Struts multi modules.
    38   * Methods in this implementation are aware of the Struts module context.
    39   * <br>
    40   * <ul>
    41   * <li>The method getFactory(...) returns the factory for the current Struts
    42   * module.</li>
    43   * <li>Methods doForward() and doInclude() use their counterparts in the
    44   * current RequestProcessor (todo).</li>
    45   * <li>The method createFactory(...) creates a factory for the current module and
    46   * stores it under the appropriate property name.</li>
    47   * </ul>
    48   */
    49  public class TilesUtilStrutsModulesImpl extends TilesUtilStrutsImpl {
    50  
    51      /**
    52       * Do a forward using request dispatcher.
    53       *
    54       * This method is used by the Tiles package anytime a forward is required.
    55       * @param uri Uri or Definition name to forward.
    56       * @param request Current page request.
    57       * @param response Current page response.
    58       * @param servletContext Current servlet context.
    59       */
    60      public void doForward(
    61          String uri,
    62          HttpServletRequest request,
    63          HttpServletResponse response,
    64          ServletContext servletContext)
    65          throws IOException, ServletException {
    66  
    67          request.getRequestDispatcher(uri).forward(request, response);
    68      }
    69  
    70      /**
    71       * Do an include using request dispatcher.
    72       *
    73       * This method is used by the Tiles package anytime an include is required.
    74       * @param uri Uri or Definition name to forward.
    75       * @param request Current page request.
    76       * @param response Current page response.
    77       * @param servletContext Current servlet context.
    78       */
    79      public void doInclude(
    80          String uri,
    81          HttpServletRequest request,
    82          HttpServletResponse response,
    83          ServletContext servletContext)
    84          throws IOException, ServletException {
    85  
    86          request.getRequestDispatcher(uri).include(request, response);
    87      }
    88  
    89      /**
    90       * Get the definition factory from appropriate servlet context.
    91       * @param request Current request.
    92       * @param servletContext Current servlet context.
    93       * @return Definitions factory or null if not found.
    94       */
    95      public DefinitionsFactory getDefinitionsFactory(
    96          ServletRequest request,
    97          ServletContext servletContext) {
    98  
    99          return getDefinitionsFactory(
    100             servletContext,
    101             getModuleConfig((HttpServletRequest) request, servletContext));
    102     }
    103 
    104     /**
    105      * Get definition factory for the module attached to specified moduleConfig.
    106      * @param servletContext Current servlet context.
    107      * @param moduleConfig Module config of the module for which the factory is requested.
    108      * @return Definitions factory or null if not found.
    109      */
    110     public DefinitionsFactory getDefinitionsFactory(
    111         ServletContext servletContext,
    112         ModuleConfig moduleConfig) {
    113 
    114         return (DefinitionsFactory) servletContext.getAttribute(
    115             DEFINITIONS_FACTORY + moduleConfig.getPrefix());
    116     }
    117 
    118     /**
    119      * Make definition factory accessible to tags.
    120      * Factory is stored in servlet context.
    121      * @param factory Factory to be made accessible.
    122      * @param servletContext Current servlet context.
    123      */
    124     protected void makeDefinitionsFactoryAccessible(
    125         DefinitionsFactory factory,
    126         ServletContext servletContext) {
    127 
    128         String prefix = factory.getConfig().getFactoryName();
    129         servletContext.setAttribute(DEFINITIONS_FACTORY + prefix, factory);
    130     }
    131 
    132     /**
    133      * Get Tiles RequestProcessor associated to the current module.
    134      * @param request Current request.
    135      * @param servletContext Current servlet context.
    136      * @return The {@link TilesRequestProcessor} for the current request.
    137      */
    138     protected TilesRequestProcessor getRequestProcessor(
    139         HttpServletRequest request,
    140         ServletContext servletContext) {
    141 
    142         ModuleConfig moduleConfig = getModuleConfig(request, servletContext);
    143 
    144         return (TilesRequestProcessor) servletContext.getAttribute(
    145             Globals.REQUEST_PROCESSOR_KEY + moduleConfig.getPrefix());
    146     }
    147 
    148     /**
    149      * Get the current ModuleConfig.
    150      * <br>
    151      * Lookup in the request and do selectModule if not found. The side effect
    152      * is, that the ModuleConfig object is set in the request if it was not present.
    153      * @param request Current request.
    154      * @param servletContext Current servlet context*.
    155      * @return The ModuleConfig for current request.
    156      */
    157     protected ModuleConfig getModuleConfig(
    158         HttpServletRequest request,
    159         ServletContext servletContext) {
    160 
    161         ModuleConfig moduleConfig =
    162             ModuleUtils.getInstance().getModuleConfig(request);
    163 
    164         if (moduleConfig == null) {
    165             // ModuleConfig not found in current request. Select it.
    166             ModuleUtils.getInstance().selectModule(request, servletContext);
    167             moduleConfig = ModuleUtils.getInstance().getModuleConfig(request);
    168         }
    169 
    170         return moduleConfig;
    171     }
    172 
    173 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
