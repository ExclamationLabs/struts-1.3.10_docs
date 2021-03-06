[View Javadoc](../../apidocs/examples/SuccessAction.html.md)


    1   /*
    2    * $Id: SuccessAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples;
    23  
    24  import javax.servlet.http.HttpServletRequest;
    25  import javax.servlet.http.HttpServletResponse;
    26  
    27  import org.apache.struts.action.Action;
    28  import org.apache.struts.action.ActionForm;
    29  import org.apache.struts.action.ActionForward;
    30  import org.apache.struts.action.ActionMapping;
    31  
    32  /**
    33   * <p>An Action that forwards control via a "success" ActionFoward.</p>
    34   *
    35   * <p>A recommended strategy is that view pages should link only to Actions and
    36   * never directly to other views. In situations where the view does not require
    37   * any preparation you can use a SuccessAction, specifying the view as an
    38   * ActionForward named "success" in your action mapping.</p>
    39   *
    40   * <p>e.g. If you configure an ActionMapping in struts-config.xml like this:</p>
    41   *
    42   * <pre>
    43   *    &lt;action path="/prepareView"
    44   *            type="examples.SuccessAction"&gt;
    45   *        &lt;forward name="success" path="/jsp/View.jsp"/&gt;
    46   *    &lt/action&gt;
    47   * </pre>
    48   *
    49   * <p>You could create a link to the view (via the Action) as follows:</p>
    50   *
    51   * <pre>
    52   *     &lt.html.md:link action="/prepareView"&gt;Display 'view' page&lt;/html:link&gt;
    53   * </pre>
    54   *
    55   * <p>If you later change your application such that the view page requires some
    56   * initialization you can change a single ActionMapping definition in
    57   * struts-config.xml rather than lots of link definitions in many JSPs.</p>
    58   *
    59   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    60   */
    61  public class SuccessAction extends Action {
    62  
    63      // ------------------------------------------------------------ Constructors
    64  
    65      /**
    66       * Constructor for SuccessAction.
    67       */
    68      public SuccessAction() {
    69          super();
    70      }
    71  
    72      // ---------------------------------------------------------- Action Methods
    73  
    74      /**
    75       * Returns the <code>ActionForward</code> named "success" if one is
    76       * configured or <code>null</code>if it cannot be found.
    77       *
    78       * Searches first for a local forward, then a global forward.
    79       *
    80       * @param mapping The ActionMapping used to select this instance
    81       * @param form The optional ActionForm bean for this request (if any)
    82       * @param request The HTTP request we are processing
    83       * @param response The HTTP response we are creating
    84       *
    85       * @exception Exception if mapping.findForward throws an Exception
    86       *
    87       * @return the "success" ActionForward, or null if it cannot be found
    88       */
    89      public ActionForward execute(
    90          ActionMapping mapping,
    91          ActionForm form,
    92          HttpServletRequest request,
    93          HttpServletResponse response)
    94          throws Exception {
    95  
    96          return mapping.findForward("success");
    97  
    98      }
    99  
    100 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
