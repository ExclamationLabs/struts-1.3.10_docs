[View Javadoc](../../../../../../apidocs/org/apache/struts/apps/scriptingmailreader/Constants.html.md)


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
    21  
    22  
    23  package org.apache.struts.apps.scriptingmailreader;
    24  
    25  
    26  /**
    27   * <p>
    28   * Manifest constants for the MailReader application.
    29   * </p>
    30   *
    31   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    32   */
    33  
    34  public final class Constants {
    35  
    36      // --- Tokens ----
    37  
    38      /**
    39       * <p>
    40       * The token representing a "create" task.
    41       * </p>
    42       */
    43      public static final String CREATE = "Create";
    44  
    45      /**
    46       * <p>
    47       * The application scope attribute under which our user database
    48       * is stored.
    49       * </p>
    50       */
    51      public static final String DATABASE_KEY = "database";
    52  
    53      /**
    54       * <p>
    55       * The token representing a "edit" task.
    56       * </p>
    57       */
    58      public static final String DELETE = "Delete";
    59  
    60      /**
    61       * <p>
    62       * The token representing a "edit" task.
    63       * </p>
    64       */
    65      public static final String EDIT = "Edit";
    66  
    67      /**
    68       * <p>
    69       * The request attributes key under the WelcomeAction stores an ArrayList
    70       * of error messages, if required resources are missing.
    71       * </p>
    72       */
    73      public static final String ERROR_KEY = "ERROR";
    74  
    75      /**
    76       * <p>
    77       * The token representing a "failure" result for this application.
    78       * </p>
    79       */
    80      public static final String FAILURE = "Failure";
    81  
    82      /**
    83       * <p>
    84       * The token representing a "logon" result for this application.
    85       * </p>
    86       */
    87      public static final String LOGON = "Logon";
    88  
    89      /**
    90       * <p>
    91       * The package name for this application.
    92       * </p>
    93       */
    94      public static final String PACKAGE = "org.apache.struts.apps.scriptingmailreader";
    95  
    96      /**
    97       * <p>
    98       * The token representing a "save" task.
    99       * </p>
    100      */
    101     public static final String SAVE = "Save";
    102 
    103     /**
    104      * <p>
    105      * The session scope attribute under which the Subscription object
    106      * currently selected by our logged-in User is stored.
    107      * </p>
    108      */
    109     public static final String SUBSCRIPTION_KEY = "subscription";
    110 
    111     /**
    112      * <p>
    113      * The token representing a "success" result for this application.
    114      * </p>
    115      */
    116     public static final String SUCCESS = "Success";
    117 
    118     /**
    119      * <p>
    120      * The session scope attribute under which the User object
    121      * for the currently logged in user is stored.
    122      * </p>
    123      */
    124     public static final String USER_KEY = "user";
    125 
    126     // ---- Error Messages ----
    127 
    128     /**
    129      * <p>
    130      * A static message in case database resource is not loaded.
    131      * <p>
    132      */
    133     public static final String ERROR_DATABASE_NOT_LOADED =
    134             "ERROR:  User database not loaded -- check servlet container logs for error messages.";
    135 
    136     /**
    137      * <p>
    138      * A static message in case message resource is not loaded.
    139      * </p>
    140      */
    141     public static final String ERROR_MESSAGES_NOT_LOADED =
    142             "ERROR:  Message resources not loaded -- check servlet container logs for error messages.";
    143 
    144     // ---- Error Tokens ----
    145 
    146     /**
    147      * <p>
    148      * The resource key for an error with the transactional token.
    149      * </p>
    150      */
    151     public static final String MSG_TRANSACTION_TOKEN = "error.transaction.token";
    152 
    153     // ---- Log Messages ----
    154 
    155     /**
    156      * <p>
    157      * The message to log when cancelling a transaction.
    158      * </p>
    159      */
    160     public static final String LOG_CANCEL = " Transaction cancelled: ";
    161 
    162     /**
    163      * <p>
    164      * The message to log when forwarding to a result.
    165      * </p>
    166      */
    167     public static final String LOG_RESULT = " Forwarding to result: ";
    168 
    169     /**
    170      * <p>
    171      * The message to log when forwarding to a 'failure' result.
    172      * <p>
    173      */
    174     public static final String LOG_FAILURE = LOG_RESULT + FAILURE;
    175 
    176     /**
    177      * <p>
    178      * The message to log when forwarding to a 'logon' result.
    179      * </p>
    180      */
    181     public static final String LOG_LOGON = LOG_RESULT + LOGON;
    182 
    183     /**
    184      * <p>
    185      * The message to log when populating a form.
    186      * </p>
    187      */
    188     public static final String LOG_POPULATE_FORM = " Populating form from: ";
    189 
    190     /**
    191      * <p>
    192      * The message to log when populating a subscription.
    193      * </p>
    194      */
    195     public static final String LOG_POPULATE_SUBSCRIPTION = " Populating subscription: ";
    196 
    197     /**
    198      * <p>
    199      * The message to log when populating a user.
    200      * </p>
    201      */
    202     public static final String LOG_POPULATE_USER = " Populating user: ";
    203 
    204     /**
    205      * <p>
    206      * The message to log when forwarding to a 'success' result.
    207      * </p>
    208      */
    209     public static final String LOG_PROCESSING = " Processing: ";
    210 
    211     /**
    212      * <p>
    213      * The message to log when forwarding to a 'success' result.
    214      * </p>
    215      */
    216     public static final String LOG_SUCCESS = LOG_RESULT + SUCCESS;
    217 
    218     /**
    219      * <p>
    220      * The message to log when setting a transactional token.
    221      * </p>
    222      */
    223     public static final String LOG_TOKEN = " Setting transactional control token";
    224 
    225     /**
    226      * <p>
    227      * The message to log when checking a transactional token.
    228      * </p>
    229      */
    230     public static final String LOG_TOKEN_CHECK = " Checking transactional control token";
    231 
    232 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
