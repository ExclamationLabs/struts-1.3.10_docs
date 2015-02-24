[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/actions/TilesAction.html.md)


    1   /*
    2    * $Id: TilesAction.java 471754 2006-11-06 14:55:09Z husted $
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
    24  import javax.servlet.ServletException;
    25  import javax.servlet.http.HttpServletRequest;
    26  import javax.servlet.http.HttpServletResponse;
    27  
    28  import org.apache.struts.action.Action;
    29  import org.apache.struts.action.ActionForm;
    30  import org.apache.struts.action.ActionForward;
    31  import org.apache.struts.action.ActionMapping;
    32  import org.apache.struts.tiles.ComponentContext;
    33  
    34  /**
    35   * Base class for Tiles Actions.
    36   * This class has the same role as Struts Action. It provides a method execute(...)
    37   * called when action is invoked. The difference is, that the execute() method takes
    38   * an additional parameter : tile context.
    39   * This class extends Struts Action. Subclasses should override
    40   * execute(ComponentContext ...) method instead of Struts
    41   * execute(ActionMapping ...) method.
    42   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    43   */
    44  public abstract class TilesAction extends Action {
    45  
    46      /**
    47       * Original Struts Action's method.
    48       * Retrieve current Tile context and call TilesAction execute method.
    49       * Do not overload this method!
    50       *
    51       * @param mapping The ActionMapping used to select this instance.
    52       * @param form The optional ActionForm bean for this request (if any).
    53       * @param request The HTTP request we are processing.
    54       * @param response The HTTP response we are creating.
    55       *
    56       * @exception Exception if the application business logic throws
    57       *  an exception
    58       * @since Struts 1.1
    59       */
    60      public ActionForward execute(
    61          ActionMapping mapping,
    62          ActionForm form,
    63          HttpServletRequest request,
    64          HttpServletResponse response)
    65          throws Exception {
    66  
    67          // Try to retrieve tile context
    68          ComponentContext context = ComponentContext.getContext(request);
    69          if (context == null) {
    70              throw new ServletException(
    71                  "Can't find Tile context for '"
    72                      + this.getClass().getName()
    73                      + "'. TilesAction subclasses must be called from a Tile");
    74          }
    75  
    76          return this.execute(context, mapping, form, request, response);
    77      }
    78  
    79      /**
    80       * Process the specified HTTP request and create the corresponding HTTP
    81       * response (or forward to another web component that will create it),
    82       * with provision for handling exceptions thrown by the business logic.
    83       * <br>
    84       * Override this method to provide functionality.
    85       *
    86       * @param context The current Tile context, containing Tile attributes.
    87       * @param mapping The ActionMapping used to select this instance.
    88       * @param form The optional ActionForm bean for this request (if any).
    89       * @param request The HTTP request we are processing.
    90       * @param response The HTTP response we are creating.
    91       *
    92       * @exception Exception if the application business logic throws
    93       *  an exception
    94       * @since Struts 1.1
    95       */
    96      public ActionForward execute(
    97          ComponentContext context,
    98          ActionMapping mapping,
    99          ActionForm form,
    100         HttpServletRequest request,
    101         HttpServletResponse response)
    102         throws Exception {
    103 
    104         return null;
    105     }
    106 
    107 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
