[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/TilesUtilImpl.html.md)


    1   /*
    2    * $Id: TilesUtilImpl.java 529384 2007-04-16 20:19:17Z bayard $
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
    25  import java.io.Serializable;
    26  
    27  import java.lang.reflect.Method;
    28  import java.lang.reflect.InvocationTargetException;
    29  
    30  import javax.servlet.ServletContext;
    31  import javax.servlet.ServletException;
    32  import javax.servlet.ServletRequest;
    33  import javax.servlet.http.HttpServletRequest;
    34  import javax.servlet.http.HttpServletResponse;
    35  import javax.servlet.jsp.PageContext;
    36  
    37  import org.apache.commons.logging.Log;
    38  import org.apache.commons.logging.LogFactory;
    39  import org.apache.struts.tiles.definition.ComponentDefinitionsFactoryWrapper;
    40  import org.apache.struts.util.RequestUtils;
    41  
    42  /**
    43   * Default implementation of TilesUtil.
    44   * This class contains default implementation of utilities. This implementation
    45   * is intended to be used without Struts.
    46   */
    47  public class TilesUtilImpl implements Serializable {
    48  
    49      /** Commons Logging instance.*/
    50      protected static final Log log = LogFactory.getLog(TilesUtil.class);
    51  
    52      /** Constant name used to store factory in servlet context */
    53      public static final String DEFINITIONS_FACTORY =
    54          "org.apache.struts.tiles.DEFINITIONS_FACTORY";
    55  
    56      /**
    57       * JSP 2.0 include method to use which supports configurable flushing.
    58       */
    59      private static Method include = null;
    60  
    61      /**
    62       * Initialize the include variable with the
    63       * JSP 2.0 method if available.
    64       */
    65      static {
    66  
    67          try {
    68              // get version of include method with flush argument
    69              Class[] args = new Class[]{String.class, boolean.class};
    70              include = PageContext.class.getMethod("include", args);
    71          } catch (NoSuchMethodException e) {
    72              log.debug("Could not find JSP 2.0 include method.  Using old one that doesn't support " +
    73                        "configurable flushing.", e);
    74          }
    75      }
    76  
    77      /**
    78       * Do a forward using request dispatcher.
    79       *
    80       * This method is used by the Tiles package anytime a forward is required.
    81       * @param uri Uri or Definition name to forward.
    82       * @param request Current page request.
    83       * @param servletContext Current servlet context.
    84       */
    85      public void doForward(
    86          String uri,
    87          HttpServletRequest request,
    88          HttpServletResponse response,
    89          ServletContext servletContext)
    90          throws IOException, ServletException {
    91  
    92          request.getRequestDispatcher(uri).forward(request, response);
    93      }
    94  
    95      /**
    96       * Do an include using request dispatcher.
    97       *
    98       * This method is used by the Tiles package when an include is required.
    99       * The Tiles package can use indifferently any form of this method.
    100      * @param uri Uri or Definition name to forward.
    101      * @param request Current page request.
    102      * @param response Current page response.
    103      * @param servletContext Current servlet context.
    104      */
    105     public void doInclude(
    106         String uri,
    107         HttpServletRequest request,
    108         HttpServletResponse response,
    109         ServletContext servletContext)
    110         throws IOException, ServletException {
    111 
    112         request.getRequestDispatcher(uri).include(request, response);
    113     }
    114 
    115     /**
    116      * Do an include using PageContext.include().
    117      *
    118      * This method is used by the Tiles package when an include is required.
    119      * The Tiles package can use indifferently any form of this method.
    120      * @param uri Uri or Definition name to forward.
    121      * @param pageContext Current page context.
    122      * @param flush If the writer should be flushed before the include
    123      */
    124     public void doInclude(String uri, PageContext pageContext, boolean flush)
    125         throws IOException, ServletException {
    126         try {
    127             // perform include with new JSP 2.0 method that supports flushing
    128             if (include != null) {
    129                 include.invoke(pageContext, new Object[]{uri, Boolean.valueOf(flush)});
    130                 return;
    131             }
    132         } catch (IllegalAccessException e) {
    133             log.debug("Could not find JSP 2.0 include method.  Using old one.", e);
    134         } catch (InvocationTargetException e) {
    135             if (e.getCause() instanceof ServletException){
    136                throw ((ServletException)e.getCause());
    137             } else if (e.getCause() instanceof IOException){
    138                throw ((IOException)e.getCause());
    139             } else {
    140                throw new ServletException(e);
    141             }
    142         }
    143 
    144         pageContext.include(uri);
    145     }
    146 
    147     /**
    148      * Get definition factory from appropriate servlet context.
    149      * @return Definitions factory or <code>null</code> if not found.
    150      */
    151     public DefinitionsFactory getDefinitionsFactory(
    152         ServletRequest request,
    153         ServletContext servletContext) {
    154 
    155         return (DefinitionsFactory) servletContext.getAttribute(DEFINITIONS_FACTORY);
    156     }
    157 
    158     /**
    159      * Create Definition factory from specified configuration object.
    160      * Create an instance of the factory with the class specified in the config
    161      * object. Then, initialize this factory and finally store the factory in
    162      * appropriate context by calling
    163      * {@link #makeDefinitionsFactoryAccessible(DefinitionsFactory, ServletContext)}.
    164      * Factory creation is done by {@link #createDefinitionFactoryInstance(String)}.
    165      * <p>
    166      *
    167      * @param servletContext Servlet Context passed to newly created factory.
    168      * @param factoryConfig Configuration object passed to factory.
    169      * @return newly created factory of type specified in the config object.
    170      * @throws DefinitionsFactoryException If an error occur while initializing factory
    171      */
    172     public DefinitionsFactory createDefinitionsFactory(
    173         ServletContext servletContext,
    174         DefinitionsFactoryConfig factoryConfig)
    175         throws DefinitionsFactoryException {
    176 
    177         // Create configurable factory
    178         DefinitionsFactory factory =
    179             createDefinitionFactoryInstance(factoryConfig.getFactoryClassname());
    180 
    181         factory.init(factoryConfig, servletContext);
    182 
    183         // Make factory accessible from jsp tags (push it in appropriate context)
    184         makeDefinitionsFactoryAccessible(factory, servletContext);
    185         return factory;
    186     }
    187 
    188     /**
    189      * Create Definition factory of specified classname.
    190      * Factory class must extend the {@link DefinitionsFactory} class.
    191      * The factory is wrapped appropriately with {@link ComponentDefinitionsFactoryWrapper}
    192      * if it is an instance of the deprecated ComponentDefinitionsFactory class.
    193      * @param classname Class name of the factory to create.
    194      * @return newly created factory.
    195      * @throws DefinitionsFactoryException If an error occur while initializing factory
    196      */
    197     protected DefinitionsFactory createDefinitionFactoryInstance(String classname)
    198         throws DefinitionsFactoryException {
    199 
    200         try {
    201             Class factoryClass = RequestUtils.applicationClass(classname);
    202             Object factory = factoryClass.newInstance();
    203 
    204             // Backward compatibility : if factory classes implements old interface,
    205             // provide appropriate wrapper
    206             if (factory instanceof ComponentDefinitionsFactory) {
    207                 factory =
    208                     new ComponentDefinitionsFactoryWrapper(
    209                         (ComponentDefinitionsFactory) factory);
    210             }
    211             return (DefinitionsFactory) factory;
    212 
    213         } catch (ClassCastException ex) { // Bad classname
    214             throw new DefinitionsFactoryException(
    215                 "Error - createDefinitionsFactory : Factory class '"
    216                     + classname
    217                     + " must implement 'TilesDefinitionsFactory'.",
    218                 ex);
    219 
    220         } catch (ClassNotFoundException ex) { // Bad classname
    221             throw new DefinitionsFactoryException(
    222                 "Error - createDefinitionsFactory : Bad class name '"
    223                     + classname
    224                     + "'.",
    225                 ex);
    226 
    227         } catch (InstantiationException ex) { // Bad constructor or error
    228             throw new DefinitionsFactoryException(ex);
    229 
    230         } catch (IllegalAccessException ex) {
    231             throw new DefinitionsFactoryException(ex);
    232         }
    233     }
    234 
    235     /**
    236      * Make definition factory accessible to Tags.
    237      * Factory is stored in servlet context.
    238      * @param factory Factory to be made accessible.
    239      * @param servletContext Current servlet context.
    240      */
    241     protected void makeDefinitionsFactoryAccessible(
    242         DefinitionsFactory factory,
    243         ServletContext servletContext) {
    244 
    245         servletContext.setAttribute(DEFINITIONS_FACTORY, factory);
    246     }
    247 
    248 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
