[View Javadoc](../../../../../../../apidocs/org/apache/struts/tiles/taglib/util/TagUtils.html.md)


    1   /*
    2    * $Id: TagUtils.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles.taglib.util;
    23  
    24  import java.lang.reflect.InvocationTargetException;
    25  import java.util.Map;
    26  import java.util.HashMap;
    27  
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.PageContext;
    30  
    31  import org.apache.commons.beanutils.PropertyUtils;
    32  import org.apache.struts.Globals;
    33  import org.apache.struts.tiles.taglib.ComponentConstants;
    34  import org.apache.struts.tiles.ComponentContext;
    35  import org.apache.struts.tiles.ComponentDefinition;
    36  import org.apache.struts.tiles.DefinitionsFactoryException;
    37  import org.apache.struts.tiles.FactoryNotFoundException;
    38  import org.apache.struts.tiles.NoSuchDefinitionException;
    39  import org.apache.struts.tiles.TilesUtil;
    40  
    41  /**
    42   * Collection of utilities.
    43   * This class also serves as an interface between Components and Struts. If
    44   * you want to rip away Struts, simply reimplement some methods in this class.
    45   * You can copy them from Struts.
    46   *
    47   */
    48  public class TagUtils {
    49  
    50      /** Debug flag */
    51      public static final boolean debug = true;
    52  
    53      /**
    54       * Maps lowercase JSP scope names to their PageContext integer constant
    55       * values.
    56       */
    57      private static final Map scopes = new HashMap();
    58  
    59      /**
    60       * Initialize the scope names map and the encode variable with the
    61       * Java 1.4 method if available.
    62       */
    63      static {
    64          scopes.put("page", new Integer(PageContext.PAGE_SCOPE));
    65          scopes.put("request", new Integer(PageContext.REQUEST_SCOPE));
    66          scopes.put("session", new Integer(PageContext.SESSION_SCOPE));
    67          scopes.put("application", new Integer(PageContext.APPLICATION_SCOPE));
    68      }
    69  
    70  
    71      /**
    72      * Get scope value from string value
    73      * @param scopeName Scope as a String.
    74      * @param defaultValue Returned default value, if not found.
    75      * @return Scope as an <code>int</code>, or <code>defaultValue</code> if scope is <code>null</code>.
    76      * @throws JspException Scope name is not recognized as a valid scope.
    77      */
    78      public static int getScope(String scopeName, int defaultValue) throws JspException {
    79          if (scopeName == null) {
    80              return defaultValue;
    81          }
    82  
    83          if (scopeName.equalsIgnoreCase("component")) {
    84              return ComponentConstants.COMPONENT_SCOPE;
    85  
    86          } else if (scopeName.equalsIgnoreCase("template")) {
    87              return ComponentConstants.COMPONENT_SCOPE;
    88  
    89          } else if (scopeName.equalsIgnoreCase("tile")) {
    90              return ComponentConstants.COMPONENT_SCOPE;
    91  
    92          } else {
    93              return getScope(scopeName);
    94          }
    95      }
    96  
    97      /**
    98       * Converts the scope name into its corresponding PageContext constant value.
    99       * @param scopeName Can be "page", "request", "session", or "application" in any
    100      * case.
    101      * @return The constant representing the scope (ie. PageContext.REQUEST_SCOPE).
    102      * @throws JspException if the scopeName is not a valid name.
    103      */
    104     public static int getScope(String scopeName) throws JspException {
    105         Integer scope = (Integer) scopes.get(scopeName.toLowerCase());
    106 
    107         if (scope == null) {
    108             //throw new JspException(messages.getMessage("lookup.scope", scope));
    109             throw new JspException("Unable to retrieve the scope "+scopeName);
    110         }
    111 
    112         return scope.intValue();
    113     }
    114 
    115 
    116     /**
    117      * Retrieve bean from page context, using specified scope.
    118      * If scope is not set, use <code>findAttribute()</code>.
    119      *
    120      * @param beanName Name of bean to retrieve.
    121      * @param scopeName Scope or <code>null</code>. If <code>null</code>, bean is searched using
    122      *  findAttribute().
    123      * @param pageContext Current pageContext.
    124      * @return Requested bean or <code>null</code> if not found.
    125      * @throws JspException Scope name is not recognized as a valid scope.
    126      */
    127     public static Object retrieveBean(String beanName, String scopeName, PageContext pageContext)
    128         throws JspException {
    129 
    130         if (scopeName == null) {
    131             return findAttribute(beanName, pageContext);
    132         }
    133 
    134         // Default value doesn't matter because we have already check it
    135         int scope = getScope(scopeName, PageContext.PAGE_SCOPE);
    136 
    137         //return pageContext.getAttribute( beanName, scope );
    138         return getAttribute(beanName, scope, pageContext);
    139     }
    140 
    141     /**
    142      * Search attribute in different contexts.
    143      * First, check in component context, then use pageContext.findAttribute().
    144      * @param beanName Name of bean to retrieve.
    145      * @param pageContext Current pageContext.
    146      * @return Requested bean or <code>null</code> if not found.
    147      */
    148     public static Object findAttribute(String beanName, PageContext pageContext) {
    149         ComponentContext compContext = ComponentContext.getContext(pageContext.getRequest());
    150 
    151         if (compContext != null) {
    152             Object attribute = compContext.findAttribute(beanName, pageContext);
    153             if (attribute != null) {
    154                 return attribute;
    155             }
    156         }
    157 
    158         // Search in pageContext scopes
    159         return pageContext.findAttribute(beanName);
    160     }
    161 
    162     /**
    163      * Get object from requested context. Return <code>null</code> if not found.
    164      * Context can be "component" or normal JSP contexts.
    165      * @param beanName Name of bean to retrieve.
    166      * @param scope Scope from which bean must be retrieved.
    167      * @param pageContext Current pageContext.
    168      * @return Requested bean or <code>null</code> if not found.
    169      */
    170     public static Object getAttribute(String beanName, int scope, PageContext pageContext) {
    171         if (scope == ComponentConstants.COMPONENT_SCOPE) {
    172             ComponentContext compContext = ComponentContext.getContext(pageContext.getRequest());
    173             return compContext.getAttribute(beanName);
    174         }
    175         return pageContext.getAttribute(beanName, scope);
    176     }
    177 
    178     /**
    179      * Locate and return the specified property of the specified bean, from
    180      * an optionally specified scope, in the specified page context.
    181      *
    182      * @param pageContext Page context to be searched.
    183      * @param beanName Name of the bean to be retrieved.
    184      * @param beanProperty Name of the property to be retrieved, or
    185      *  <code>null</code> to retrieve the bean itself.
    186      * @param beanScope Scope to be searched (page, request, session, application)
    187      *  or <code>null</code> to use <code>findAttribute()</code> instead.
    188      *
    189      * @exception JspException Scope name is not recognized as a valid scope
    190      * @exception JspException if the specified bean is not found
    191      * @exception JspException if accessing this property causes an
    192      *  IllegalAccessException, IllegalArgumentException,
    193      *  InvocationTargetException, or NoSuchMethodException
    194      */
    195     public static Object getRealValueFromBean(
    196         String beanName,
    197         String beanProperty,
    198         String beanScope,
    199         PageContext pageContext)
    200         throws JspException {
    201 
    202         try {
    203             Object realValue;
    204             Object bean = retrieveBean(beanName, beanScope, pageContext);
    205             if (bean != null && beanProperty != null) {
    206                 realValue = PropertyUtils.getProperty(bean, beanProperty);
    207             } else {
    208                 realValue = bean; // value can be null
    209             }
    210             return realValue;
    211 
    212         } catch (NoSuchMethodException ex) {
    213             throw new JspException(
    214                 "Error - component.PutAttributeTag : Error while retrieving value from bean '"
    215                     + beanName
    216                     + "' with property '"
    217                     + beanProperty
    218                     + "' in scope '"
    219                     + beanScope
    220                     + "'. (exception : "
    221                     + ex.getMessage(), ex);
    222 
    223         } catch (InvocationTargetException ex) {
    224             throw new JspException(
    225                 "Error - component.PutAttributeTag : Error while retrieving value from bean '"
    226                     + beanName
    227                     + "' with property '"
    228                     + beanProperty
    229                     + "' in scope '"
    230                     + beanScope
    231                     + "'. (exception : "
    232                     + ex.getMessage(), ex);
    233 
    234         } catch (IllegalAccessException ex) {
    235             throw new JspException(
    236                 "Error - component.PutAttributeTag : Error while retrieving value from bean '"
    237                     + beanName
    238                     + "' with property '"
    239                     + beanProperty
    240                     + "' in scope '"
    241                     + beanScope
    242                     + "'. (exception : "
    243                     + ex.getMessage(), ex);
    244         }
    245     }
    246 
    247     /**
    248      * Store bean in requested context.
    249      * If scope is <code>null</code>, save it in REQUEST_SCOPE context.
    250      *
    251      * @param pageContext Current pageContext.
    252      * @param name Name of the bean.
    253      * @param scope Scope under which bean is saved (page, request, session, application)
    254      *  or <code>null</code> to store in <code>request()</code> instead.
    255      * @param value Bean value to store.
    256      *
    257      * @exception JspException Scope name is not recognized as a valid scope
    258      */
    259     public static void setAttribute(
    260         PageContext pageContext,
    261         String name,
    262         Object value,
    263         String scope)
    264         throws JspException {
    265 
    266         if (scope == null)
    267             pageContext.setAttribute(name, value, PageContext.REQUEST_SCOPE);
    268         else if (scope.equalsIgnoreCase("page"))
    269             pageContext.setAttribute(name, value, PageContext.PAGE_SCOPE);
    270         else if (scope.equalsIgnoreCase("request"))
    271             pageContext.setAttribute(name, value, PageContext.REQUEST_SCOPE);
    272         else if (scope.equalsIgnoreCase("session"))
    273             pageContext.setAttribute(name, value, PageContext.SESSION_SCOPE);
    274         else if (scope.equalsIgnoreCase("application"))
    275             pageContext.setAttribute(name, value, PageContext.APPLICATION_SCOPE);
    276         else {
    277             throw new JspException("Error - bad scope name '" + scope + "'");
    278         }
    279     }
    280 
    281     /**
    282      * Store bean in REQUEST_SCOPE context.
    283      *
    284      * @param pageContext Current pageContext.
    285      * @param name Name of the bean.
    286      * @param beanValue Bean value to store.
    287      *
    288      * @exception JspException Scope name is not recognized as a valid scope
    289      */
    290     public static void setAttribute(PageContext pageContext, String name, Object beanValue)
    291         throws JspException {
    292         pageContext.setAttribute(name, beanValue, PageContext.REQUEST_SCOPE);
    293     }
    294 
    295     /**
    296      * Save the specified exception as a request attribute for later use.
    297      *
    298      * @param pageContext The PageContext for the current page.
    299      * @param exception The exception to be saved.
    300      */
    301     public static void saveException(PageContext pageContext, Throwable exception) {
    302         pageContext.setAttribute(Globals.EXCEPTION_KEY, exception, PageContext.REQUEST_SCOPE);
    303     }
    304 
    305     /**
    306      * Get component definition by its name.
    307      * @param name Definition name.
    308      * @param pageContext The PageContext for the current page.
    309      * @throws JspException -
    310      */
    311     public static ComponentDefinition getComponentDefinition(String name, PageContext pageContext)
    312         throws JspException {
    313 
    314         try {
    315             return TilesUtil.getDefinition(
    316                 name,
    317                 pageContext.getRequest(),
    318                 pageContext.getServletContext());
    319 
    320         } catch (NoSuchDefinitionException ex) {
    321             throw new JspException(
    322                 "Error : Can't get component definition for '"
    323                     + name
    324                     + "'. Check if this name exist in component definitions.",ex);
    325         } catch (FactoryNotFoundException ex) { // factory not found.
    326             throw new JspException(ex);
    327 
    328         } catch (DefinitionsFactoryException ex) {
    329             if (debug)
    330                 ex.printStackTrace();
    331             // Save exception to be able to show it later
    332             saveException(pageContext, ex);
    333             throw new JspException(ex);
    334         }
    335     }
    336 
    337 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
