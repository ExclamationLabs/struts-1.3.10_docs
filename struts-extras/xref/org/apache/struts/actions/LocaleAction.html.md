[View Javadoc](../../../../../apidocs/org/apache/struts/actions/LocaleAction.html.md)


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
    21  package org.apache.struts.actions;
    22  
    23  import org.apache.commons.beanutils.PropertyUtils;
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.struts.Globals;
    27  import org.apache.struts.action.ActionForm;
    28  import org.apache.struts.action.ActionForward;
    29  import org.apache.struts.action.ActionMapping;
    30  
    31  import javax.servlet.http.HttpServletRequest;
    32  import javax.servlet.http.HttpServletResponse;
    33  import javax.servlet.http.HttpSession;
    34  
    35  import java.util.Locale;
    36  
    37  /**
    38   * Implementation of <strong>Action</strong> that changes the user's {@link
    39   * java.util.Locale} and forwards to a page, based on request level parameters
    40   * that are set  (language, country, &amp; page).
    41   */
    42  public final class LocaleAction extends BaseAction {
    43      /**
    44       * Commons Logging instance.
    45       */
    46      private Log log =
    47          LogFactory.getFactory().getInstance(this.getClass().getName());
    48  
    49      /**
    50       * <p> Change the user's {@link java.util.Locale} based on {@link
    51       * ActionForm} properties. </p> <p> This <code>Action</code> looks for
    52       * <code>language</code> and <code>country</code> properties on the given
    53       * form, constructs an appropriate Locale object, and sets it as the
    54       * Struts Locale for this user's session. Any <code>ActionForm</code>,
    55       * including a {@link org.apache.struts.action.DynaActionForm}, may be
    56       * used. </p> <p> If a <code>page</code> property is also provided, then
    57       * after setting the Locale, control is forwarded to that URI path.
    58       * Otherwise, control is forwarded to "success". </p>
    59       *
    60       * @param mapping  The ActionMapping used to select this instance
    61       * @param form     The optional ActionForm bean for this request (if any)
    62       * @param request  The HTTP request we are processing
    63       * @param response The HTTP response we are creating
    64       * @return Action to forward to
    65       * @throws Exception if an input/output error or servlet exception occurs
    66       */
    67      public ActionForward execute(ActionMapping mapping, ActionForm form,
    68          HttpServletRequest request, HttpServletResponse response)
    69          throws Exception {
    70          // Extract attributes we will need
    71          HttpSession session = request.getSession();
    72          Locale locale = getLocale(request);
    73  
    74          String language = null;
    75          String country = null;
    76          String page = null;
    77  
    78          try {
    79              language =
    80                  (String) PropertyUtils.getSimpleProperty(form, "language");
    81              country = (String) PropertyUtils.getSimpleProperty(form, "country");
    82              page = (String) PropertyUtils.getSimpleProperty(form, "page");
    83          } catch (Exception e) {
    84              log.error(e.getMessage(), e);
    85          }
    86  
    87          boolean isLanguage = ((language != null) && (language.length() > 0));
    88          boolean isCountry = ((country != null) && (country.length() > 0));
    89  
    90          if ((isLanguage) && (isCountry)) {
    91              locale = new java.util.Locale(language, country);
    92          } else if (isLanguage) {
    93              locale = new java.util.Locale(language, "");
    94          }
    95  
    96          session.setAttribute(Globals.LOCALE_KEY, locale);
    97  
    98          if (null == page) {
    99              return mapping.findForward("success");
    100         } else {
    101             return new ActionForward(page);
    102         }
    103     }
    104 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
