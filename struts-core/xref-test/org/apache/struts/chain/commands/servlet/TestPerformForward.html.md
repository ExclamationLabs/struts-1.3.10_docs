
    1   /*
    2    * $Id: TestPerformForward.java 481833 2006-12-03 17:32:52Z niallp $
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
    26  import org.apache.struts.chain.contexts.ServletActionContext;
    27  import org.apache.struts.config.ForwardConfig;
    28  import org.apache.struts.mock.MockActionServlet;
    29  import org.apache.struts.mock.MockHttpServletRequest;
    30  import org.apache.struts.mock.MockHttpServletResponse;
    31  import org.apache.struts.mock.MockPrincipal;
    32  import org.apache.struts.mock.MockServletConfig;
    33  import org.apache.struts.mock.MockServletContext;
    34  
    35  /* JUnitTest case for class: org.apache.struts.chain.commands.servlet.PerformForward */
    36  public class TestPerformForward extends TestCase {
    37      MockHttpServletRequest request = null;
    38      MockPrincipal principal = null;
    39      ServletWebContext swContext = null;
    40      ServletActionContext saContext = null;
    41      PerformForward command = null;
    42  
    43      public TestPerformForward(String _name) {
    44          super(_name);
    45      }
    46  
    47      /* setUp method for test case */
    48      protected void setUp() throws Exception {
    49          this.request = new MockHttpServletRequest();
    50          this.principal =
    51              new MockPrincipal("Mr. Macri", new String[] { "administrator" });
    52          this.request.setUserPrincipal(principal);
    53  
    54          MockServletConfig servletConfig = new MockServletConfig();
    55          MockServletContext servletContext = new MockServletContext();
    56          MockActionServlet servlet =
    57              new MockActionServlet(servletContext, servletConfig);
    58  
    59          servlet.initInternal();
    60  
    61          this.saContext =
    62              new ServletActionContext(servletContext, request,
    63                  new MockHttpServletResponse());
    64  
    65          this.saContext.setActionServlet(servlet);
    66          this.command = new PerformForward();
    67      }
    68  
    69      /* tearDown method for test case */
    70      protected void tearDown() {
    71      }
    72  
    73      public void testNullForwardPath()
    74          throws Exception {
    75          ForwardConfig config = new ForwardConfig();
    76  
    77          config.setPath(null);
    78  
    79          try {
    80              command.perform(saContext, config);
    81              fail(
    82                  "Didn't throw an illegal argument exception on null forward path");
    83          } catch (IllegalArgumentException ex) {
    84              System.out.println("exception: " + ex.getMessage());
    85  
    86              // Do nothing, the test passed
    87          }
    88      }
    89  
    90      /* Executes the test case */
    91      public static void main(String[] argv) {
    92          String[] testCaseList = { TestPerformForward.class.getName() };
    93  
    94          junit.textui.TestRunner.main(testCaseList);
    95      }
    96  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
