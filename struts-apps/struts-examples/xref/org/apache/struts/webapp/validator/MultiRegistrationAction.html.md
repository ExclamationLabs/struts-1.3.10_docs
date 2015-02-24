[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/validator/MultiRegistrationAction.html.md)


    1   /*
    2    * $Id: MultiRegistrationAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.webapp.validator;
    23  
    24  import javax.servlet.http.HttpServletRequest;
    25  import javax.servlet.http.HttpServletResponse;
    26  import javax.servlet.http.HttpSession;
    27  
    28  import org.apache.commons.logging.Log;
    29  import org.apache.commons.logging.LogFactory;
    30  import org.apache.struts.action.Action;
    31  import org.apache.struts.action.ActionForm;
    32  import org.apache.struts.action.ActionForward;
    33  import org.apache.struts.action.ActionMapping;
    34  import org.apache.struts.action.ActionMessages;
    35  
    36  /**
    37   * Implementation of <strong>Action</strong> that validates a multi-page
    38   * registration form.
    39   *
    40   */
    41  public final class MultiRegistrationAction extends Action {
    42  
    43      /**
    44       * Commons Logging instance.
    45       */
    46      private Log log = LogFactory.getFactory().getInstance(this.getClass().getName());
    47  
    48      /**
    49       * Process the specified HTTP request, and create the corresponding HTTP
    50       * response (or forward to another web component that will create it).
    51       * Return an <code>ActionForward</code> instance describing where and how
    52       * control should be forwarded, or <code>null</code> if the response has
    53       * already been completed.
    54       *
    55       * @param mapping The ActionMapping used to select this instance
    56       * @param form The optional ActionForm bean for this request (if any)
    57       * @param request The HTTP request we are processing
    58       * @param response The HTTP response we are creating
    59       *
    60       * @exception Exception if an input/output error or servlet exception occurs
    61       */
    62      public ActionForward execute(
    63          ActionMapping mapping,
    64          ActionForm form,
    65          HttpServletRequest request,
    66          HttpServletResponse response)
    67          throws Exception {
    68  
    69          // Extract attributes we will need
    70          RegistrationForm info = (RegistrationForm) form;
    71  
    72  
    73          // Was this transaction cancelled?
    74          if (isCancelled(request)) {
    75              if (log.isInfoEnabled()) {
    76                  log.info(
    77                      " "
    78                          + mapping.getAttribute()
    79                          + " - Registration transaction was cancelled");
    80              }
    81  
    82              removeFormBean(mapping, request);
    83  
    84              return mapping.findForward("success");
    85          }
    86  
    87          ActionMessages errors = info.validate(mapping, request);
    88  
    89          if (errors != null && errors.isEmpty()) {
    90              if (info.getPage() == 1)
    91                  return mapping.findForward("input2");
    92  
    93              if (info.getPage() == 2)
    94                  return mapping.findForward("success");
    95  
    96          } else {
    97              this.saveErrors(request, errors);
    98  
    99              if (info.getPage() == 1){
    100                 return mapping.findForward("input" + info.getPage());
    101             }
    102 
    103             if (info.getPage() == 2){
    104                 return mapping.findForward("input" + info.getPage());
    105             }
    106         }
    107 
    108         return mapping.findForward("input1");
    109     }
    110 
    111     /**
    112      * Convenience method for removing the obsolete form bean.
    113      *
    114      * @param mapping The ActionMapping used to select this instance
    115      * @param request The HTTP request we are processing
    116      */
    117     protected void removeFormBean(
    118         ActionMapping mapping,
    119         HttpServletRequest request) {
    120 
    121         // Remove the obsolete form bean
    122         if (mapping.getAttribute() != null) {
    123             if ("request".equals(mapping.getScope())) {
    124                 request.removeAttribute(mapping.getAttribute());
    125             } else {
    126                 HttpSession session = request.getSession();
    127                 session.removeAttribute(mapping.getAttribute());
    128             }
    129         }
    130     }
    131 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
