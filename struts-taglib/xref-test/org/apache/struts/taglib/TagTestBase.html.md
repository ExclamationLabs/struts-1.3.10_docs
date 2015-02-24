
    1   /*
    2    * $Id: $
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
    21  package org.apache.struts.taglib;
    22  
    23  import junit.framework.TestCase;
    24  
    25  import org.apache.struts.Globals;
    26  import org.apache.struts.config.ForwardConfig;
    27  import org.apache.struts.config.ModuleConfig;
    28  import org.apache.struts.config.impl.ModuleConfigImpl;
    29  import org.apache.struts.mock.MockHttpServletRequest;
    30  import org.apache.struts.mock.MockHttpServletResponse;
    31  import org.apache.struts.mock.MockHttpSession;
    32  import org.apache.struts.mock.MockPageContext;
    33  import org.apache.struts.mock.MockServletConfig;
    34  import org.apache.struts.mock.MockServletContext;
    35  import org.apache.struts.util.MessageResources;
    36  import org.apache.struts.util.MessageResourcesFactory;
    37  import org.apache.struts.util.PropertyMessageResources;
    38  
    39  public class TagTestBase extends TestCase {
    40      protected TagUtils tagutils = TagUtils.getInstance();
    41      protected MockServletConfig servletConfig;
    42      protected MockServletContext servletContext;
    43      protected MockHttpServletRequest request;
    44      protected MockPageContext pageContext;
    45      protected ModuleConfig moduleConfig;
    46      protected ModuleConfig moduleConfig2;
    47      protected ModuleConfig moduleConfig3;
    48  
    49      public TagTestBase() {
    50          super();
    51      }
    52  
    53      public TagTestBase(String theName) {
    54          super(theName);
    55      }
    56  
    57      /**
    58       * Helper method that creates/configures a basic configuration of Mock
    59       * Objects.
    60       *
    61       *
    62       * PageContext ServletConfig ServletContext HttpServletRequest HttpSession
    63       * HttpServletResponse
    64       *
    65       * "/myapp", "/foo", null, null,
    66       */
    67      public void setUp() {
    68          // -- default Module
    69          this.moduleConfig = new ModuleConfigImpl("");
    70          this.moduleConfig.addForwardConfig(new ForwardConfig("foo", "/bar.jsp",
    71                  false));
    72          this.moduleConfig.addForwardConfig(new ForwardConfig("relative1",
    73                  "relative.jsp", false));
    74          this.moduleConfig.addForwardConfig(new ForwardConfig("relative2",
    75                  "relative.jsp", false));
    76          this.moduleConfig.addForwardConfig(new ForwardConfig("external",
    77                  "http://struts.apache.org/", false));
    78  
    79          // -- module "/2"
    80          this.moduleConfig2 = new ModuleConfigImpl("/2");
    81          this.moduleConfig2.addForwardConfig(new ForwardConfig("foo",
    82                  "/baz.jsp", false));
    83          this.moduleConfig2.addForwardConfig(new ForwardConfig("relative1",
    84                  "relative.jsp", false));
    85          this.moduleConfig2.addForwardConfig(new ForwardConfig("relative2",
    86                  "relative.jsp", false));
    87          this.moduleConfig2.addForwardConfig(new ForwardConfig("external",
    88                  "http://struts.apache.org/", false));
    89  
    90          // -- module "/3"
    91          this.moduleConfig3 = new ModuleConfigImpl("/3");
    92  
    93          // -- configure the ServletContext
    94          this.servletContext = new MockServletContext();
    95          this.servletContext.setAttribute(Globals.MODULE_KEY, moduleConfig);
    96          this.servletContext.setAttribute(Globals.MODULE_KEY + "/2",
    97              moduleConfig2);
    98          this.servletContext.setAttribute(Globals.MODULE_KEY + "/3",
    99              moduleConfig3);
    100 
    101         // -- configure the ServletConfig
    102         this.servletConfig = new MockServletConfig();
    103         this.servletConfig.setServletContext(servletContext);
    104 
    105         // -- configure the request
    106         this.request = new MockHttpServletRequest(new MockHttpSession());
    107 
    108         pageContext =
    109             new MockPageContext(servletConfig, request,
    110                 new MockHttpServletResponse());
    111     }
    112 
    113     public void tearDown() {
    114         this.moduleConfig = null;
    115         this.moduleConfig2 = null;
    116         this.moduleConfig3 = null;
    117         this.pageContext = null;
    118         this.request = null;
    119     }
    120 
    121     protected void putBundleInScope(int scope, boolean returnNull) {
    122         MessageResourcesFactory factory =
    123             MessageResourcesFactory.createFactory();
    124         MessageResources messageResources =
    125             new PropertyMessageResources(factory,
    126                 "org.apache.struts.taglib.sample");
    127 
    128         messageResources.setReturnNull(returnNull);
    129         pageContext.setAttribute(Globals.MESSAGES_KEY, messageResources, scope);
    130     }
    131 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
