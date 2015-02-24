[View Javadoc](../../../../apidocs/org/apache/struts/Globals.html.md)


    1   /*
    2    * $Id: Globals.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts;
    22  
    23  import java.io.Serializable;
    24  
    25  /**
    26   * Global manifest constants for the entire Struts Framework.
    27   *
    28   * @version $Rev: 471754 $ $Date: 2005-06-18 20:27:26 -0400 (Sat, 18 Jun 2005)
    29   *          $
    30   */
    31  public class Globals implements Serializable {
    32      // ----------------------------------------------------- Manifest Constants
    33  
    34      /**
    35       * The context attributes key under which our <code>ActionServlet</code>
    36       * instance will be stored.
    37       *
    38       * @since Struts 1.1
    39       */
    40      public static final String ACTION_SERVLET_KEY =
    41          "org.apache.struts.action.ACTION_SERVLET";
    42  
    43      /**
    44       * The request attributes key under which a boolean <code>true</code>
    45       * value should be stored if this request was cancelled.
    46       *
    47       * @since Struts 1.1
    48       */
    49      public static final String CANCEL_KEY = "org.apache.struts.action.CANCEL";
    50  
    51      /**
    52       * <p>The base of the context attributes key under which our
    53       * <code>ModuleConfig</code> data structure will be stored.  This will be
    54       * suffixed with the actual module prefix (including the leading "/"
    55       * character) to form the actual attributes key.</p>
    56       *
    57       * <p>For each request processed by the controller servlet, the
    58       * <code>ModuleConfig</code> object for the module selected by the request
    59       * URI currently being processed will also be exposed under this key as a
    60       * request attribute.</p>
    61       *
    62       * @since Struts 1.1
    63       */
    64      public static final String MODULE_KEY = "org.apache.struts.action.MODULE";
    65  
    66      /**
    67       * The ServletContext attribute under which we store the module prefixes
    68       * String[].
    69       *
    70       * @since Struts 1.2
    71       */
    72      public static final String MODULE_PREFIXES_KEY =
    73          "org.apache.struts.globals.MODULE_PREFIXES";
    74  
    75      /**
    76       * The request attribute under which we store the original URI of the
    77       * request.
    78       *
    79       * @since Struts 1.3
    80       */
    81      public static final String ORIGINAL_URI_KEY =
    82          "org.apache.struts.globals.ORIGINAL_URI_KEY";
    83  
    84      /**
    85       * The request attributes key under which your action should store an
    86       * <code>org.apache.struts.action.ActionErrors</code> object, if you are
    87       * using the corresponding custom tag library elements.
    88       */
    89      public static final String ERROR_KEY = "org.apache.struts.action.ERROR";
    90  
    91      /**
    92       * The request attributes key under which Struts custom tags might store a
    93       * <code>Throwable</code> that caused them to report a JspException at
    94       * runtime.  This value can be used on an error page to provide more
    95       * detailed information about what really went wrong.
    96       */
    97      public static final String EXCEPTION_KEY =
    98          "org.apache.struts.action.EXCEPTION";
    99  
    100     /**
    101      * The session attributes key under which the user's selected
    102      * <code>java.util.Locale</code> is stored, if any.  If no such attribute
    103      * is found, the system default locale will be used when retrieving
    104      * internationalized messages.  If used, this attribute is typically set
    105      * during user login processing.
    106      */
    107     public static final String LOCALE_KEY = "org.apache.struts.action.LOCALE";
    108 
    109     /**
    110      * The request attributes key under which our <code>org.apache.struts.ActionMapping</code>
    111      * instance is passed.
    112      */
    113     public static final String MAPPING_KEY =
    114         "org.apache.struts.action.mapping.instance";
    115 
    116     /**
    117      * The request attributes key under which your action should store an
    118      * <code>org.apache.struts.action.ActionMessages</code> object, if you are
    119      * using the corresponding custom tag library elements.
    120      *
    121      * @since Struts 1.1
    122      */
    123     public static final String MESSAGE_KEY =
    124         "org.apache.struts.action.ACTION_MESSAGE";
    125 
    126     /**
    127      * <p>The base of the context attributes key under which our module
    128      * <code>MessageResources</code> will be stored.  This will be suffixed
    129      * with the actual module prefix (including the leading "/" character) to
    130      * form the actual resources key.</p>
    131      *
    132      * <p>For each request processed by the controller servlet, the
    133      * <code>MessageResources</code> object for the module selected by the
    134      * request URI currently being processed will also be exposed under this
    135      * key as a request attribute.</p>
    136      */
    137     public static final String MESSAGES_KEY =
    138         "org.apache.struts.action.MESSAGE";
    139 
    140     /**
    141      * The request attributes key under which our multipart class is stored.
    142      */
    143     public static final String MULTIPART_KEY =
    144         "org.apache.struts.action.mapping.multipartclass";
    145 
    146     /**
    147      * <p>The base of the context attributes key under which an array of
    148      * <code>PlugIn</code> instances will be stored.  This will be suffixed
    149      * with the actual module prefix (including the leading "/" character) to
    150      * form the actual attributes key.</p>
    151      *
    152      * @since Struts 1.1
    153      */
    154     public static final String PLUG_INS_KEY =
    155         "org.apache.struts.action.PLUG_INS";
    156 
    157     /**
    158      * <p>The base of the context attributes key under which our
    159      * <code>RequestProcessor</code> instance will be stored.  This will be
    160      * suffixed with the actual module prefix (including the leading "/"
    161      * character) to form the actual attributes key.</p>
    162      *
    163      * @since Struts 1.1
    164      */
    165     public static final String REQUEST_PROCESSOR_KEY =
    166         "org.apache.struts.action.REQUEST_PROCESSOR";
    167 
    168     /**
    169      * The context attributes key under which we store the mapping defined for
    170      * our controller serlet, which will be either a path-mapped pattern
    171      * (<code>/action/*</code>) or an extension mapped pattern
    172      * (<code>*.do</code>).
    173      */
    174     public static final String SERVLET_KEY =
    175         "org.apache.struts.action.SERVLET_MAPPING";
    176 
    177     /**
    178      * The session attributes key under which our transaction token is stored,
    179      * if it is used.
    180      */
    181     public static final String TRANSACTION_TOKEN_KEY =
    182         "org.apache.struts.action.TOKEN";
    183 
    184     /**
    185      * The page attributes key under which .html.md status is stored.  This may
    186      * be "true" or "false".  When set to true, the.html.md tags output xhtml.
    187      *
    188      * @since Struts 1.1
    189      */
    190     public static final String XHTML_KEY = "org.apache.struts.globals.XHTML";
    191 
    192     /**
    193      * The name of the taglib package.
    194      */
    195     public static final String TAGLIB_PACKAGE = "org.apache.struts.taglib.html.md";
    196 
    197     /**
    198      * The property under which a Cancel button press is reported.
    199      */
    200     public static final String CANCEL_PROPERTY = TAGLIB_PACKAGE + ".CANCEL";
    201 
    202     /**
    203      * The property under which a Cancel button press is reported, if the
    204      * Cancel button is rendered as an image.
    205      */
    206     public static final String CANCEL_PROPERTY_X = TAGLIB_PACKAGE + ".CANCEL.x";
    207 
    208     /**
    209      * The property under which a transaction token is reported.
    210      */
    211     public static final String TOKEN_KEY = TAGLIB_PACKAGE + ".TOKEN";
    212 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
