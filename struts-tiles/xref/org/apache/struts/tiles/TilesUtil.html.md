[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/TilesUtil.html.md)


    1   /*
    2    * $Id: TilesUtil.java 471754 2006-11-06 14:55:09Z husted $
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
    31  import javax.servlet.jsp.PageContext;
    32  
    33  import org.apache.commons.logging.Log;
    34  import org.apache.commons.logging.LogFactory;
    35  
    36  /**
    37   * Class containing utility methods for Tiles.
    38   * Methods of this class are static and thereby accessible from anywhere.
    39   * The underlying implementation can be changed with
    40   * {@link #setTilesUtil(TilesUtilImpl)}.
    41   * <br>
    42   * Real implementation classes should derive from the {@link TilesUtilImpl} class.
    43   * <br>
    44   * Some methods are specified to throw the <code>UnsupportedOperationException</code>
    45   * if the underlying implementation doesn't support the operation.
    46   */
    47  public class TilesUtil {
    48  
    49      /** Commons Logging instance.*/
    50      protected static Log log = LogFactory.getLog(TilesUtil.class);
    51  
    52      /** The implementation of tilesUtilImpl */
    53      protected static TilesUtilImpl tilesUtilImpl = new TilesUtilImpl();
    54  
    55      /**
    56       * Get the real implementation.
    57       * @return The underlying implementation object.
    58       */
    59      static public TilesUtilImpl getTilesUtil() {
    60          return tilesUtilImpl;
    61      }
    62  
    63      /**
    64       * Set the real implementation.
    65       * This method should be called only once.
    66       * Successive calls have no effect.
    67       * @param tilesUtil The implementaion.
    68       */
    69      static public void setTilesUtil(TilesUtilImpl tilesUtil) {
    70          if (implAlreadySet) {
    71              return;
    72          }
    73          tilesUtilImpl = tilesUtil;
    74          implAlreadySet = true;
    75      }
    76  
    77      /**
    78       * Getter to know if the underlying implementation is already set to another
    79       * value than the default value.
    80       * @return <code>true</code> if {@link #setTilesUtil} has already been called.
    81       */
    82      static boolean isTilesUtilImplSet() {
    83          return implAlreadySet;
    84      }
    85  
    86      /** Flag to know if internal implementation has been set by the setter method */
    87      private static boolean implAlreadySet = false;
    88  
    89      /**
    90       * Do a forward using request dispatcher.
    91       *
    92       * This method is used by the Tiles package anytime a forward is required.
    93       * @param uri Uri or Definition name to forward.
    94       * @param request Current page request.
    95       * @param response Current page response.
    96       * @param servletContext Current servlet context.
    97       */
    98      public static void doForward(
    99          String uri,
    100         HttpServletRequest request,
    101         HttpServletResponse response,
    102         ServletContext servletContext)
    103         throws IOException, ServletException {
    104 
    105         tilesUtilImpl.doForward(uri, request, response, servletContext);
    106     }
    107 
    108     /**
    109      * Do an include using request dispatcher.
    110      *
    111      * This method is used by the Tiles package when an include is required.
    112      * The Tiles package can use indifferently any form of this method.
    113      * @param uri Uri or Definition name to forward.
    114      * @param request Current page request.
    115      * @param response Current page response.
    116      * @param servletContext Current servlet context.
    117      */
    118     public static void doInclude(
    119         String uri,
    120         HttpServletRequest request,
    121         HttpServletResponse response,
    122         ServletContext servletContext)
    123         throws IOException, ServletException {
    124 
    125         tilesUtilImpl.doInclude(uri, request, response, servletContext);
    126     }
    127 
    128     /**
    129      * Do an include using PageContext.include().
    130      *
    131      * This method is used by the Tiles package when an include is required.
    132      * The Tiles package can use indifferently any form of this method.
    133      * @param uri Uri or Definition name to forward.
    134      * @param pageContext Current page context.
    135      */
    136     public static void doInclude(String uri, PageContext pageContext)
    137         throws IOException, ServletException {
    138         doInclude(uri, pageContext, true);
    139     }
    140 
    141     /**
    142      * Do an include using PageContext.include().
    143      *
    144      * This method is used by the Tiles package when an include is required.
    145      * The Tiles package can use indifferently any form of this method.
    146      * @param uri Uri or Definition name to forward.
    147      * @param flush If the writer should be flushed before the include
    148      * @param pageContext Current page context.
    149      */
    150     public static void doInclude(String uri, PageContext pageContext, boolean flush)
    151         throws IOException, ServletException {
    152         tilesUtilImpl.doInclude(uri, pageContext, flush);
    153     }
    154 
    155     /**
    156      * Get definition factory from appropriate servlet context.
    157      * @return Definitions factory or <code>null</code> if not found.
    158      */
    159     public static DefinitionsFactory getDefinitionsFactory(
    160         ServletRequest request,
    161         ServletContext servletContext) {
    162         return tilesUtilImpl.getDefinitionsFactory(request, servletContext);
    163     }
    164 
    165     /**
    166      * Create Definition factory from specified configuration object.
    167      * Create a ConfigurableDefinitionsFactory and initialize it with the configuration
    168      * object. This later can contain the factory classname to use.
    169      * Factory is made accessible from tags.
    170      * <p>
    171      * Fallback of several factory creation methods.
    172      *
    173      * @param servletContext Servlet Context passed to newly created factory.
    174      * @param factoryConfig Configuration object passed to factory.
    175      * @return newly created factory of type ConfigurableDefinitionsFactory.
    176      * @throws DefinitionsFactoryException If an error occur while initializing factory
    177      */
    178     public static DefinitionsFactory createDefinitionsFactory(
    179         ServletContext servletContext,
    180         DefinitionsFactoryConfig factoryConfig)
    181         throws DefinitionsFactoryException {
    182         return tilesUtilImpl.createDefinitionsFactory(servletContext, factoryConfig);
    183     }
    184 
    185     /**
    186      * Get a definition by its name.
    187      * First, retrieve definition factory and then get requested definition.
    188      * Throw appropriate exception if definition or definition factory is not found.
    189      * @param definitionName Name of requested definition.
    190      * @param request Current servelet request.
    191      * @param servletContext current servlet context.
    192      * @throws FactoryNotFoundException Can't find definition factory.
    193      * @throws DefinitionsFactoryException General error in factory while getting definition.
    194      * @throws NoSuchDefinitionException No definition found for specified name
    195      */
    196     public static ComponentDefinition getDefinition(
    197         String definitionName,
    198         ServletRequest request,
    199         ServletContext servletContext)
    200         throws FactoryNotFoundException, DefinitionsFactoryException {
    201 
    202         try {
    203             return getDefinitionsFactory(request, servletContext).getDefinition(
    204                 definitionName,
    205                 (HttpServletRequest) request,
    206                 servletContext);
    207 
    208         } catch (NullPointerException ex) { // Factory not found in context
    209             throw new FactoryNotFoundException("Can't get definitions factory from context.");
    210         }
    211     }
    212 
    213     /**
    214      * Reset internal state.
    215      * This method is used by test suites to reset the class to its original state.
    216      */
    217     protected static void testReset() {
    218         implAlreadySet = false;
    219         tilesUtilImpl = new TilesUtilImpl();
    220     }
    221 
    222 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
