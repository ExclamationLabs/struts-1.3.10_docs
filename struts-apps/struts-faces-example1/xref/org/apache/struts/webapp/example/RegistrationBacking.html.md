[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/RegistrationBacking.html.md)


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
    23  package org.apache.struts.webapp.example;
    24  
    25  
    26  import javax.faces.component.UIData;
    27  import javax.faces.context.FacesContext;
    28  import org.apache.commons.logging.Log;
    29  import org.apache.commons.logging.LogFactory;
    30  
    31  
    32  /**
    33   * <p>Backing bean for the <code>registration.jsp</code> page.</p>
    34   */
    35  
    36  public class RegistrationBacking extends AbstractBacking {
    37  
    38  
    39      // -------------------------------------------------------- Static Variables
    40  
    41  
    42      private static final Log log = LogFactory.getLog(RegistrationBacking.class);
    43  
    44  
    45      // -------------------------------------------------------------- Properties
    46  
    47  
    48      private UIData table = null;
    49  
    50  
    51      /**
    52       * <p>Return the <code>UIData</code> instance we are bound to.</p>
    53       */
    54      public UIData getTable() {
    55  
    56          return (this.table);
    57  
    58      }
    59  
    60  
    61      /**
    62       * <p>Set the <code>UIData</code> instance we are bound to.</p>
    63       *
    64       * @param table The <code>UIData</code> instance
    65       */
    66      public void setTable(UIData table) {
    67  
    68          this.table = table;
    69  
    70      }
    71  
    72  
    73  
    74      // ----------------------------------------------------------------- Actions
    75  
    76  
    77      /**
    78       * <p>Create a new subscription.</p>
    79       */
    80      public String create() {
    81  
    82          if (log.isDebugEnabled()) {
    83              log.debug("create()");
    84          }
    85          FacesContext context = FacesContext.getCurrentInstance();
    86          StringBuffer url = subscription(context);
    87          url.append("?action=Create");
    88          url.append("&username=");
    89          User user = (User)
    90              context.getExternalContext().getSessionMap().get("user");
    91          url.append(user.getUsername());
    92          forward(context, url.toString());
    93          return (null);
    94  
    95      }
    96  
    97  
    98      /**
    99       * <p>Delete an existing subscription.</p>
    100      */
    101     public String delete() {
    102 
    103         if (log.isDebugEnabled()) {
    104             log.debug("delete()");
    105         }
    106         FacesContext context = FacesContext.getCurrentInstance();
    107         StringBuffer url = subscription(context);
    108         url.append("?action=Delete");
    109         url.append("&username=");
    110         User user = (User)
    111             context.getExternalContext().getSessionMap().get("user");
    112         url.append(user.getUsername());
    113         url.append("&host=");
    114         Subscription subscription = (Subscription)
    115             context.getExternalContext().getRequestMap().get("subscription");
    116         url.append(subscription.getHost());
    117         forward(context, url.toString());
    118         return (null);
    119 
    120     }
    121 
    122 
    123     /**
    124      * <p>Edit an existing subscription.</p>
    125      */
    126     public String edit() {
    127 
    128         if (log.isDebugEnabled()) {
    129             log.debug("edit()");
    130         }
    131         FacesContext context = FacesContext.getCurrentInstance();
    132         StringBuffer url = subscription(context);
    133         url.append("?action=Edit");
    134         url.append("&username=");
    135         User user = (User)
    136             context.getExternalContext().getSessionMap().get("user");
    137         url.append(user.getUsername());
    138         url.append("&host=");
    139         Subscription subscription = (Subscription)
    140             context.getExternalContext().getRequestMap().get("subscription");
    141         url.append(subscription.getHost());
    142         forward(context, url.toString());
    143         return (null);
    144 
    145     }
    146 
    147 
    148     /**
    149      * <p>Update the subscriptions to reflect any revisions to the
    150      * <code>type</code> and <code>autoConnect</code> properties.</p>
    151      */
    152     public String update() {
    153 
    154         if (log.isDebugEnabled()) {
    155             log.debug("update()");
    156         }
    157 
    158         FacesContext context = FacesContext.getCurrentInstance();
    159 
    160         // Updates went directly to the underlying rows, so all we need to do
    161         // is save the database
    162         try {
    163             UserDatabase database = (UserDatabase)
    164                 context.getExternalContext().getApplicationMap().
    165                 get(Constants.DATABASE_KEY);
    166             database.save();
    167         } catch (Exception e) {
    168             log.error("Database save", e);
    169         }
    170 
    171         // Forward back to the edit registration page
    172         StringBuffer sb = registration(context);
    173         sb.append("?action=Edit");
    174         forward(context, sb.toString());
    175         return (null);
    176 
    177     }
    178 
    179 
    180 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
