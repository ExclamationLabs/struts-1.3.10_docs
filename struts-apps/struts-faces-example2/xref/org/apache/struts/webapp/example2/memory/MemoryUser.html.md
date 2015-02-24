[View Javadoc](../../../../../../../apidocs/org/apache/struts/webapp/example2/memory/MemoryUser.html.md)


    1   /*
    2    * $Id: MemoryUser.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import java.util.HashMap;
    27  import org.apache.struts.webapp.example2.Subscription;
    28  import org.apache.struts.webapp.example2.User;
    29  import org.apache.struts.webapp.example2.UserDatabase;
    30  
    31  
    32  /**
    33   * <p>Concrete implementation of {@link User} for an in-memory
    34   * database backed by an XML data file.</p>
    35   *
    36   * @author Craig R. McClanahan
    37   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    38   * @since Struts 1.1
    39   */
    40  
    41  public final class MemoryUser implements User {
    42  
    43  
    44      // ----------------------------------------------------------- Constructors
    45  
    46  
    47      /**
    48       * <p>Construct a new User associated with the specified
    49       * {@link UserDatabase}.
    50       *
    51       * @param database The user database with which we are associated
    52       * @param username The username of this user
    53       */
    54      public MemoryUser(MemoryUserDatabase database, String username) {
    55  
    56          super();
    57          this.database = database;
    58          this.username = username;
    59  
    60      }
    61  
    62  
    63      // ----------------------------------------------------- Instance Variables
    64  
    65  
    66      /**
    67       * The {@link UserDatabase} with which we are associated.
    68       */
    69      private MemoryUserDatabase database = null;
    70  
    71  
    72      /**
    73       * The {@link Subscription}s for this User, keyed by hostname.
    74       */
    75      private HashMap subscriptions = new HashMap();
    76  
    77  
    78      /**
    79       * The username for this user.
    80       */
    81      private String username = null;
    82  
    83  
    84      // ------------------------------------------------------------- Properties
    85  
    86  
    87      /**
    88       * The {@link UserDatabase} with which we are associated.
    89       */
    90      public UserDatabase getDatabase() {
    91          return (this.database);
    92      }
    93  
    94  
    95      /**
    96       * The email address from which messages are sent.
    97       */
    98      private String fromAddress = null;
    99  
    100     public String getFromAddress() {
    101         return (this.fromAddress);
    102     }
    103 
    104     public void setFromAddress(String fromAddress) {
    105         this.fromAddress = fromAddress;
    106     }
    107 
    108 
    109     /**
    110      * The full name of this user, included in from addresses.
    111      */
    112     private String fullName = null;
    113 
    114     public String getFullName() {
    115         return (this.fullName);
    116     }
    117 
    118     public void setFullName(String fullName) {
    119         this.fullName = fullName;
    120     }
    121 
    122 
    123     /**
    124      * The password (in clear text).
    125      */
    126     private String password = null;
    127 
    128     public String getPassword() {
    129         return (this.password);
    130     }
    131 
    132     public void setPassword(String password) {
    133         this.password = password;
    134     }
    135 
    136 
    137     /**
    138      * The EMAIL address to which replies should be sent.
    139      */
    140     private String replyToAddress = null;
    141 
    142     public String getReplyToAddress() {
    143         return (this.replyToAddress);
    144     }
    145 
    146     public void setReplyToAddress(String replyToAddress) {
    147         this.replyToAddress = replyToAddress;
    148     }
    149 
    150 
    151     /**
    152      * Find and return all {@link Subscription}s associated with this user.
    153      * If there are none, a zero-length array is returned.
    154      */
    155     public Subscription[] getSubscriptions() {
    156 
    157         synchronized (subscriptions) {
    158             Subscription results[] = new Subscription[subscriptions.size()];
    159             return ((Subscription[]) subscriptions.values().toArray(results));
    160         }
    161 
    162     }
    163 
    164 
    165     /**
    166      * The username (must be unique).
    167      */
    168     public String getUsername() {
    169         return (this.username);
    170     }
    171 
    172 
    173     // --------------------------------------------------------- Public Methods
    174 
    175 
    176     /**
    177      * Create and return a new {@link Subscription} associated with this
    178      * User, for the specified host name.
    179      *
    180      * @param host Host name for which to create a subscription
    181      *
    182      * @exception IllegalArgumentException if the host name is not unique
    183      *  for this user
    184      */
    185     public Subscription createSubscription(String host) {
    186 
    187         synchronized (subscriptions) {
    188             if (subscriptions.get(host) != null) {
    189                 throw new IllegalArgumentException("Duplicate host '" + host
    190                                                    + "' for user '" +
    191                                                    username + "'");
    192             }
    193             MemorySubscription subscription =
    194                 new MemorySubscription(this, host);
    195             synchronized (subscriptions) {
    196                 subscriptions.put(host, subscription);
    197             }
    198             return (subscription);
    199         }
    200 
    201     }
    202 
    203 
    204     /**
    205      * Find and return the {@link Subscription} associated with the specified
    206      * host.  If none is found, return <code>null</code>.
    207      *
    208      * @param host Host name to look up
    209      */
    210     public Subscription findSubscription(String host) {
    211 
    212         synchronized (subscriptions) {
    213             return ((Subscription) subscriptions.get(host));
    214         }
    215 
    216     }
    217 
    218 
    219     /**
    220      * Remove the specified {@link Subscription} from being associated
    221      * with this User.
    222      *
    223      * @param subscription Subscription to be removed
    224      *
    225      * @exception IllegalArgumentException if the specified subscription is not
    226      *  associated with this User
    227      */
    228     public void removeSubscription(Subscription subscription) {
    229 
    230         if (!(this == subscription.getUser())) {
    231             throw new IllegalArgumentException
    232                 ("Subscription not associated with this user");
    233         }
    234         synchronized (subscriptions) {
    235             subscriptions.remove(subscription.getHost());
    236         }
    237 
    238     }
    239 
    240 
    241     /**
    242      * Return a String representation of this object.
    243      */
    244     public String toString() {
    245 
    246         StringBuffer sb = new StringBuffer("<user username=\"");
    247         sb.append(username);
    248         sb.append("\"");
    249         if (fromAddress != null) {
    250             sb.append(" fromAddress=\"");
    251             sb.append(fromAddress);
    252             sb.append("\"");
    253         }
    254         if (fullName != null) {
    255             sb.append(" fullName=\"");
    256             sb.append(fullName);
    257             sb.append("\"");
    258         }
    259         if (password != null) {
    260             sb.append(" password=\"");
    261             sb.append(password);
    262             sb.append("\"");
    263         }
    264         if (replyToAddress != null) {
    265             sb.append(" replyToAddress=\"");
    266             sb.append(replyToAddress);
    267             sb.append("\"");
    268         }
    269         sb.append(">");
    270         return (sb.toString());
    271 
    272     }
    273 
    274 
    275 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
