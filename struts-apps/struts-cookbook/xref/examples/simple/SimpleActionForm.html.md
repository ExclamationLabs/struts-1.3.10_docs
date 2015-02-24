[View Javadoc](../../../apidocs/examples/simple/SimpleActionForm.html.md)


    1   /*
    2    * $Id: SimpleActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples.simple;
    23  
    24  import javax.servlet.http.HttpServletRequest;
    25  
    26  import org.apache.struts.action.ActionErrors;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionMapping;
    29  import org.apache.struts.action.ActionMessage;
    30  
    31  /**
    32   * A simple ActionForm
    33   *
    34   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    35   */
    36  public class SimpleActionForm extends ActionForm {
    37  
    38      // ------------------------------------------------------ Instance Variables
    39  
    40      /** Name */
    41      private String name = null;
    42  
    43      /** Secret */
    44      private String secret = null;
    45  
    46      /** Color */
    47      private String color = null;
    48  
    49      /** Confirm */
    50      private boolean confirm = false;
    51  
    52      /** Rating */
    53      private String rating = null;
    54  
    55      /** Message */
    56      private String message = null;
    57  
    58      /** Hidden */
    59      private String hidden = null;
    60  
    61      // ------------------------------------------------------------ Constructors
    62  
    63      /**
    64       * Constructor for MultiboxActionForm.
    65       */
    66      public SimpleActionForm() {
    67          super();
    68      }
    69  
    70      // ---------------------------------------------------------- Public Methods
    71  
    72      /**
    73       * Reset all properties to their default values.
    74       *
    75       * @param mapping The mapping used to select this instance
    76       * @param request The servlet request we are processing
    77       */
    78      public void reset(ActionMapping mapping, HttpServletRequest request) {
    79  
    80          this.name = null;
    81          this.secret = null;
    82          this.color = null;
    83          this.confirm = false;
    84          this.rating = null;
    85          this.message = null;
    86          this.hidden = null;
    87  
    88      }
    89  
    90      /**
    91       * Validate the properties that have been set from this HTTP request,
    92       * and return an <code>ActionMessages</code> object that encapsulates any
    93       * validation errors that have been found.  If no errors are found, return
    94       * <code>null</code> or an <code>ActionMessages</code> object with no
    95       * recorded error messages.
    96       *
    97       * @param mapping The mapping used to select this instance
    98       * @param request The servlet request we are processing
    99       *
    100      * @return ActionMessages if any validation errors occurred
    101      */
    102     public ActionErrors validate(
    103         ActionMapping mapping,
    104         HttpServletRequest request) {
    105 
    106         ActionErrors errors = new ActionErrors();
    107 
    108         // Name must be entered
    109         if ((name == null) || (name.length() < 1)) {
    110             errors.add("name", new ActionMessage("errors.name.required"));
    111         }
    112 
    113         // Secret Phrase must be entered
    114         if ((secret == null) || (secret.length() < 1)) {
    115             errors.add("secret", new ActionMessage("errors.secret.required"));
    116         }
    117 
    118         return (errors);
    119 
    120     }
    121 
    122     // -------------------------------------------------------------- Properties
    123 
    124     /**
    125      * Returns the color.
    126      * @return String
    127      */
    128     public String getColor() {
    129         return color;
    130     }
    131 
    132     /**
    133      * Returns the confirm.
    134      * @return boolean
    135      */
    136     public boolean getConfirm() {
    137         return confirm;
    138     }
    139 
    140     /**
    141      * Returns the hidden.
    142      * @return String
    143      */
    144     public String getHidden() {
    145         return hidden;
    146     }
    147 
    148     /**
    149      * Returns the message.
    150      * @return String
    151      */
    152     public String getMessage() {
    153         return message;
    154     }
    155 
    156     /**
    157      * Returns the name.
    158      * @return String
    159      */
    160     public String getName() {
    161         return name;
    162     }
    163 
    164     /**
    165      * Returns the rating.
    166      * @return String
    167      */
    168     public String getRating() {
    169         return rating;
    170     }
    171 
    172     /**
    173      * Returns the secret.
    174      * @return String
    175      */
    176     public String getSecret() {
    177         return secret;
    178     }
    179 
    180     /**
    181      * Sets the color.
    182      * @param color The color to set
    183      */
    184     public void setColor(String color) {
    185         this.color = color;
    186     }
    187 
    188     /**
    189      * Sets the confirm.
    190      * @param confirm The confirm to set
    191      */
    192     public void setConfirm(boolean confirm) {
    193         this.confirm = confirm;
    194     }
    195 
    196     /**
    197      * Sets the hidden.
    198      * @param hidden The hidden to set
    199      */
    200     public void setHidden(String hidden) {
    201         this.hidden = hidden;
    202     }
    203 
    204     /**
    205      * Sets the message.
    206      * @param message The message to set
    207      */
    208     public void setMessage(String message) {
    209         this.message = message;
    210     }
    211 
    212     /**
    213      * Sets the name.
    214      * @param name The name to set
    215      */
    216     public void setName(String name) {
    217         this.name = name;
    218     }
    219 
    220     /**
    221      * Sets the rating.
    222      * @param rating The rating to set
    223      */
    224     public void setRating(String rating) {
    225         this.rating = rating;
    226     }
    227 
    228     /**
    229      * Sets the secret.
    230      * @param secret The secret to set
    231      */
    232     public void setSecret(String secret) {
    233         this.secret = secret;
    234     }
    235 
    236 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
