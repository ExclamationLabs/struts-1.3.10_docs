[View Javadoc](../../../../../apidocs/org/apache/struts/chain/Constants.html.md)


    1   /*
    2    * $Id: Constants.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain;
    22  
    23  
    24  /**
    25   * <p>Global constants for the Chain of Responsibility Library.</p>
    26   */
    27  public final class Constants {
    28      // -------------------------------------------------- Context Attribute Keys
    29  
    30      /**
    31       * <p>The default context attribute under which the Action for the current
    32       * request will be stored.</p>
    33       */
    34      public static final String ACTION_KEY = "action";
    35  
    36      /**
    37       * <p>The default context attribute under which the ActionConfig for the
    38       * current request will be stored.</p>
    39       */
    40      public static final String ACTION_CONFIG_KEY = "actionConfig";
    41  
    42      /**
    43       * <p>The default context attribute under which the ActionForm for the
    44       * current request will be stored.</p>
    45       */
    46      public static final String ACTION_FORM_KEY = "actionForm";
    47  
    48      /**
    49       * <p>The default context attribute under which the ActionServet for the
    50       * current application will be stored.</p>
    51       */
    52      public static final String ACTION_SERVLET_KEY = "actionServlet";
    53  
    54      /**
    55       * <p>The default context attribute under which a boolean flag indicating
    56       * whether this request has been cancelled will be stored.</p>
    57       */
    58      public static final String CANCEL_KEY = "cancel";
    59  
    60      /**
    61       * <p>The default context attribute under which an Exception will be
    62       * stored before passing it to an exception handler chain.</p>
    63       */
    64      public static final String EXCEPTION_KEY = "exception";
    65  
    66      /**
    67       * <p>The default context attribute under which the ForwardConfig for the
    68       * current request will be stored.</p>
    69       */
    70      public static final String FORWARD_CONFIG_KEY = "forwardConfig";
    71  
    72      /**
    73       * <p>The default context attribute under which the include path for the
    74       * current request will be stored.</p>
    75       */
    76      public static final String INCLUDE_KEY = "include";
    77  
    78      /**
    79       * <p>The default context attribute under which the Locale for the current
    80       * request will be stored.</p>
    81       */
    82      public static final String LOCALE_KEY = "locale";
    83  
    84      /**
    85       * <p>The default context attribute under which the MessageResources for
    86       * the current request will be stored.</p>
    87       */
    88      public static final String MESSAGE_RESOURCES_KEY = "messageResources";
    89  
    90      /**
    91       * <p>The default context attribute under which the ModuleConfig for the
    92       * current request will be stored.</p>
    93       */
    94      public static final String MODULE_CONFIG_KEY = "moduleConfig";
    95  
    96      /**
    97       * <p>The default context attribute key under which a Boolean is stored,
    98       * indicating the valid state of the current request.  If not present, a
    99       * value of Boolean.FALSE should be assumed.
    100      */
    101     public static final String VALID_KEY = "valid";
    102 
    103     // --------------------------------------------------------- Other Constants
    104 
    105     /**
    106      * <p>The base part of the context attribute under which a Map containing
    107      * the Action instances associated with this module are stored. This value
    108      * must be suffixed with the module prefix in order to create a unique key
    109      * per module.</p>
    110      */
    111     public static final String ACTIONS_KEY = "actions";
    112 
    113     /**
    114      * <p>The context attribute under which the Catalog containing our defined
    115      * command chains has been stored.</p>
    116      */
    117     public static final String CATALOG_ATTR = "org.apache.struts.chain.CATALOG";
    118 
    119     /**
    120      * <p>The request attribute under which the path information is stored for
    121      * processing during a RequestDispatcher.include() call.</p>
    122      */
    123     public static final String INCLUDE_PATH_INFO =
    124         "javax.servlet.include.path_info";
    125 
    126     /**
    127      * <p>The request attribute under which the servlet path is stored for
    128      * processing during a RequestDispatcher.include() call.</p>
    129      */
    130     public static final String INCLUDE_SERVLET_PATH =
    131         "javax.servlet.include.servlet_path";
    132 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
