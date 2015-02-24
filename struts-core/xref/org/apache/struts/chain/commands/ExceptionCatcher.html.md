[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/ExceptionCatcher.html.md)


    1   /*
    2    * $Id: ExceptionCatcher.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands;
    22  
    23  import org.apache.commons.chain.Catalog;
    24  import org.apache.commons.chain.CatalogFactory;
    25  import org.apache.commons.chain.Command;
    26  import org.apache.commons.chain.Context;
    27  import org.apache.commons.chain.Filter;
    28  import org.apache.commons.logging.Log;
    29  import org.apache.commons.logging.LogFactory;
    30  import org.apache.struts.chain.contexts.ActionContext;
    31  
    32  /**
    33   * <p>Intercept any exception thrown by a subsequent <code>Command</code> in
    34   * this processing chain, and fire the configured exception handler chain
    35   * after storing the exception that has occurred into the
    36   * <code>Context</code>. </p>
    37   *
    38   * @version $Rev: 471754 $ $Date: 2005-11-12 13:01:44 -0500 (Sat, 12 Nov 2005)
    39   *          $
    40   */
    41  public class ExceptionCatcher extends ActionCommandBase implements Filter {
    42      /**
    43       * <p> Provide Commons Logging instance for this class. </p>
    44       */
    45      private static final Log LOG = LogFactory.getLog(ExceptionCatcher.class);
    46  
    47      // ------------------------------------------------------ Instance Variables
    48  
    49      /**
    50       * <p> Field for CatalogName property. </p>
    51       */
    52      private String catalogName = null;
    53  
    54      /**
    55       * <p> Field for ExceptionCommand property. </p>
    56       */
    57      private String exceptionCommand = null;
    58  
    59      // -------------------------------------------------------------- Properties
    60  
    61      /**
    62       * <p> Return the name of the <code>Catalog</code> in which to perform
    63       * lookups, or <code>null</code> for the default <code>Catalog</code>.
    64       * </p>
    65       *
    66       * @return Name of catalog to use, or null
    67       */
    68      public String getCatalogName() {
    69          return (this.catalogName);
    70      }
    71  
    72      /**
    73       * <p>Set the name of the <code>Catalog</code> in which to perform
    74       * lookups, or <code>null</code> for the default <code>Catalog</code>.</p>
    75       *
    76       * @param catalogName The new catalog name or <code>null</code>
    77       */
    78      public void setCatalogName(String catalogName) {
    79          this.catalogName = catalogName;
    80      }
    81  
    82      /**
    83       * <p> Return the name of the command to be executed if an exception
    84       * occurs. </p>
    85       *
    86       * @return The name of the command to be executed on an exception
    87       */
    88      public String getExceptionCommand() {
    89          return (this.exceptionCommand);
    90      }
    91  
    92      /**
    93       * <p>Set the name of the command to be executed if an exception
    94       * occurs.</p>
    95       *
    96       * @param exceptionCommand The name of the chain to be executed
    97       */
    98      public void setExceptionCommand(String exceptionCommand) {
    99          this.exceptionCommand = exceptionCommand;
    100     }
    101 
    102     // ---------------------------------------------------------- Public Methods
    103 
    104     /**
    105      * <p>Clear any existing stored exception and pass the
    106      * <code>context</code> on to the remainder of the current chain.</p>
    107      *
    108      * @param actionCtx The <code>Context</code> for the current request
    109      * @return <code>false</code> so that processing continues
    110      * @throws Exception On any error
    111      */
    112     public boolean execute(ActionContext actionCtx)
    113         throws Exception {
    114         actionCtx.setException(null);
    115 
    116         return (false);
    117     }
    118 
    119     /**
    120      * <p>If an exception was thrown by a subsequent <code>Command</code>,
    121      * pass it on to the specified exception handling chain.  Otherwise, do
    122      * nothing.</p>
    123      *
    124      * @param context   The {@link Context} to be processed by this {@link
    125      *                  Filter}
    126      * @param exception The <code>Exception</code> (if any) that was thrown by
    127      *                  the last {@link Command} that was executed; otherwise
    128      *                  <code>null</code>
    129      * @return TRUE if post processing an exception occurred and the exception
    130      *         processing chain invoked
    131      * @throws IllegalStateException If exception throws exception
    132      */
    133     public boolean postprocess(Context context, Exception exception) {
    134         // Do nothing if there was no exception thrown
    135         if (exception == null) {
    136             return (false);
    137         }
    138 
    139         // Stash the exception in the specified context attribute
    140         if (LOG.isDebugEnabled()) {
    141             LOG.debug("Attempting to handle a thrown exception");
    142         }
    143 
    144         ActionContext actionCtx = (ActionContext) context;
    145 
    146         actionCtx.setException(exception);
    147 
    148         // Execute the specified command
    149         try {
    150             Command command = lookupExceptionCommand();
    151 
    152             if (command == null) {
    153                 LOG.error("Cannot find exceptionCommand '" + exceptionCommand
    154                     + "'");
    155                 throw new IllegalStateException(
    156                     "Cannot find exceptionCommand '" + exceptionCommand + "'");
    157             }
    158 
    159             if (LOG.isTraceEnabled()) {
    160                 LOG.trace("Calling exceptionCommand '" + exceptionCommand + "'");
    161             }
    162 
    163             command.execute(context);
    164         } catch (Exception e) {
    165             LOG.warn("Exception from exceptionCommand '" + exceptionCommand
    166                 + "'", e);
    167             throw new IllegalStateException("Exception chain threw exception");
    168         }
    169 
    170         return (true);
    171     }
    172 
    173     /**
    174      * <p> Return the command to be executed if an exception occurs. </p>
    175      *
    176      * @return The command to be executed if an exception occurs
    177      * @throws IllegalArgumentException If catalog cannot be found
    178      * @throws IllegalStateException    If command property is not specified
    179      */
    180     protected Command lookupExceptionCommand() {
    181         String catalogName = getCatalogName();
    182         Catalog catalog;
    183 
    184         if (catalogName == null) {
    185             catalog = CatalogFactory.getInstance().getCatalog();
    186 
    187             if (catalog == null) {
    188                 LOG.error("Cannot find default catalog");
    189                 throw new IllegalArgumentException(
    190                     "Cannot find default catalog");
    191             }
    192         } else {
    193             catalog = CatalogFactory.getInstance().getCatalog(catalogName);
    194 
    195             if (catalog == null) {
    196                 LOG.error("Cannot find catalog '" + catalogName + "'");
    197                 throw new IllegalArgumentException("Cannot find catalog '"
    198                     + catalogName + "'");
    199             }
    200         }
    201 
    202         String exceptionCommand = getExceptionCommand();
    203 
    204         if (exceptionCommand == null) {
    205             LOG.error("No exceptionCommand property specified");
    206             throw new IllegalStateException(
    207                 "No exceptionCommand property specfied");
    208         }
    209 
    210         return catalog.getCommand(exceptionCommand);
    211     }
    212 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
