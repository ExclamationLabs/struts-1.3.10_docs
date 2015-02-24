[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/RegistrationForm.html.md)


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
    23  package org.apache.struts.webapp.example2;
    24  
    25  
    26  import javax.servlet.http.HttpServletRequest;
    27  import org.apache.struts.action.ActionMessage;
    28  import org.apache.struts.action.ActionErrors;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.validator.ValidatorForm;
    31  
    32  
    33  /**
    34   * Form bean for the user registration page.  This form has the following
    35   * fields, with default values in square brackets:
    36   * <ul>
    37   * <li><b>action</b> - The maintenance action we are performing (Create,
    38   *     Delete, or Edit).
    39   * <li><b>fromAddress</b> - The EMAIL address of the sender, to be included
    40   *     on sent messages.  [REQUIRED]
    41   * <li><b>fullName</b> - The full name of the sender, to be included on
    42   *     sent messages.  [REQUIRED]
    43   * <li><b>password</b> - The password used by this user to log on.
    44   * <li><b>password2</b> - The confirmation password, which must match
    45   *     the password when changing or setting.
    46   * <li><b>replyToAddress</b> - The "Reply-To" address to be included on
    47   *     sent messages.  [Same as from address]
    48   * <li><b>username</b> - The registered username, which must be unique.
    49   *     [REQUIRED]
    50   * </ul>
    51   *
    52   * @author Craig R. McClanahan
    53   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    54   */
    55  
    56  public final class RegistrationForm extends ValidatorForm  {
    57  
    58  
    59      // ----------------------------------------------------- Instance Variables
    60  
    61  
    62      /**
    63       * The maintenance action we are performing (Create or Edit).
    64       */
    65      private String action = "Create";
    66  
    67  
    68      /**
    69       * The from address.
    70       */
    71      private String fromAddress = null;
    72  
    73  
    74      /**
    75       * The full name.
    76       */
    77      private String fullName = null;
    78  
    79  
    80      /**
    81       * The password.
    82       */
    83      private String password = null;
    84  
    85  
    86      /**
    87       * The confirmation password.
    88       */
    89      private String password2 = null;
    90  
    91  
    92      /**
    93       * The reply to address.
    94       */
    95      private String replyToAddress = null;
    96  
    97  
    98  
    99      /**
    100      * The username.
    101      */
    102     private String username = null;
    103 
    104 
    105     // ----------------------------------------------------------- Properties
    106 
    107 
    108     /**
    109      * Return the maintenance action.
    110      */
    111     public String getAction() {
    112 
    113     return (this.action);
    114 
    115     }
    116 
    117 
    118     /**
    119      * Set the maintenance action.
    120      *
    121      * @param action The new maintenance action.
    122      */
    123     public void setAction(String action) {
    124 
    125         this.action = action;
    126 
    127     }
    128 
    129 
    130     /**
    131      * Return the from address.
    132      */
    133     public String getFromAddress() {
    134 
    135     return (this.fromAddress);
    136 
    137     }
    138 
    139 
    140     /**
    141      * Set the from address.
    142      *
    143      * @param fromAddress The new from address
    144      */
    145     public void setFromAddress(String fromAddress) {
    146 
    147         this.fromAddress = fromAddress;
    148 
    149     }
    150 
    151 
    152     /**
    153      * Return the full name.
    154      */
    155     public String getFullName() {
    156 
    157     return (this.fullName);
    158 
    159     }
    160 
    161 
    162     /**
    163      * Set the full name.
    164      *
    165      * @param fullName The new full name
    166      */
    167     public void setFullName(String fullName) {
    168 
    169         this.fullName = fullName;
    170 
    171     }
    172 
    173 
    174     /**
    175      * Return the password.
    176      */
    177     public String getPassword() {
    178 
    179     return (this.password);
    180 
    181     }
    182 
    183 
    184     /**
    185      * Set the password.
    186      *
    187      * @param password The new password
    188      */
    189     public void setPassword(String password) {
    190 
    191         this.password = password;
    192 
    193     }
    194 
    195 
    196     /**
    197      * Return the confirmation password.
    198      */
    199     public String getPassword2() {
    200 
    201     return (this.password2);
    202 
    203     }
    204 
    205 
    206     /**
    207      * Set the confirmation password.
    208      *
    209      * @param password2 The new confirmation password
    210      */
    211     public void setPassword2(String password2) {
    212 
    213         this.password2 = password2;
    214 
    215     }
    216 
    217 
    218     /**
    219      * Return the reply to address.
    220      */
    221     public String getReplyToAddress() {
    222 
    223     return (this.replyToAddress);
    224 
    225     }
    226 
    227 
    228     /**
    229      * Set the reply to address.
    230      *
    231      * @param replyToAddress The new reply to address
    232      */
    233     public void setReplyToAddress(String replyToAddress) {
    234 
    235         this.replyToAddress = replyToAddress;
    236 
    237     }
    238 
    239 
    240     /**
    241      * Return the username.
    242      */
    243     public String getUsername() {
    244 
    245     return (this.username);
    246 
    247     }
    248 
    249 
    250     /**
    251      * Set the username.
    252      *
    253      * @param username The new username
    254      */
    255     public void setUsername(String username) {
    256 
    257         this.username = username;
    258 
    259     }
    260 
    261 
    262     // --------------------------------------------------------- Public Methods
    263 
    264 
    265     /**
    266      * Reset all properties to their default values.
    267      *
    268      * @param mapping The mapping used to select this instance
    269      * @param request The servlet request we are processing
    270      */
    271     public void reset(ActionMapping mapping, HttpServletRequest request) {
    272 
    273         this.action = "Create";
    274         this.fromAddress = null;
    275         this.fullName = null;
    276         this.password = null;
    277         this.password2 = null;
    278         this.replyToAddress = null;
    279         this.username = null;
    280 
    281     }
    282 
    283 
    284     /**
    285      * Validate the properties that have been set from this HTTP request,
    286      * and return an <code>ActionErrors</code> object that encapsulates any
    287      * validation errors that have been found.  If no errors are found, return
    288      * <code>null</code> or an <code>ActionErrors</code> object with no
    289      * recorded error messages.
    290      *
    291      * @param mapping The mapping used to select this instance
    292      * @param request The servlet request we are processing
    293      */
    294     public ActionErrors validate(ActionMapping mapping,
    295                                  HttpServletRequest request) {
    296 
    297         // Perform validator framework validations
    298         ActionErrors errors = super.validate(mapping, request);
    299 
    300         // Only need crossfield validations here
    301         if (((password == null) && (password2 != null)) ||
    302             ((password != null) && (password2 == null)) ||
    303             ((password != null) && (password2 != null) &&
    304              !password.equals(password2))) {
    305             errors.add("password2",
    306                        new ActionMessage("error.password.match"));
    307         }
    308         return errors;
    309 
    310     }
    311 
    312 
    313 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
