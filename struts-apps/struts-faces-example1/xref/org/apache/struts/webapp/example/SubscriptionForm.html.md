[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/SubscriptionForm.html.md)


    1   /*
    2    * $Id: SubscriptionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import javax.servlet.http.HttpServletRequest;
    27  import org.apache.struts.action.ActionErrors;
    28  import org.apache.struts.action.ActionMessage;
    29  import org.apache.struts.action.ActionForm;
    30  import org.apache.struts.action.ActionMapping;
    31  
    32  
    33  /**
    34   * Form bean for the user profile page.  This form has the following fields,
    35   * with default values in square brackets:
    36   * <ul>
    37   * <li><b>action</b> - The maintenance action we are performing (Create, Delete,
    38   *     or Edit).
    39   * <li><b>host</b> - The mail host for this subscription.  [REQUIRED]
    40   * <li><b>password</b> - The password for this subscription.  [REQUIRED]
    41   * <li><b>type</b> - The subscription type (imap,pop3)
    42         for this subscription.  [REQUIRED]
    43   * <li><b>username</b> - The username of this subscription.  [REQUIRED]
    44   * </ul>
    45   *
    46   * @author Craig R. McClanahan
    47   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    48   */
    49  
    50  public final class SubscriptionForm extends ActionForm  {
    51  
    52  
    53      // --------------------------------------------------- Instance Variables
    54  
    55  
    56      /**
    57       * The maintenance action we are performing (Create or Edit).
    58       */
    59      private String action = "Create";
    60  
    61  
    62      /**
    63       * Should we auto-connect at startup time?
    64       */
    65      private boolean autoConnect = false;
    66  
    67  
    68      /**
    69       * The host name.
    70       */
    71      private String host = null;
    72  
    73  
    74      /**
    75       * The password.
    76       */
    77      private String password = null;
    78  
    79  
    80      /**
    81       * The subscription type.
    82       */
    83      private String type = null;
    84  
    85  
    86      /**
    87       * The username.
    88       */
    89      private String username = null;
    90  
    91  
    92      // ----------------------------------------------------------- Properties
    93  
    94  
    95      /**
    96       * Return the maintenance action.
    97       */
    98      public String getAction() {
    99  
    100     return (this.action);
    101 
    102     }
    103 
    104 
    105     /**
    106      * Set the maintenance action.
    107      *
    108      * @param action The new maintenance action.
    109      */
    110     public void setAction(String action) {
    111 
    112         this.action = action;
    113 
    114     }
    115 
    116 
    117     /**
    118      * Return the auto-connect flag.
    119      */
    120     public boolean getAutoConnect() {
    121 
    122         return (this.autoConnect);
    123 
    124     }
    125 
    126 
    127     /**
    128      * Set the auto-connect flag.
    129      *
    130      * @param autoConnect The new auto-connect flag
    131      */
    132     public void setAutoConnect(boolean autoConnect) {
    133 
    134         this.autoConnect = autoConnect;
    135     }
    136 
    137 
    138     /**
    139      * Return the host name.
    140      */
    141     public String getHost() {
    142 
    143     return (this.host);
    144 
    145     }
    146 
    147 
    148     /**
    149      * Set the host name.
    150      *
    151      * @param host The host name
    152      */
    153     public void setHost(String host) {
    154 
    155         this.host = host;
    156 
    157     }
    158 
    159 
    160     /**
    161      * Return the password.
    162      */
    163     public String getPassword() {
    164 
    165     return (this.password);
    166 
    167     }
    168 
    169 
    170     /**
    171      * Set the password.
    172      *
    173      * @param password The new password
    174      */
    175     public void setPassword(String password) {
    176 
    177         this.password = password;
    178 
    179     }
    180 
    181 
    182     /**
    183      * Return the subscription type.
    184      */
    185     public String getType() {
    186 
    187     return (this.type);
    188 
    189     }
    190 
    191 
    192     /**
    193      * Set the subscription type.
    194      *
    195      * @param type The subscription type
    196      */
    197     public void setType(String type) {
    198 
    199         this.type = type;
    200 
    201     }
    202 
    203 
    204     /**
    205      * Return the username.
    206      */
    207     public String getUsername() {
    208 
    209     return (this.username);
    210 
    211     }
    212 
    213 
    214     /**
    215      * Set the username.
    216      *
    217      * @param username The new username
    218      */
    219     public void setUsername(String username) {
    220 
    221         this.username = username;
    222 
    223     }
    224 
    225 
    226     // --------------------------------------------------------- Public Methods
    227 
    228 
    229     /**
    230      * Reset all properties to their default values.
    231      *
    232      * @param mapping The mapping used to select this instance
    233      * @param request The servlet request we are processing
    234      */
    235     public void reset(ActionMapping mapping, HttpServletRequest request) {
    236 
    237         this.action = "Create";
    238         this.autoConnect = false;
    239         this.host = null;
    240         this.password = null;
    241         this.type = null;
    242         this.username = null;
    243 
    244     }
    245 
    246 
    247     /**
    248      * Validate the properties that have been set from this HTTP request,
    249      * and return an <code>ActionMessages</code> object that encapsulates any
    250      * validation errors that have been found.  If no errors are found, return
    251      * <code>null</code> or an <code>ActionMessages</code> object with no
    252      * recorded error messages.
    253      *
    254      * @param mapping The mapping used to select this instance
    255      * @param request The servlet request we are processing
    256      */
    257     public ActionErrors validate(ActionMapping mapping,
    258                                  HttpServletRequest request) {
    259 
    260         ActionErrors errors = new ActionErrors();
    261 
    262     if ((host == null) || (host.length() < 1))
    263             errors.add("host",
    264                        new ActionMessage("error.host.required"));
    265     if ((username == null) || (username.length() < 1))
    266             errors.add("username",
    267                        new ActionMessage("error.username.required"));
    268     if ((password == null) || (password.length() < 1))
    269             errors.add("password",
    270                        new ActionMessage("error.password.required"));
    271     if ((type == null) || (type.length() < 1))
    272             errors.add("type",
    273                        new ActionMessage("error.type.required"));
    274     else if (!"imap".equals(type) && !"pop3".equals(type))
    275             errors.add("type",
    276                        new ActionMessage("error.type.invalid", type));
    277 
    278     return (errors);
    279 
    280     }
    281 
    282 
    283     /**
    284      * <p>Return a string representation of this form bean.</p>
    285      */
    286     public String toString() {
    287 
    288         StringBuffer sb = new StringBuffer(super.toString());
    289         sb.append(",action=");
    290         sb.append(action);
    291         sb.append(",autoConnect=");
    292         sb.append(autoConnect);
    293         sb.append(",host=");
    294         sb.append(host);
    295         sb.append(",password=");
    296         sb.append(password);
    297         sb.append(",type=");
    298         sb.append(type);
    299         sb.append(",username=");
    300         sb.append(username);
    301         return (sb.toString());
    302 
    303     }
    304 
    305 
    306 }
    307 

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
