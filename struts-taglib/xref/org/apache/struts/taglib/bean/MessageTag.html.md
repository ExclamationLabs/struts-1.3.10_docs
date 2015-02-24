[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/MessageTag.html.md)


    1   /*
    2    * $Id: MessageTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.bean;
    22  
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.MessageResources;
    26  
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  import java.util.Locale;
    31  
    32  /**
    33   * Custom tag that retrieves an internationalized messages string (with
    34   * optional parametric replacement) from the <code>ActionResources</code>
    35   * object stored as a context attribute by our associated
    36   * <code>ActionServlet</code> implementation.
    37   *
    38   * @version $Rev: 471754 $ $Date: 2005-09-16 09:38:33 -0400 (Fri, 16 Sep 2005)
    39   *          $
    40   */
    41  public class MessageTag extends TagSupport {
    42      /**
    43       * The message resources for this package.
    44       */
    45      protected static MessageResources messages =
    46          MessageResources.getMessageResources(
    47              "org.apache.struts.taglib.bean.LocalStrings");
    48  
    49      // ------------------------------------------------------------- Properties
    50  
    51      /**
    52       * The first optional argument.
    53       */
    54      protected String arg0 = null;
    55  
    56      /**
    57       * The second optional argument.
    58       */
    59      protected String arg1 = null;
    60  
    61      /**
    62       * The third optional argument.
    63       */
    64      protected String arg2 = null;
    65  
    66      /**
    67       * The fourth optional argument.
    68       */
    69      protected String arg3 = null;
    70  
    71      /**
    72       * The fifth optional argument.
    73       */
    74      protected String arg4 = null;
    75  
    76      /**
    77       * The servlet context attribute key for our resources.
    78       */
    79      protected String bundle = null;
    80  
    81      /**
    82       * The message key of the message to be retrieved.
    83       */
    84      protected String key = null;
    85  
    86      /**
    87       * Name of the bean that contains the message key.
    88       */
    89      protected String name = null;
    90  
    91      /**
    92       * Name of the property to be accessed on the specified bean.
    93       */
    94      protected String property = null;
    95  
    96      /**
    97       * The scope to be searched to retrieve the specified bean.
    98       */
    99      protected String scope = null;
    100 
    101     /**
    102      * The session scope key under which our Locale is stored.
    103      */
    104     protected String localeKey = Globals.LOCALE_KEY;
    105 
    106     public String getArg0() {
    107         return (this.arg0);
    108     }
    109 
    110     public void setArg0(String arg0) {
    111         this.arg0 = arg0;
    112     }
    113 
    114     public String getArg1() {
    115         return (this.arg1);
    116     }
    117 
    118     public void setArg1(String arg1) {
    119         this.arg1 = arg1;
    120     }
    121 
    122     public String getArg2() {
    123         return (this.arg2);
    124     }
    125 
    126     public void setArg2(String arg2) {
    127         this.arg2 = arg2;
    128     }
    129 
    130     public String getArg3() {
    131         return (this.arg3);
    132     }
    133 
    134     public void setArg3(String arg3) {
    135         this.arg3 = arg3;
    136     }
    137 
    138     public String getArg4() {
    139         return (this.arg4);
    140     }
    141 
    142     public void setArg4(String arg4) {
    143         this.arg4 = arg4;
    144     }
    145 
    146     public String getBundle() {
    147         return (this.bundle);
    148     }
    149 
    150     public void setBundle(String bundle) {
    151         this.bundle = bundle;
    152     }
    153 
    154     public String getKey() {
    155         return (this.key);
    156     }
    157 
    158     public void setKey(String key) {
    159         this.key = key;
    160     }
    161 
    162     public String getName() {
    163         return (this.name);
    164     }
    165 
    166     public void setName(String name) {
    167         this.name = name;
    168     }
    169 
    170     public String getProperty() {
    171         return (this.property);
    172     }
    173 
    174     public void setProperty(String property) {
    175         this.property = property;
    176     }
    177 
    178     public String getScope() {
    179         return (this.scope);
    180     }
    181 
    182     public void setScope(String scope) {
    183         this.scope = scope;
    184     }
    185 
    186     public String getLocale() {
    187         return (this.localeKey);
    188     }
    189 
    190     public void setLocale(String localeKey) {
    191         this.localeKey = localeKey;
    192     }
    193 
    194     // --------------------------------------------------------- Public Methods
    195 
    196     /**
    197      * Process the start tag.
    198      *
    199      * @throws JspException if a JSP exception has occurred
    200      */
    201     public int doStartTag() throws JspException {
    202         String key = this.key;
    203 
    204         if (key == null) {
    205             // Look up the requested property value
    206             Object value =
    207                 TagUtils.getInstance().lookup(pageContext, name, property, scope);
    208 
    209             if ((value != null) && !(value instanceof String)) {
    210                 JspException e =
    211                     new JspException(messages.getMessage("message.property", key));
    212 
    213                 TagUtils.getInstance().saveException(pageContext, e);
    214                 throw e;
    215             }
    216 
    217             key = (String) value;
    218         }
    219 
    220         // Construct the optional arguments array we will be using
    221         Object[] args = new Object[] { arg0, arg1, arg2, arg3, arg4 };
    222 
    223         // Retrieve the message string we are looking for
    224         String message =
    225             TagUtils.getInstance().message(pageContext, this.bundle,
    226                 this.localeKey, key, args);
    227 
    228         if (message == null) {
    229             Locale locale =
    230                 TagUtils.getInstance().getUserLocale(pageContext, this.localeKey);
    231             String localeVal =
    232                 (locale == null) ? "default locale" : locale.toString();
    233             JspException e =
    234                 new JspException(messages.getMessage("message.message",
    235                         "\"" + key + "\"",
    236                         "\"" + ((bundle == null) ? "(default bundle)" : bundle)
    237                         + "\"", localeVal));
    238 
    239             TagUtils.getInstance().saveException(pageContext, e);
    240             throw e;
    241         }
    242 
    243         TagUtils.getInstance().write(pageContext, message);
    244 
    245         return (SKIP_BODY);
    246     }
    247 
    248     /**
    249      * Release any acquired resources.
    250      */
    251     public void release() {
    252         super.release();
    253         arg0 = null;
    254         arg1 = null;
    255         arg2 = null;
    256         arg3 = null;
    257         arg4 = null;
    258         bundle = Globals.MESSAGES_KEY;
    259         key = null;
    260         name = null;
    261         property = null;
    262         scope = null;
    263         localeKey = Globals.LOCALE_KEY;
    264     }
    265 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
