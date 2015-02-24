[View Javadoc](../../../apidocs/examples/options/PrepareOptionsAction.html.md)


    1   /*
    2    * $Id: PrepareOptionsAction.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package examples.options;
    23  
    24  import java.util.ArrayList;
    25  import java.util.HashMap;
    26  
    27  import javax.servlet.http.HttpServletRequest;
    28  import javax.servlet.http.HttpServletResponse;
    29  
    30  import org.apache.struts.action.Action;
    31  import org.apache.struts.action.ActionForm;
    32  import org.apache.struts.action.ActionForward;
    33  import org.apache.struts.action.ActionMapping;
    34  import org.apache.struts.util.LabelValueBean;
    35  
    36  /**
    37   * Perform any tasks and setup any data that
    38   * must be prepared before the form is displayed.
    39   *
    40   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    41   */
    42  public class PrepareOptionsAction extends Action {
    43  
    44      // ------------------------------------------------------------ Constructors
    45  
    46      /**
    47       * Constructor for PrepareOptionsAction.
    48       */
    49      public PrepareOptionsAction() {
    50          super();
    51      }
    52  
    53      // ---------------------------------------------------------- Action Methods
    54  
    55      /**
    56       * Process the request and return an <code>ActionForward</code> instance
    57       * describing where and how control should be forwarded, or
    58       * <code>null</code>if the response has already been completed.
    59       *
    60       * @param mapping The ActionMapping used to select this instance
    61       * @param form The optional ActionForm bean for this request (if any)
    62       * @param request The HTTP request we are processing
    63       * @param response The HTTP response we are creating
    64       *
    65       * @exception Exception if an exception occurs
    66       *
    67       * @return the ActionForward to forward control to
    68       */
    69      public ActionForward execute(
    70          ActionMapping mapping,
    71          ActionForm form,
    72          HttpServletRequest request,
    73          HttpServletResponse response)
    74          throws Exception {
    75  
    76          /* An array */
    77          String[] fruits =
    78              {
    79                  "Strawberry",
    80                  "Apple",
    81                  "Orange",
    82                  "Pear",
    83                  "Mango",
    84                  "Banana",
    85                  "Pineapple" };
    86          request.setAttribute("fruits", fruits);
    87  
    88          /* Two arrays - one for labels and one for values */
    89          String[] colors =
    90              { "Red", "Orange", "Yellow", "Green", "Blue", "Indigo", "Violet" };
    91          request.setAttribute("colors", colors);
    92  
    93          String[] colorCodes =
    94              {
    95                  "#FF0000",
    96                  "#FFA500",
    97                  "#FFFF00",
    98                  "#00FF00",
    99                  "#0000FF",
    100                 "#4B0082",
    101                 "#EE82EE" };
    102         request.setAttribute("colorCodes", colorCodes);
    103 
    104         /* A Collection */
    105         ArrayList colorList = new ArrayList();
    106         colorList.add("Red");
    107         colorList.add("Orange");
    108         colorList.add("Yellow");
    109         colorList.add("Green");
    110         colorList.add("Blue");
    111         colorList.add("Indigo");
    112         colorList.add("Violet");
    113         request.setAttribute("colorCollection", colorList);
    114 
    115         /* A Collection of LabelValue beans */
    116         ArrayList days = new ArrayList();
    117         days.add(new LabelValueBean("Monday", "1"));
    118         days.add(new LabelValueBean("Tuesday", "2"));
    119         days.add(new LabelValueBean("Wednesday", "3"));
    120         days.add(new LabelValueBean("Thursday", "4"));
    121         days.add(new LabelValueBean("Friday", "5"));
    122         days.add(new LabelValueBean("Saturday", "6"));
    123         days.add(new LabelValueBean("Sunday", "7"));
    124         request.setAttribute("days", days);
    125 
    126         /* Collection of custom beans */
    127         ArrayList books = new ArrayList();
    128         books.add(new BookBean("0596003285", "Programming Jakarta Struts"));
    129         books.add(new BookBean("1930110502", "Struts in Action"));
    130         books.add(
    131             new BookBean("1861007817", "Professional Struts Applications"));
    132         books.add(new BookBean("0672324725", "Struts Kick Start"));
    133         books.add(new BookBean("0471213020", "Mastering Jakarta Struts"));
    134         books.add(new BookBean("1558608621", "The Struts Framework"));
    135         books.add(new BookBean("0971661901", "Struts Fast Track"));
    136         request.setAttribute("books", books);
    137 
    138         /* A Map
    139          *
    140          * Note: We are using a HashMap which is unsorted - the resulting
    141          * options could appear in any order. If you want to your options to be
    142          * in a particular order you should you a SortedMap implementation such
    143          * as the TreeMap. This behaviour is a feature of the standard Map
    144          * implementaions and nothing to to with Struts tags.
    145          *
    146          * Also, we've used an Integer as the key to demonstrate that the
    147          * .html.md:options> and <html:optionsCollection> tags do not require
    148          * String values for the label and values. If they are passed an object
    149          * other than a String, they will automatically call the toString()
    150          * method and use the result.
    151          */
    152         HashMap animals = new HashMap();
    153         animals.put(new Integer(1), "Cat");
    154         animals.put(new Integer(2), "Dog");
    155         animals.put(new Integer(3), "Horse");
    156         animals.put(new Integer(4), "Rabbit");
    157         animals.put(new Integer(5), "Goldfish");
    158         request.setAttribute("animals", animals);
    159 
    160         // Forward to form page
    161         return mapping.findForward("success");
    162 
    163     }
    164 
    165 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
