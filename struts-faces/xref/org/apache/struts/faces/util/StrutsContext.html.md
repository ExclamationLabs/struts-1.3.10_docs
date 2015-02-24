[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/util/StrutsContext.html.md)


    1   /*
    2    * $Id: StrutsContext.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.util;
    23  
    24  
    25  import java.util.Locale;
    26  
    27  import javax.faces.context.ExternalContext;
    28  import javax.faces.context.FacesContext;
    29  import javax.faces.event.ActionEvent;
    30  
    31  import javax.sql.DataSource;
    32  
    33  import org.apache.struts.Globals;
    34  import org.apache.struts.action.ActionMapping;
    35  import org.apache.struts.action.ActionMessages;
    36  import org.apache.struts.action.ActionServlet;
    37  import org.apache.struts.config.ModuleConfig;
    38  import org.apache.struts.faces.Constants;
    39  import org.apache.struts.util.MessageResources;
    40  
    41  
    42  /**
    43   * <p>Context bean providing accessors for the Struts related request,
    44   * session, and application scope objects reated to this request.  Note
    45   * that this bean's methods will trigger exceptions unless there is a
    46   * <code>FacesContext</code> instance for this request.</p>
    47   */
    48  
    49  public class StrutsContext {
    50  
    51  
    52      // ------------------------------------------------------ Instance Variables
    53  
    54  
    55      /**
    56       * <p>The <code>FacesContext</code> for the current request.</p>
    57       */
    58      private FacesContext fcontext =
    59          FacesContext.getCurrentInstance();
    60  
    61  
    62      /**
    63       * <p>The <code>ExternalContext</code> for the current request.</p>
    64       */
    65      private ExternalContext econtext =
    66          fcontext.getExternalContext();
    67  
    68  
    69      // ---------------------------------------------------------- Public Methods
    70  
    71  
    72      /**
    73       * <p>Return the <code>ActionEvent</code> for the current request
    74       * (if any).</p>
    75       */
    76      public ActionEvent getActionEvent() {
    77  
    78          return ((ActionEvent) econtext.getRequestMap().
    79                  get(Constants.ACTION_EVENT_KEY));
    80  
    81      }
    82  
    83  
    84      /**
    85       * <p>Return the <code>ActionMapping</code> for the current
    86       * request (if any).</p>
    87       */
    88      public ActionMapping getActionMapping() {
    89  
    90          return ((ActionMapping) econtext.getRequestMap().
    91                  get(Globals.MAPPING_KEY));
    92  
    93      }
    94  
    95  
    96      /**
    97       * <p>Return the <code>ActionMessages</code> instance containing
    98       * application error messages for this request (if any).</p>
    99       */
    100     public ActionMessages getActionMessages() {
    101 
    102         return ((ActionMessages) econtext.getRequestMap().
    103                 get(Globals.MESSAGE_KEY));
    104 
    105     }
    106 
    107 
    108     /**
    109      * <p>Return the <code>ActionServlet</code> instance for this
    110      * web application.</p>
    111      */
    112     public ActionServlet getActionServlet() {
    113 
    114         return ((ActionServlet) econtext.getApplicationMap().
    115                 get(Globals.ACTION_SERVLET_KEY));
    116 
    117     }
    118 
    119 
    120     /**
    121      * <p>Return <code>true</code> if a Boolean true value has been stored
    122      * in the request attribute indicating that this request has been
    123      * cancelled.</p>
    124      */
    125     public boolean isCancelled() {
    126 
    127         Object value = econtext.getRequestMap().get(Globals.CANCEL_KEY);
    128         if (value instanceof Boolean) {
    129             return (((Boolean) value).booleanValue());
    130         } else {
    131             return (false);
    132         }
    133 
    134     }
    135 
    136 
    137 
    138     /**
    139      * <p>Return the exception that caused one of the Struts custom tags
    140      * to report a JspException (if any).</p>
    141      */
    142     public Throwable getException() {
    143 
    144         return ((Throwable) econtext.getRequestMap().
    145                 get(Globals.EXCEPTION_KEY));
    146 
    147     }
    148 
    149 
    150     /**
    151      * <p>Return the <code>ExternalContext</code> for the current request.</p>
    152      */
    153     public ExternalContext getExternalContext() {
    154 
    155         return (econtext);
    156 
    157     }
    158 
    159 
    160     /**
    161      * <p>Return the <code>FacesContext</code> for the current request.</p>
    162      */
    163     public FacesContext getFacesContext() {
    164 
    165         return (fcontext);
    166 
    167     }
    168 
    169 
    170     /**
    171      * <p>Return the <code>Locale</code> stored in the current user's
    172      * session (if any) for Struts based localization.</p>
    173      */
    174     public Locale getLocale() {
    175 
    176         if (econtext.getSession(false) != null) {
    177             return ((Locale) econtext.getSessionMap().
    178                     get(Globals.LOCALE_KEY));
    179         } else {
    180             return (null);
    181         }
    182 
    183     }
    184 
    185 
    186     /**
    187      * <p>Return the <code>MessageResources</code> instance for the
    188      * application module that is processing this request (if any).</p>
    189      */
    190     public MessageResources getMessageResources() {
    191 
    192         return ((MessageResources) econtext.getRequestMap().
    193                 get(Globals.MESSAGES_KEY));
    194 
    195     }
    196 
    197 
    198     /**
    199      * <p>Return the <code>ModuleConfig</code> for the application module
    200      * to which this request has been assigned (if any).</p>
    201      */
    202     public ModuleConfig getModuleConfig() {
    203 
    204         return ((ModuleConfig) econtext.getRequestMap().
    205                 get(Globals.MODULE_KEY));
    206 
    207     }
    208 
    209 
    210 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
