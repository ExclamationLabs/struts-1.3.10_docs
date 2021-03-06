[View Javadoc](../../../../../../../apidocs/org/apache/struts/chain/commands/servlet/ValidateActionForm.html.md)


    1   /*
    2    * $Id: ValidateActionForm.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands.servlet;
    22  
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.action.ActionErrors;
    26  import org.apache.struts.action.ActionForm;
    27  import org.apache.struts.action.ActionMapping;
    28  import org.apache.struts.chain.commands.AbstractValidateActionForm;
    29  import org.apache.struts.chain.contexts.ActionContext;
    30  import org.apache.struts.chain.contexts.ServletActionContext;
    31  import org.apache.struts.config.ActionConfig;
    32  
    33  /**
    34   * <p>Validate the properties of the form bean for this request.  If there are
    35   * any validation errors, execute the child commands in our chain; otherwise,
    36   * proceed normally.  Also, if any errors are found and the request is a
    37   * multipart request, rollback the <code>MultipartRequestHandler</code>.</p>
    38   *
    39   * @version $Rev: 471754 $ $Date: 2005-06-04 10:58:46 -0400 (Sat, 04 Jun 2005)
    40   *          $
    41   */
    42  public class ValidateActionForm extends AbstractValidateActionForm {
    43      // ------------------------------------------------------ Instance Variables
    44      private static final Log log = LogFactory.getLog(ValidateActionForm.class);
    45  
    46      // ------------------------------------------------------- Protected Methods
    47  
    48      /**
    49       * <p>Call the <code>validate()</code> method of the specified form bean,
    50       * and return the resulting <code>ActionErrors</code> object.</p>
    51       *
    52       * @param context    The context for this request
    53       * @param actionForm The form bean for this request
    54       */
    55      protected ActionErrors validate(ActionContext context,
    56          ActionConfig actionConfig, ActionForm actionForm) {
    57          ServletActionContext saContext = (ServletActionContext) context;
    58          ActionErrors errors =
    59              (actionForm.validate((ActionMapping) actionConfig,
    60                  saContext.getRequest()));
    61  
    62          // Special handling for multipart request
    63          if ((errors != null) && !errors.isEmpty()) {
    64              if (actionForm.getMultipartRequestHandler() != null) {
    65                  if (log.isTraceEnabled()) {
    66                      log.trace("  Rolling back multipart request");
    67                  }
    68  
    69                  actionForm.getMultipartRequestHandler().rollback();
    70              }
    71          }
    72  
    73          return errors;
    74      }
    75  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
