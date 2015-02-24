[View Javadoc](../../../../../apidocs/org/apache/struts/config/ConfigHelperInterface.html.md)


    1   /*
    2    * $Id: ConfigHelperInterface.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.config;
    22  
    23  import org.apache.struts.action.ActionForm;
    24  import org.apache.struts.action.ActionFormBean;
    25  import org.apache.struts.action.ActionForward;
    26  import org.apache.struts.action.ActionMapping;
    27  import org.apache.struts.action.ActionMessages;
    28  import org.apache.struts.upload.MultipartRequestWrapper;
    29  import org.apache.struts.util.MessageResources;
    30  
    31  /**
    32   * <p> NOTE: THIS CLASS IS UNDER ACTIVE DEVELOPMENT. THE CURRENT CODE IS
    33   * WRITTEN FOR CLARITY NOT EFFICIENCY. NOT EVERY API FUNCTION HAS BEEN
    34   * IMPLEMENTED YET. </p><p> A helper object to expose the Struts shared
    35   * resources, which are be stored in the application, session, or request
    36   * contexts, as appropriate. </p><p> An instance should be created for each
    37   * request processed. The  methods which return resources from the request or
    38   * session contexts are not thread-safe. </p><p> Provided for use by other
    39   * servlets in the application so they can easily access the Struts shared
    40   * resources. </p><p> The resources are stored under attributes in the
    41   * application, session, or request contexts. </p><p> The ActionConfig methods
    42   * simply return the resources from under the context and key used by the
    43   * Struts ActionServlet when the resources are created. </p>
    44   *
    45   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    46   *          $
    47   * @since Struts 1.1
    48   */
    49  public interface ConfigHelperInterface {
    50      // ------------------------------------------------ Application Context
    51  
    52      /**
    53       * <p> The <code>org.apache.struts.action.ActionFormBeans</code>
    54       * collection for this application. </p>
    55       */
    56      public ActionMessages getActionMessages();
    57  
    58      /**
    59       * <p> The application resources for this application. </p>
    60       */
    61      public MessageResources getMessageResources();
    62  
    63      /**
    64       * <p> The path-mapped pattern (<code>/action/*</code>) or extension
    65       * mapped pattern ((<code>*.do</code>) used to determine our Action URIs
    66       * in this application. </p>
    67       */
    68      public String getServletMapping();
    69  
    70      // ---------------------------------------------------- Session Context
    71  
    72      /**
    73       * <p> The transaction token stored in this session, if it is used. </p>
    74       */
    75      public String getToken();
    76  
    77      // ---------------------------------------------------- Request Context
    78  
    79      /**
    80       * <p> The runtime JspException that may be been thrown by a Struts tag
    81       * extension, or compatible presentation extension, and placed in the
    82       * request. </p>
    83       */
    84      public Throwable getException();
    85  
    86      /**
    87       * <p> The multipart object for this request. </p>
    88       */
    89      public MultipartRequestWrapper getMultipartRequestWrapper();
    90  
    91      /**
    92       * <p> The <code>org.apache.struts.ActionMapping</code> instance for this
    93       * request. </p>
    94       */
    95      public ActionMapping getMapping();
    96  
    97      // ---------------------------------------------------- Utility Methods
    98  
    99      /**
    100      * <p> Return true if a message string for the specified message key is
    101      * present for the user's Locale. </p>
    102      *
    103      * @param key Message key
    104      */
    105     public boolean isMessage(String key);
    106 
    107     /**
    108      * <p> Retrieve and return the <code>ActionForm</code> bean associated
    109      * with this mapping, creating and stashing one if necessary.  If there is
    110      * no form bean associated with this mapping, return <code>null</code>.
    111      * </p>
    112      */
    113     public ActionForm getActionForm();
    114 
    115     /**
    116      * <p> Return the form bean definition associated with the specified
    117      * logical name, if any; otherwise return <code>null</code>. </p>
    118      *
    119      * @param name Logical name of the requested form bean definition
    120      */
    121     public ActionFormBean getFormBean(String name);
    122 
    123     /**
    124      * <p> Return the forwarding associated with the specified logical name,
    125      * if any; otherwise return <code>null</code>. </p>
    126      *
    127      * @param name Logical name of the requested forwarding
    128      */
    129     public ActionForward getActionForward(String name);
    130 
    131     /**
    132      * <p> Return the mapping associated with the specified request path, if
    133      * any; otherwise return <code>null</code>. </p>
    134      *
    135      * @param path Request path for which a mapping is requested
    136      */
    137     public ActionMapping getActionMapping(String path);
    138 
    139     /**
    140      * <p> Return the form action converted into an action mapping path.  The
    141      * value of the <code>action</code> property is manipulated as follows in
    142      * computing the name of the requested mapping:
    143      *
    144      * <ul>
    145      *
    146      * <li>Any filename extension is removed (on the theory that extension
    147      * mapping is being used to select the controller servlet).</li>
    148      *
    149      * <li>If the resulting value does not start with a slash, then a slash is
    150      * prepended.</li>
    151      *
    152      * </ul> <p> :FIXME: Bad assumption =:o) </p>
    153      */
    154     public String getActionMappingName(String action);
    155 
    156     /**
    157      * <p> Return the form action converted into a server-relative URL. </p>
    158      */
    159     public String getActionMappingURL(String action);
    160 
    161     /**
    162      * <p> Return the url encoded to maintain the user session, if any. </p>
    163      */
    164     public String getEncodeURL(String url);
    165 
    166     // ------------------------------------------------ Presentation API
    167 
    168     /**
    169      * <p> Renders the reference for a HTML <base> element </p>
    170      */
    171     public String getOrigRef();
    172 
    173     /**
    174      * <p> Renders the reference for a HTML <base> element </p>
    175      */
    176     public String getBaseRef();
    177 
    178     /**
    179      * <p> Return the path for the specified forward, otherwise return
    180      * <code>null</code>. </p>
    181      *
    182      * @param name Name given to local or global forward.
    183      */
    184     public String getLink(String name);
    185 
    186     /**
    187      * <p> Return the localized message for the specified key, otherwise
    188      * return <code>null</code>. </p>
    189      *
    190      * @param key Message key
    191      */
    192     public String getMessage(String key);
    193 
    194     /**
    195      * <p> Look up and return a message string, based on the specified
    196      * parameters. </p>
    197      *
    198      * @param key  Message key to be looked up and returned
    199      * @param args Replacement parameters for this message
    200      */
    201     public String getMessage(String key, Object[] args);
    202 
    203     /**
    204      * <p> Return the URL for the specified ActionMapping, otherwise return
    205      * <code>null</code>. </p>
    206      *
    207      * @param path Name given to local or global forward.
    208      */
    209     public String getAction(String path);
    210 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
