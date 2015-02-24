[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/ErrorsRenderer.html.md)


    1   /*
    2    * $Id: ErrorsRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.renderer;
    23  
    24  
    25  import java.beans.Beans;
    26  import java.io.IOException;
    27  import java.util.Iterator;
    28  import java.util.Locale;
    29  
    30  import javax.faces.application.FacesMessage;
    31  import javax.faces.component.UIComponent;
    32  import javax.faces.context.FacesContext;
    33  import javax.faces.context.ResponseWriter;
    34  
    35  import org.apache.commons.logging.Log;
    36  import org.apache.commons.logging.LogFactory;
    37  import org.apache.struts.Globals;
    38  import org.apache.struts.action.ActionMessages;
    39  import org.apache.struts.action.ActionMessage;
    40  import org.apache.struts.util.MessageResources;
    41  
    42  
    43  /**
    44   * <p><code>Renderer</code> implementation for the <code>errors</code> tag
    45   * from the <em>Struts-Faces Integration Library</em>.</p>
    46   *
    47   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    48   */
    49  
    50  public class ErrorsRenderer extends AbstractRenderer {
    51  
    52  
    53      // -------------------------------------------------------- Static Variables
    54  
    55  
    56      /**
    57       * <p>The <code>Log</code> instance for this class.</p>
    58       */
    59      private static Log log = LogFactory.getLog(ErrorsRenderer.class);
    60  
    61  
    62      /**
    63       * The dummy message resources for this package.
    64       */
    65      protected static MessageResources dummy =
    66        MessageResources.getMessageResources
    67          ("org.apache.struts.faces.renderer.Dummy");
    68  
    69      // ---------------------------------------------------------- Public Methods
    70  
    71  
    72      /**
    73       * <p>Render a combination of error messages from JavaServer Faces
    74       * <code>Validator</code>s, and Struts messages from form bean
    75       * <code>validate()</code> methods and corresponding business logic
    76       * error checks.</p>
    77       *
    78       * @param context FacesContext for the request we are processing
    79       * @param component UIComponent to be rendered
    80       *
    81       * @exception IOException if an input/output error occurs while rendering
    82       * @exception NullPointerException if <code>context</code>
    83       *  or <code>component</code> is null
    84       */
    85      public void encodeEnd(FacesContext context, UIComponent component)
    86          throws IOException {
    87  
    88          if ((context == null) || (component == null)) {
    89              throw new NullPointerException();
    90          }
    91  
    92          if (log.isDebugEnabled()) {
    93              log.debug("encodeEnd() started");
    94          }
    95  
    96          // Look up availability of our predefined resource keys
    97          MessageResources resources = resources(context, component);
    98          if (Beans.isDesignTime() && (resources == null)) {
    99              resources = dummy;
    100         }
    101         Locale locale = context.getViewRoot().getLocale();
    102         boolean headerPresent = resources.isPresent(locale, "errors.header");
    103         boolean footerPresent = resources.isPresent(locale, "errors.footer");
    104         boolean prefixPresent = resources.isPresent(locale, "errors.prefix");
    105         boolean suffixPresent = resources.isPresent(locale, "errors.suffix");
    106 
    107         // Set up to render the error messages appropriately
    108         boolean headerDone = false;
    109         ResponseWriter writer = context.getResponseWriter();
    110         String id = component.getId();
    111         String property = (String) component.getAttributes().get("property");
    112         if (id != null) {
    113             writer.startElement("span", component);
    114             if (id != null) {
    115                 writer.writeAttribute("id", component.getClientId(context),
    116                                       "id");
    117             }
    118         }
    119 
    120         // Render any JavaServer Faces messages
    121         Iterator messages = context.getMessages(property);
    122         while (messages.hasNext()) {
    123             FacesMessage message = (FacesMessage) messages.next();
    124             if (log.isTraceEnabled()) {
    125                 log.trace("Processing FacesMessage: " + message.getSummary());
    126             }
    127             if (!headerDone) {
    128                 if (headerPresent) {
    129                     writer.write
    130                         (resources.getMessage(locale, "errors.header"));
    131                 }
    132                 headerDone = true;
    133             }
    134             if (prefixPresent) {
    135                 writer.write(resources.getMessage(locale, "errors.prefix"));
    136             }
    137             writer.write(message.getSummary());
    138             if (suffixPresent) {
    139                 writer.write(resources.getMessage(locale, "errors.suffix"));
    140             }
    141         }
    142 
    143         // Render any Struts messages
    144         ActionMessages errors = (ActionMessages)
    145             context.getExternalContext().getRequestMap().get
    146             (Globals.ERROR_KEY);
    147         if (errors != null) {
    148             if (log.isTraceEnabled()) {
    149                 log.trace("Processing Struts messages for property '" +
    150                           property + "'");
    151             }
    152             Iterator reports = null;
    153             if (property == null) {
    154                 reports = errors.get();
    155             } else {
    156                 reports = errors.get(property);
    157             }
    158             while (reports.hasNext()) {
    159                 ActionMessage report = (ActionMessage) reports.next();
    160                 if (log.isTraceEnabled()) {
    161                     log.trace("Processing Struts message key='" +
    162                               report.getKey() + "'");
    163                 }
    164                 if (!headerDone) {
    165                     writer = context.getResponseWriter();
    166                     if (headerPresent) {
    167                         writer.write
    168                             (resources.getMessage(locale, "errors.header"));
    169                     }
    170                     headerDone = true;
    171                 }
    172                 if (prefixPresent) {
    173                     writer.write
    174                         (resources.getMessage(locale, "errors.prefix"));
    175                 }
    176                 writer.write(resources.getMessage(locale, report.getKey(),
    177                                                   report.getValues()));
    178                 if (suffixPresent) {
    179                     writer.write
    180                         (resources.getMessage(locale, "errors.suffix"));
    181                 }
    182             }
    183         }
    184 
    185         // Append the list footer if needed
    186         if (headerDone && footerPresent) {
    187             writer.write(resources.getMessage(locale, "errors.footer"));
    188         }
    189         if (id != null) {
    190             writer.endElement("span");
    191         }
    192 
    193         if (log.isDebugEnabled()) {
    194             log.debug("encodeEnd() finished");
    195         }
    196 
    197     }
    198 
    199 
    200 
    201     // ------------------------------------------------------ Protected Methods
    202 
    203 
    204     /**
    205      * <p>Return the <code>MessageResources</code> bundle from which
    206      * we should return any Struts based error messages.  If no such
    207      * bundle can be located, return <code>null</code>.</p>
    208      *
    209      * @param context FacesContext for the request we are processing
    210      * @param component UIComponent to be rendered
    211      */
    212     protected MessageResources resources(FacesContext context,
    213                                          UIComponent component) {
    214 
    215         String bundle = (String) component.getAttributes().get("bundle");
    216         if (bundle == null) {
    217             bundle = Globals.MESSAGES_KEY;
    218         }
    219         return ((MessageResources)
    220                 context.getExternalContext().getApplicationMap().get(bundle));
    221 
    222     }
    223 
    224 
    225 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
