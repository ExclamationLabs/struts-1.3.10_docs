[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/validator/EditTypeAction.html.md)


    1   /*
    2    * $Id: EditTypeAction.java 471754 2006-11-06 14:55:09Z husted $
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
    26  
    27  import java.util.ArrayList;
    28  import org.apache.commons.logging.Log;
    29  import org.apache.commons.logging.LogFactory;
    30  import org.apache.struts.action.Action;
    31  import org.apache.struts.action.ActionForm;
    32  import org.apache.struts.action.ActionForward;
    33  import org.apache.struts.action.ActionMapping;
    34  import org.apache.struts.util.LabelValueBean;
    35  
    36  /**
    37   * Initializes ActionForm.
    38   *
    39   */
    40  public final class EditTypeAction extends Action {
    41  
    42      /**
    43       * Commons Logging instance.
    44       */
    45      private Log log = LogFactory.getFactory().getInstance(this.getClass().getName());
    46  
    47      /**
    48       * Process the specified HTTP request, and create the corresponding HTTP
    49       * response (or forward to another web component that will create it).
    50       * Return an <code>ActionForward</code> instance describing where and how
    51       * control should be forwarded, or <code>null</code> if the response has
    52       * already been completed.
    53       *
    54       * @param mapping The ActionMapping used to select this instance
    55       * @param form The optional ActionForm bean for this request (if any)
    56       * @param request The HTTP request we are processing
    57       * @param response The HTTP response we are creating
    58       *
    59       * @return Action to forward to
    60       * @exception Exception if an input/output error or servlet exception occurs
    61       */
    62      public ActionForward execute(
    63              ActionMapping mapping,
    64              ActionForm form,
    65              HttpServletRequest request,
    66              HttpServletResponse response)
    67              throws Exception {
    68  
    69          // Was this transaction cancelled?
    70  
    71          initFormBeans(mapping, form, request);
    72  
    73          return mapping.findForward("success");
    74      }
    75  
    76      /**
    77       * Convenience method for initializing form bean.
    78       * @param mapping The ActionMapping used to select this instance
    79       * @param request The HTTP request we are processing
    80       */
    81      protected void initFormBeans(
    82              ActionMapping mapping, ActionForm form,
    83              HttpServletRequest request) {
    84  
    85          log.debug("initFromBeans");
    86  
    87          // Initialize
    88          ArrayList satisfactionList = new ArrayList();
    89          satisfactionList.add(new LabelValueBean("Very Satisfied", "4"));
    90          satisfactionList.add(new LabelValueBean("Satisfied", "3"));
    91          satisfactionList.add(new LabelValueBean("Not Very Satisfied", "2"));
    92          satisfactionList.add(new LabelValueBean("Not Satisfied", "1"));
    93          request.setAttribute("satisfactionList", satisfactionList);
    94  
    95          ArrayList osTypes = new ArrayList();
    96          osTypes.add(new LabelValueBean("Mac OsX", "OsX"));
    97          osTypes.add(new LabelValueBean("Windows 95/98/Me", "Win32"));
    98          osTypes.add(new LabelValueBean("Windows NT/2000/XP/2003", "WinNT"));
    99          osTypes.add(new LabelValueBean("Linux", "Linux"));
    100         osTypes.add(new LabelValueBean("BSD NetBSD/FreeBSD/OpenBSD", "BSD"));
    101         request.setAttribute("osTypes", osTypes);
    102 
    103         ArrayList languageTypes = new ArrayList();
    104         languageTypes.add(new LabelValueBean("C++", "C++"));
    105         languageTypes.add(new LabelValueBean("C#", "C#"));
    106         languageTypes.add(new LabelValueBean("Java", "java"));
    107         languageTypes.add(new LabelValueBean("Smalltalk", "Smalltalk"));
    108         request.setAttribute("languageTypes", languageTypes);
    109     }
    110 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
