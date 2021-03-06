[View Javadoc](../../../../../../../apidocs/org/apache/struts/chain/commands/servlet/ExecuteAction.html.md)


    1   /*
    2    * $Id: ExecuteAction.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.action.Action;
    24  import org.apache.struts.action.ActionForm;
    25  import org.apache.struts.action.ActionMapping;
    26  import org.apache.struts.chain.commands.AbstractExecuteAction;
    27  import org.apache.struts.chain.contexts.ActionContext;
    28  import org.apache.struts.chain.contexts.ServletActionContext;
    29  import org.apache.struts.config.ActionConfig;
    30  import org.apache.struts.config.ForwardConfig;
    31  
    32  /**
    33   * <p>Invoke the appropriate <code>Action</code> for this request, and cache
    34   * the returned <code>ActionForward</code>.</p>
    35   *
    36   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    37   *          $
    38   */
    39  public class ExecuteAction extends AbstractExecuteAction {
    40      // ------------------------------------------------------- Protected Methods
    41  
    42      /**
    43       * <p>Execute the specified <code>Action</code>, and return the resulting
    44       * <code>ActionForward</code>.</p>
    45       *
    46       * @param context      The <code>Context</code> for this request
    47       * @param action       The <code>Action</code> to be executed
    48       * @param actionConfig The <code>ActionConfig</code> defining this action
    49       * @param actionForm   The <code>ActionForm</code> (if any) for this
    50       *                     action
    51       * @throws Exception if thrown by the <code>Action</code>
    52       */
    53      protected ForwardConfig execute(ActionContext context, Action action,
    54          ActionConfig actionConfig, ActionForm actionForm)
    55          throws Exception {
    56          ServletActionContext saContext = (ServletActionContext) context;
    57  
    58          return (action.execute((ActionMapping) actionConfig, actionForm,
    59              saContext.getRequest(), saContext.getResponse()));
    60      }
    61  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
