[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/ResourceTag.html.md)


    1   /*
    2    * $Id: ResourceTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.MessageResources;
    25  
    26  import javax.servlet.jsp.JspException;
    27  import javax.servlet.jsp.tagext.TagSupport;
    28  
    29  import java.io.IOException;
    30  import java.io.InputStream;
    31  import java.io.InputStreamReader;
    32  
    33  /**
    34   * Define a scripting variable based on the contents of the specified web
    35   * application resource.
    36   *
    37   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    38   *          $
    39   */
    40  public class ResourceTag extends TagSupport {
    41      // ------------------------------------------------------------- Properties
    42  
    43      /**
    44       * Buffer size to use when reading the input stream.
    45       */
    46      protected static final int BUFFER_SIZE = 256;
    47  
    48      /**
    49       * The message resources for this package.
    50       */
    51      protected static MessageResources messages =
    52          MessageResources.getMessageResources(
    53              "org.apache.struts.taglib.bean.LocalStrings");
    54  
    55      /**
    56       * The name of the scripting variable that will be exposed as a page scope
    57       * attribute.
    58       */
    59      protected String id = null;
    60  
    61      /**
    62       * Return an InputStream to the specified resource if this is non-null.
    63       */
    64      protected String input = null;
    65  
    66      /**
    67       * The module-relative URI of the resource whose contents are to be
    68       * exposed.
    69       */
    70      protected String name = null;
    71  
    72      public String getId() {
    73          return (this.id);
    74      }
    75  
    76      public void setId(String id) {
    77          this.id = id;
    78      }
    79  
    80      public String getInput() {
    81          return (this.input);
    82      }
    83  
    84      public void setInput(String input) {
    85          this.input = input;
    86      }
    87  
    88      public String getName() {
    89          return (this.name);
    90      }
    91  
    92      public void setName(String name) {
    93          this.name = name;
    94      }
    95  
    96      // --------------------------------------------------------- Public Methods
    97  
    98      /**
    99       * Retrieve the required property and expose it as a scripting variable.
    100      *
    101      * @throws JspException if a JSP exception has occurred
    102      */
    103     public int doStartTag() throws JspException {
    104         // Acquire an input stream to the specified resource
    105         InputStream stream =
    106             pageContext.getServletContext().getResourceAsStream(name);
    107 
    108         if (stream == null) {
    109             JspException e =
    110                 new JspException(messages.getMessage("resource.get", name));
    111 
    112             TagUtils.getInstance().saveException(pageContext, e);
    113             throw e;
    114         }
    115 
    116         // If we are returning an InputStream, do so and return
    117         if (input != null) {
    118             pageContext.setAttribute(id, stream);
    119 
    120             return (SKIP_BODY);
    121         }
    122 
    123         // Accumulate the contents of this resource into a StringBuffer
    124         try {
    125             StringBuffer sb = new StringBuffer();
    126             InputStreamReader reader = new InputStreamReader(stream);
    127             char[] buffer = new char[BUFFER_SIZE];
    128             int n = 0;
    129 
    130             while (true) {
    131                 n = reader.read(buffer);
    132 
    133                 if (n < 1) {
    134                     break;
    135                 }
    136 
    137                 sb.append(buffer, 0, n);
    138             }
    139 
    140             reader.close();
    141             pageContext.setAttribute(id, sb.toString());
    142         } catch (IOException e) {
    143             TagUtils.getInstance().saveException(pageContext, e);
    144             throw new JspException(messages.getMessage("resource.get", name));
    145         }
    146 
    147         return (SKIP_BODY);
    148     }
    149 
    150     /**
    151      * Release all allocated resources.
    152      */
    153     public void release() {
    154         super.release();
    155         id = null;
    156         input = null;
    157         name = null;
    158     }
    159 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
