[View Javadoc](../../../../../apidocs/org/apache/struts/util/TokenProcessor.html.md)


    1   /*
    2    * $Id: TokenProcessor.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.Globals;
    24  
    25  import javax.servlet.http.HttpServletRequest;
    26  import javax.servlet.http.HttpSession;
    27  
    28  import java.security.MessageDigest;
    29  import java.security.NoSuchAlgorithmException;
    30  
    31  /**
    32   * TokenProcessor is responsible for handling all token related functionality.
    33   * The methods in this class are synchronized to protect token processing from
    34   * multiple threads.  Servlet containers are allowed to return a different
    35   * HttpSession object for two threads accessing the same session so it is not
    36   * possible to synchronize on the session.
    37   *
    38   * @since Struts 1.1
    39   */
    40  public class TokenProcessor {
    41      /**
    42       * The singleton instance of this class.
    43       */
    44      private static TokenProcessor instance = new TokenProcessor();
    45  
    46      /**
    47       * The timestamp used most recently to generate a token value.
    48       */
    49      private long previous;
    50  
    51      /**
    52       * Protected constructor for TokenProcessor.  Use TokenProcessor.getInstance()
    53       * to obtain a reference to the processor.
    54       */
    55      protected TokenProcessor() {
    56          super();
    57      }
    58  
    59      /**
    60       * Retrieves the singleton instance of this class.
    61       */
    62      public static TokenProcessor getInstance() {
    63          return instance;
    64      }
    65  
    66      /**
    67       * <p>Return <code>true</code> if there is a transaction token stored in
    68       * the user's current session, and the value submitted as a request
    69       * parameter with this action matches it.  Returns <code>false</code>
    70       * under any of the following circumstances:</p>
    71       *
    72       * <ul>
    73       *
    74       * <li>No session associated with this request</li>
    75       *
    76       * <li>No transaction token saved in the session</li>
    77       *
    78       * <li>No transaction token included as a request parameter</li>
    79       *
    80       * <li>The included transaction token value does not match the transaction
    81       * token in the user's session</li>
    82       *
    83       * </ul>
    84       *
    85       * @param request The servlet request we are processing
    86       */
    87      public synchronized boolean isTokenValid(HttpServletRequest request) {
    88          return this.isTokenValid(request, false);
    89      }
    90  
    91      /**
    92       * Return <code>true</code> if there is a transaction token stored in the
    93       * user's current session, and the value submitted as a request parameter
    94       * with this action matches it.  Returns <code>false</code>
    95       *
    96       * <ul>
    97       *
    98       * <li>No session associated with this request</li> <li>No transaction
    99       * token saved in the session</li>
    100      *
    101      * <li>No transaction token included as a request parameter</li>
    102      *
    103      * <li>The included transaction token value does not match the transaction
    104      * token in the user's session</li>
    105      *
    106      * </ul>
    107      *
    108      * @param request The servlet request we are processing
    109      * @param reset   Should we reset the token after checking it?
    110      */
    111     public synchronized boolean isTokenValid(HttpServletRequest request,
    112         boolean reset) {
    113         // Retrieve the current session for this request
    114         HttpSession session = request.getSession(false);
    115 
    116         if (session == null) {
    117             return false;
    118         }
    119 
    120         // Retrieve the transaction token from this session, and
    121         // reset it if requested
    122         String saved =
    123             (String) session.getAttribute(Globals.TRANSACTION_TOKEN_KEY);
    124 
    125         if (saved == null) {
    126             return false;
    127         }
    128 
    129         if (reset) {
    130             this.resetToken(request);
    131         }
    132 
    133         // Retrieve the transaction token included in this request
    134         String token = request.getParameter(Globals.TOKEN_KEY);
    135 
    136         if (token == null) {
    137             return false;
    138         }
    139 
    140         return saved.equals(token);
    141     }
    142 
    143     /**
    144      * Reset the saved transaction token in the user's session.  This
    145      * indicates that transactional token checking will not be needed on the
    146      * next request that is submitted.
    147      *
    148      * @param request The servlet request we are processing
    149      */
    150     public synchronized void resetToken(HttpServletRequest request) {
    151         HttpSession session = request.getSession(false);
    152 
    153         if (session == null) {
    154             return;
    155         }
    156 
    157         session.removeAttribute(Globals.TRANSACTION_TOKEN_KEY);
    158     }
    159 
    160     /**
    161      * Save a new transaction token in the user's current session, creating a
    162      * new session if necessary.
    163      *
    164      * @param request The servlet request we are processing
    165      */
    166     public synchronized void saveToken(HttpServletRequest request) {
    167         HttpSession session = request.getSession();
    168         String token = generateToken(request);
    169 
    170         if (token != null) {
    171             session.setAttribute(Globals.TRANSACTION_TOKEN_KEY, token);
    172         }
    173     }
    174 
    175     /**
    176      * Generate a new transaction token, to be used for enforcing a single
    177      * request for a particular transaction.
    178      *
    179      * @param request The request we are processing
    180      */
    181     public synchronized String generateToken(HttpServletRequest request) {
    182         HttpSession session = request.getSession();
    183 
    184         return generateToken(session.getId());
    185     }
    186 
    187     /**
    188      * Generate a new transaction token, to be used for enforcing a single
    189      * request for a particular transaction.
    190      *
    191      * @param id a unique Identifier for the session or other context in which
    192      *           this token is to be used.
    193      */
    194     public synchronized String generateToken(String id) {
    195         try {
    196             long current = System.currentTimeMillis();
    197 
    198             if (current == previous) {
    199                 current++;
    200             }
    201 
    202             previous = current;
    203 
    204             byte[] now = new Long(current).toString().getBytes();
    205             MessageDigest md = MessageDigest.getInstance("MD5");
    206 
    207             md.update(id.getBytes());
    208             md.update(now);
    209 
    210             return toHex(md.digest());
    211         } catch (NoSuchAlgorithmException e) {
    212             return null;
    213         }
    214     }
    215 
    216     /**
    217      * Convert a byte array to a String of hexadecimal digits and return it.
    218      *
    219      * @param buffer The byte array to be converted
    220      */
    221     private String toHex(byte[] buffer) {
    222         StringBuffer sb = new StringBuffer(buffer.length * 2);
    223 
    224         for (int i = 0; i < buffer.length; i++) {
    225             sb.append(Character.forDigit((buffer[i] & 0xf0) >> 4, 16));
    226             sb.append(Character.forDigit(buffer[i] & 0x0f, 16));
    227         }
    228 
    229         return sb.toString();
    230     }
    231 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
