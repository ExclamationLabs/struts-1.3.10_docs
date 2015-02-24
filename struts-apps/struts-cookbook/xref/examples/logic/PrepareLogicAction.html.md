[View Javadoc](../../../apidocs/examples/logic/PrepareLogicAction.html.md)


    1   /*
    2    * $Id: PrepareLogicAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples.logic;
    23  
    24  import java.util.ArrayList;
    25  
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.http.HttpServletResponse;
    28  
    29  import org.apache.struts.action.Action;
    30  import org.apache.struts.action.ActionErrors;
    31  import org.apache.struts.action.ActionForm;
    32  import org.apache.struts.action.ActionForward;
    33  import org.apache.struts.action.ActionMapping;
    34  import org.apache.struts.action.ActionMessage;
    35  import org.apache.struts.action.ActionMessages;
    36  
    37  import examples.TestBean;
    38  import examples.options.BookBean;
    39  
    40  /**
    41   * Perform any tasks and setup any data that
    42   * must be prepared before the form is displayed.
    43   *
    44   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    45   */
    46  public class PrepareLogicAction extends Action {
    47  
    48      // ------------------------------------------------------------ Constructors
    49  
    50      /**
    51       * Constructor for PrepareOptionsAction.
    52       */
    53      public PrepareLogicAction() {
    54          super();
    55      }
    56  
    57      // ---------------------------------------------------------- Action Methods
    58  
    59      /**
    60       * Process the request and return an <code>ActionForward</code> instance
    61       * describing where and how control should be forwarded, or
    62       * <code>null</code>if the response has already been completed.
    63       *
    64       * @param mapping The ActionMapping used to select this instance
    65       * @param form The optional ActionForm bean for this request (if any)
    66       * @param request The HTTP request we are processing
    67       * @param response The HTTP response we are creating
    68       *
    69       * @exception Exception if an exception occurs
    70       *
    71       * @return the ActionForward to forward control to
    72       */
    73      public ActionForward execute(
    74          ActionMapping mapping,
    75          ActionForm form,
    76          HttpServletRequest request,
    77          HttpServletResponse response)
    78          throws Exception {
    79  
    80          TestBean bean = new TestBean();
    81          request.setAttribute("testBean", bean);
    82  
    83          ArrayList items = new ArrayList();
    84          request.setAttribute("items", items);
    85  
    86          request.setAttribute("intValue", new Integer(7));
    87          request.setAttribute("stringValue", "Hello, world!");
    88  
    89          /* Collection of custom beans */
    90          ArrayList books = new ArrayList();
    91          books.add(new BookBean("0596003285", "Programming Jakarta Struts"));
    92          books.add(new BookBean("1930110502", "Struts in Action"));
    93          books.add(new BookBean("1861007817", "Professional Struts Applications"));
    94          books.add(new BookBean("0672324725", "Struts Kick Start"));
    95          books.add(new BookBean("0471213020", "Mastering Jakarta Struts"));
    96          books.add(new BookBean("1558608621", "The Struts Framework"));
    97          books.add(new BookBean("0971661901", "Struts Fast Track"));
    98          request.setAttribute("books", books);
    99  
    100         ActionErrors errors = new ActionErrors();
    101 
    102         errors.add(ActionMessages.GLOBAL_MESSAGE,
    103             new ActionMessage("errors.detail", "This is a global error #1"));
    104         errors.add(ActionMessages.GLOBAL_MESSAGE,
    105             new ActionMessage("errors.detail", "This is a global error #2"));
    106         errors.add("test",
    107             new ActionMessage("errors.detail", "This is a test error"));
    108 
    109         ActionMessages messages = new ActionMessages();
    110         messages.add(ActionMessages.GLOBAL_MESSAGE,
    111             new ActionMessage("message.detail", "This is global message #1"));
    112         messages.add(ActionMessages.GLOBAL_MESSAGE,
    113             new ActionMessage("message.detail", "This is global message #2"));
    114         messages.add("test",
    115             new ActionMessage("message.example.simple"));
    116 
    117 
    118         saveMessages(request, messages);
    119         saveErrors(request, errors);
    120 
    121         // Forward to the form
    122         return mapping.findForward("success");
    123 
    124     }
    125 
    126 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
