[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/application/ViewHandlerImpl.html.md)


    1   /*
    2    * $Id: ViewHandlerImpl.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.application;
    23  
    24  
    25  import java.io.IOException;
    26  import java.util.Locale;
    27  import javax.faces.FacesException;
    28  import javax.faces.application.ViewHandler;
    29  import javax.faces.component.UIViewRoot;
    30  import javax.faces.context.ExternalContext;
    31  import javax.faces.context.FacesContext;
    32  
    33  import org.apache.commons.logging.Log;
    34  import org.apache.commons.logging.LogFactory;
    35  import org.apache.struts.Globals;
    36  
    37  
    38  /**
    39   * <p>Custom <code>ViewHandler</code> implementation that adds features
    40   * specific to the Struts-Faces Integration Library.  It leverages the
    41   * "decorator pattern" customization strategy that JSF supports, by
    42   * delegating most processing to the <code>ViewHandler</code> instance
    43   * handed to our constructor.</p>
    44   */
    45  
    46  public class ViewHandlerImpl extends ViewHandler {
    47  
    48  
    49      // ------------------------------------------------------------ Constructors
    50  
    51  
    52      /**
    53       * <p>Construct a <code>ViewHandlerImpl</code> decorating the
    54       * specified <code>ViewHandler</code> instance.</p>
    55       *
    56       * @param handler <code>ViewHandler</code> to be decorated
    57       */
    58      public ViewHandlerImpl(ViewHandler handler) {
    59          if (log.isDebugEnabled()) {
    60              log.debug("Creating ViewHandler instance, wrapping handler " +
    61                        handler);
    62          }
    63          this.handler = handler;
    64      }
    65  
    66  
    67      // ------------------------------------------------------ Instance Variables
    68  
    69  
    70      /**
    71       * <p>The <code>ViewHandler</code> instance that we are decorating.</p>
    72       */
    73      private ViewHandler handler = null;
    74  
    75  
    76      // -------------------------------------------------------- Static Variables
    77  
    78  
    79      /**
    80       * <p>The <code>Log</code> instance for this class.</p>
    81       */
    82      private static final Log log =
    83          LogFactory.getLog(ViewHandlerImpl.class);
    84  
    85  
    86  
    87      // -------------------------------------------------------------- Properties
    88  
    89  
    90      /**
    91       * <p>Return the <code>ViewHandler</code> instance we are decorating.</p>
    92       */
    93      public ViewHandler getHandler() {
    94          return this.handler;
    95      }
    96  
    97  
    98      /**
    99       * <p>Set the <code>ViewHandler</code> instance we are decorating.</p>
    100      *
    101      * @param handler <code>ViewHandler</code> instance to decorate
    102      */
    103     public void setHandler(ViewHandler handler) {
    104         this.handler = handler;
    105     }
    106 
    107 
    108     // ----------------------------------------------------- Specialized Methods
    109 
    110 
    111     /**
    112      * <p>If the Struts application has set a <code>Locale</code>, pass it
    113      * on to JSF prior to delegating the actual rendering.</p>
    114      *
    115      * @param context <code>FacesContext</code> for the current request
    116      * @param view <code>UIViewRoot</code> to be rendered
    117      */
    118     public void renderView(FacesContext context, UIViewRoot view)
    119         throws IOException, FacesException {
    120 
    121         if (log.isDebugEnabled()) {
    122             log.debug("renderView(" + view.getViewId() + ")");
    123         }
    124         ExternalContext econtext = context.getExternalContext();
    125         if (econtext.getSession(false) != null) {
    126             Locale locale = (Locale)
    127                 econtext.getSessionMap().get(Globals.LOCALE_KEY);
    128             if (locale != null) {
    129                 if (log.isTraceEnabled()) {
    130                     log.trace("Setting view locale to " + locale);
    131                 }
    132                 view.setLocale(locale);
    133             }
    134         }
    135         handler.renderView(context, view);
    136 
    137     }
    138 
    139 
    140     // ------------------------------------------------------- Delegated Methods
    141 
    142 
    143     // See ViewHandler JavaDocs for method descriptions
    144 
    145 
    146     public Locale calculateLocale(FacesContext context) {
    147         return handler.calculateLocale(context);
    148     }
    149 
    150 
    151     public String calculateRenderKitId(FacesContext context) {
    152         return handler.calculateRenderKitId(context);
    153     }
    154 
    155 
    156     public UIViewRoot createView(FacesContext context, String viewId) {
    157         return handler.createView(context, viewId);
    158     }
    159 
    160 
    161     public String getActionURL(FacesContext context, String viewId) {
    162         return handler.getActionURL(context, viewId);
    163     }
    164 
    165 
    166     public String getResourceURL(FacesContext context, String viewId) {
    167         return handler.getResourceURL(context, viewId);
    168     }
    169 
    170 
    171     public UIViewRoot restoreView(FacesContext context, String viewId) {
    172         return handler.restoreView(context, viewId);
    173     }
    174 
    175 
    176     public void writeState(FacesContext context) throws IOException {
    177         handler.writeState(context);
    178     }
    179 
    180 
    181 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
