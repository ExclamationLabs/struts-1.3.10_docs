[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example/RegistrationForm.html.md)


    1   /*
    2    * $Id: RegistrationForm.java 471754 2006-11-06 14:55:09Z husted $
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
    27  
    28  import org.apache.struts.action.ActionErrors;
    29  import org.apache.struts.action.ActionMessage;
    30  import org.apache.struts.action.ActionMapping;
    31  import org.apache.struts.validator.ValidatorForm;
    32  
    33  
    34  /**
    35   * Form bean for the user registration page.  This form has the following
    36   * fields, with default values in square brackets:
    37   * <ul>
    38   * <li><b>action</b> - The maintenance action we are performing (Create,
    39   *     Delete, or Edit).
    40   * <li><b>fromAddress</b> - The EMAIL address of the sender, to be included
    41   *     on sent messages.  [REQUIRED]
    42   * <li><b>fullName</b> - The full name of the sender, to be included on
    43   *     sent messages.  [REQUIRED]
    44   * <li><b>password</b> - The password used by this user to log on.
    45   * <li><b>password2</b> - The confirmation password, which must match
    46   *     the password when changing or setting.
    47   * <li><b>replyToAddress</b> - The "Reply-To" address to be included on
    48   *     sent messages.  [Same as from address]
    49   * <li><b>username</b> - The registered username, which must be unique.
    50   *     [REQUIRED]
    51   * </ul>
    52   *
    53   * @author Craig R. McClanahan
    54   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    55   */
    56  
    57  public final class RegistrationForm extends ValidatorForm  {
    58  
    59  
    60      // ----------------------------------------------------- Instance Variables
    61  
    62  
    63      /**
    64       * The maintenance action we are performing (Create or Edit).
    65       */
    66      private String action = "Create";
    67  
    68  
    69      /**
    70       * The from address.
    71       */
    72      private String fromAddress = null;
    73  
    74  
    75      /**
    76       * The full name.
    77       */
    78      private String fullName = null;
    79  
    80  
    81      /**
    82       * The password.
    83       */
    84      private String password = null;
    85  
    86  
    87      /**
    88       * The confirmation password.
    89       */
    90      private String password2 = null;
    91  
    92  
    93      /**
    94       * The reply to address.
    95       */
    96      private String replyToAddress = null;
    97  
    98  
    99  
    100     /**
    101      * The username.
    102      */
    103     private String username = null;
    104 
    105 
    106     // ----------------------------------------------------------- Properties
    107 
    108 
    109     /**
    110      * Return the maintenance action.
    111      */
    112     public String getAction() {
    113 
    114     return (this.action);
    115 
    116     }
    117 
    118 
    119     /**
    120      * Set the maintenance action.
    121      *
    122      * @param action The new maintenance action.
    123      */
    124     public void setAction(String action) {
    125 
    126         this.action = action;
    127 
    128     }
    129 
    130 
    131     /**
    132      * Return the from address.
    133      */
    134     public String getFromAddress() {
    135 
    136     return (this.fromAddress);
    137 
    138     }
    139 
    140 
    141     /**
    142      * Set the from address.
    143      *
    144      * @param fromAddress The new from address
    145      */
    146     public void setFromAddress(String fromAddress) {
    147 
    148         this.fromAddress = fromAddress;
    149 
    150     }
    151 
    152 
    153     /**
    154      * Return the full name.
    155      */
    156     public String getFullName() {
    157 
    158     return (this.fullName);
    159 
    160     }
    161 
    162 
    163     /**
    164      * Set the full name.
    165      *
    166      * @param fullName The new full name
    167      */
    168     public void setFullName(String fullName) {
    169 
    170         this.fullName = fullName;
    171 
    172     }
    173 
    174 
    175     /**
    176      * Return the password.
    177      */
    178     public String getPassword() {
    179 
    180     return (this.password);
    181 
    182     }
    183 
    184 
    185     /**
    186      * Set the password.
    187      *
    188      * @param password The new password
    189      */
    190     public void setPassword(String password) {
    191 
    192         this.password = password;
    193 
    194     }
    195 
    196 
    197     /**
    198      * Return the confirmation password.
    199      */
    200     public String getPassword2() {
    201 
    202     return (this.password2);
    203 
    204     }
    205 
    206 
    207     /**
    208      * Set the confirmation password.
    209      *
    210      * @param password2 The new confirmation password
    211      */
    212     public void setPassword2(String password2) {
    213 
    214         this.password2 = password2;
    215 
    216     }
    217 
    218 
    219     /**
    220      * Return the reply to address.
    221      */
    222     public String getReplyToAddress() {
    223 
    224     return (this.replyToAddress);
    225 
    226     }
    227 
    228 
    229     /**
    230      * Set the reply to address.
    231      *
    232      * @param replyToAddress The new reply to address
    233      */
    234     public void setReplyToAddress(String replyToAddress) {
    235 
    236         this.replyToAddress = replyToAddress;
    237 
    238     }
    239 
    240 
    241     /**
    242      * Return the username.
    243      */
    244     public String getUsername() {
    245 
    246     return (this.username);
    247 
    248     }
    249 
    250 
    251     /**
    252      * Set the username.
    253      *
    254      * @param username The new username
    255      */
    256     public void setUsername(String username) {
    257 
    258         this.username = username;
    259 
    260     }
    261 
    262 
    263     // --------------------------------------------------------- Public Methods
    264 
    265 
    266     /**
    267      * Reset all properties to their default values.
    268      *
    269      * @param mapping The mapping used to select this instance
    270      * @param request The servlet request we are processing
    271      */
    272     public void reset(ActionMapping mapping, HttpServletRequest request) {
    273 
    274         this.action = "Create";
    275         this.fromAddress = null;
    276         this.fullName = null;
    277         this.password = null;
    278         this.password2 = null;
    279         this.replyToAddress = null;
    280         this.username = null;
    281 
    282     }
    283 
    284 
    285     /**
    286      * Validate the properties that have been set from this HTTP request,
    287      * and return an <code>ActionMessages</code> object that encapsulates any
    288      * validation errors that have been found.  If no errors are found, return
    289      * <code>null</code> or an <code>ActionMessages</code> object with no
    290      * recorded error messages.
    291      *
    292      * @param mapping The mapping used to select this instance
    293      * @param request The servlet request we are processing
    294      */
    295     public ActionErrors validate(ActionMapping mapping,
    296                                  HttpServletRequest request) {
    297 
    298         // Perform validator framework validations
    299         ActionErrors errors = super.validate(mapping, request);
    300 
    301         // Only need crossfield validations here
    302         if (((password == null) && (password2 != null)) ||
    303             ((password != null) && (password2 == null)) ||
    304             ((password != null) && (password2 != null) &&
    305              !password.equals(password2))) {
    306             errors.add("password2",
    307                        new ActionMessage("error.password.match"));
    308         }
    309         return errors;
    310 
    311     }
    312 
    313 
    314 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
