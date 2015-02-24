[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/WriteRenderer.html.md)


    1   /*
    2    * $Id: WriteRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    25  import java.io.IOException;
    26  import javax.faces.component.UIComponent;
    27  import javax.faces.component.UIViewRoot;
    28  import javax.faces.component.ValueHolder;
    29  import javax.faces.context.FacesContext;
    30  import javax.faces.context.ResponseWriter;
    31  import org.apache.commons.logging.Log;
    32  import org.apache.commons.logging.LogFactory;
    33  import org.apache.struts.util.ResponseUtils;
    34  
    35  
    36  /**
    37   * <p><code>Renderer</code> implementation for the <code>write</code> tag
    38   * from the <em>Struts-Faces Integration Library</em>.</p>
    39   *
    40   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    41   */
    42  
    43  public class WriteRenderer extends AbstractRenderer {
    44  
    45  
    46      // -------------------------------------------------------- Static Variables
    47  
    48  
    49      /**
    50       * <p>The <code>Log</code> instance for this class.</p>
    51       */
    52      private static Log log = LogFactory.getLog(WriteRenderer.class);
    53  
    54  
    55      // ---------------------------------------------------------- Public Methods
    56  
    57  
    58      /**
    59       * <p>Encode the specified text to our response.</p>
    60       *
    61       * @param context FacesContext for the response we are creating
    62       * @param component Component to be rendered
    63       *
    64       * @exception IOException if an input/output error occurs
    65       * @exception NullPointerException if <code>context</code>
    66       *  or <code>component</code> is <code>null</code>
    67       */
    68      public void encodeEnd(FacesContext context, UIComponent component)
    69          throws IOException {
    70  
    71          if ((context == null) || (component == null)) {
    72              throw new NullPointerException();
    73          }
    74  
    75          ResponseWriter writer = context.getResponseWriter();
    76          String id = component.getId();
    77          if ((id != null) && id.startsWith(UIViewRoot.UNIQUE_ID_PREFIX)) {
    78              id = null;
    79          }
    80          String style =
    81              (String) component.getAttributes().get("style");
    82          String styleClass =
    83              (String) component.getAttributes().get("styleClass");
    84          if (log.isTraceEnabled()) {
    85              log.trace("id='" + id + "', style='" + style + "', styleClass='" +
    86                        styleClass + "'");
    87          }
    88          if ((id != null) || (style != null) || (styleClass != null)) {
    89              writer.startElement("span", component);
    90              if (id != null) {
    91                  writer.writeAttribute("id", component.getClientId(context),
    92                                        "id");
    93              }
    94              if (style != null) {
    95                  writer.writeAttribute("style", style, "style");
    96              }
    97              if (styleClass != null) {
    98                  writer.writeAttribute("class", styleClass, "styleClass");
    99              }
    100             writer.writeText("", null);
    101         }
    102         String text = getText(context, component);
    103         if (log.isTraceEnabled()) {
    104             log.trace("encodeEnd(" + component.getClientId(context) +
    105                       "," + text + ")");
    106         }
    107         writer.write(text);
    108         if ((id != null) || (style != null) || (styleClass != null)) {
    109             writer.endElement("span");
    110         }
    111 
    112     }
    113 
    114 
    115     // ------------------------------------------------------- Protected Methods
    116 
    117 
    118     /**
    119      * <p>Return the text to be rendered for this component, optionally
    120      * filtered if requested.</p>
    121      *
    122      * @param context FacesContext for the response we are creating
    123      * @param component Component to be rendered
    124      */
    125     protected String getText(FacesContext context, UIComponent component) {
    126 
    127         String text = getAsString(context, component,
    128                                   ((ValueHolder) component).getValue());
    129         Boolean filter = (Boolean) component.getAttributes().get("filter");
    130         if (filter == null) {
    131             filter = Boolean.FALSE;
    132         }
    133         if (filter.booleanValue()) {
    134             return (ResponseUtils.filter(text));
    135         } else {
    136             return (text);
    137         }
    138 
    139     }
    140 
    141 
    142 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
