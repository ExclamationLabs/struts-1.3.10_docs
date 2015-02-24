[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/actions/DefinitionDispatcherAction.html.md)


    1   /*
    2    * $Id: DefinitionDispatcherAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles.actions;
    23  
    24  import java.io.IOException;
    25  import java.io.PrintWriter;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.http.HttpServletResponse;
    29  
    30  import org.apache.commons.logging.Log;
    31  import org.apache.commons.logging.LogFactory;
    32  import org.apache.struts.action.Action;
    33  import org.apache.struts.action.ActionForm;
    34  import org.apache.struts.action.ActionForward;
    35  import org.apache.struts.action.ActionMapping;
    36  import org.apache.struts.tiles.ComponentDefinition;
    37  import org.apache.struts.tiles.DefinitionsFactoryException;
    38  import org.apache.struts.tiles.DefinitionsUtil;
    39  import org.apache.struts.tiles.FactoryNotFoundException;
    40  import org.apache.struts.tiles.NoSuchDefinitionException;
    41  import org.apache.struts.tiles.TilesUtil;
    42  
    43  /**
    44   * <p>An <strong>Action</strong> that dispatches to a Tiles Definition
    45   * that is named by the request parameter whose name is specified
    46   * by the <code>parameter</code> property of the corresponding
    47   * ActionMapping.
    48   * This action is useful in following situations:
    49   * <li>
    50   * <ul>To associate an Url to a definition</ul>
    51   * <ul>To use Struts &lt.html.md:link&gt; tag on a definition</ul>
    52   * </li>
    53   * <p>To configure the use of this action in your
    54   * <code>struts-config.xml</code> file, create an entry like this:</p>
    55   *
    56   * <code>
    57   *   &lt;action path="/saveSubscription"
    58   *           type="org.apache.struts.tiles.actions.DefinitionDispatcherAction"
    59   *           parameter="def"/&gt;
    60   *     &lt;forward name="success"   path="anything" //&gt;
    61   *     &lt;forward name="error"     path="path.to.error.page" //&gt;
    62   * </code>
    63   *
    64   * <p>which will use the value of the request parameter named "def"
    65   * to pick the appropriate definition name.
    66   * <p>  The value for success doesn't matter. The forward will forward to
    67   * appropriate definition.
    68   * <p> The value for error should denote a valid jsp path or definition name.
    69   *
    70   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    71   */
    72  public class DefinitionDispatcherAction extends Action {
    73  
    74      /**
    75       * Commons Logging instance.
    76       */
    77      protected static Log log = LogFactory.getLog(DefinitionDispatcherAction.class);
    78  
    79      /**
    80       * Process the specified HTTP request, and create the corresponding HTTP
    81       * response (or forward to another web component that will create it),
    82       * with provision for handling exceptions thrown by the business logic.
    83       *
    84       * @param mapping The ActionMapping used to select this instance
    85       * @param form The optional ActionForm bean for this request (if any)
    86       * @param request The HTTP request we are processing
    87       * @param response The HTTP response we are creating
    88       *
    89       * @exception Exception if the application business logic throws
    90       *  an exception
    91       * @since Struts 1.1
    92       */
    93      public ActionForward execute(
    94          ActionMapping mapping,
    95          ActionForm form,
    96          HttpServletRequest request,
    97          HttpServletResponse response)
    98          throws Exception {
    99  
    100         // Identify the request parameter containing the method name
    101         // If none defined, use "def"
    102         String parameter = mapping.getParameter();
    103         if (parameter == null) {
    104             parameter = "def";
    105         }
    106 
    107         // Identify the method name to be dispatched to
    108         String name = request.getParameter(parameter);
    109         if (name == null) {
    110             log.error("Can't get parameter '" + parameter + "'.");
    111 
    112             return mapping.findForward("error");
    113         }
    114 
    115         // Try to dispatch to requested definition
    116         try {
    117             // Read definition from factory, but we can create it here.
    118             ComponentDefinition definition =
    119                 TilesUtil.getDefinition(
    120                     name,
    121                     request,
    122                     getServlet().getServletContext());
    123 
    124             if (log.isDebugEnabled()) {
    125                 log.debug("Get Definition " + definition);
    126             }
    127 
    128             DefinitionsUtil.setActionDefinition(request, definition);
    129 
    130         } catch (FactoryNotFoundException e) {
    131             log.error("Can't get definition factory.", e);
    132             return mapping.findForward("error");
    133 
    134         } catch (NoSuchDefinitionException e) {
    135             log.error("Can't get definition '" + name + "'.", e);
    136             return mapping.findForward("error");
    137 
    138         } catch (DefinitionsFactoryException e) {
    139             log.error("General Factory error '" + e.getMessage() + "'.", e);
    140             return mapping.findForward("error");
    141 
    142         } catch (Exception e) {
    143             log.error("General error '" + e.getMessage() + "'.", e);
    144             return mapping.findForward("error");
    145         }
    146 
    147         return mapping.findForward("success");
    148 
    149     }
    150 
    151     /**
    152      * @deprecated This will be removed after Struts 1.2.
    153      */
    154     protected void printError(HttpServletResponse response, String msg)
    155         throws IOException {
    156         response.setContentType("text/plain");
    157         PrintWriter writer = response.getWriter();
    158         writer.println(msg);
    159         writer.flush();
    160         writer.close();
    161     }
    162 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
