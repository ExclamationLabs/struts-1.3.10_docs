[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/StrutsTag.html.md)


    1   /*
    2    * $Id: StrutsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.config.ModuleConfig;
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.MessageResources;
    26  
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  /**
    31   * Define a scripting variable that exposes the requested Struts internal
    32   * configuraton object.
    33   *
    34   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    35   *          $
    36   */
    37  public class StrutsTag extends TagSupport {
    38      /**
    39       * The message resources for this package.
    40       */
    41      protected static MessageResources messages =
    42          MessageResources.getMessageResources(
    43              "org.apache.struts.taglib.bean.LocalStrings");
    44  
    45      // ------------------------------------------------------------- Properties
    46  
    47      /**
    48       * The name of the scripting variable that will be exposed as a page scope
    49       * attribute.
    50       */
    51      protected String id = null;
    52  
    53      /**
    54       * The name of the <code>ActionFormBean</code> object to be exposed.
    55       */
    56      protected String formBean = null;
    57  
    58      /**
    59       * The name of the <code>ActionForward</code> object to be exposed.
    60       */
    61      protected String forward = null;
    62  
    63      /**
    64       * The name of the <code>ActionMapping</code> object to be exposed.
    65       */
    66      protected String mapping = null;
    67  
    68      public String getId() {
    69          return (this.id);
    70      }
    71  
    72      public void setId(String id) {
    73          this.id = id;
    74      }
    75  
    76      public String getFormBean() {
    77          return (this.formBean);
    78      }
    79  
    80      public void setFormBean(String formBean) {
    81          this.formBean = formBean;
    82      }
    83  
    84      public String getForward() {
    85          return (this.forward);
    86      }
    87  
    88      public void setForward(String forward) {
    89          this.forward = forward;
    90      }
    91  
    92      public String getMapping() {
    93          return (this.mapping);
    94      }
    95  
    96      public void setMapping(String mapping) {
    97          this.mapping = mapping;
    98      }
    99  
    100     // --------------------------------------------------------- Public Methods
    101 
    102     /**
    103      * Retrieve the required configuration object and expose it as a scripting
    104      * variable.
    105      *
    106      * @throws JspException if a JSP exception has occurred
    107      */
    108     public int doStartTag() throws JspException {
    109         // Validate the selector arguments
    110         int n = 0;
    111 
    112         if (formBean != null) {
    113             n++;
    114         }
    115 
    116         if (forward != null) {
    117             n++;
    118         }
    119 
    120         if (mapping != null) {
    121             n++;
    122         }
    123 
    124         if (n != 1) {
    125             JspException e =
    126                 new JspException(messages.getMessage("struts.selector"));
    127 
    128             TagUtils.getInstance().saveException(pageContext, e);
    129             throw e;
    130         }
    131 
    132         // Retrieve our module configuration information
    133         ModuleConfig config =
    134             TagUtils.getInstance().getModuleConfig(pageContext);
    135 
    136         // Retrieve the requested object to be exposed
    137         Object object = null;
    138         String selector = null;
    139 
    140         if (formBean != null) {
    141             selector = formBean;
    142             object = config.findFormBeanConfig(formBean);
    143         } else if (forward != null) {
    144             selector = forward;
    145             object = config.findForwardConfig(forward);
    146         } else if (mapping != null) {
    147             selector = mapping;
    148             object = config.findActionConfig(mapping);
    149         }
    150 
    151         if (object == null) {
    152             JspException e =
    153                 new JspException(messages.getMessage("struts.missing", selector));
    154 
    155             TagUtils.getInstance().saveException(pageContext, e);
    156             throw e;
    157         }
    158 
    159         // Expose this value as a scripting variable
    160         pageContext.setAttribute(id, object);
    161 
    162         return (SKIP_BODY);
    163     }
    164 
    165     /**
    166      * Release all allocated resources.
    167      */
    168     public void release() {
    169         super.release();
    170         id = null;
    171         formBean = null;
    172         forward = null;
    173         mapping = null;
    174     }
    175 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
