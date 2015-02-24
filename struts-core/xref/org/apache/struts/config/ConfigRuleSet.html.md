[View Javadoc](../../../../../apidocs/org/apache/struts/config/ConfigRuleSet.html.md)


    1   /*
    2    * $Id: ConfigRuleSet.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.config;
    22  
    23  import org.apache.commons.digester.AbstractObjectCreationFactory;
    24  import org.apache.commons.digester.Digester;
    25  import org.apache.commons.digester.Rule;
    26  import org.apache.commons.digester.RuleSetBase;
    27  import org.apache.commons.digester.SetPropertyRule;
    28  import org.apache.struts.util.RequestUtils;
    29  import org.xml.sax.Attributes;
    30  
    31  /**
    32   * <p>The set of Digester rules required to parse a Struts configuration file
    33   * (<code>struts-config.xml</code>).</p>
    34   *
    35   * @version $Rev: 471754 $ $Date: 2005-08-16 15:53:27 -0400 (Tue, 16 Aug 2005)
    36   *          $
    37   * @since Struts 1.1
    38   */
    39  public class ConfigRuleSet extends RuleSetBase {
    40      // --------------------------------------------------------- Public Methods
    41  
    42      /**
    43       * <p>Add the set of Rule instances defined in this RuleSet to the
    44       * specified <code>Digester</code> instance, associating them with our
    45       * namespace URI (if any).  This method should only be called by a
    46       * Digester instance.  These rules assume that an instance of
    47       * <code>org.apache.struts.config.ModuleConfig</code> is pushed onto the
    48       * evaluation stack before parsing begins.</p>
    49       *
    50       * @param digester Digester instance to which the new Rule instances
    51       *                 should be added.
    52       */
    53      public void addRuleInstances(Digester digester) {
    54          ClassLoader cl = digester.getClassLoader();
    55  
    56          digester.addRule("struts-config/action-mappings",
    57              new SetActionMappingClassRule());
    58  
    59          digester.addFactoryCreate("struts-config/action-mappings/action",
    60              new ActionMappingFactory(cl));
    61          digester.addSetProperties("struts-config/action-mappings/action");
    62          digester.addSetNext("struts-config/action-mappings/action",
    63              "addActionConfig", "org.apache.struts.config.ActionConfig");
    64  
    65          digester.addRule("struts-config/action-mappings/action/set-property",
    66              new BaseConfigSetPropertyRule());
    67  
    68          digester.addObjectCreate("struts-config/action-mappings/action/exception",
    69              "org.apache.struts.config.ExceptionConfig", "className");
    70          digester.addSetProperties(
    71              "struts-config/action-mappings/action/exception");
    72          digester.addSetNext("struts-config/action-mappings/action/exception",
    73              "addExceptionConfig", "org.apache.struts.config.ExceptionConfig");
    74  
    75          digester.addRule("struts-config/action-mappings/action/exception/set-property",
    76              new BaseConfigSetPropertyRule());
    77  
    78          digester.addFactoryCreate("struts-config/action-mappings/action/forward",
    79              new ActionForwardFactory(cl));
    80          digester.addSetProperties(
    81              "struts-config/action-mappings/action/forward");
    82          digester.addSetNext("struts-config/action-mappings/action/forward",
    83              "addForwardConfig", "org.apache.struts.config.ForwardConfig");
    84  
    85          digester.addRule("struts-config/action-mappings/action/forward/set-property",
    86              new BaseConfigSetPropertyRule());
    87  
    88          digester.addObjectCreate("struts-config/controller",
    89              "org.apache.struts.config.ControllerConfig", "className");
    90          digester.addSetProperties("struts-config/controller");
    91          digester.addSetNext("struts-config/controller", "setControllerConfig",
    92              "org.apache.struts.config.ControllerConfig");
    93  
    94          digester.addRule("struts-config/controller/set-property",
    95              new BaseConfigSetPropertyRule());
    96  
    97          digester.addRule("struts-config/form-beans",
    98              new SetActionFormBeanClassRule());
    99  
    100         digester.addFactoryCreate("struts-config/form-beans/form-bean",
    101             new ActionFormBeanFactory(cl));
    102         digester.addSetProperties("struts-config/form-beans/form-bean");
    103         digester.addSetNext("struts-config/form-beans/form-bean",
    104             "addFormBeanConfig", "org.apache.struts.config.FormBeanConfig");
    105 
    106         digester.addObjectCreate("struts-config/form-beans/form-bean/form-property",
    107             "org.apache.struts.config.FormPropertyConfig", "className");
    108         digester.addSetProperties(
    109             "struts-config/form-beans/form-bean/form-property");
    110         digester.addSetNext("struts-config/form-beans/form-bean/form-property",
    111             "addFormPropertyConfig",
    112             "org.apache.struts.config.FormPropertyConfig");
    113 
    114         digester.addRule("struts-config/form-beans/form-bean/form-property/set-property",
    115             new BaseConfigSetPropertyRule());
    116 
    117         digester.addRule("struts-config/form-beans/form-bean/set-property",
    118             new BaseConfigSetPropertyRule());
    119 
    120         digester.addObjectCreate("struts-config/global-exceptions/exception",
    121             "org.apache.struts.config.ExceptionConfig", "className");
    122         digester.addSetProperties("struts-config/global-exceptions/exception");
    123         digester.addSetNext("struts-config/global-exceptions/exception",
    124             "addExceptionConfig", "org.apache.struts.config.ExceptionConfig");
    125 
    126         digester.addRule("struts-config/global-exceptions/exception/set-property",
    127             new BaseConfigSetPropertyRule());
    128 
    129         digester.addRule("struts-config/global-forwards",
    130             new SetActionForwardClassRule());
    131 
    132         digester.addFactoryCreate("struts-config/global-forwards/forward",
    133             new GlobalForwardFactory(cl));
    134         digester.addSetProperties("struts-config/global-forwards/forward");
    135         digester.addSetNext("struts-config/global-forwards/forward",
    136             "addForwardConfig", "org.apache.struts.config.ForwardConfig");
    137 
    138         digester.addRule("struts-config/global-forwards/forward/set-property",
    139             new BaseConfigSetPropertyRule());
    140 
    141         digester.addObjectCreate("struts-config/message-resources",
    142             "org.apache.struts.config.MessageResourcesConfig", "className");
    143         digester.addSetProperties("struts-config/message-resources");
    144         digester.addSetNext("struts-config/message-resources",
    145             "addMessageResourcesConfig",
    146             "org.apache.struts.config.MessageResourcesConfig");
    147 
    148         digester.addRule("struts-config/message-resources/set-property",
    149             new BaseConfigSetPropertyRule());
    150 
    151         digester.addObjectCreate("struts-config/plug-in",
    152             "org.apache.struts.config.PlugInConfig");
    153         digester.addSetProperties("struts-config/plug-in");
    154         digester.addSetNext("struts-config/plug-in", "addPlugInConfig",
    155             "org.apache.struts.config.PlugInConfig");
    156 
    157         digester.addRule("struts-config/plug-in/set-property",
    158             new PlugInSetPropertyRule());
    159 
    160         // PluginConfig does not extend BaseConfig, at least for now.
    161     }
    162 }
    163 
    164 
    165 /**
    166  * <p> Class that records the name and value of a configuration property to be
    167  * used in configuring a <code>PlugIn</code> instance when instantiated. </p>
    168  */
    169 final class PlugInSetPropertyRule extends Rule {
    170     public PlugInSetPropertyRule() {
    171         super();
    172     }
    173 
    174     public void begin(String namespace, String names, Attributes attributes)
    175         throws Exception {
    176         PlugInConfig plugInConfig = (PlugInConfig) digester.peek();
    177 
    178         plugInConfig.addProperty(attributes.getValue("property"),
    179             attributes.getValue("value"));
    180     }
    181 }
    182 
    183 
    184 /**
    185  * <p> Class that sets the name of the class to use when creating action form
    186  * bean instances. The value is set on the object on the top of the stack,
    187  * which must be a <code>org.apache.struts.config.ModuleConfig</code>. </p>
    188  */
    189 final class SetActionFormBeanClassRule extends Rule {
    190     public SetActionFormBeanClassRule() {
    191         super();
    192     }
    193 
    194     public void begin(String namespace, String name, Attributes attributes)
    195         throws Exception {
    196         String className = attributes.getValue("type");
    197 
    198         if (className != null) {
    199             ModuleConfig mc = (ModuleConfig) digester.peek();
    200 
    201             mc.setActionFormBeanClass(className);
    202         }
    203     }
    204 }
    205 
    206 
    207 /**
    208  * <p> A variant of the standard Digester <code>SetPropertyRule</code>.  If
    209  * the element being processed has a "key" attribute, then the value will be
    210  * used to call <code>setProperty(key,value)</code> on the object on top of
    211  * the stack, which will be assumed to be of type <code>ActionConfig</code>.
    212  * Otherwise, the standard <code>SetPropertyRule</code> behavior is invoked,
    213  * and the value will be used to set a bean property on the object on top of
    214  * the Digester stack. In that case, the element being processed is assumed to
    215  * have attributes "property" and "value". </p>
    216  */
    217 final class BaseConfigSetPropertyRule extends SetPropertyRule {
    218     public BaseConfigSetPropertyRule() {
    219         super("property", "value");
    220     }
    221 
    222     public void begin(Attributes attributes)
    223         throws Exception {
    224         if (attributes.getIndex("key") == -1) {
    225             super.begin(attributes);
    226 
    227             return;
    228         }
    229 
    230         if (attributes.getIndex("property") != -1) {
    231             throw new IllegalArgumentException(
    232                 "<set-property> accepts only one of 'key' or 'property' attributes.");
    233         }
    234 
    235         Object topOfStack = digester.peek();
    236 
    237         if (topOfStack instanceof BaseConfig) {
    238             BaseConfig config = (BaseConfig) topOfStack;
    239 
    240             config.setProperty(attributes.getValue("key"),
    241                 attributes.getValue("value"));
    242         } else {
    243             throw new IllegalArgumentException(
    244                 "'key' attribute of <set-property> only applicable to subclasses of BaseConfig; "
    245                 + "object on top of stack is " + topOfStack + " [key: "
    246                 + attributes.getValue("key") + ", value: "
    247                 + attributes.getValue("value") + "]");
    248         }
    249     }
    250 }
    251 
    252 
    253 /**
    254  * <p> An object creation factory which creates action form bean instances,
    255  * taking into account the default class name, which may have been specified
    256  * on the parent element and which is made available through the object on the
    257  * top of the stack, which must be a <code>org.apache.struts.config.ModuleConfig</code>.
    258  * </p>
    259  */
    260 final class ActionFormBeanFactory extends AbstractObjectCreationFactory {
    261     private ClassLoader cl;
    262 
    263     public ActionFormBeanFactory(ClassLoader cl) {
    264         super();
    265         this.cl = cl;
    266     }
    267 
    268     public Object createObject(Attributes attributes) {
    269         // Identify the name of the class to instantiate
    270         String className = attributes.getValue("className");
    271 
    272         if (className == null) {
    273             ModuleConfig mc = (ModuleConfig) digester.peek();
    274 
    275             className = mc.getActionFormBeanClass();
    276         }
    277 
    278         // Instantiate the new object and return it
    279         Object actionFormBean = null;
    280 
    281         try {
    282             actionFormBean = RequestUtils.applicationInstance(className, cl);
    283         } catch (Exception e) {
    284             digester.getLogger().error("ActionFormBeanFactory.createObject: ", e);
    285         }
    286 
    287         return actionFormBean;
    288     }
    289 }
    290 
    291 
    292 /**
    293  * <p> Class that sets the name of the class to use when creating action
    294  * mapping instances. The value is set on the object on the top of the stack,
    295  * which must be a <code>org.apache.struts.config.ModuleConfig</code>. </p>
    296  */
    297 final class SetActionMappingClassRule extends Rule {
    298     public SetActionMappingClassRule() {
    299         super();
    300     }
    301 
    302     public void begin(String namespace, String name, Attributes attributes)
    303         throws Exception {
    304         String className = attributes.getValue("type");
    305 
    306         if (className != null) {
    307             ModuleConfig mc = (ModuleConfig) digester.peek();
    308 
    309             mc.setActionMappingClass(className);
    310         }
    311     }
    312 }
    313 
    314 
    315 /**
    316  * <p> An object creation factory which creates action mapping instances,
    317  * taking into account the default class name, which may have been specified
    318  * on the parent element and which is made available through the object on the
    319  * top of the stack, which must be a <code>org.apache.struts.config.ModuleConfig</code>.
    320  * </p>
    321  */
    322 final class ActionMappingFactory extends AbstractObjectCreationFactory {
    323     private ClassLoader cl;
    324 
    325     public ActionMappingFactory(ClassLoader cl) {
    326         super();
    327         this.cl = cl;
    328     }
    329 
    330     public Object createObject(Attributes attributes) {
    331         // Identify the name of the class to instantiate
    332         String className = attributes.getValue("className");
    333 
    334         if (className == null) {
    335             ModuleConfig mc = (ModuleConfig) digester.peek();
    336 
    337             className = mc.getActionMappingClass();
    338         }
    339 
    340         // Instantiate the new object and return it
    341         Object actionMapping = null;
    342 
    343         try {
    344             actionMapping = RequestUtils.applicationInstance(className, cl);
    345         } catch (Exception e) {
    346             digester.getLogger().error("ActionMappingFactory.createObject: ", e);
    347         }
    348 
    349         return actionMapping;
    350     }
    351 }
    352 
    353 
    354 /**
    355  * <p> Class that sets the name of the class to use when creating global
    356  * forward instances. The value is set on the object on the top of the stack,
    357  * which must be a <code>org.apache.struts.config.ModuleConfig</code>. </p>
    358  */
    359 final class SetActionForwardClassRule extends Rule {
    360     public SetActionForwardClassRule() {
    361         super();
    362     }
    363 
    364     public void begin(String namespace, String name, Attributes attributes)
    365         throws Exception {
    366         String className = attributes.getValue("type");
    367 
    368         if (className != null) {
    369             ModuleConfig mc = (ModuleConfig) digester.peek();
    370 
    371             mc.setActionForwardClass(className);
    372         }
    373     }
    374 }
    375 
    376 
    377 /**
    378  * <p> An object creation factory which creates global forward instances,
    379  * taking into account the default class name, which may have been specified
    380  * on the parent element and which is made available through the object on the
    381  * top of the stack, which must be a <code>org.apache.struts.config.ModuleConfig</code>.
    382  * </p>
    383  */
    384 final class GlobalForwardFactory extends AbstractObjectCreationFactory {
    385     private ClassLoader cl;
    386 
    387     public GlobalForwardFactory(ClassLoader cl) {
    388         super();
    389         this.cl = cl;
    390     }
    391 
    392     public Object createObject(Attributes attributes) {
    393         // Identify the name of the class to instantiate
    394         String className = attributes.getValue("className");
    395 
    396         if (className == null) {
    397             ModuleConfig mc = (ModuleConfig) digester.peek();
    398 
    399             className = mc.getActionForwardClass();
    400         }
    401 
    402         // Instantiate the new object and return it
    403         Object globalForward = null;
    404 
    405         try {
    406             globalForward = RequestUtils.applicationInstance(className, cl);
    407         } catch (Exception e) {
    408             digester.getLogger().error("GlobalForwardFactory.createObject: ", e);
    409         }
    410 
    411         return globalForward;
    412     }
    413 }
    414 
    415 
    416 /**
    417  * <p> An object creation factory which creates action forward instances,
    418  * taking into account the default class name, which may have been specified
    419  * on the parent element and which is made available through the object on the
    420  * top of the stack, which must be a <code>org.apache.struts.config.ModuleConfig</code>.
    421  * </p>
    422  */
    423 final class ActionForwardFactory extends AbstractObjectCreationFactory {
    424     private ClassLoader cl;
    425 
    426     public ActionForwardFactory(ClassLoader cl) {
    427         super();
    428         this.cl = cl;
    429     }
    430 
    431     public Object createObject(Attributes attributes) {
    432         // Identify the name of the class to instantiate
    433         String className = attributes.getValue("className");
    434 
    435         if (className == null) {
    436             ModuleConfig mc = (ModuleConfig) digester.peek(1);
    437 
    438             className = mc.getActionForwardClass();
    439         }
    440 
    441         // Instantiate the new object and return it
    442         Object actionForward = null;
    443 
    444         try {
    445             actionForward = RequestUtils.applicationInstance(className, cl);
    446         } catch (Exception e) {
    447             digester.getLogger().error("ActionForwardFactory.createObject: ", e);
    448         }
    449 
    450         return actionForward;
    451     }
    452 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
