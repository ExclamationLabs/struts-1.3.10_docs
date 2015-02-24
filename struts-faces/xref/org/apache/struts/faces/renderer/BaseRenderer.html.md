[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/renderer/BaseRenderer.html.md)


    1   /*
    2    * $Id: BaseRenderer.java 471754 2006-11-06 14:55:09Z husted $
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
    26  import java.lang.reflect.InvocationTargetException;
    27  
    28  import javax.faces.FacesException;
    29  import javax.faces.component.UIComponent;
    30  import javax.faces.context.FacesContext;
    31  import javax.faces.context.ResponseWriter;
    32  import javax.servlet.http.HttpServletRequest;
    33  
    34  import org.apache.commons.beanutils.MethodUtils;
    35  import org.apache.commons.logging.Log;
    36  import org.apache.commons.logging.LogFactory;
    37  
    38  
    39  /**
    40   * <p><code>Renderer</code> implementation for the <code>base</code> tag
    41   * from the <em>Struts-Faces Integration Library</em>.</p>
    42   *
    43   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    44   */
    45  
    46  public class BaseRenderer extends AbstractRenderer {
    47  
    48  
    49      // -------------------------------------------------------- Static Variables
    50  
    51  
    52      /**
    53       * <p>The <code>Log</code> instance for this class.</p>
    54       */
    55      private static Log log = LogFactory.getLog(BaseRenderer.class);
    56  
    57  
    58      // ---------------------------------------------------------- Public Methods
    59  
    60  
    61      /**
    62       * <p>Render an HTML <code>base</code> element.</p>
    63       *
    64       * @param context FacesContext for the request we are processing
    65       * @param component UIComponent to be rendered
    66       *
    67       * @exception IOException if an input/output error occurs while rendering
    68       * @exception NullPointerException if <code>context</code>
    69       *  or <code>component</code> is null
    70       */
    71      public void encodeEnd(FacesContext context, UIComponent component)
    72          throws IOException {
    73  
    74          if ((context == null) || (component == null)) {
    75              throw new NullPointerException();
    76          }
    77  
    78          if (log.isTraceEnabled()) {
    79              log.trace("viewId='" + context.getViewRoot().getViewId() +
    80                        "' --> uri='" + uri(context) + "'");
    81          }
    82  
    83          ResponseWriter writer = context.getResponseWriter();
    84          writer.startElement("base", component);
    85          writer.writeURIAttribute("href", uri(context), null);
    86          String target = (String) component.getAttributes().get("target");
    87          if (target != null) {
    88              writer.writeAttribute("target", target, "target");
    89          }
    90          writer.endElement("base");
    91          writer.writeText("\n", null);
    92  
    93      }
    94  
    95  
    96  
    97      // ------------------------------------------------------- Protected Methods
    98  
    99  
    100     /**
    101      * <p>Return <code>true</code> if this is a portlet request instance.
    102      * NOTE:  Implementation must not require portlet API classes to be
    103      * present.</p>
    104      *
    105      * @param context <code>FacesContext</code> for the current request
    106      */
    107     protected boolean isPortletRequest(FacesContext context) {
    108 
    109         Object request = context.getExternalContext().getRequest();
    110         Class clazz = request.getClass();
    111         while (clazz != null) {
    112             // Does this class implement PortletRequest?
    113             Class interfaces[] = clazz.getInterfaces();
    114             if (interfaces == null) {
    115                 interfaces = new Class[0];
    116             }
    117             for (int i = 0; i < interfaces.length; i++) {
    118                 if ("javax.portlet.PortletRequest".equals
    119                     (interfaces[i].getName())) {
    120                     return (true);
    121                 }
    122             }
    123             // Try our superclass (if any)
    124             clazz = clazz.getSuperclass();
    125         }
    126         return (false);
    127 
    128     }
    129 
    130 
    131     /**
    132      * <p>Return <code>true</code> if this is a servlet request instance.</p>
    133      *
    134      * @param context <code>FacesContext</code> for the current request
    135      */
    136     protected boolean isServletRequest(FacesContext context) {
    137 
    138         Object request = context.getExternalContext().getRequest();
    139         return (request instanceof HttpServletRequest);
    140 
    141     }
    142 
    143 
    144     /**
    145      * <p>Return an absolute URI for the current page suitable for use
    146      * in a portlet environment.  NOTE:  Implementation must not require
    147      * portlet API classes to be present, so use reflection as needed.</p>
    148      *
    149      * @param context <code>FacesContext</code> for the current request
    150      */
    151     protected String portletUri(FacesContext context) {
    152 
    153         Object request = context.getExternalContext().getRequest();
    154         try {
    155             String scheme = (String)
    156                 MethodUtils.invokeMethod(request, "getScheme", null);
    157             StringBuffer sb = new StringBuffer(scheme);
    158             sb.append("://");
    159             sb.append(MethodUtils.invokeMethod(request, "getServerName", null));
    160             Integer port = (Integer)
    161                 MethodUtils.invokeMethod(request, "getServerPort", null);
    162             if ("http".equals(scheme) && (port.intValue() == 80)) {
    163                 ;
    164             } else if ("https".equals(scheme) && (port.intValue() == 443)) {
    165                 ;
    166             } else {
    167                 sb.append(":" + port);
    168             }
    169             sb.append
    170                 (MethodUtils.invokeMethod(request, "getContextPath", null));
    171             sb.append(context.getViewRoot().getViewId());
    172             return (sb.toString());
    173         } catch (InvocationTargetException e) {
    174             throw new FacesException(e.getTargetException());
    175         } catch (Exception e) {
    176             throw new FacesException(e);
    177         }
    178 
    179     }
    180 
    181 
    182     /**
    183      * <p>Return an absolute URI for the current page suitable for use
    184      * in a servlet environment.</p>
    185      *
    186      * @param context <code>FacesContext</code> for the current request
    187      */
    188     protected String servletUri(FacesContext context) {
    189 
    190         HttpServletRequest request = (HttpServletRequest)
    191             context.getExternalContext().getRequest();
    192         StringBuffer sb = new StringBuffer(request.getScheme());
    193         sb.append("://");
    194         sb.append(request.getServerName());
    195         if ("http".equals(request.getScheme()) &&
    196             (80 == request.getServerPort())) {
    197             ;
    198         } else if ("https".equals(request.getScheme()) &&
    199                    (443 == request.getServerPort())) {
    200             ;
    201         } else {
    202             sb.append(":" + request.getServerPort());
    203         }
    204         sb.append(request.getContextPath());
    205         sb.append(context.getViewRoot().getViewId());
    206         return (sb.toString());
    207 
    208     }
    209 
    210 
    211     /**
    212      * <p>Return the absolute URI to be rendered as the value of the
    213      * <code>href</code> attribute.</p>
    214      *
    215      * @param context <code>FacesContext</code> for the current request
    216      */
    217     protected String uri(FacesContext context) {
    218 
    219         if (isServletRequest(context)) {
    220             return (servletUri(context));
    221         } else if (isPortletRequest(context)) {
    222             return (portletUri(context));
    223         } else {
    224             throw new IllegalArgumentException
    225                 ("Request is neither HttpServletRequest nor PortletRequest");
    226         }
    227 
    228     }
    229 
    230 
    231 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
