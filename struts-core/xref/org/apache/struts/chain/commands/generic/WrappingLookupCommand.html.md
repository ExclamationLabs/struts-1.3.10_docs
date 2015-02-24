[View Javadoc](../../../../../../../apidocs/org/apache/struts/chain/commands/generic/WrappingLookupCommand.html.md)


    1   /*
    2    * $Id: WrappingLookupCommand.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands.generic;
    22  
    23  import org.apache.commons.beanutils.ConstructorUtils;
    24  import org.apache.commons.chain.Catalog;
    25  import org.apache.commons.chain.CatalogFactory;
    26  import org.apache.commons.chain.Command;
    27  import org.apache.commons.chain.Context;
    28  import org.apache.commons.chain.Filter;
    29  import org.apache.commons.logging.Log;
    30  import org.apache.commons.logging.LogFactory;
    31  import org.apache.struts.chain.commands.util.ClassUtils;
    32  
    33  import java.lang.reflect.InvocationTargetException;
    34  
    35  /**
    36   * <p>Variant on chain LookupCommand which can optionally wrap the context it
    37   * passes to the looked up command in an alternative class.</p>
    38   */
    39  public class WrappingLookupCommand implements Filter {
    40      /**
    41       * Provide Commons Logging instance for this class.
    42       */
    43      private static final Log LOG =
    44          LogFactory.getLog(WrappingLookupCommand.class);
    45  
    46      // ------------------------------------------------------ Instance Variables
    47  
    48      /**
    49       * <p>Field for property.</p>
    50       */
    51      private String catalogName = null;
    52  
    53      /**
    54       * <p>Field for property.</p>
    55       */
    56      private String name = null;
    57  
    58      /**
    59       * <p>Field for property.</p>
    60       */
    61      private String nameKey = null;
    62  
    63      /**
    64       * <p>Field for property.</p>
    65       */
    66      private String wrapperClassName = null;
    67  
    68      /**
    69       * <p>Field for property.</p>
    70       */
    71      private boolean optional = false;
    72  
    73      /**
    74       * <p>Zero-argument constructor.</p>
    75       */
    76      public WrappingLookupCommand() {
    77          catalogName = null;
    78          name = null;
    79          nameKey = null;
    80          optional = false;
    81      }
    82  
    83      /**
    84       * <p>Return CatalogName property.  </p>
    85       *
    86       * @return Value of CatalogName property.
    87       */
    88      public String getCatalogName() {
    89          return catalogName;
    90      }
    91  
    92      /**
    93       * <p>Set CatalogName property.</p>
    94       *
    95       * @param catalogName New value for CatalogName
    96       */
    97      public void setCatalogName(String catalogName) {
    98          this.catalogName = catalogName;
    99      }
    100 
    101     /**
    102      * <p>Retrieve Name property.</p>
    103      *
    104      * @return Value of Name property
    105      */
    106     public String getName() {
    107         return name;
    108     }
    109 
    110     /**
    111      * <p>Set Name property.</p>
    112      *
    113      * @param name New value for Name
    114      */
    115     public void setName(String name) {
    116         this.name = name;
    117     }
    118 
    119     /**
    120      * <p>Return NameKey property.</p>
    121      *
    122      * @return Value of NameKey property.
    123      */
    124     public String getNameKey() {
    125         return nameKey;
    126     }
    127 
    128     /**
    129      * <p>Set NameKey property.</p>
    130      *
    131      * @param nameKey New value for NameKey
    132      */
    133     public void setNameKey(String nameKey) {
    134         this.nameKey = nameKey;
    135     }
    136 
    137     /**
    138      * <p>Test Optional property.</p>
    139      *
    140      * @return TRUE if Optional is TRUE.
    141      */
    142     public boolean isOptional() {
    143         return optional;
    144     }
    145 
    146     /**
    147      * <p>Set Optional property.</p>
    148      *
    149      * @param optional New value for Optional
    150      */
    151     public void setOptional(boolean optional) {
    152         this.optional = optional;
    153     }
    154 
    155     /**
    156      * <p>Return the WrapperClass property.</p>
    157      *
    158      * @return The WrapperClass property
    159      */
    160     public String getWrapperClassName() {
    161         return wrapperClassName;
    162     }
    163 
    164     /**
    165      * <p>Set WrappClassName property. </p>
    166      *
    167      * @param wrapperClassName The name of a WrapperClass
    168      */
    169     public void setWrapperClassName(String wrapperClassName) {
    170         this.wrapperClassName = wrapperClassName;
    171     }
    172 
    173     /**
    174      * <p>Invoke the Command for a Context, returning TRUE if processing
    175      * should halt.</p>
    176      *
    177      * @param context Our ActionContext
    178      * @return TRUE if processing should halt
    179      * @throws Exception On any error
    180      */
    181     public boolean execute(Context context)
    182         throws Exception {
    183         if (LOG.isTraceEnabled()) {
    184             LOG.trace("execute [" + this + "]");
    185         }
    186 
    187         Command command = getCommand(context);
    188 
    189         if (command != null) {
    190             return command.execute(getContext(context));
    191         } else {
    192             return false;
    193         }
    194     }
    195 
    196     /**
    197      * <p>Process the Exception for any Command that is a filter.</p>
    198      *
    199      * @param context   Our ActionContext
    200      * @param exception The Exception thrown by another Comamnd in a Chain
    201      * @return TRUE if there is a Filter to process
    202      */
    203     public boolean postprocess(Context context, Exception exception) {
    204         Command command = getCommand(context);
    205 
    206         if ((command != null) && (command instanceof Filter)) {
    207             try {
    208                 return ((Filter) command).postprocess(getContext(context),
    209                     exception);
    210             } catch (NoSuchMethodException ex) {
    211                 LOG.error("Error wrapping context in postprocess", ex);
    212             } catch (IllegalAccessException ex) {
    213                 LOG.error("Error wrapping context in postprocess", ex);
    214             } catch (InvocationTargetException ex) {
    215                 LOG.error("Error wrapping context in postprocess", ex);
    216             } catch (InstantiationException ex) {
    217                 LOG.error("Error wrapping context in postprocess", ex);
    218             } catch (ClassNotFoundException ex) {
    219                 LOG.error("Error wrapping context in postprocess", ex);
    220             }
    221         }
    222 
    223         return false;
    224     }
    225 
    226     /**
    227      * <p>Return the Command to process for this Context.</p>
    228      *
    229      * @param context The Context we are processing
    230      * @return The Command to process for this Context
    231      */
    232     protected Command getCommand(Context context) {
    233         CatalogFactory catalogFactory = CatalogFactory.getInstance();
    234         String catalogName = getCatalogName();
    235         Catalog catalog;
    236 
    237         if (catalogName == null) {
    238             catalog = catalogFactory.getCatalog();
    239             catalogName = "{default}"; // for debugging purposes
    240         } else {
    241             catalog = catalogFactory.getCatalog(catalogName);
    242         }
    243 
    244         if (catalog == null) {
    245             throw new IllegalArgumentException("Cannot find catalog '"
    246                 + catalogName + "'");
    247         }
    248 
    249         Command command;
    250         String name = getName();
    251 
    252         if (name == null) {
    253             name = (String) context.get(getNameKey());
    254         }
    255 
    256         if (name != null) {
    257             if (LOG.isDebugEnabled()) {
    258                 LOG.debug("Lookup command " + name + " in catalog "
    259                     + catalogName);
    260             }
    261 
    262             command = catalog.getCommand(name);
    263 
    264             if (LOG.isDebugEnabled()) {
    265                 LOG.debug("Found command " + command + ";" + " optional: "
    266                     + isOptional());
    267             }
    268 
    269             if ((command == null) && !isOptional()) {
    270                 throw new IllegalArgumentException("Cannot find command " + "'"
    271                     + name + "' in catalog '" + catalogName + "'");
    272             } else {
    273                 return command;
    274             }
    275         } else {
    276             throw new IllegalArgumentException("No command name");
    277         }
    278     }
    279 
    280     /**
    281      * <p>If the wrapperClassName property is not null, return a Context of
    282      * the type specified by wrapperClassName, instantiated using a single-arg
    283      * constructor which takes the context passed as an argument to this
    284      * method.</p>
    285      *
    286      * <p>This method throws an exception if the wrapperClass cannot be found,
    287      * or if there are any errors instantiating the wrapping context.</p>
    288      *
    289      * @param context Context we are processing
    290      * @return Context wrapper
    291      * @throws ClassNotFoundException    On failed instantiation
    292      * @throws InstantiationException    On failed instantiation
    293      * @throws InvocationTargetException On failed instantiation
    294      * @throws IllegalAccessException    On failed instantiation
    295      * @throws NoSuchMethodException     On failed instantiation
    296      */
    297     protected Context getContext(Context context)
    298         throws ClassNotFoundException, InstantiationException,
    299             InvocationTargetException, IllegalAccessException,
    300             NoSuchMethodException {
    301         if (wrapperClassName == null) {
    302             if (LOG.isDebugEnabled()) {
    303                 LOG.debug("No defined wrapper class; "
    304                     + "returning original context.");
    305             }
    306 
    307             return context;
    308         }
    309 
    310         if (LOG.isDebugEnabled()) {
    311             LOG.debug("Looking for wrapper class: " + wrapperClassName);
    312         }
    313 
    314         Class wrapperClass = ClassUtils.getApplicationClass(wrapperClassName);
    315 
    316         if (LOG.isDebugEnabled()) {
    317             LOG.debug("Instantiating wrapper class");
    318         }
    319 
    320         return (Context) ConstructorUtils.invokeConstructor(wrapperClass,
    321             new Object[] { context });
    322     }
    323 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
