[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/MessagesTag.html)


    1   /*
    2    * $Id: MessagesTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.html.md;
    22  
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.action.ActionMessage;
    25  import org.apache.struts.action.ActionMessages;
    26  import org.apache.struts.taglib.TagUtils;
    27  import org.apache.struts.util.MessageResources;
    28  
    29  import javax.servlet.jsp.JspException;
    30  import javax.servlet.jsp.tagext.BodyTagSupport;
    31  
    32  import java.util.Iterator;
    33  
    34  /**
    35   * Custom tag that iterates the elements of a message collection. It defaults
    36   * to retrieving the messages from <code>Globals.ERROR_KEY</code>, but if the
    37   * message attribute is set to true then the messages will be retrieved from
    38   * <code>Globals.MESSAGE_KEY</code>. This is an alternative to the default
    39   * <code>ErrorsTag</code>.
    40   *
    41   * @version $Rev: 471754 $ $Date: 2005-11-08 23:50:53 -0500 (Tue, 08 Nov 2005)
    42   *          $
    43   * @since Struts 1.1
    44   */
    45  public class MessagesTag extends BodyTagSupport {
    46      /**
    47       * The message resources for this package.
    48       */
    49      protected static MessageResources messageResources =
    50          MessageResources.getMessageResources(Constants.Package
    51              + ".LocalStrings");
    52  
    53      /**
    54       * Iterator of the elements of this error collection, while we are
    55       * actually running.
    56       */
    57      protected Iterator iterator = null;
    58  
    59      /**
    60       * Whether or not any error messages have been processed.
    61       */
    62      protected boolean processed = false;
    63  
    64      /**
    65       * The name of the scripting variable to be exposed.
    66       */
    67      protected String id = null;
    68  
    69      /**
    70       * The servlet context attribute key for our resources.
    71       */
    72      protected String bundle = null;
    73  
    74      /**
    75       * The session attribute key for our locale.
    76       */
    77      protected String locale = Globals.LOCALE_KEY;
    78  
    79      /**
    80       * The request attribute key for our error messages (if any).
    81       */
    82      protected String name = Globals.ERROR_KEY;
    83  
    84      /**
    85       * The name of the property for which error messages should be returned,
    86       * or <code>null</code> to return all errors.
    87       */
    88      protected String property = null;
    89  
    90      /**
    91       * The message resource key for errors header.
    92       */
    93      protected String header = null;
    94  
    95      /**
    96       * The message resource key for errors footer.
    97       */
    98      protected String footer = null;
    99  
    100     /**
    101      * If this is set to 'true', then the <code>Globals.MESSAGE_KEY</code>
    102      * will be used to retrieve the messages from scope.
    103      */
    104     protected String message = null;
    105 
    106     public String getId() {
    107         return (this.id);
    108     }
    109 
    110     public void setId(String id) {
    111         this.id = id;
    112     }
    113 
    114     public String getBundle() {
    115         return (this.bundle);
    116     }
    117 
    118     public void setBundle(String bundle) {
    119         this.bundle = bundle;
    120     }
    121 
    122     public String getLocale() {
    123         return (this.locale);
    124     }
    125 
    126     public void setLocale(String locale) {
    127         this.locale = locale;
    128     }
    129 
    130     public String getName() {
    131         return (this.name);
    132     }
    133 
    134     public void setName(String name) {
    135         this.name = name;
    136     }
    137 
    138     public String getProperty() {
    139         return (this.property);
    140     }
    141 
    142     public void setProperty(String property) {
    143         this.property = property;
    144     }
    145 
    146     public String getHeader() {
    147         return (this.header);
    148     }
    149 
    150     public void setHeader(String header) {
    151         this.header = header;
    152     }
    153 
    154     public String getFooter() {
    155         return (this.footer);
    156     }
    157 
    158     public void setFooter(String footer) {
    159         this.footer = footer;
    160     }
    161 
    162     public String getMessage() {
    163         return (this.message);
    164     }
    165 
    166     public void setMessage(String message) {
    167         this.message = message;
    168     }
    169 
    170     /**
    171      * Construct an iterator for the specified collection, and begin looping
    172      * through the body once per element.
    173      *
    174      * @throws JspException if a JSP exception has occurred
    175      */
    176     public int doStartTag() throws JspException {
    177         // Initialize for a new request.
    178         processed = false;
    179 
    180         // Were any messages specified?
    181         ActionMessages messages = null;
    182 
    183         // Make a local copy of the name attribute that we can modify.
    184         String name = this.name;
    185 
    186         if ((message != null) && "true".equalsIgnoreCase(message)) {
    187             name = Globals.MESSAGE_KEY;
    188         }
    189 
    190         try {
    191             messages =
    192                 TagUtils.getInstance().getActionMessages(pageContext, name);
    193         } catch (JspException e) {
    194             TagUtils.getInstance().saveException(pageContext, e);
    195             throw e;
    196         }
    197 
    198         // Acquire the collection we are going to iterate over
    199         this.iterator =
    200             (property == null) ? messages.get() : messages.get(property);
    201 
    202         // Store the first value and evaluate, or skip the body if none
    203         if (!this.iterator.hasNext()) {
    204             return SKIP_BODY;
    205         }
    206 
    207         // process the first message
    208         processMessage((ActionMessage) iterator.next());
    209 
    210         if ((header != null) && (header.length() > 0)) {
    211             String headerMessage =
    212                 TagUtils.getInstance().message(pageContext, bundle, locale,
    213                     header);
    214 
    215             if (headerMessage != null) {
    216                 TagUtils.getInstance().write(pageContext, headerMessage);
    217             }
    218         }
    219 
    220         // Set the processed variable to true so the
    221         // doEndTag() knows processing took place
    222         processed = true;
    223 
    224         return (EVAL_BODY_TAG);
    225     }
    226 
    227     /**
    228      * Make the next collection element available and loop, or finish the
    229      * iterations if there are no more elements.
    230      *
    231      * @throws JspException if a JSP exception has occurred
    232      */
    233     public int doAfterBody() throws JspException {
    234         // Render the output from this iteration to the output stream
    235         if (bodyContent != null) {
    236             TagUtils.getInstance().writePrevious(pageContext,
    237                 bodyContent.getString());
    238             bodyContent.clearBody();
    239         }
    240 
    241         // Decide whether to iterate or quit
    242         if (iterator.hasNext()) {
    243             processMessage((ActionMessage) iterator.next());
    244 
    245             return (EVAL_BODY_TAG);
    246         } else {
    247             return (SKIP_BODY);
    248         }
    249     }
    250 
    251     /**
    252      * Process a message.
    253      */
    254     private void processMessage(ActionMessage report)
    255         throws JspException {
    256         String msg = null;
    257 
    258         if (report.isResource()) {
    259             msg = TagUtils.getInstance().message(pageContext, bundle, locale,
    260                     report.getKey(), report.getValues());
    261 
    262             if (msg == null) {
    263                 String bundleName = (bundle == null) ? "default" : bundle;
    264 
    265                 msg = messageResources.getMessage("messagesTag.notfound",
    266                         report.getKey(), bundleName);
    267             }
    268         } else {
    269             msg = report.getKey();
    270         }
    271 
    272         if (msg == null) {
    273             pageContext.removeAttribute(id);
    274         } else {
    275             pageContext.setAttribute(id, msg);
    276         }
    277     }
    278 
    279     /**
    280      * Clean up after processing this enumeration.
    281      *
    282      * @throws JspException if a JSP exception has occurred
    283      */
    284     public int doEndTag() throws JspException {
    285         if (processed && (footer != null) && (footer.length() > 0)) {
    286             String footerMessage =
    287                 TagUtils.getInstance().message(pageContext, bundle, locale,
    288                     footer);
    289 
    290             if (footerMessage != null) {
    291                 TagUtils.getInstance().write(pageContext, footerMessage);
    292             }
    293         }
    294 
    295         return EVAL_PAGE;
    296     }
    297 
    298     /**
    299      * Release all allocated resources.
    300      */
    301     public void release() {
    302         super.release();
    303         iterator = null;
    304         processed = false;
    305         id = null;
    306         bundle = null;
    307         locale = Globals.LOCALE_KEY;
    308         name = Globals.ERROR_KEY;
    309         property = null;
    310         header = null;
    311         footer = null;
    312         message = null;
    313     }
    314 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
