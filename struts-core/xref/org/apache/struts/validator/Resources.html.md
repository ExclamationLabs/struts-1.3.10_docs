[View Javadoc](../../../../../apidocs/org/apache/struts/validator/Resources.html.md)


    1   /*
    2    * $Id: Resources.java 476419 2006-11-18 02:28:07Z niallp $
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
    21  package org.apache.struts.validator;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.commons.validator.Arg;
    26  import org.apache.commons.validator.Field;
    27  import org.apache.commons.validator.Msg;
    28  import org.apache.commons.validator.Validator;
    29  import org.apache.commons.validator.ValidatorAction;
    30  import org.apache.commons.validator.ValidatorResources;
    31  import org.apache.commons.validator.Var;
    32  import org.apache.struts.Globals;
    33  import org.apache.struts.action.ActionMessage;
    34  import org.apache.struts.action.ActionMessages;
    35  import org.apache.struts.config.ModuleConfig;
    36  import org.apache.struts.util.MessageResources;
    37  import org.apache.struts.util.ModuleUtils;
    38  import org.apache.struts.util.RequestUtils;
    39  
    40  import javax.servlet.ServletContext;
    41  import javax.servlet.http.HttpServletRequest;
    42  
    43  import java.util.Locale;
    44  
    45  /**
    46   * This class helps provides some useful methods for retrieving objects from
    47   * different scopes of the application.
    48   *
    49   * @version $Rev: 476419 $ $Date: 2005-09-16 23:34:41 -0400 (Fri, 16 Sep 2005)
    50   *          $
    51   * @since Struts 1.1
    52   */
    53  public class Resources {
    54      /**
    55       * The message resources for this package.
    56       */
    57      private static MessageResources sysmsgs =
    58          MessageResources.getMessageResources(
    59              "org.apache.struts.validator.LocalStrings");
    60  
    61      /**
    62       * <p>Commons Logging instance.</p>
    63       */
    64      private static Log log = LogFactory.getLog(Resources.class);
    65  
    66      /**
    67       * Resources key the <code>ServletContext</code> is stored under.
    68       */
    69      private static String SERVLET_CONTEXT_PARAM =
    70          "javax.servlet.ServletContext";
    71  
    72      /**
    73       * Resources key the <code>HttpServletRequest</code> is stored under.
    74       */
    75      private static String HTTP_SERVLET_REQUEST_PARAM =
    76          "javax.servlet.http.HttpServletRequest";
    77  
    78      /**
    79       * Resources key the <code>ActionMessages</code> is stored under.
    80       */
    81      private static String ACTION_MESSAGES_PARAM =
    82          "org.apache.struts.action.ActionMessages";
    83  
    84      /**
    85       * Retrieve <code>ValidatorResources</code> for the current module.
    86       *
    87       * @param application Application Context
    88       * @param request     The ServletRequest
    89       */
    90      public static ValidatorResources getValidatorResources(
    91          ServletContext application, HttpServletRequest request) {
    92          String prefix =
    93              ModuleUtils.getInstance().getModuleConfig(request, application)
    94                         .getPrefix();
    95  
    96          return (ValidatorResources) application.getAttribute(ValidatorPlugIn.VALIDATOR_KEY
    97              + prefix);
    98      }
    99  
    100     /**
    101      * Retrieve <code>MessageResources</code> for the module.
    102      *
    103      * @param request the servlet request
    104      */
    105     public static MessageResources getMessageResources(
    106         HttpServletRequest request) {
    107         return (MessageResources) request.getAttribute(Globals.MESSAGES_KEY);
    108     }
    109 
    110     /**
    111      * Retrieve <code>MessageResources</code> for the module and bundle.
    112      *
    113      * @param application the servlet context
    114      * @param request     the servlet request
    115      * @param bundle      the bundle key
    116      */
    117     public static MessageResources getMessageResources(
    118         ServletContext application, HttpServletRequest request, String bundle) {
    119         if (bundle == null) {
    120             bundle = Globals.MESSAGES_KEY;
    121         }
    122 
    123         MessageResources resources =
    124             (MessageResources) request.getAttribute(bundle);
    125 
    126         if (resources == null) {
    127             ModuleConfig moduleConfig =
    128                 ModuleUtils.getInstance().getModuleConfig(request, application);
    129 
    130             resources =
    131                 (MessageResources) application.getAttribute(bundle
    132                     + moduleConfig.getPrefix());
    133         }
    134 
    135         if (resources == null) {
    136             resources = (MessageResources) application.getAttribute(bundle);
    137         }
    138 
    139         if (resources == null) {
    140             throw new NullPointerException(
    141                 "No message resources found for bundle: " + bundle);
    142         }
    143 
    144         return resources;
    145     }
    146 
    147     /**
    148      * Get the value of a variable.
    149      *
    150      * @param varName   The variable name
    151      * @param field     the validator Field
    152      * @param validator The Validator
    153      * @param request   the servlet request
    154      * @param required  Whether the variable is mandatory
    155      * @return The variable's value
    156      */
    157     public static String getVarValue(String varName, Field field,
    158         Validator validator, HttpServletRequest request, boolean required) {
    159         Var var = field.getVar(varName);
    160 
    161         if (var == null) {
    162             String msg = sysmsgs.getMessage("variable.missing", varName);
    163 
    164             if (required) {
    165                 throw new IllegalArgumentException(msg);
    166             }
    167 
    168             if (log.isDebugEnabled()) {
    169                 log.debug(field.getProperty() + ": " + msg);
    170             }
    171 
    172             return null;
    173         }
    174 
    175         ServletContext application =
    176             (ServletContext) validator.getParameterValue(SERVLET_CONTEXT_PARAM);
    177 
    178         return getVarValue(var, application, request, required);
    179     }
    180 
    181     /**
    182      * Get the value of a variable.
    183      *
    184      * @param var         the validator variable
    185      * @param application The ServletContext
    186      * @param request     the servlet request
    187      * @param required    Whether the variable is mandatory
    188      * @return The variables values
    189      */
    190     public static String getVarValue(Var var, ServletContext application,
    191         HttpServletRequest request, boolean required) {
    192         String varName = var.getName();
    193         String varValue = var.getValue();
    194 
    195         // Non-resource variable
    196         if (!var.isResource()) {
    197             return varValue;
    198         }
    199 
    200         // Get the message resources
    201         String bundle = var.getBundle();
    202         MessageResources messages =
    203             getMessageResources(application, request, bundle);
    204 
    205         // Retrieve variable's value from message resources
    206         Locale locale = RequestUtils.getUserLocale(request, null);
    207         String value = messages.getMessage(locale, varValue, null);
    208 
    209         // Not found in message resources
    210         if ((value == null) && required) {
    211             throw new IllegalArgumentException(sysmsgs.getMessage(
    212                     "variable.resource.notfound", varName, varValue, bundle));
    213         }
    214 
    215         if (log.isDebugEnabled()) {
    216             log.debug("Var=[" + varName + "], " + "bundle=[" + bundle + "], "
    217                 + "key=[" + varValue + "], " + "value=[" + value + "]");
    218         }
    219 
    220         return value;
    221     }
    222 
    223     /**
    224      * Gets the <code>Locale</code> sensitive value based on the key passed
    225      * in.
    226      *
    227      * @param messages The Message resources
    228      * @param locale   The locale.
    229      * @param key      Key used to lookup the message
    230      */
    231     public static String getMessage(MessageResources messages, Locale locale,
    232         String key) {
    233         String message = null;
    234 
    235         if (messages != null) {
    236             message = messages.getMessage(locale, key);
    237         }
    238 
    239         return (message == null) ? "" : message;
    240     }
    241 
    242     /**
    243      * Gets the <code>Locale</code> sensitive value based on the key passed
    244      * in.
    245      *
    246      * @param request servlet request
    247      * @param key     the request key
    248      */
    249     public static String getMessage(HttpServletRequest request, String key) {
    250         MessageResources messages = getMessageResources(request);
    251 
    252         return getMessage(messages, RequestUtils.getUserLocale(request, null),
    253             key);
    254     }
    255 
    256     /**
    257      * Gets the locale sensitive message based on the <code>ValidatorAction</code>
    258      * message and the <code>Field</code>'s arg objects.
    259      *
    260      * @param messages The Message resources
    261      * @param locale   The locale
    262      * @param va       The Validator Action
    263      * @param field    The Validator Field
    264      */
    265     public static String getMessage(MessageResources messages, Locale locale,
    266         ValidatorAction va, Field field) {
    267         String[] args = getArgs(va.getName(), messages, locale, field);
    268         String msg =
    269             (field.getMsg(va.getName()) != null) ? field.getMsg(va.getName())
    270                                                  : va.getMsg();
    271 
    272         return messages.getMessage(locale, msg, args);
    273     }
    274 
    275     /**
    276      * Gets the <code>Locale</code> sensitive value based on the key passed
    277      * in.
    278      *
    279      * @param application     the servlet context
    280      * @param request         the servlet request
    281      * @param defaultMessages The default Message resources
    282      * @param locale          The locale
    283      * @param va              The Validator Action
    284      * @param field           The Validator Field
    285      */
    286     public static String getMessage(ServletContext application,
    287         HttpServletRequest request, MessageResources defaultMessages,
    288         Locale locale, ValidatorAction va, Field field) {
    289         Msg msg = field.getMessage(va.getName());
    290 
    291         if ((msg != null) && !msg.isResource()) {
    292             return msg.getKey();
    293         }
    294 
    295         String msgKey = null;
    296         String msgBundle = null;
    297         MessageResources messages = defaultMessages;
    298 
    299         if (msg == null) {
    300             msgKey = va.getMsg();
    301         } else {
    302             msgKey = msg.getKey();
    303             msgBundle = msg.getBundle();
    304 
    305             if (msg.getBundle() != null) {
    306                 messages =
    307                     getMessageResources(application, request, msg.getBundle());
    308             }
    309         }
    310 
    311         if ((msgKey == null) || (msgKey.length() == 0)) {
    312             return "??? " + va.getName() + "." + field.getProperty() + " ???";
    313         }
    314 
    315         // Get the arguments
    316         Arg[] args = field.getArgs(va.getName());
    317         String[] argValues =
    318             getArgValues(application, request, messages, locale, args);
    319 
    320         // Return the message
    321         return messages.getMessage(locale, msgKey, argValues);
    322     }
    323 
    324     /**
    325      * Gets the <code>ActionMessage</code> based on the
    326      * <code>ValidatorAction</code> message and the <code>Field</code>'s arg
    327      * objects.
    328      * <p>
    329      * <strong>Note:</strong> this method does not respect bundle information
    330      * stored with the field's &lt;msg&gt; or &lt;arg&gt; elements, and localization
    331      * will not work for alternative resource bundles. This method is
    332      * deprecated for this reason, and you should use
    333      * {@link #getActionMessage(Validator,HttpServletRequest,ValidatorAction,Field)}
    334      * instead. 
    335      *
    336      * @param request the servlet request
    337      * @param va      Validator action
    338      * @param field   the validator Field
    339      * @deprecated Use getActionMessage(Validator, HttpServletRequest,
    340      *    ValidatorAction, Field) method instead
    341      */
    342     public static ActionMessage getActionMessage(HttpServletRequest request,
    343         ValidatorAction va, Field field) {
    344         String[] args =
    345             getArgs(va.getName(), getMessageResources(request),
    346                 RequestUtils.getUserLocale(request, null), field);
    347 
    348         String msg =
    349             (field.getMsg(va.getName()) != null) ? field.getMsg(va.getName())
    350                                                  : va.getMsg();
    351 
    352         return new ActionMessage(msg, args);
    353     }
    354 
    355     /**
    356      * Gets the <code>ActionMessage</code> based on the
    357      * <code>ValidatorAction</code> message and the <code>Field</code>'s arg
    358      * objects.
    359      *
    360      * @param validator the Validator
    361      * @param request   the servlet request
    362      * @param va        Validator action
    363      * @param field     the validator Field
    364      */
    365     public static ActionMessage getActionMessage(Validator validator,
    366         HttpServletRequest request, ValidatorAction va, Field field) {
    367         Msg msg = field.getMessage(va.getName());
    368 
    369         if ((msg != null) && !msg.isResource()) {
    370             return new ActionMessage(msg.getKey(), false);
    371         }
    372 
    373         String msgKey = null;
    374         String msgBundle = null;
    375 
    376         if (msg == null) {
    377             msgKey = va.getMsg();
    378         } else {
    379             msgKey = msg.getKey();
    380             msgBundle = msg.getBundle();
    381         }
    382 
    383         if ((msgKey == null) || (msgKey.length() == 0)) {
    384             return new ActionMessage("??? " + va.getName() + "."
    385                 + field.getProperty() + " ???", false);
    386         }
    387 
    388         ServletContext application =
    389             (ServletContext) validator.getParameterValue(SERVLET_CONTEXT_PARAM);
    390         MessageResources messages =
    391             getMessageResources(application, request, msgBundle);
    392         Locale locale = RequestUtils.getUserLocale(request, null);
    393 
    394         Arg[] args = field.getArgs(va.getName());
    395         String[] argValues =
    396             getArgValues(application, request, messages, locale, args);
    397 
    398         ActionMessage actionMessage = null;
    399 
    400         if (msgBundle == null) {
    401             actionMessage = new ActionMessage(msgKey, argValues);
    402         } else {
    403             String message = messages.getMessage(locale, msgKey, argValues);
    404 
    405             actionMessage = new ActionMessage(message, false);
    406         }
    407 
    408         return actionMessage;
    409     }
    410 
    411     /**
    412      * Gets the message arguments based on the current <code>ValidatorAction</code>
    413      * and <code>Field</code>.
    414      *
    415      * @param actionName action name
    416      * @param messages   message resources
    417      * @param locale     the locale
    418      * @param field      the validator field
    419      */
    420     public static String[] getArgs(String actionName,
    421         MessageResources messages, Locale locale, Field field) {
    422         String[] argMessages = new String[4];
    423 
    424         Arg[] args =
    425             new Arg[] {
    426                 field.getArg(actionName, 0), field.getArg(actionName, 1),
    427                 field.getArg(actionName, 2), field.getArg(actionName, 3)
    428             };
    429 
    430         for (int i = 0; i < args.length; i++) {
    431             if (args[i] == null) {
    432                 continue;
    433             }
    434 
    435             if (args[i].isResource()) {
    436                 argMessages[i] = getMessage(messages, locale, args[i].getKey());
    437             } else {
    438                 argMessages[i] = args[i].getKey();
    439             }
    440         }
    441 
    442         return argMessages;
    443     }
    444 
    445     /**
    446      * Gets the message arguments based on the current <code>ValidatorAction</code>
    447      * and <code>Field</code>.
    448      *
    449      * @param application     the servlet context
    450      * @param request         the servlet request
    451      * @param defaultMessages Default message resources
    452      * @param locale          the locale
    453      * @param args            The arguments for the message
    454      */
    455     private static String[] getArgValues(ServletContext application,
    456         HttpServletRequest request, MessageResources defaultMessages,
    457         Locale locale, Arg[] args) {
    458         if ((args == null) || (args.length == 0)) {
    459             return null;
    460         }
    461 
    462         String[] values = new String[args.length];
    463 
    464         for (int i = 0; i < args.length; i++) {
    465             if (args[i] != null) {
    466                 if (args[i].isResource()) {
    467                     MessageResources messages = defaultMessages;
    468 
    469                     if (args[i].getBundle() != null) {
    470                         messages =
    471                             getMessageResources(application, request,
    472                                 args[i].getBundle());
    473                     }
    474 
    475                     values[i] = messages.getMessage(locale, args[i].getKey());
    476                 } else {
    477                     values[i] = args[i].getKey();
    478                 }
    479             }
    480         }
    481 
    482         return values;
    483     }
    484 
    485     /**
    486      * Initialize the <code>Validator</code> to perform validation.
    487      *
    488      * @param key         The key that the validation rules are under (the
    489      *                    form elements name attribute).
    490      * @param bean        The bean validation is being performed on.
    491      * @param application servlet context
    492      * @param request     The current request object.
    493      * @param errors      The object any errors will be stored in.
    494      * @param page        This in conjunction with  the page property of a
    495      *                    <code>Field<code> can control the processing of
    496      *                    fields.  If the field's page is less than or equal
    497      *                    to this page value, it will be processed.
    498      */
    499     public static Validator initValidator(String key, Object bean,
    500         ServletContext application, HttpServletRequest request,
    501         ActionMessages errors, int page) {
    502         ValidatorResources resources =
    503             Resources.getValidatorResources(application, request);
    504 
    505         Locale locale = RequestUtils.getUserLocale(request, null);
    506 
    507         Validator validator = new Validator(resources, key);
    508 
    509         validator.setUseContextClassLoader(true);
    510 
    511         validator.setPage(page);
    512 
    513         validator.setParameter(SERVLET_CONTEXT_PARAM, application);
    514         validator.setParameter(HTTP_SERVLET_REQUEST_PARAM, request);
    515         validator.setParameter(Validator.LOCALE_PARAM, locale);
    516         validator.setParameter(ACTION_MESSAGES_PARAM, errors);
    517         validator.setParameter(Validator.BEAN_PARAM, bean);
    518 
    519         return validator;
    520     }
    521 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
