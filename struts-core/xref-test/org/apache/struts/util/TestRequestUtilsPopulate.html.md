
    1   /*
    2    * $Id: TestRequestUtilsPopulate.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.util;
    23  
    24  import javax.servlet.ServletException;
    25  
    26  import junit.framework.Test;
    27  import junit.framework.TestSuite;
    28  
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.util.RequestUtils;
    31  import org.apache.struts.Globals;
    32  import org.apache.struts.mock.TestMockBase;
    33  import org.apache.struts.mock.MockFormBean;
    34  import org.apache.struts.mock.MockMultipartRequestHandler;
    35  
    36  /**
    37   * Unit tests for the RequestUtil's <code>populate</code> method.
    38   *
    39   * @version $Rev: 471754 $
    40   */
    41  public class TestRequestUtilsPopulate extends TestMockBase {
    42  
    43      /**
    44       * Defines the testcase name for JUnit.
    45       *
    46       * @param theName the testcase's name.
    47       */
    48      public TestRequestUtilsPopulate(String theName) {
    49          super(theName);
    50      }
    51  
    52      /**
    53       * Start the tests.
    54       *
    55       * @param theArgs the arguments. Not used
    56       */
    57      public static void main(String[] theArgs) {
    58          junit.awtui.TestRunner.main(
    59              new String[] { TestRequestUtilsPopulate.class.getName()});
    60      }
    61  
    62      /**
    63       * @return a test suite (<code>TestSuite</code>) that includes all methods
    64       *         starting with "test"
    65       */
    66      public static Test suite() {
    67          // All methods starting with "test" will be executed in the test suite.
    68          return new TestSuite(TestRequestUtilsPopulate.class);
    69      }
    70  
    71      public void setUp() {
    72          super.setUp();
    73      }
    74  
    75      public void tearDown() {
    76          super.tearDown();
    77      }
    78  
    79      /**
    80       * Ensure that the getMultipartRequestHandler cannot be seen in
    81       * a subclass of ActionForm.
    82       *
    83       * The purpose of this test is to ensure that Bug #38534 is fixed.
    84       *
    85       */
    86      public void testMultipartVisibility() throws Exception {
    87  
    88          String mockMappingName = "mockMapping";
    89          String stringValue     = "Test";
    90  
    91          MockFormBean  mockForm = new MockFormBean();
    92          ActionMapping mapping  = new ActionMapping();
    93          mapping.setName(mockMappingName);
    94  
    95          // Set up the mock HttpServletRequest
    96          request.setMethod("POST");
    97          request.setContentType("multipart/form-data");
    98          request.setAttribute(Globals.MULTIPART_KEY, MockMultipartRequestHandler.class.getName());
    99          request.setAttribute(Globals.MAPPING_KEY, mapping);
    100 
    101         request.addParameter("stringProperty", stringValue);
    102         request.addParameter("multipartRequestHandler.mapping.name", "Bad");
    103 
    104         // Check the Mapping/ActionForm before
    105         assertNull("Multipart Handler already set",    mockForm.getMultipartRequestHandler());
    106         assertEquals("Mapping name not set correctly", mockMappingName, mapping.getName());
    107 
    108         // Try to populate
    109         try {
    110             RequestUtils.populate(mockForm, request);
    111         } catch(ServletException se) {
    112             // Expected BeanUtils.populate() to throw a NestedNullException
    113             // which gets wrapped in RequestUtils in a ServletException
    114             assertEquals("Unexpected type of Exception thrown", "BeanUtils.populate", se.getMessage());
    115         }
    116 
    117         // Check the Mapping/ActionForm after
    118         assertNotNull("Multipart Handler Missing", mockForm.getMultipartRequestHandler());
    119         assertEquals("Mapping name has been modified", mockMappingName, mapping.getName());
    120 
    121     }
    122 
    123 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
