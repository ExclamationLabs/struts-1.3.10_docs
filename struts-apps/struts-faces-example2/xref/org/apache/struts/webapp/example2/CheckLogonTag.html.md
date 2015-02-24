[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/example2/CheckLogonTag.html.md)


    1   /*
    2    * $Id: CheckLogonTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.webapp.example2;
    24  
    25  
    26  import javax.servlet.http.HttpSession;
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  
    31  /**
    32   * Check for a valid User logged on in the current session.  If there is no
    33   * such user, forward control to the logon page.
    34   *
    35   * @author Craig R. McClanahan
    36   * @author Marius Barduta
    37   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    38   */
    39  
    40  public final class CheckLogonTag extends TagSupport {
    41  
    42  
    43      // --------------------------------------------------- Instance Variables
    44  
    45  
    46      /**
    47       * The key of the session-scope bean we look for.
    48       */
    49      private String name = Constants.USER_KEY;
    50  
    51  
    52      /**
    53       * The page to which we should forward for the user to log on.
    54       */
    55      private String page = "/logon.jsp";
    56  
    57  
    58      // ----------------------------------------------------------- Properties
    59  
    60  
    61      /**
    62       * Return the bean name.
    63       */
    64      public String getName() {
    65  
    66      return (this.name);
    67  
    68      }
    69  
    70  
    71      /**
    72       * Set the bean name.
    73       *
    74       * @param name The new bean name
    75       */
    76      public void setName(String name) {
    77  
    78      this.name = name;
    79  
    80      }
    81  
    82  
    83      /**
    84       * Return the forward page.
    85       */
    86      public String getPage() {
    87  
    88      return (this.page);
    89  
    90      }
    91  
    92  
    93      /**
    94       * Set the forward page.
    95       *
    96       * @param page The new forward page
    97       */
    98      public void setPage(String page) {
    99  
    100     this.page = page;
    101 
    102     }
    103 
    104 
    105     // ------------------------------------------------------- Public Methods
    106 
    107 
    108     /**
    109      * Defer our checking until the end of this tag is encountered.
    110      *
    111      * @exception JspException if a JSP exception has occurred
    112      */
    113     public int doStartTag() throws JspException {
    114 
    115     return (SKIP_BODY);
    116 
    117     }
    118 
    119 
    120     /**
    121      * Perform our logged-in user check by looking for the existence of
    122      * a session scope bean under the specified name.  If this bean is not
    123      * present, control is forwarded to the specified logon page.
    124      *
    125      * @exception JspException if a JSP exception has occurred
    126      */
    127     public int doEndTag() throws JspException {
    128 
    129     // Is there a valid user logged on?
    130     boolean valid = false;
    131     HttpSession session = pageContext.getSession();
    132     if ((session != null) && (session.getAttribute(name) != null))
    133         valid = true;
    134 
    135     // Forward control based on the results
    136     if (valid)
    137         return (EVAL_PAGE);
    138     else {
    139         try {
    140         pageContext.forward(page);
    141         } catch (Exception e) {
    142         throw new JspException(e.toString());
    143         }
    144         return (SKIP_PAGE);
    145     }
    146 
    147     }
    148 
    149 
    150     /**
    151      * Release any acquired resources.
    152      */
    153     public void release() {
    154 
    155         super.release();
    156         this.name = Constants.USER_KEY;
    157         this.page = "/logon.jsp";
    158 
    159     }
    160 
    161 
    162 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
