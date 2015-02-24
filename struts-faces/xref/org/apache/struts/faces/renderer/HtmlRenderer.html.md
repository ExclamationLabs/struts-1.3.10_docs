[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/HtmlRenderer.html.md)


    1   /*
    2    * $Id: HtmlRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import java.util.Locale;
    27  import javax.faces.component.UIComponent;
    28  import javax.faces.context.FacesContext;
    29  import javax.faces.context.ResponseWriter;
    30  import javax.servlet.http.HttpSession;
    31  import org.apache.commons.logging.Log;
    32  import org.apache.commons.logging.LogFactory;
    33  import org.apache.struts.Globals;
    34  
    35  
    36  /**
    37   * <p><code>Renderer</code> implementation for the <code.html.md</code> tag
    38   * from the <em>Struts-Faces Integration Library</em>.</p>
    39   *
    40   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    41   */
    42  
    43  public class HtmlRenderer extends AbstractRenderer {
    44  
    45  
    46      // -------------------------------------------------------- Static Variables
    47  
    48  
    49      /**
    50       * <p>The <code>Log</code> instance for this class.</p>
    51       */
    52      private static Log log = LogFactory.getLog(HtmlRenderer.class);
    53  
    54  
    55      // ---------------------------------------------------------- Public Methods
    56  
    57  
    58      /**
    59       * <p>Render the beginning <code.html.md</code> tag.</p>
    60       *
    61       * @param context FacesContext for the current request
    62       * @param component UIComponent to be rendered
    63       *
    64       * @exception IOException if an input/output error occurs while rendering
    65       * @exception NullPointerException if <code>context</code>
    66       *  or <code>component</code> is <code>null</code>
    67       */
    68      public void encodeBegin(FacesContext context, UIComponent component)
    69          throws IOException {
    70  
    71          if ((context == null) || (component == null)) {
    72              throw new NullPointerException();
    73          }
    74  
    75          Locale currentLocale = getCurrentLocale(context, component);
    76          String lang = currentLocale.getLanguage();
    77          boolean validLanguage = ((lang != null) && (lang.length() > 0));
    78  
    79          ResponseWriter writer = context.getResponseWriter();
    80          writer.startElement(.html.md", component);
    81          if (is.html.md(component)) {
    82              // FIXME -- page scope attribute Globals.XHTML_KEY to "true"?
    83              writer.writeAttribute("xmlns",
    84                                    "http://www.w3.org/1999/.html.md", null);
    85          }
    86          if ((isLocale(component) || is.html.md(component)) && validLanguage) {
    87              writer.writeAttribute("lang", lang, null);
    88          }
    89          if (is.html.md(component) && validLanguage) {
    90              writer.writeAttribute("xml:lang", lang, null);
    91          }
    92          writer.writeText("\n", null);
    93  
    94      }
    95  
    96  
    97      /**
    98       * <p>Render the end of the <code.html.md</code> element.</p>
    99       *
    100      * @param context FacesContext for the request we are processing
    101      * @param component UIComponent to be rendered
    102      *
    103      * @exception IOException if an input/output error occurs while rendering
    104      * @exception NullPointerException if <code>context</code>
    105      *  or <code>component</code> is null
    106      */
    107     public void encodeEnd(FacesContext context, UIComponent component)
    108         throws IOException {
    109 
    110         if ((context == null) || (component == null)) {
    111             throw new NullPointerException();
    112         }
    113 
    114         ResponseWriter writer = context.getResponseWriter();
    115         writer.endElement(.html.md");
    116 
    117     }
    118 
    119 
    120 
    121     // ------------------------------------------------------ Protected Methods
    122 
    123 
    124     /**
    125      * <p>Return the current <code>Locale</code> for this request, creating a
    126      * new one if necessary.</p>
    127      *
    128      * @param context FacesContext for this request
    129      * @param component UIComponent we are rendering
    130      */
    131     protected Locale getCurrentLocale
    132         (FacesContext context, UIComponent component) {
    133 
    134         // If locale support not requested, just extract one from the request
    135         if (!isLocale(component)) {
    136             return (context.getExternalContext().getRequestLocale());
    137         }
    138 
    139         // Create a new session if necessary
    140         HttpSession session = (HttpSession)
    141             context.getExternalContext().getSession(true);
    142 
    143         // Return current locale or a new one that is created
    144         Locale current = (Locale) session.getAttribute(Globals.LOCALE_KEY);
    145         if (current != null) {
    146             return (current);
    147         }
    148         current = context.getExternalContext().getRequestLocale();
    149         session.setAttribute(Globals.LOCALE_KEY, current);
    150         return (current);
    151 
    152     }
    153 
    154 
    155 
    156     /**
    157      * <p>Return the state of the <code>locale</code> attribute.</p>
    158      *
    159      * @param component Component to process
    160      */
    161     protected boolean isLocale(UIComponent component) {
    162 
    163         Boolean locale = (Boolean) component.getAttributes().get("locale");
    164         if (locale != null) {
    165             return locale.booleanValue();
    166         } else {
    167             return (false);
    168         }
    169 
    170     }
    171 
    172 
    173     /**
    174      * <p>Return the state of the <code>.html.md</code> attribute.</p>
    175      *
    176      * @param component Component to process
    177      */
    178     protected boolean is.html.md(UIComponent component) {
    179 
    180         Boolean .html.md = (Boolean) component.getAttributes().get("xhtml");
    181         if (.html.md != null) {
    182             return .html.md.booleanValue();
    183         } else {
    184             return (false);
    185         }
    186 
    187     }
    188 
    189 
    190 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
