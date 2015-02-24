[View Javadoc](../../../../../../../apidocs/org/apache/struts/apps/mailreader/actions/LocaleAction.html.md)


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
    21  package org.apache.struts.apps.mailreader.actions;
    22  
    23  import org.apache.struts.Globals;
    24  import org.apache.struts.action.ActionForm;
    25  import org.apache.struts.action.ActionForward;
    26  import org.apache.struts.action.ActionMapping;
    27  
    28  import javax.servlet.http.HttpServletRequest;
    29  import javax.servlet.http.HttpServletResponse;
    30  import javax.servlet.http.HttpSession;
    31  import java.util.Locale;
    32  
    33  
    34  /**
    35   * <p>
    36   * Change user's Struts {@link java.util.Locale}.
    37   * </p>
    38   */
    39  public final class LocaleAction extends BaseAction {
    40  
    41      /**
    42       * <p>
    43       * Return true if parameter is null or trims to empty.
    44       * </p>
    45       *
    46       * @param string The string to text; may be  null
    47       * @return true if parameter is null or empty
    48       */
    49      private boolean isBlank(String string) {
    50          return ((string == null) || (string.trim().length() == 0));
    51      }
    52  
    53      /**
    54       * <p>
    55       * Parameter for {@link java.util.Locale} language property. ["language"]
    56       * </p>
    57       */
    58      private static final String LANGUAGE = "language";
    59  
    60      /**
    61       * <p>
    62       * Parameter for {@link java.util.Locale} country property. ["country"]
    63       * </p>
    64       */
    65      private static final String COUNTRY = "country";
    66  
    67      /**
    68       * <p>
    69       * Parameter for response page URI. ["page"]
    70       * </p>
    71       */
    72      private static final String PAGE = "page";
    73  
    74      /**
    75       * <p>
    76       * Parameter for response forward name. ["forward"]
    77       * </p>
    78       */
    79      private static final String FORWARD = "forward";
    80  
    81      /**
    82       * <p>
    83       * Logging message if LocaleAction is missing a target parameter.
    84       * </p>
    85       */
    86      private static final String LOCALE_LOG =
    87              "LocaleAction: Missing page or forward parameter";
    88  
    89      /**
    90       * <p>
    91       * Change the user's Struts {@link java.util.Locale} based on request
    92       * parameters for "language", "country".
    93       * After setting the Locale, control is forwarded to an URI path
    94       * indicated by a "page" parameter, or a forward indicated by a
    95       * "forward" parameter, or to a forward given as the mappings
    96       * "parameter" property.
    97       * The response location must be specified one of these ways.
    98       * </p>
    99       *
    100      * @param mapping  The ActionMapping used to select this instance
    101      * @param form     The optional ActionForm bean for this request (if any)
    102      * @param request  The HTTP request we are processing
    103      * @param response The HTTP response we are creating
    104      * @return An ActionForward indicate the resources that will render the
    105      *         response
    106      * @throws Exception if an input/output error or servlet exception occurs
    107      */
    108     public ActionForward execute(ActionMapping mapping,
    109                                  ActionForm form,
    110                                  HttpServletRequest request,
    111                                  HttpServletResponse response)
    112             throws Exception {
    113 
    114         String language = request.getParameter(LANGUAGE);
    115         String country = request.getParameter(COUNTRY);
    116 
    117         Locale locale = getLocale(request);
    118 
    119         if ((!isBlank(language)) && (!isBlank(country))) {
    120             locale = new Locale(language, country);
    121         } else if (!isBlank(language)) {
    122             locale = new Locale(language, "");
    123         }
    124 
    125         HttpSession session = request.getSession();
    126         session.setAttribute(Globals.LOCALE_KEY, locale);
    127 
    128         String target = request.getParameter(PAGE);
    129         if (!isBlank(target)) {
    130             return new ActionForward(target);
    131         }
    132 
    133         target = request.getParameter(FORWARD);
    134         if (isBlank(target)) {
    135             target = mapping.getParameter();
    136         }
    137         if (isBlank(target)) {
    138             log.warn(LOCALE_LOG);
    139             return null;
    140         }
    141         return mapping.findForward(target);
    142     }
    143 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
