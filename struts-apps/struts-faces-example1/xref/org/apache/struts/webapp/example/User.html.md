[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/User.html.md)


    1   /*
    2    * $Id: User.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.webapp.example;
    24  
    25  
    26  /**
    27   * <p>A <strong>User</strong> which is stored, along with his or her
    28   * associated {@link Subscription}s, in a {@link UserDatabase}.</p>
    29   *
    30   * @author Craig R. McClanahan
    31   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    32   * @since Struts 1.1
    33   */
    34  
    35  public interface User {
    36  
    37  
    38      // ------------------------------------------------------------- Properties
    39  
    40  
    41      /**
    42       * Return the {@link UserDatabase} with which we are associated.
    43       */
    44      public UserDatabase getDatabase();
    45  
    46  
    47      /**
    48       * Return the from address.
    49       */
    50      public String getFromAddress();
    51  
    52  
    53      /**
    54       * Set the from address.
    55       *
    56       * @param fromAddress The new from address
    57       */
    58      public void setFromAddress(String fromAddress);
    59  
    60  
    61      /**
    62       * Return the full name.
    63       */
    64      public String getFullName();
    65  
    66  
    67      /**
    68       * Set the full name.
    69       *
    70       * @param fullName The new full name
    71       */
    72      public void setFullName(String fullName);
    73  
    74  
    75      /**
    76       * Return the password.
    77       */
    78      public String getPassword();
    79  
    80  
    81      /**
    82       * Set the password.
    83       *
    84       * @param password The new password
    85       */
    86      public void setPassword(String password);
    87  
    88  
    89      /**
    90       * Return the reply-to address.
    91       */
    92      public String getReplyToAddress();
    93  
    94  
    95      /**
    96       * Set the reply-to address.
    97       *
    98       * @param replyToAddress The new reply-to address
    99       */
    100     public void setReplyToAddress(String replyToAddress);
    101 
    102 
    103     /**
    104      * Find and return all {@link Subscription}s associated with this user.
    105      * If there are none, a zero-length array is returned.
    106      */
    107     public Subscription[] getSubscriptions();
    108 
    109 
    110     /**
    111      * Return the username.
    112      */
    113     public String getUsername();
    114 
    115 
    116     // --------------------------------------------------------- Public Methods
    117 
    118 
    119     /**
    120      * Create and return a new {@link Subscription} associated with this
    121      * User, for the specified host name.
    122      *
    123      * @param host Host name for which to create a subscription
    124      *
    125      * @exception IllegalArgumentException if the host name is not unique
    126      *  for this user
    127      */
    128     public Subscription createSubscription(String host);
    129 
    130 
    131     /**
    132      * Find and return the {@link Subscription} associated with the specified
    133      * host.  If none is found, return <code>null</code>.
    134      *
    135      * @param host Host name to look up
    136      */
    137     public Subscription findSubscription(String host);
    138 
    139 
    140     /**
    141      * Remove the specified {@link Subscription} from being associated
    142      * with this User.
    143      *
    144      * @param subscription Subscription to be removed
    145      *
    146      * @exception IllegalArgumentException if the specified subscription is not
    147      *  associated with this User
    148      */
    149     public void removeSubscription(Subscription subscription);
    150 
    151 
    152 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
