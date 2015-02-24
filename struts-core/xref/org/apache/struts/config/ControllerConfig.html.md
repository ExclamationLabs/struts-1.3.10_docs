[View Javadoc](../../../../../apidocs/org/apache/struts/config/ControllerConfig.html.md)


    1   /*
    2    * $Id: ControllerConfig.java 471754 2006-11-06 14:55:09Z husted $
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
    23  
    24  /**
    25   * <p>A JavaBean representing the configuration information of a
    26   * <code>&lt;controller&gt;</code> element in a Struts configuration
    27   * file.</p>
    28   *
    29   * @version $Rev: 471754 $ $Date: 2005-05-12 18:41:19 -0400 (Thu, 12 May 2005)
    30   *          $
    31   * @since Struts 1.1
    32   */
    33  public class ControllerConfig extends BaseConfig {
    34      // ------------------------------------------------------------- Properties
    35  
    36      /**
    37       * <p> The input buffer size for file uploads. </p>
    38       */
    39      protected int bufferSize = 4096;
    40  
    41      /**
    42       * <p> The content type and character encoding to be set on each response.
    43       * </p>
    44       */
    45      protected String contentType = "text.html.md";
    46  
    47      /**
    48       * <p> The chain catalog name for this module. </p>
    49       */
    50      protected String catalog = "struts";
    51  
    52      /**
    53       * <p> The chain command to execute for each request. </p>
    54       */
    55      protected String command = "servlet-standard";
    56  
    57      /**
    58       * <p>The replacement pattern used to determine a context-relative URL
    59       * from a {@link ForwardConfig} element.  The pattern may consist of any
    60       * combination of the following markers and characters:</p>
    61       *
    62       * <ul>
    63       *
    64       * <li><code><strong>$M</strong></code> - Replaced by the module prefix
    65       * for the current module.</li>
    66       *
    67       * <li><code><strong>$P</strong></code> - Replaced by the
    68       * <code>path</code> property of a {@link ForwardConfig} instance.</li>
    69       *
    70       * <li><code><strong>$$</strong></code> - Renders a literal dollar sign
    71       * ("$") character in the resulting URL.</li>
    72       *
    73       * <li>A dollar sign followed by any other character is reserved for
    74       * future use, and both characters are silently swallowed.</li>
    75       *
    76       * <li>All other characters in the pattern are passed through unchanged.
    77       * </li>
    78       *
    79       * </ul>
    80       *
    81       * <p>If this property is set to <code>null</code>, a default pattern of
    82       * <code>$M$P</code> is utilized, which is backwards compatible with the
    83       * hard coded functionality in prior versions.</p>
    84       */
    85      protected String forwardPattern = null;
    86  
    87      /**
    88       * <p>Should the <code>input</code> property of {@link ActionConfig}
    89       * instances associated with this module be treated as the name of a
    90       * corresponding {@link ForwardConfig}.  A <code>false</code> value treats
    91       * them as a module-relative path (consistent with the hard coded behavior
    92       * of earlier versions of Struts.</p>
    93       *
    94       * @since Struts 1.1
    95       */
    96      protected boolean inputForward = false;
    97  
    98      /**
    99       * <p> Should we store a Locale object in the user's session if needed?
    100      * </p>
    101      */
    102     protected boolean locale = true;
    103 
    104     /**
    105      * <p> The maximum file size to process for file uploads. </p>
    106      */
    107     protected String maxFileSize = "250M";
    108 
    109     /**
    110      * <p> The maximum file size to retain in memory. </p>
    111      */
    112     protected String memFileSize = "256K";
    113 
    114     /**
    115      * <p> The fully qualified Java class name of the MultipartRequestHandler
    116      * class to be used. </p>
    117      */
    118     protected String multipartClass =
    119         "org.apache.struts.upload.CommonsMultipartRequestHandler";
    120 
    121     /**
    122      * <p> Should we set no-cache HTTP headers on each response? </p>
    123      */
    124     protected boolean nocache = false;
    125 
    126     /**
    127      * <p>The replacement pattern used to determine a context-relative URL
    128      * from the <code>page</code> attribute of Struts tags and configuration
    129      * properties.  The pattern may consist of any combination of the
    130      * following markers and characters:</p>
    131      *
    132      * <ul>
    133      *
    134      * <li><code><strong>$M</strong></code> - Replaced by the module prefix
    135      * for the current module.</li>
    136      *
    137      * <li><code><strong>$P</strong></code> - Replaced by the
    138      * <code>page</code> attribute value being evaluated.</li>
    139      *
    140      * <li><code><strong>$$</strong></code> - Renders a literal dollar sign
    141      * ("$") character in the resulting URL.</li>
    142      *
    143      * <li>A dollar sign followed by any other character is reserved for
    144      * future use, and both characters are silently swallowed.</li>
    145      *
    146      * <li>All other characters in the pattern are passed through unchanged.
    147      * </li>
    148      *
    149      * </ul>
    150      *
    151      * <p>If this property is set to <code>null</code>, a default pattern of
    152      * <code>$M$P</code> is utilized, which is backwards compatible with the
    153      * hard coded functionality in prior versions.</p>
    154      */
    155     protected String pagePattern = null;
    156 
    157     /**
    158      * <p> The fully qualified class name of the RequestProcessor
    159      * implementation class to be used for this module. </p>
    160      */
    161     protected String processorClass =
    162         "org.apache.struts.chain.ComposableRequestProcessor";
    163 
    164     /**
    165      * <p> The temporary working directory to use for file uploads. </p>
    166      */
    167     protected String tempDir = null;
    168 
    169     public int getBufferSize() {
    170         return (this.bufferSize);
    171     }
    172 
    173     public void setBufferSize(int bufferSize) {
    174         if (configured) {
    175             throw new IllegalStateException("Configuration is frozen");
    176         }
    177 
    178         this.bufferSize = bufferSize;
    179     }
    180 
    181     public String getContentType() {
    182         return (this.contentType);
    183     }
    184 
    185     public void setContentType(String contentType) {
    186         if (configured) {
    187             throw new IllegalStateException("Configuration is frozen");
    188         }
    189 
    190         this.contentType = contentType;
    191     }
    192 
    193     public String getCatalog() {
    194         return (this.catalog);
    195     }
    196 
    197     public void setCatalog(String catalog) {
    198         if (configured) {
    199             throw new IllegalStateException("Configuration is frozen");
    200         }
    201 
    202         this.catalog = catalog;
    203     }
    204 
    205     public String getCommand() {
    206         return (this.command);
    207     }
    208 
    209     public void setCommand(String command) {
    210         if (configured) {
    211             throw new IllegalStateException("Configuration is frozen");
    212         }
    213 
    214         this.command = command;
    215     }
    216 
    217     public String getForwardPattern() {
    218         return (this.forwardPattern);
    219     }
    220 
    221     public void setForwardPattern(String forwardPattern) {
    222         this.forwardPattern = forwardPattern;
    223     }
    224 
    225     public boolean getInputForward() {
    226         return (this.inputForward);
    227     }
    228 
    229     public void setInputForward(boolean inputForward) {
    230         this.inputForward = inputForward;
    231     }
    232 
    233     public boolean getLocale() {
    234         return (this.locale);
    235     }
    236 
    237     public void setLocale(boolean locale) {
    238         if (configured) {
    239             throw new IllegalStateException("Configuration is frozen");
    240         }
    241 
    242         this.locale = locale;
    243     }
    244 
    245     public String getMaxFileSize() {
    246         return (this.maxFileSize);
    247     }
    248 
    249     public void setMaxFileSize(String maxFileSize) {
    250         if (configured) {
    251             throw new IllegalStateException("Configuration is frozen");
    252         }
    253 
    254         this.maxFileSize = maxFileSize;
    255     }
    256 
    257     public String getMemFileSize() {
    258         return (this.memFileSize);
    259     }
    260 
    261     public void setMemFileSize(String memFileSize) {
    262         if (configured) {
    263             throw new IllegalStateException("Configuration is frozen");
    264         }
    265 
    266         this.memFileSize = memFileSize;
    267     }
    268 
    269     public String getMultipartClass() {
    270         return (this.multipartClass);
    271     }
    272 
    273     public void setMultipartClass(String multipartClass) {
    274         if (configured) {
    275             throw new IllegalStateException("Configuration is frozen");
    276         }
    277 
    278         this.multipartClass = multipartClass;
    279     }
    280 
    281     public boolean getNocache() {
    282         return (this.nocache);
    283     }
    284 
    285     public void setNocache(boolean nocache) {
    286         if (configured) {
    287             throw new IllegalStateException("Configuration is frozen");
    288         }
    289 
    290         this.nocache = nocache;
    291     }
    292 
    293     public String getPagePattern() {
    294         return (this.pagePattern);
    295     }
    296 
    297     public void setPagePattern(String pagePattern) {
    298         this.pagePattern = pagePattern;
    299     }
    300 
    301     public String getProcessorClass() {
    302         return (this.processorClass);
    303     }
    304 
    305     public void setProcessorClass(String processorClass) {
    306         if (configured) {
    307             throw new IllegalStateException("Configuration is frozen");
    308         }
    309 
    310         this.processorClass = processorClass;
    311     }
    312 
    313     public String getTempDir() {
    314         return (this.tempDir);
    315     }
    316 
    317     public void setTempDir(String tempDir) {
    318         if (configured) {
    319             throw new IllegalStateException("Configuration is frozen");
    320         }
    321 
    322         this.tempDir = tempDir;
    323     }
    324 
    325     // --------------------------------------------------------- Public Methods
    326 
    327     /**
    328      * <p> Return a String representation of this object. </p>
    329      */
    330     public String toString() {
    331         StringBuffer sb = new StringBuffer("ControllerConfig[");
    332 
    333         sb.append("bufferSize=");
    334         sb.append(this.bufferSize);
    335 
    336         if (this.contentType != null) {
    337             sb.append(",contentType=");
    338             sb.append(this.contentType);
    339         }
    340 
    341         if (this.forwardPattern != null) {
    342             sb.append(",forwardPattern=");
    343             sb.append(this.forwardPattern);
    344         }
    345 
    346         sb.append(",inputForward=");
    347         sb.append(this.inputForward);
    348         sb.append(",locale=");
    349         sb.append(this.locale);
    350 
    351         if (this.maxFileSize != null) {
    352             sb.append(",maxFileSize=");
    353             sb.append(this.maxFileSize);
    354         }
    355 
    356         if (this.memFileSize != null) {
    357             sb.append(",memFileSize=");
    358             sb.append(this.memFileSize);
    359         }
    360 
    361         sb.append(",multipartClass=");
    362         sb.append(this.multipartClass);
    363         sb.append(",nocache=");
    364         sb.append(this.nocache);
    365 
    366         if (this.pagePattern != null) {
    367             sb.append(",pagePattern=");
    368             sb.append(this.pagePattern);
    369         }
    370 
    371         sb.append(",processorClass=");
    372         sb.append(this.processorClass);
    373 
    374         if (this.tempDir != null) {
    375             sb.append(",tempDir=");
    376             sb.append(this.tempDir);
    377         }
    378 
    379         sb.append("]");
    380 
    381         return (sb.toString());
    382     }
    383 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
