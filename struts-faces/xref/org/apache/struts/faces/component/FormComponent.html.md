[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/component/FormComponent.html.md)


    1   /*
    2    * $Id: FormComponent.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.component;
    23  
    24  
    25  import java.util.Map;
    26  import javax.faces.component.UIForm;
    27  import javax.faces.context.FacesContext;
    28  import javax.faces.el.ValueBinding;
    29  import javax.servlet.http.HttpSession;
    30  import org.apache.commons.beanutils.DynaBean;
    31  import org.apache.commons.logging.Log;
    32  import org.apache.commons.logging.LogFactory;
    33  import org.apache.struts.Globals;
    34  import org.apache.struts.action.ActionForm;
    35  import org.apache.struts.action.ActionServlet;
    36  import org.apache.struts.action.DynaActionFormClass;
    37  import org.apache.struts.config.ActionConfig;
    38  import org.apache.struts.config.FormBeanConfig;
    39  import org.apache.struts.config.ModuleConfig;
    40  import org.apache.struts.util.RequestUtils;
    41  
    42  
    43  /**
    44   * <p><strong>FormComponent</strong> is a specialized subclass of
    45   * <code>javax.faces.component.UIForm</code> that supports automatic
    46   * creation of form beans in request or session scope.</p>
    47   *
    48   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    49   */
    50  public class FormComponent extends UIForm {
    51  
    52  
    53      // -------------------------------------------------------- Static Variables
    54  
    55  
    56      /**
    57       * <p>The <code>Log</code> instance for this class.</p>
    58       */
    59      protected static Log log = LogFactory.getLog(FormComponent.class);
    60  
    61  
    62      // ------------------------------------------------------ Instance Variables
    63  
    64  
    65      private String action = null;
    66      private String enctype = null;
    67      private String focus = null;
    68      private String focusIndex = null;
    69      private String onreset = null;
    70      private String onsubmit = null;
    71      private String style = null;
    72      private String styleClass = null;
    73      private String target = null;
    74  
    75  
    76      // ---------------------------------------------------- Component Properties
    77  
    78  
    79      /**
    80       * <p>Return the Struts action path to which this form should be submitted.
    81       * </p>
    82       */
    83      public String getAction() {
    84  
    85          if (this.action != null) {
    86              return (this.action);
    87          }
    88          ValueBinding vb = getValueBinding("action");
    89          if (vb != null) {
    90              return ((String) vb.getValue(getFacesContext()));
    91          } else {
    92              return (null);
    93          }
    94  
    95      }
    96  
    97  
    98      /**
    99       * <p>Set the Struts action to which this form should be submitted.</p>
    100      *
    101      * @param action The new action path
    102      */
    103     public void setAction(String action) {
    104 
    105         this.action = action;
    106 
    107     }
    108 
    109 
    110     /**
    111      * <p>Return the encoding type for this form submit.</p>
    112      */
    113     public String getEnctype() {
    114 
    115         if (this.enctype != null) {
    116             return (this.enctype);
    117         }
    118         ValueBinding vb = getValueBinding("enctype");
    119         if (vb != null) {
    120             return ((String) vb.getValue(getFacesContext()));
    121         } else {
    122             return (null);
    123         }
    124 
    125     }
    126 
    127 
    128     /**
    129      * <p>Set the encoding type for this form submit.</p>
    130      *
    131      * @param enctype The new enctype path
    132      */
    133     public void setEnctype(String enctype) {
    134 
    135         this.enctype = enctype;
    136 
    137     }
    138 
    139 
    140     /**
    141      * <p>Return the component family to which this component belongs.</p>
    142      */
    143     public String getFamily() {
    144 
    145         return "org.apache.struts.faces.Form";
    146 
    147     }
    148 
    149 
    150     /**
    151      * <p>Return the focus element name.</p>
    152      */
    153     public String getFocus() {
    154 
    155         if (this.focus != null) {
    156             return (this.focus);
    157         }
    158         ValueBinding vb = getValueBinding("focus");
    159         if (vb != null) {
    160             return ((String) vb.getValue(getFacesContext()));
    161         } else {
    162             return (null);
    163         }
    164 
    165     }
    166 
    167 
    168     /**
    169      * <p>Set the focus element name.</p>
    170      *
    171      * @param focus The new focus path
    172      */
    173     public void setFocus(String focus) {
    174 
    175         this.focus = focus;
    176 
    177     }
    178 
    179 
    180     /**
    181      * <p>Return the focus element index.</p>
    182      */
    183     public String getFocusIndex() {
    184 
    185         if (this.focusIndex != null) {
    186             return (this.focusIndex);
    187         }
    188         ValueBinding vb = getValueBinding("focusIndex");
    189         if (vb != null) {
    190             return ((String) vb.getValue(getFacesContext()));
    191         } else {
    192             return (null);
    193         }
    194 
    195     }
    196 
    197 
    198     /**
    199      * <p>Set the focus element index.</p>
    200      *
    201      * @param focusIndex The new focusIndex path
    202      */
    203     public void setFocusIndex(String focusIndex) {
    204 
    205         this.focusIndex = focusIndex;
    206 
    207     }
    208 
    209 
    210     /**
    211      * <p>Return the JavaScript to execute on form reset.</p>
    212      */
    213     public String getOnreset() {
    214 
    215         if (this.onreset != null) {
    216             return (this.onreset);
    217         }
    218         ValueBinding vb = getValueBinding("onreset");
    219         if (vb != null) {
    220             return ((String) vb.getValue(getFacesContext()));
    221         } else {
    222             return (null);
    223         }
    224 
    225     }
    226 
    227 
    228     /**
    229      * <p>Set the JavaScript to execute on form reset.</p>
    230      *
    231      * @param onreset The new onreset path
    232      */
    233     public void setOnreset(String onreset) {
    234 
    235         this.onreset = onreset;
    236 
    237     }
    238 
    239 
    240     /**
    241      * <p>Return the JavaScript to execute on form submit.</p>
    242      */
    243     public String getOnsubmit() {
    244 
    245         if (this.onsubmit != null) {
    246             return (this.onsubmit);
    247         }
    248         ValueBinding vb = getValueBinding("onsubmit");
    249         if (vb != null) {
    250             return ((String) vb.getValue(getFacesContext()));
    251         } else {
    252             return (null);
    253         }
    254 
    255     }
    256 
    257 
    258     /**
    259      * <p>Set the JavaScript to execute on form submit.</p>
    260      *
    261      * @param onsubmit The new onsubmit path
    262      */
    263     public void setOnsubmit(String onsubmit) {
    264 
    265         this.onsubmit = onsubmit;
    266 
    267     }
    268 
    269 
    270     /**
    271      * <p>Return the CSS style(s) to be rendered for this component.</p>
    272      */
    273     public String getStyle() {
    274 
    275         ValueBinding vb = getValueBinding("style");
    276         if (vb != null) {
    277             return (String) vb.getValue(getFacesContext());
    278         } else {
    279             return style;
    280         }
    281 
    282     }
    283 
    284 
    285     /**
    286      * <p>Set the CSS style(s) to be rendered for this component.</p>
    287      *
    288      * @param style The new CSS style(s)
    289      */
    290     public void setStyle(String style) {
    291 
    292         this.style = style;
    293 
    294     }
    295 
    296 
    297     /**
    298      * <p>Return the CSS style class(es) to be rendered for this component.</p>
    299      */
    300     public String getStyleClass() {
    301 
    302         ValueBinding vb = getValueBinding("styleClass");
    303         if (vb != null) {
    304             return (String) vb.getValue(getFacesContext());
    305         } else {
    306             return styleClass;
    307         }
    308 
    309     }
    310 
    311 
    312     /**
    313      * <p>Set the CSS style class(es) to be rendered for this component.</p>
    314      *
    315      * @param styleClass The new CSS style class(es)
    316      */
    317     public void setStyleClass(String styleClass) {
    318 
    319         this.styleClass = styleClass;
    320 
    321     }
    322 
    323 
    324     /**
    325      * <p>Return the target frame for the response to this form submit.</p>
    326      */
    327     public String getTarget() {
    328 
    329         ValueBinding vb = getValueBinding("target");
    330         if (vb != null) {
    331             return (String) vb.getValue(getFacesContext());
    332         } else {
    333             return target;
    334         }
    335 
    336     }
    337 
    338 
    339     /**
    340      * <p>Set the target frame for the response to this form submit.</p>
    341      *
    342      * @param target The new CSS target(s)
    343      */
    344     public void setTarget(String target) {
    345 
    346         this.target = target;
    347 
    348     }
    349 
    350 
    351     // ---------------------------------------------------------- UIForm Methods
    352 
    353 
    354     /**
    355      * <p>Create an instance of the form bean (if necessary) before
    356      * delegating to the standard decoding process.</p>
    357      *
    358      * @param context FacesContext for the request we are processing
    359      */
    360     public void processDecodes(FacesContext context) {
    361 
    362         if (context == null) {
    363             throw new NullPointerException();
    364         }
    365 
    366         if (log.isDebugEnabled()) {
    367             log.debug("processDecodes(" + getClientId(context) + ")");
    368         }
    369 
    370         // Create the form bean (if necessary)
    371         Map params = context.getExternalContext().getRequestParameterMap();
    372         if (params.containsKey(getClientId(context))) {
    373             createActionForm(context);
    374         }
    375 
    376         // Perform the standard decode processing
    377         super.processDecodes(context);
    378 
    379     }
    380 
    381 
    382     /**
    383      * <p>Restore our state from the specified object.</p>
    384      *
    385      * @param context <code>FacesContext</code> for the current request
    386      * @param state Object containing our saved state
    387      */
    388     public void restoreState(FacesContext context, Object state) {
    389 
    390         Object values[] = (Object[]) state;
    391         super.restoreState(context, values[0]);
    392         action = (String) values[1];
    393         enctype = (String) values[2];
    394         focus = (String) values[3];
    395         focusIndex = (String) values[4];
    396         onreset = (String) values[5];
    397         onsubmit = (String) values[6];
    398         style = (String) values[7];
    399         styleClass = (String) values[8];
    400         target = (String) values[9];
    401 
    402     }
    403 
    404 
    405     /**
    406      * <p>Create and return an object representing our state to be saved.</p>
    407      *
    408      * @param context <code>FacesContext</code> for the current request
    409      */
    410     public Object saveState(FacesContext context) {
    411 
    412         Object values[] = new Object[10];
    413         values[0] = super.saveState(context);
    414         values[1] = action;
    415         values[2] = enctype;
    416         values[3] = focus;
    417         values[4] = focusIndex;
    418         values[5] = onreset;
    419         values[6] = onsubmit;
    420         values[7] = style;
    421         values[8] = styleClass;
    422         values[9] = target;
    423         return (values);
    424 
    425     }
    426 
    427 
    428 
    429     // ---------------------------------------------------------- Public Methods
    430 
    431 
    432     /**
    433      * <p>Create an appropriate form bean in the appropriate scope, if one
    434      * does not already exist.</p>
    435      *
    436      * @param context FacesContext for the current request
    437      *
    438      * @exception IllegalArgumentException if no ActionConfig for the
    439      *  specified action attribute can be located
    440      * @exception IllegalArgumentException if no FormBeanConfig for the
    441      *  specified form bean can be located
    442      * @exception IllegalArgumentException if no ModuleConfig can be
    443      *  located for this application module
    444      */
    445     public void createActionForm(FacesContext context) {
    446 
    447         // Look up the application module configuration information we need
    448         ModuleConfig moduleConfig = lookupModuleConfig(context);
    449 
    450         // Look up the ActionConfig we are processing
    451         String action = getAction();
    452         ActionConfig actionConfig = moduleConfig.findActionConfig(action);
    453         if (actionConfig == null) {
    454             throw new IllegalArgumentException("Cannot find action '" +
    455                                                action + "' configuration");
    456         }
    457 
    458         // Does this ActionConfig specify a form bean?
    459         String name = actionConfig.getName();
    460         if (name == null) {
    461             return;
    462         }
    463 
    464         // Look up the FormBeanConfig we are processing
    465         FormBeanConfig fbConfig = moduleConfig.findFormBeanConfig(name);
    466         if (fbConfig == null) {
    467             throw new IllegalArgumentException("Cannot find form bean '" +
    468                                                name + "' configuration");
    469         }
    470 
    471         // Does a usable form bean attribute already exist?
    472         String attribute = actionConfig.getAttribute();
    473         String scope = actionConfig.getScope();
    474         ActionForm instance = null;
    475         if ("request".equals(scope)) {
    476             instance = (ActionForm)
    477                 context.getExternalContext().getRequestMap().get(attribute);
    478         } else if ("session".equals(scope)) {
    479             HttpSession session = (HttpSession)
    480                 context.getExternalContext().getSession(true);
    481             instance = (ActionForm)
    482                 context.getExternalContext().getSessionMap().get(attribute);
    483         }
    484         if (instance != null) {
    485             if (fbConfig.getDynamic()) {
    486                 String className =
    487                     ((DynaBean) instance).getDynaClass().getName();
    488                 if (className.equals(fbConfig.getName())) {
    489                     if (log.isDebugEnabled()) {
    490                         log.debug
    491                             (" Recycling existing DynaActionForm instance " +
    492                              "of type '" + className + "'");
    493                     }
    494                     return;
    495                 }
    496             } else {
    497                 try {
    498                     Class configClass =
    499                         RequestUtils.applicationClass(fbConfig.getType());
    500                     if (configClass.isAssignableFrom(instance.getClass())) {
    501                         if (log.isDebugEnabled()) {
    502                             log.debug
    503                                 (" Recycling existing ActionForm instance " +
    504                                  "of class '" + instance.getClass().getName()
    505                                  + "'");
    506                         }
    507                         return;
    508                     }
    509                 } catch (Throwable t) {
    510                     throw new IllegalArgumentException
    511                         ("Cannot load form bean class '" +
    512                          fbConfig.getType() + "'");
    513                 }
    514             }
    515         }
    516 
    517         // Create a new form bean instance
    518         if (fbConfig.getDynamic()) {
    519             try {
    520                 DynaActionFormClass dynaClass =
    521                     DynaActionFormClass.createDynaActionFormClass(fbConfig);
    522                 instance = (ActionForm) dynaClass.newInstance();
    523                 if (log.isDebugEnabled()) {
    524                     log.debug
    525                         (" Creating new DynaActionForm instance " +
    526                          "of type '" + fbConfig.getType() + "'");
    527                     log.trace(" --> " + instance);
    528                 }
    529             } catch (Throwable t) {
    530                 throw new IllegalArgumentException
    531                     ("Cannot create form bean of type '" +
    532                      fbConfig.getType() + "'");
    533             }
    534         } else {
    535             try {
    536                 instance = (ActionForm)
    537                     RequestUtils.applicationInstance(fbConfig.getType());
    538                 if (log.isDebugEnabled()) {
    539                     log.debug
    540                         (" Creating new ActionForm instance " +
    541                          "of type '" + fbConfig.getType() + "'");
    542                     log.trace(" --> " + instance);
    543                 }
    544             } catch (Throwable t) {
    545                 throw new IllegalArgumentException
    546                     ("Cannot create form bean of class '" +
    547                      fbConfig.getType() + "'");
    548             }
    549         }
    550 
    551         // Configure and cache the form bean instance in the correct scope
    552         ActionServlet servlet = (ActionServlet)
    553             context.getExternalContext().getApplicationMap().get
    554             (Globals.ACTION_SERVLET_KEY);
    555         instance.setServlet(servlet);
    556         if ("request".equals(scope)) {
    557             context.getExternalContext().getRequestMap().put
    558                 (attribute, instance);
    559         } else if ("session".equals(scope)) {
    560             context.getExternalContext().getSessionMap().put
    561                 (attribute, instance);
    562         }
    563 
    564     }
    565 
    566 
    567     /**
    568      * <p>Return the <code>ModuleConfig</code> for the application module
    569      * this form is being processed for.</p>
    570      *
    571      * @param context The <code>FacesContext</code> for the current request
    572      *
    573      * @exception IllegalArgumentException if no <code>ModuleConfig</code>
    574      *  can be found
    575      */
    576     public ModuleConfig lookupModuleConfig(FacesContext context) {
    577 
    578         // Look up the application module configuration information we need
    579         ModuleConfig modConfig = (ModuleConfig)
    580             context.getExternalContext().getRequestMap().get
    581             (Globals.MODULE_KEY);
    582         if (modConfig == null) {
    583             modConfig = (ModuleConfig)
    584                 context.getExternalContext().getApplicationMap().get
    585                 (Globals.MODULE_KEY);
    586         }
    587         if (modConfig == null) {
    588             throw new IllegalArgumentException
    589                 ("Cannot find module configuration");
    590         }
    591         return (modConfig);
    592 
    593     }
    594 
    595 
    596 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
