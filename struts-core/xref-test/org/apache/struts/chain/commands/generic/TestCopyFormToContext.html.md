
    1   /*
    2    * $Id: TestCopyFormToContext.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands.generic;
    22  
    23  import junit.framework.TestCase;
    24  
    25  import org.apache.struts.action.ActionForm;
    26  import org.apache.struts.action.DynaActionForm;
    27  import org.apache.struts.chain.contexts.MockActionContext;
    28  import org.apache.struts.config.ActionConfig;
    29  import org.apache.struts.config.FormBeanConfig;
    30  import org.apache.struts.config.FormPropertyConfig;
    31  import org.apache.struts.config.impl.ModuleConfigImpl;
    32  import org.apache.struts.mock.MockFormBean;
    33  
    34  /**
    35   * @version $Id: TestCopyFormToContext.java 161516 2005-04-15 19:22:47Z
    36   *          germuska $
    37   */
    38  public class TestCopyFormToContext extends TestCase {
    39      private static final String POST_EXECUTION_CONTEXT_KEY = "afterTest";
    40      private MockActionContext context = null;
    41  
    42      public static void main(String[] args) {
    43          junit.textui.TestRunner.run(TestCopyFormToContext.class);
    44      }
    45  
    46      /*
    47       * @see TestCase#setUp()
    48       */
    49      protected void setUp() throws Exception {
    50          context = new MockActionContext();
    51  
    52          ModuleConfigImpl moduleConfig = new ModuleConfigImpl("/");
    53  
    54          context.setModuleConfig(moduleConfig);
    55  
    56          FormBeanConfig fooFBC = new FormBeanConfig();
    57  
    58          fooFBC.setName("foo");
    59          fooFBC.setType("org.apache.struts.mock.MockFormBean");
    60          moduleConfig.addFormBeanConfig(fooFBC);
    61  
    62          FormBeanConfig barFBC = new FormBeanConfig();
    63  
    64          barFBC.setName("bar");
    65          barFBC.setType("org.apache.struts.action.DynaActionForm"); // use a different type so we can verify lookups better
    66  
    67          FormPropertyConfig fpc = new FormPropertyConfig();
    68  
    69          fpc.setName("property");
    70          fpc.setType("java.lang.String");
    71          fpc.setInitial("test");
    72          barFBC.addFormPropertyConfig(fpc);
    73          moduleConfig.addFormBeanConfig(barFBC);
    74  
    75          ActionConfig testActionConfig = new ActionConfig();
    76  
    77          testActionConfig.setPath("/Test");
    78          testActionConfig.setName("foo");
    79          testActionConfig.setScope("request");
    80          moduleConfig.addActionConfig(testActionConfig);
    81  
    82          moduleConfig.freeze(); // otherwise, ActionConfigMatcher will be null and we'll get an NPE...
    83      }
    84  
    85      public void testLookupByNameAndRequestScope()
    86          throws Exception {
    87          CopyFormToContext command = new CopyFormToContext();
    88          String formName = "foo";
    89  
    90          command.setFormName(formName);
    91          command.setScope("request");
    92          command.setToKey(POST_EXECUTION_CONTEXT_KEY);
    93  
    94          assertNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    95          assertNull(context.getRequestScope().get(formName));
    96          assertNull(context.getSessionScope().get(formName));
    97  
    98          command.execute(context);
    99  
    100         assertNotNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    101         assertNotNull(context.getRequestScope().get(formName));
    102         assertNull(context.getSessionScope().get(formName));
    103 
    104         assertSame(context.get(POST_EXECUTION_CONTEXT_KEY),
    105             context.getRequestScope().get(formName));
    106 
    107         ActionForm theForm =
    108             (ActionForm) context.get(POST_EXECUTION_CONTEXT_KEY);
    109 
    110         assertTrue(theForm instanceof MockFormBean);
    111     }
    112 
    113     public void testLookupByActionPath()
    114         throws Exception {
    115         CopyFormToContext command = new CopyFormToContext();
    116 
    117         command.setActionPath("/Test");
    118         command.setToKey(POST_EXECUTION_CONTEXT_KEY);
    119 
    120         String formName = "foo"; // we know this, even though it's not being used for the lookup.
    121 
    122         assertNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    123         assertNull(context.getRequestScope().get(formName));
    124         assertNull(context.getSessionScope().get(formName));
    125 
    126         command.execute(context);
    127 
    128         assertNotNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    129         assertNotNull(context.getRequestScope().get(formName));
    130         assertNull(context.getSessionScope().get(formName));
    131 
    132         assertSame(context.get(POST_EXECUTION_CONTEXT_KEY),
    133             context.getRequestScope().get(formName));
    134 
    135         ActionForm theForm =
    136             (ActionForm) context.get(POST_EXECUTION_CONTEXT_KEY);
    137 
    138         assertTrue(theForm instanceof MockFormBean);
    139     }
    140 
    141     public void testLookupByNameAndSessionScope()
    142         throws Exception {
    143         CopyFormToContext command = new CopyFormToContext();
    144         String formName = "bar";
    145 
    146         command.setFormName(formName);
    147         command.setScope("session");
    148         command.setToKey(POST_EXECUTION_CONTEXT_KEY);
    149 
    150         assertNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    151         assertNull(context.getRequestScope().get(formName));
    152         assertNull(context.getSessionScope().get(formName));
    153 
    154         command.execute(context);
    155 
    156         assertNotNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    157         assertNull(context.getRequestScope().get(formName));
    158         assertNotNull(context.getSessionScope().get(formName));
    159 
    160         assertSame(context.get(POST_EXECUTION_CONTEXT_KEY),
    161             context.getSessionScope().get(formName));
    162 
    163         ActionForm theForm =
    164             (ActionForm) context.get(POST_EXECUTION_CONTEXT_KEY);
    165 
    166         assertTrue(theForm instanceof DynaActionForm);
    167 
    168         DynaActionForm dForm = (DynaActionForm) theForm;
    169 
    170         assertEquals("test", dForm.get("property"));
    171     }
    172 
    173     public void testExceptionHandlingWithNullFormName()
    174         throws Exception {
    175         CopyFormToContext command = new CopyFormToContext();
    176         String formName = "bar";
    177 
    178         // skip setting form name to test exception
    179         // command.setFormName(formName);
    180         command.setScope("session");
    181         command.setToKey(POST_EXECUTION_CONTEXT_KEY);
    182 
    183         assertNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    184         assertNull(context.getRequestScope().get(formName));
    185         assertNull(context.getSessionScope().get(formName));
    186 
    187         try {
    188             command.execute(context);
    189             fail(
    190                 "Execution should throw an exception when form name is not set.");
    191         } catch (IllegalStateException e) {
    192             ; // expected.
    193         }
    194     }
    195 
    196     public void testExceptionHandlingWithNullEverything()
    197         throws Exception {
    198         CopyFormToContext command = new CopyFormToContext();
    199         String formName = "bar";
    200 
    201         // skip setting form name to test exception
    202         // command.setFormName(formName);
    203         // command.setScope("session");
    204         // command.setToKey(POST_EXECUTION_CONTEXT_KEY);
    205         assertNull(context.get(POST_EXECUTION_CONTEXT_KEY));
    206         assertNull(context.getRequestScope().get(formName));
    207         assertNull(context.getSessionScope().get(formName));
    208 
    209         try {
    210             command.execute(context);
    211             fail(
    212                 "Execution should throw an exception when no properties are set.");
    213         } catch (IllegalStateException e) {
    214             ; // expected.
    215         }
    216     }
    217 
    218     public void testCopyToDefaultContextKey()
    219         throws Exception {
    220         CopyFormToContext command = new CopyFormToContext();
    221         String formName = "foo";
    222 
    223         command.setFormName(formName);
    224         command.setScope("request");
    225 
    226         assertNull(context.getActionForm());
    227         assertNull(context.getRequestScope().get(POST_EXECUTION_CONTEXT_KEY));
    228         assertNull(context.getSessionScope().get(POST_EXECUTION_CONTEXT_KEY));
    229 
    230         command.execute(context);
    231 
    232         assertNotNull(context.getActionForm());
    233         assertNotNull(context.getRequestScope().get(formName));
    234         assertNull(context.getSessionScope().get(formName));
    235 
    236         assertSame(context.getActionForm(),
    237             context.getRequestScope().get(formName));
    238 
    239         ActionForm theForm = (ActionForm) context.getActionForm();
    240 
    241         assertTrue(theForm instanceof MockFormBean);
    242     }
    243 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
