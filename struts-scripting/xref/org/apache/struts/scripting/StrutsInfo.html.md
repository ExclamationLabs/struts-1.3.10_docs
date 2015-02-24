[View Javadoc](../../../../../apidocs/org/apache/struts/scripting/StrutsInfo.html.md)


    1   /*
    2    * $Id: StrutsInfo.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.scripting;
    23  
    24  // struts imports:
    25  import org.apache.struts.action.ActionForm;
    26  import org.apache.struts.action.ActionForward;
    27  import org.apache.struts.action.ActionMapping;
    28  import org.apache.struts.util.MessageResources;
    29  
    30  
    31  /**
    32   *  Holds Struts objects.
    33   */
    34  public class StrutsInfo {
    35  
    36      /** Forward name. */
    37      private String forwardName = null;
    38  
    39      /** Forward object. */
    40      private ActionForward forward = null;
    41  
    42      /** ActionForm for this request. */
    43      private ActionForm form = null;
    44  
    45      /** ActionMapping for this request. */
    46      private ActionMapping mapping = null;
    47  
    48      /** ScriptAction instance for this request. */
    49      private ScriptAction action = null;
    50  
    51      /** The message resources for this request. */
    52      private MessageResources res = null;
    53  
    54      /**
    55       *  Constructor.
    56       *
    57       * @param action The action instance
    58       * @param mapping The action mapping
    59       * @param form  The action form
    60       * @param res   The message resources for the current locale
    61       */
    62      public StrutsInfo(ScriptAction action, ActionMapping mapping,
    63          ActionForm form, MessageResources res) {
    64          this.action = action;
    65          this.mapping = mapping;
    66          this.form = form;
    67          this.res = res;
    68      }
    69  
    70      /**
    71       *  Sets the forward name.
    72       *
    73       * @param f The forward name
    74       */
    75      public void setForwardName(String f) {
    76          forwardName = f;
    77      }
    78  
    79      /**
    80       *  Gets the forward object.  If none is set, it tries to find the set
    81       *  forward name.
    82       *
    83       * @return The action forward
    84       */
    85      public ActionForward getForward() {
    86          if (forward == null) {
    87              if (forwardName != null) {
    88                  return mapping.findForward(forwardName);
    89              }
    90          }
    91          return forward;
    92      }
    93  
    94      /**
    95       *  Sets the action forward object.
    96       *
    97       * @param f The action forward
    98       */
    99      public void setForward(ActionForward f) {
    100         forward = f;
    101     }
    102 
    103     /**
    104      *  Sets the action form.
    105      *
    106      * @param form The action form
    107      */
    108     public void setForm(ActionForm form) {
    109         this.form = form;
    110     }
    111 
    112     /**
    113      *  Sets the action mapping.
    114      *
    115      * @param mapping The action mapping
    116      */
    117     public void setMapping(ActionMapping mapping) {
    118         this.mapping = mapping;
    119     }
    120 
    121     /**
    122      *  Sets the action instance.
    123      *
    124      * @param action The Struts action
    125      */
    126     public void setAction(ScriptAction action) {
    127         this.action = action;
    128     }
    129 
    130     /**
    131      *  Sets the message resources.
    132      *
    133      * @param res The message resources
    134      */
    135     public void setMessages(MessageResources res) {
    136         this.res = res;
    137     }
    138 
    139     /**
    140      *  Gets the action form.
    141      *
    142      * @return The action form
    143      */
    144     public ActionForm getForm() {
    145         return form;
    146     }
    147 
    148     /**
    149      *  Gets the action mapping.
    150      *
    151      * @return The action mapping
    152      */
    153     public ActionMapping getMapping() {
    154         return mapping;
    155     }
    156 
    157     /**
    158      *  Gets the action instance.
    159      *
    160      * @return The Struts action
    161      */
    162     public ScriptAction getAction() {
    163         return action;
    164     }
    165 
    166     /**
    167      *  Gets the message resources.
    168      *
    169      * @return The message resources
    170      */
    171     public MessageResources getMessages() {
    172         return res;
    173     }
    174 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
