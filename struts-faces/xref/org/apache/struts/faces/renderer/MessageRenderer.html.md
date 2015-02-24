[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/MessageRenderer.html.md)


    1   /*
    2    * $Id: MessageRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import java.util.ArrayList;
    26  import java.util.Iterator;
    27  
    28  import javax.faces.component.UIComponent;
    29  import javax.faces.component.UIParameter;
    30  import javax.faces.component.ValueHolder;
    31  import javax.faces.context.FacesContext;
    32  
    33  import org.apache.commons.logging.Log;
    34  import org.apache.commons.logging.LogFactory;
    35  import org.apache.struts.Globals;
    36  import org.apache.struts.util.MessageResources;
    37  import org.apache.struts.util.ResponseUtils;
    38  
    39  
    40  /**
    41   * <p><code>Renderer</code> implementation for the <code>message</code> tag
    42   * from the <em>Struts-Faces Integration Library</em>.</p>
    43   *
    44   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    45   */
    46  
    47  public class MessageRenderer extends WriteRenderer {
    48  
    49  
    50      // -------------------------------------------------------- Static Variables
    51  
    52  
    53      /**
    54       * <p>The <code>Log</code> instance for this class.</p>
    55       */
    56      private static Log log = LogFactory.getLog(MessageRenderer.class);
    57  
    58  
    59      // ---------------------------------------------------------- Public Methods
    60  
    61  
    62      // ------------------------------------------------------- Protected Methods
    63  
    64  
    65      /**
    66       * <p>Return the message format String to be processed for this message.
    67       * </p>
    68       *
    69       * @param context FacesContext for the response we are creating
    70       * @param component Component to be rendered
    71       *
    72       * @exception IllegalArgumentException if no MessageResources bundle
    73       *  can be found
    74       * @exception IllegalArgumentException if no message key can be found
    75       */
    76      protected String getText(FacesContext context, UIComponent component) {
    77  
    78          // Look up the MessageResources bundle to be used
    79          String bundle = (String) component.getAttributes().get("bundle");
    80          if (bundle == null) {
    81              bundle = Globals.MESSAGES_KEY;
    82          }
    83          MessageResources resources = (MessageResources)
    84              context.getExternalContext().getApplicationMap().get(bundle);
    85          if (resources == null) { // FIXME - i18n
    86              throw new IllegalArgumentException("MessageResources bundle " +
    87                                                 bundle + " not found");
    88          }
    89  
    90          // Look up the message key to be used
    91          Object value = component.getAttributes().get("key");
    92          if (value == null) {
    93              value = ((ValueHolder) component).getValue();
    94          }
    95          if (value == null) { // FIXME - i18n
    96              throw new NullPointerException("Component '" +
    97                                             component.getClientId(context) +
    98                                             "' has no current value");
    99          }
    100         String key = value.toString();
    101 
    102         // Build the substitution arguments list
    103         ArrayList list = new ArrayList();
    104         Iterator kids = component.getChildren().iterator();
    105         while (kids.hasNext()) {
    106             UIComponent kid = (UIComponent) kids.next();
    107             if (!(kid instanceof UIParameter)) {
    108                 continue;
    109             }
    110             list.add(((UIParameter) kid).getValue());
    111         }
    112         Object args[] = list.toArray(new Object[list.size()]);
    113 
    114         // Look up the requested message
    115         String text = resources.getMessage(context.getViewRoot().getLocale(),
    116                                            key, args);
    117         Boolean filter = (Boolean) component.getAttributes().get("filter");
    118         if (filter == null) {
    119             filter = Boolean.FALSE;
    120         }
    121         if (filter.booleanValue()) {
    122             return (ResponseUtils.filter(text));
    123         } else {
    124             return (text);
    125         }
    126 
    127     }
    128 
    129 
    130 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
