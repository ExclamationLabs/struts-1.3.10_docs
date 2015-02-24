[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/contexts/ActionContext.html.md)


    1   /*
    2    * $Id: ActionContext.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.contexts;
    22  
    23  import org.apache.commons.chain.Context;
    24  import org.apache.struts.action.Action;
    25  import org.apache.struts.action.ActionForm;
    26  import org.apache.struts.action.ActionMessages;
    27  import org.apache.struts.config.ActionConfig;
    28  import org.apache.struts.config.ForwardConfig;
    29  import org.apache.struts.config.ModuleConfig;
    30  import org.apache.struts.util.MessageResources;
    31  
    32  import java.util.Locale;
    33  import java.util.Map;
    34  
    35  /**
    36   * <p>An ActionContext represents a view of a commons-chain
    37   * <code>Context</code> which encapsulates access to request and
    38   * session-scoped resources and services</p>
    39   */
    40  public interface ActionContext extends Context {
    41      public static final String APPLICATION_SCOPE = "application";
    42      public static final String SESSION_SCOPE = "session";
    43      public static final String REQUEST_SCOPE = "request";
    44  
    45      // -------------------------------
    46      // General Application Support
    47      // -------------------------------
    48  
    49      /**
    50       * Signal to the instance that it will not be used any more, so that any
    51       * resources which should be cleaned up can be cleaned up.
    52       */
    53      void release();
    54  
    55      /**
    56       * <p>Return a <code>Map</code> of Application scoped values.</p>
    57       *
    58       * <p>This is implemented in analogy with the Application scope in the
    59       * Servlet API, but it seems reasonable to expect that any Struts
    60       * implementation will have an equivalent concept.</p>
    61       *
    62       * <p>The ultimate meaning of "application scope" is an implementation
    63       * detail left unspecified by Struts.</p>
    64       *
    65       * @return A Map of "application scope" attributes.
    66       */
    67      Map getApplicationScope();
    68  
    69      /**
    70       * <p>Return a <code>Map</code> of Session scoped values.  A session is
    71       * understood as a sequence of requests made by the same user.</p>
    72       *
    73       * <p>This is implemented in analogy with the Session scope in the Servlet
    74       * API, but it seems reasonable to expect that any Struts implementation
    75       * will have an equivalent concept.</p>
    76       *
    77       * <p>The ultimate meaning of "session scope" is an implementation detail
    78       * left unspecified by Struts.</p>
    79       *
    80       * @return A Map of "session scope" attributes.
    81       */
    82      Map getSessionScope();
    83  
    84      /**
    85       * <p>Return a <code>Map</code> of request scoped values.  A request is
    86       * understood as the fundamental motivation for any particular instance of
    87       * an <code>ActionContext</code>.</p>
    88       *
    89       * <p>This is implemented in analogy with the Request Context in the
    90       * Servlet API, but it seems reasonable to expect that any Struts
    91       * implementation will have an equivalent concept.</p>
    92       *
    93       * <p>The ultimate meaning of "request scope" is an implementation detail
    94       * left unspecified by Struts.</p>
    95       *
    96       * @return a Map of "request scope" attributes.
    97       */
    98      Map getRequestScope();
    99  
    100     /**
    101      * Return the Map representing the scope identified by
    102      * <code>scopeName</code>. Implementations should support at minimum the
    103      * names associated with the constants <code>APPLICATION_SCOPE</code>,
    104      * <code>SESSION_SCOPE</code>, and <code>REQUEST_SCOPE</code>, but are
    105      * permitted to support others as well.
    106      *
    107      * @param scopeName A token identifying a scope, including but not limited
    108      *                  to <code>APPLICATION_SCOPE</code>, <code>SESSION_SCOPE</code>,
    109      *                  <code>REQUEST_SCOPE</code>.
    110      * @return A Map of attributes for the specified scope.
    111      */
    112     Map getScope(String scopeName);
    113 
    114     /**
    115      * <p>Return a <code>Map</code> of parameters submitted by the user as
    116      * part of this request.  The keys to this map will be request parameter
    117      * names (of type <code>String</code>), and the values will be
    118      * <code>String[]</code>.</p>
    119      *
    120      * <p>This is implemented in analogy with the Request parameters of the
    121      * Servlet API, but it seems reasonable to expect that any Struts
    122      * implementation will have an equivalent concept.</p>
    123      *
    124      * @return A map of the request parameter attributes
    125      */
    126     Map getParameterMap();
    127 
    128     // -------------------------------
    129     // General Struts properties
    130     // -------------------------------
    131 
    132     /**
    133      * <p> Set the action which has been identified to be executed as part of
    134      * processing this request. </p>
    135      *
    136      * @param action
    137      */
    138     void setAction(Action action);
    139 
    140     /**
    141      * <p> Get the action which has been identified to be executed as part of
    142      * processing this request. </p>
    143      *
    144      * @return The action to be executed with this request
    145      */
    146     Action getAction();
    147 
    148     /**
    149      * <p> Set the ActionForm instance which will carry any data submitted as
    150      * part of this request. </p>
    151      *
    152      * @param form The ActionForm instance to use with this request
    153      */
    154     void setActionForm(ActionForm form);
    155 
    156     /**
    157      * <p> Get the ActionForm instance which will carry any data submitted as
    158      * part of this request. </p>
    159      *
    160      * @return The ActionForm being used with this request
    161      */
    162     ActionForm getActionForm();
    163 
    164     /**
    165      * <p> Set the ActionConfig class contains the details for processing this
    166      * request. </p>
    167      *
    168      * @param config The ActionConfig class to use with this request
    169      */
    170     void setActionConfig(ActionConfig config);
    171 
    172     /**
    173      * <p> Get the ActionConfig which contains the details for processing this
    174      * request.
    175      *
    176      * @return The ActionConfig class being used with this request </p>
    177      */
    178     ActionConfig getActionConfig();
    179 
    180     /**
    181      * <p> Set the ForwardConfig which should be used as the basis of the view
    182      * segment of the overall processing. This is the primary method of
    183      * "communication" with the "view" sub-chain. </p>
    184      *
    185      * @param forward The ForwardConfig to use with this request
    186      */
    187     void setForwardConfig(ForwardConfig forward);
    188 
    189     /**
    190      * <p> Get the ForwardConfig which has been identified as the basis for
    191      * view-processing. </p>
    192      *
    193      * @return The ForwardConfig being used with this request
    194      */
    195     ForwardConfig getForwardConfig();
    196 
    197     /**
    198      * <p> Set the include path which should be processed as part of
    199      * processing this request. </p>
    200      *
    201      * @param include The include path to be used with this request
    202      */
    203     void setInclude(String include);
    204 
    205     /**
    206      * <p> Get the include path which should be processed as part of
    207      * processing this request. </p>
    208      *
    209      * @return The include path being used with this request
    210      */
    211     String getInclude();
    212 
    213     /**
    214      * <p> Set the ModuleConfig which is operative for the current request.
    215      * </p>
    216      *
    217      * @param config The ModuleConfig to be used with this request
    218      */
    219     void setModuleConfig(ModuleConfig config);
    220 
    221     /**
    222      * <p> Get the ModuleConfig which is operative for the current request.
    223      * </p>
    224      *
    225      * @return The MooduleConfig being used with this request
    226      */
    227     ModuleConfig getModuleConfig();
    228 
    229     /**
    230      * <p> Is the ActionForm for this context valid? This method <em>does
    231      * not</em> actually perform form validation. It is simply a holder
    232      * property where processes which perform validation can store the results
    233      * of the validation for other processes' benefit. </p>
    234      *
    235      * @return <code>Boolean.TRUE</code> if the form passed validation;
    236      *         <code>Boolean.FALSE</code> if the form failed validation; null
    237      *         if the form has not yet been validated
    238      */
    239     Boolean getFormValid();
    240 
    241     /**
    242      * <p> Store the result of the validation of the Context's ActionForm.
    243      * </p>
    244      *
    245      * @param valid Whether the ActionForm for this request passes validation
    246      */
    247     void setFormValid(Boolean valid);
    248 
    249     /**
    250      * <p> Retrieve an exception which may have been caught by some code using
    251      * this ActionContext, usually by an exception handler. </p>
    252      *
    253      * @return Any exception that may have been caught by this ActionContext
    254      */
    255     Exception getException();
    256 
    257     /**
    258      * <p> Store an exception in this context for use by other handling code.
    259      * </p>
    260      *
    261      * @param e An exception to be stored for handling by another member
    262      */
    263     void setException(Exception e);
    264 
    265     // -------------------------------
    266     // ActionMessage Processing
    267     // -------------------------------
    268 
    269     /**
    270      * <p> Append the given messages keys to an internal cache, creating the
    271      * cache if one is not already present. </p>
    272      *
    273      * @param messages New ActionMessages to cache
    274      */
    275     void addMessages(ActionMessages messages);
    276 
    277     /**
    278      * <p> Append the given errors keys to an internal cache, creating the
    279      * cache if one is not already present. </p>
    280      *
    281      * @param errors New ActionMessages to cache as errors
    282      */
    283     void addErrors(ActionMessages errors);
    284 
    285     /**
    286      * <p> Retrieve error messages from an internal cache, creating an empty
    287      * cache if one is not already present. </p>
    288      *
    289      * @return The ActionMessage cache for errors
    290      */
    291     ActionMessages getErrors();
    292 
    293     /**
    294      * <p> Retrieve messages from an internal cache, creating an empty cache
    295      * if one is not already present. </p>
    296      *
    297      * @return The ActionMessage cache for errors
    298      */
    299     ActionMessages getMessages();
    300 
    301     /**
    302      * <p> Save the given error messages to the internal cache, clearing any
    303      * previous messages in the cache. </p> <p> If the parameter is null or
    304      * empty, the internal cache is removed. </p>
    305      *
    306      * @param errors ActionMesssages to cache as errors
    307      */
    308     void saveErrors(ActionMessages errors);
    309 
    310     /**
    311      * <p> Save the given messages to the internal cache, clearing any
    312      * previous messages in the cache. </p> <p> If the parameter is null or
    313      * empty, the internal cache is removed. </p>
    314      *
    315      * @param messages ActionMesssages to cache
    316      */
    317     void saveMessages(ActionMessages messages);
    318 
    319     /**
    320      * <p> Save the given messages to the internal cache, clearing any
    321      * previous messages in the cache, but only for the specified scope. </p>
    322      * <p> If the parameter is null or empty, the internal cache is removed.
    323      * </p>
    324      *
    325      * @param scope    The scope for the internal cache
    326      * @param messages ActionMesssages to cache
    327      */
    328     void saveMessages(String scope, ActionMessages messages);
    329 
    330     // -------------------------------
    331     // Token Processing
    332     // -------------------------------
    333 
    334     /**
    335      * <p>Generate a new transaction token, to be used for enforcing a single
    336      * request for a particular transaction.</p>
    337      */
    338     String generateToken();
    339 
    340     /**
    341      * <p> Indicate whether a transaction token for this context is valid.
    342      * </p> <p> A typical implementation will place a transaction token in the
    343      * session" scope Map and a matching value in the  "parameter" Map. If the
    344      * "session" token does not match the "parameter" attribute, or the
    345      * session token is missing, then the transactional token is deemed
    346      * invalid. </p>
    347      */
    348     boolean isTokenValid();
    349 
    350     /**
    351      * <p> Indicate whether a transaction token is stored in the "session"
    352      * scope for this context, optionally clearing the token, so that the next
    353      * check would return false. </p>
    354      *
    355      * @param reset On true, clear the transactional token
    356      */
    357     boolean isTokenValid(boolean reset);
    358 
    359     /**
    360      * <p> Clear any transactional token stored in the "session" scope for
    361      * this context, so that the next check would return false. </p>
    362      */
    363     void resetToken();
    364 
    365     /**
    366      * <p> Save a new transaction token in the "session" scope for this
    367      * context, creating new resources, if needed. </p>
    368      */
    369     void saveToken();
    370 
    371     // -------------------------------
    372     // Cancel Processing
    373     // -------------------------------
    374 
    375     /**
    376      * <p> Indicate if the "cancel event" state is set for for this context,
    377      * </p>
    378      *
    379      * @see ActionContextBase.CANCEL_KEY
    380      */
    381     Boolean getCancelled();
    382 
    383     /**
    384      * <p> Set the "cancel event" state for this context. </p> <p>
    385      *
    386      * @param cancelled On true, set the cancel event state to true. On false,
    387      *                  set the cancel event state to false.
    388      * @see ActionContextBase.CANCEL_KEY
    389      */
    390     void setCancelled(Boolean cancelled);
    391 
    392     // -------------------------------
    393     // MessageResources Processing
    394     // -------------------------------
    395 
    396     /**
    397      * <p>Return the default message resources for the current module.</p>
    398      */
    399     MessageResources getMessageResources();
    400 
    401     /**
    402      * <p>Set the default message resources for the current module.</p>
    403      */
    404     void setMessageResources(MessageResources resources);
    405 
    406     /**
    407      * <p>Return the specified message resources for the current module.</p>
    408      *
    409      * @param key The key specified in the <code>&lt;message-resources&gt;</code>
    410      *            element for the requested bundle
    411      */
    412     MessageResources getMessageResources(String key);
    413 
    414     // -------------------------------
    415     // Locale Processing
    416     // -------------------------------
    417 
    418     /**
    419      * <p>Return the user's currently selected Locale.</p>
    420      */
    421     Locale getLocale();
    422 
    423     /**
    424      * <p>Set the user's currently selected <code>Locale</code>.</p>
    425      *
    426      * @param locale The user's selected Locale to be set, or null to select
    427      *               the server's default Locale
    428      */
    429     void setLocale(Locale locale);
    430 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
