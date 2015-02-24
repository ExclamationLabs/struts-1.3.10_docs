[View Javadoc](../../../../../../../apidocs/org/apache/struts/webapp/example2/memory/MemorySubscription.html.md)


    1   /*
    2    * $Id: MemorySubscription.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.webapp.example2.memory;
    24  
    25  
    26  import org.apache.struts.webapp.example2.Subscription;
    27  import org.apache.struts.webapp.example2.User;
    28  
    29  
    30  /**
    31   * <p>Concrete implementation of {@link Subscription} for an in-memory
    32   * database backed by an XML data file.</p>
    33   *
    34   * @author Craig R. McClanahan
    35   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    36   * @since Struts 1.1
    37   */
    38  
    39  public final class MemorySubscription implements Subscription {
    40  
    41  
    42      // ----------------------------------------------------------- Constructors
    43  
    44  
    45      /**
    46       * <p>Construct a new Subscription associated with the specified
    47       * {@link User}.
    48       *
    49       * @param user The user with which we are associated
    50       * @param host The mail host for this subscription
    51       */
    52      public MemorySubscription(MemoryUser user, String host) {
    53  
    54          super();
    55          this.user = user;
    56          this.host = host;
    57  
    58      }
    59  
    60  
    61      // ----------------------------------------------------- Instance Variables
    62  
    63  
    64      /**
    65       * The mail host for this subscription.
    66       */
    67      private String host = null;
    68  
    69  
    70      /**
    71       * The {@link User} with which we are associated.
    72       */
    73      private MemoryUser user = null;
    74  
    75  
    76      // ------------------------------------------------------------- Properties
    77  
    78  
    79      /**
    80       * Should we auto-connect at startup time?
    81       */
    82      private boolean autoConnect = false;
    83  
    84      public boolean getAutoConnect() {
    85          return (this.autoConnect);
    86      }
    87  
    88      public void setAutoConnect(boolean autoConnect) {
    89          this.autoConnect = autoConnect;
    90      }
    91  
    92  
    93      /**
    94       * The mail host for this subscription.
    95       */
    96      public String getHost() {
    97          return (this.host);
    98      }
    99  
    100 
    101     /**
    102      * The password (in clear text) for this subscription.
    103      */
    104     private String password = null;
    105 
    106     public String getPassword() {
    107         return (this.password);
    108     }
    109 
    110     public void setPassword(String password) {
    111         this.password = password;
    112     }
    113 
    114 
    115     /**
    116      * The subscription type ("imap" or "pop3").
    117      */
    118     private String type = "imap";
    119 
    120     public String getType() {
    121         return (this.type);
    122     }
    123 
    124     public void setType(String type) {
    125         this.type = type;
    126     }
    127 
    128 
    129     /**
    130      * The User owning this Subscription.
    131      */
    132     public User getUser() {
    133         return (this.user);
    134     }
    135 
    136 
    137     /**
    138      * The username for this subscription.
    139      */
    140     private String username = null;
    141 
    142     public String getUsername() {
    143         return (this.username);
    144     }
    145 
    146     public void setUsername(String username) {
    147         this.username = username;
    148     }
    149 
    150 
    151     // --------------------------------------------------------- Public Methods
    152 
    153 
    154     /**
    155      * Return a String representation of this object.
    156      */
    157     public String toString() {
    158 
    159         StringBuffer sb = new StringBuffer("<subscription host=\"");
    160         sb.append(host);
    161         sb.append("\" autoConnect=\"");
    162         sb.append(autoConnect);
    163         sb.append("\"");
    164         if (password != null) {
    165             sb.append(" password=\"");
    166             sb.append(password);
    167             sb.append("\"");
    168         }
    169         if (type != null) {
    170             sb.append(" type=\"");
    171             sb.append(type);
    172             sb.append("\"");
    173         }
    174         if (username != null) {
    175             sb.append(" username=\"");
    176             sb.append(username);
    177             sb.append("\"");
    178         }
    179         sb.append(">");
    180         return (sb.toString());
    181 
    182     }
    183 
    184 
    185 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
