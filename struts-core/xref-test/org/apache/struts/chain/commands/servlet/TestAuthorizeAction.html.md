
    1   /*
    2    * $Id: TestAuthorizeAction.java 481833 2006-12-03 17:32:52Z niallp $
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
    21  package org.apache.struts.chain.commands.servlet;
    22  
    23  import junit.framework.TestCase;
    24  
    25  import org.apache.commons.chain.web.servlet.ServletWebContext;
    26  import org.apache.struts.chain.commands.UnauthorizedActionException;
    27  import org.apache.struts.chain.contexts.ServletActionContext;
    28  import org.apache.struts.config.ActionConfig;
    29  import org.apache.struts.mock.MockActionServlet;
    30  import org.apache.struts.mock.MockHttpServletRequest;
    31  import org.apache.struts.mock.MockHttpServletResponse;
    32  import org.apache.struts.mock.MockPrincipal;
    33  import org.apache.struts.mock.MockServletConfig;
    34  import org.apache.struts.mock.MockServletContext;
    35  
    36  /* JUnitTest case for class: org.apache.struts.chain.commands.servlet.AuthorizeAction */
    37  public class TestAuthorizeAction extends TestCase {
    38      MockHttpServletRequest request = null;
    39      MockPrincipal principal = null;
    40      ServletWebContext swContext = null;
    41      ServletActionContext saContext = null;
    42      AuthorizeAction command = null;
    43  
    44      public TestAuthorizeAction(String _name) {
    45          super(_name);
    46      }
    47  
    48      /* setUp method for test case */
    49      protected void setUp() throws Exception {
    50          this.request = new MockHttpServletRequest();
    51          this.principal =
    52              new MockPrincipal("Mr. Macri", new String[] { "administrator" });
    53          this.request.setUserPrincipal(principal);
    54  
    55          MockServletConfig servletConfig = new MockServletConfig();
    56          MockServletContext servletContext = new MockServletContext();
    57          MockActionServlet servlet =
    58              new MockActionServlet(servletContext, servletConfig);
    59  
    60          servlet.initInternal();
    61  
    62          this.saContext =
    63              new ServletActionContext(servletContext, request,
    64                  new MockHttpServletResponse());
    65  
    66          this.saContext.setActionServlet(servlet);
    67          this.command = new AuthorizeAction();
    68      }
    69  
    70      /* tearDown method for test case */
    71      protected void tearDown() {
    72      }
    73  
    74      public void testAuthorizeOneRole()
    75          throws Exception {
    76          ActionConfig config = new ActionConfig();
    77  
    78          config.setPath("/testAuthorizeOneRole");
    79          config.setRoles("administrator");
    80          this.saContext.setActionConfig(config);
    81  
    82          boolean result = command.execute(saContext);
    83  
    84          assertFalse(result);
    85      }
    86  
    87      public void testAuthorizeOneOfManyRoles()
    88          throws Exception {
    89          ActionConfig config = new ActionConfig();
    90  
    91          config.setPath("/testAuthorizeOneOfManyRoles");
    92          config.setRoles("administrator,roustabout,memory");
    93          this.saContext.setActionConfig(config);
    94  
    95          boolean result = command.execute(saContext);
    96  
    97          assertFalse(result);
    98      }
    99  
    100     public void testAuthorizeNoRoles()
    101         throws Exception {
    102         ActionConfig config = new ActionConfig();
    103 
    104         config.setPath("/testAuthorizeNoRoles");
    105         this.saContext.setActionConfig(config);
    106 
    107         boolean result = command.execute(saContext);
    108 
    109         assertFalse(result);
    110     }
    111 
    112     public void testNotAuthorizedOneRole()
    113         throws Exception {
    114         ActionConfig config = new ActionConfig();
    115 
    116         config.setPath("/testNotAuthorizedOneRole");
    117         config.setRoles("roustabout");
    118         this.saContext.setActionConfig(config);
    119 
    120         try {
    121             boolean result = command.execute(saContext);
    122         } catch (UnauthorizedActionException ex) {
    123         }
    124     }
    125 
    126     public void testNotAuthorizedOneOfManyRoles()
    127         throws Exception {
    128         ActionConfig config = new ActionConfig();
    129 
    130         config.setPath("/testNotAuthorizedOneOfManyRoles");
    131         config.setRoles("roustabout,memory");
    132         this.saContext.setActionConfig(config);
    133 
    134         try {
    135             boolean result = command.execute(saContext);
    136         } catch (UnauthorizedActionException ex) {
    137         }
    138     }
    139 
    140     /* Executes the test case */
    141     public static void main(String[] argv) {
    142         String[] testCaseList = { TestAuthorizeAction.class.getName() };
    143 
    144         junit.textui.TestRunner.main(testCaseList);
    145     }
    146 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
