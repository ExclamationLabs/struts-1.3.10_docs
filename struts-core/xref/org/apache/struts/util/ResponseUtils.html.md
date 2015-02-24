[View Javadoc](../../../../../apidocs/org/apache/struts/util/ResponseUtils.html.md)


    1   /*
    2    * $Id: ResponseUtils.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  
    26  import java.lang.reflect.InvocationTargetException;
    27  import java.lang.reflect.Method;
    28  
    29  import java.net.URLEncoder;
    30  
    31  /**
    32   * General purpose utility methods related to generating a servlet response in
    33   * the Struts controller framework.
    34   *
    35   * @version $Rev: 471754 $ $Date: 2005-08-21 14:46:28 -0400 (Sun, 21 Aug 2005)
    36   *          $
    37   */
    38  public class ResponseUtils {
    39      // ------------------------------------------------------- Static Variables
    40  
    41      /**
    42       * The message resources for this package.
    43       */
    44      protected static MessageResources messages =
    45          MessageResources.getMessageResources(
    46              "org.apache.struts.util.LocalStrings");
    47  
    48      /**
    49       * Java 1.4 encode method to use instead of deprecated 1.3 version.
    50       */
    51      private static Method encode = null;
    52  
    53      /**
    54       * Commons logging instance.
    55       */
    56      private static final Log log = LogFactory.getLog(ResponseUtils.class);
    57  
    58      /**
    59       * Initialize the encode variable with the
    60       * Java 1.4 method if available.
    61       */
    62      static {
    63          try {
    64              // get version of encode method with two String args
    65              Class[] args = new Class[] { String.class, String.class };
    66  
    67              encode = URLEncoder.class.getMethod("encode", args);
    68          } catch (NoSuchMethodException e) {
    69              log.debug("Could not find Java 1.4 encode method.  Using deprecated version.",
    70                  e);
    71          }
    72      }
    73  
    74      // --------------------------------------------------------- Public Methods
    75  
    76      /**
    77       * Filter the specified string for characters that are senstive to HTML
    78       * interpreters, returning the string with these characters replaced by
    79       * the corresponding character entities.
    80       *
    81       * @param value The string to be filtered and returned
    82       */
    83      public static String filter(String value) {
    84          if ((value == null) || (value.length() == 0)) {
    85              return value;
    86          }
    87  
    88          StringBuffer result = null;
    89          String filtered = null;
    90  
    91          for (int i = 0; i < value.length(); i++) {
    92              filtered = null;
    93  
    94              switch (value.charAt(i)) {
    95              case '<':
    96                  filtered = "&lt;";
    97  
    98                  break;
    99  
    100             case '>':
    101                 filtered = "&gt;";
    102 
    103                 break;
    104 
    105             case '&':
    106                 filtered = "&amp;";
    107 
    108                 break;
    109 
    110             case '"':
    111                 filtered = "&quot;";
    112 
    113                 break;
    114 
    115             case '\'':
    116                 filtered = "&#39;";
    117 
    118                 break;
    119             }
    120 
    121             if (result == null) {
    122                 if (filtered != null) {
    123                     result = new StringBuffer(value.length() + 50);
    124 
    125                     if (i > 0) {
    126                         result.append(value.substring(0, i));
    127                     }
    128 
    129                     result.append(filtered);
    130                 }
    131             } else {
    132                 if (filtered == null) {
    133                     result.append(value.charAt(i));
    134                 } else {
    135                     result.append(filtered);
    136                 }
    137             }
    138         }
    139 
    140         return (result == null) ? value : result.toString();
    141     }
    142 
    143     /**
    144      * URLencodes a string assuming the character encoding is UTF-8.
    145      *
    146      * @param url
    147      * @return String The encoded url in UTF-8
    148      */
    149     public static String encodeURL(String url) {
    150         return encodeURL(url, "UTF-8");
    151     }
    152 
    153     /**
    154      * Use the new URLEncoder.encode() method from Java 1.4 if available, else
    155      * use the old deprecated version.  This method uses reflection to find
    156      * the appropriate method; if the reflection operations throw exceptions,
    157      * this will return the url encoded with the old URLEncoder.encode()
    158      * method.
    159      *
    160      * @param enc The character encoding the urlencode is performed on.
    161      * @return String The encoded url.
    162      */
    163     public static String encodeURL(String url, String enc) {
    164         try {
    165             if ((enc == null) || (enc.length() == 0)) {
    166                 enc = "UTF-8";
    167             }
    168 
    169             // encode url with new 1.4 method and UTF-8 encoding
    170             if (encode != null) {
    171                 return (String) encode.invoke(null, new Object[] { url, enc });
    172             }
    173         } catch (IllegalAccessException e) {
    174             log.debug("Could not find Java 1.4 encode method.  Using deprecated version.",
    175                 e);
    176         } catch (InvocationTargetException e) {
    177             log.debug("Could not find Java 1.4 encode method. Using deprecated version.",
    178                 e);
    179         }
    180 
    181         return URLEncoder.encode(url);
    182     }
    183 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
