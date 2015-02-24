[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/RegistrationBacking.html.md)


    1   /*
    2    * $Id: RegistrationBacking.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.webapp.example2;
    24  
    25  
    26  import java.io.IOException;
    27  import javax.faces.FacesException;
    28  import javax.faces.context.FacesContext;
    29  
    30  
    31  /**
    32   * <p>Backing bean for the <code>registration.jsp</code> page.</p>
    33   */
    34  
    35  public class RegistrationBacking {
    36  
    37  
    38      // -------------------------------------------------------------- Properties
    39  
    40  
    41      // These methods exist to work around a bug in the PFD version of the
    42      // rendering for <h:data_table> that disallows constant values on
    43      // per-row command and output components
    44      public String getDeleteLabel() { return ("Delete"); }
    45      public String getEditLabel() { return ("Edit"); }
    46  
    47  
    48      // ----------------------------------------------------------------- Actions
    49  
    50  
    51      /**
    52       * <p>Create a new subscription.</p>
    53       */
    54      public String create() {
    55  
    56          FacesContext context = FacesContext.getCurrentInstance();
    57          StringBuffer url = base(context);
    58          url.append("?action=Create");
    59          url.append("&username=");
    60          User user = (User)
    61              context.getExternalContext().getSessionMap().get("user");
    62          url.append(user.getUsername());
    63          forward(context, url.toString());
    64          return (null);
    65  
    66      }
    67  
    68  
    69      /**
    70       * <p>Delete an existing subscription.</p>
    71       */
    72      public String delete() {
    73  
    74          FacesContext context = FacesContext.getCurrentInstance();
    75          StringBuffer url = base(context);
    76          url.append("?action=Delete");
    77          url.append("&username=");
    78          User user = (User)
    79              context.getExternalContext().getSessionMap().get("user");
    80          url.append(user.getUsername());
    81          url.append("&host=");
    82          Subscription subscription = (Subscription)
    83              context.getExternalContext().getRequestMap().get("subscription");
    84          url.append(subscription.getHost());
    85          forward(context, url.toString());
    86          return (null);
    87  
    88      }
    89  
    90  
    91      /**
    92       * <p>Edit an existing subscription.</p>
    93       */
    94      public String edit() {
    95  
    96          FacesContext context = FacesContext.getCurrentInstance();
    97          StringBuffer url = base(context);
    98          url.append("?action=Edit");
    99          url.append("&username=");
    100         User user = (User)
    101             context.getExternalContext().getSessionMap().get("user");
    102         url.append(user.getUsername());
    103         url.append("&host=");
    104         Subscription subscription = (Subscription)
    105             context.getExternalContext().getRequestMap().get("subscription");
    106         url.append(subscription.getHost());
    107         forward(context, url.toString());
    108         return (null);
    109 
    110     }
    111 
    112 
    113     // --------------------------------------------------------- Private Methods
    114 
    115 
    116     /**
    117      * <p>Return the context relative base URL for the "edit subscriptions"
    118      * action.</p>
    119      *
    120      * @param context <code>FacesContext</code> for the current request
    121      */
    122     private StringBuffer base(FacesContext context) {
    123 
    124         // FIXME - assumes extension mapping for Struts
    125         return (new StringBuffer("/editSubscription.do"));
    126 
    127     }
    128 
    129 
    130     /**
    131      * <p>Forward to the specified URL and mark this response as having
    132      * been completed.</p>
    133      *
    134      * @param context <code>FacesContext</code> for the current request
    135      * @param url Context-relative URL to forward to
    136      *
    137      * @exception FacesException if any error occurs
    138      */
    139     private void forward(FacesContext context, String url) {
    140 
    141         try {
    142             context.getExternalContext().dispatch(url);
    143         } catch (IOException e) {
    144             throw new FacesException(e);
    145         } finally {
    146             context.responseComplete();
    147         }
    148 
    149     }
    150 
    151 
    152 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
