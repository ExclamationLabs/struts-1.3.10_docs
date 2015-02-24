[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/validator/LocaleAction.html.md)


    1   /*
    2    * $Id: LocaleAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  
    23  package org.apache.struts.webapp.validator;
    24  
    25  import java.util.Locale;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.http.HttpServletResponse;
    29  import javax.servlet.http.HttpSession;
    30  
    31  import org.apache.commons.beanutils.PropertyUtils;
    32  import org.apache.commons.logging.Log;
    33  import org.apache.commons.logging.LogFactory;
    34  import org.apache.struts.Globals;
    35  import org.apache.struts.action.Action;
    36  import org.apache.struts.action.ActionForm;
    37  import org.apache.struts.action.ActionForward;
    38  import org.apache.struts.action.ActionMapping;
    39  
    40  
    41  /**
    42   * Implementation of <strong>Action</strong> that changes the user's
    43   * {@link java.util.Locale} and forwards to a page, based on request level
    44   * parameters that are set  (language, country, &amp; page).
    45   *
    46  */
    47  public final class LocaleAction extends Action {
    48  
    49      /**
    50       * Commons Logging instance.
    51      */
    52      private Log log = LogFactory.getFactory().getInstance(this.getClass().getName());
    53  
    54      /**
    55       * <p>
    56       * Change the user's {@link java.util.Locale} based on {@link ActionForm}
    57       * properties.
    58       * </p>
    59       * <p>
    60       * This <code>Action</code> looks for <code>language</code> and
    61       * <code>country</code> properties on the given form, constructs an
    62       * appropriate Locale object, and sets it as the Struts Locale for this
    63       * user's session.
    64       * Any <code>ActionForm, including a {@link DynaActionForm}, may be used.
    65       * </p>
    66       * <p>
    67       * If a <code>page</code> property is also provided, then after
    68       * setting the Locale, control is forwarded to that URI path.
    69       * Otherwise, control is forwarded to "success".
    70       * </p>
    71       *
    72       * @param mapping The ActionMapping used to select this instance
    73       * @param form The optional ActionForm bean for this request (if any)
    74       * @param request The HTTP request we are processing
    75       * @param response The HTTP response we are creating
    76       *
    77       * @return Action to forward to
    78       * @exception java.lang.Exception if an input/output error or servlet exception occurs
    79       */
    80      public ActionForward execute(ActionMapping mapping,
    81                   ActionForm form,
    82                   HttpServletRequest request,
    83                   HttpServletResponse response)
    84      throws Exception {
    85  
    86      // Extract attributes we will need
    87      HttpSession session = request.getSession();
    88      Locale locale = getLocale(request);
    89  
    90      String language = null;
    91      String country = null;
    92      String page = null;
    93  
    94      try {
    95              language = (String)
    96                PropertyUtils.getSimpleProperty(form, "language");
    97              country = (String)
    98                PropertyUtils.getSimpleProperty(form, "country");
    99              page = (String)
    100               PropertyUtils.getSimpleProperty(form, "page");
    101         } catch (Exception e) {
    102            log.error(e.getMessage(), e);
    103         }
    104 
    105         if ((language != null && language.length() > 0) &&
    106             (country != null && country.length() > 0)) {
    107            locale = new java.util.Locale(language, country);
    108         } else if (language != null && language.length() > 0) {
    109            locale = new java.util.Locale(language, "");
    110     }
    111 
    112         session.setAttribute(Globals.LOCALE_KEY, locale);
    113 
    114         if (null==page) return mapping.findForward("success");
    115         else return new ActionForward(page);
    116 
    117     }
    118 
    119 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
