[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionForward.html.md)


    1   /*
    2    * $Id: ActionForward.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.action;
    22  
    23  import org.apache.struts.config.ForwardConfig;
    24  
    25  /**
    26   * <p>An <strong>ActionForward</strong> represents a destination to which the
    27   * controller, RequestProcessor, might be directed to perform a
    28   * RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a
    29   * result of processing activities of an Action class. Instances of this class
    30   * may be created dynamically as necessary, or configured in association with
    31   * an ActionMapping instance for named lookup of potentially multiple
    32   * destinations for a particular mapping instance.</p>
    33   *
    34   * <p>An ActionForward has the following minimal set of properties. Additional
    35   * properties can be provided as needed by subclassses.</p>
    36   *
    37   * <ul>
    38   *
    39   * <li><strong>contextRelative</strong> - Should the path value be interpreted
    40   * as context-relative (instead of module-relative, if it starts with a '/'
    41   * character? [false]</li>
    42   *
    43   * <li><strong>name</strong> - Logical name by which this instance may be
    44   * looked up in relationship to a particular ActionMapping. </li>
    45   *
    46   * <li><strong>path</strong> - Module-relative or context-relative URI to
    47   * which control should be forwarded, or an absolute or relative URI to which
    48   * control should be redirected.</li>
    49   *
    50   * <li><strong>redirect</strong> - Set to true if the controller servlet
    51   * should call HttpServletResponse.sendRedirect() on the associated path;
    52   * otherwise false. [false]</li>
    53   *
    54   * </ul>
    55   *
    56   * <p>Since Struts 1.1 this class extends ForwardConfig and inherits the
    57   * contextRelative property.
    58   *
    59   * <p><strong>NOTE</strong> - This class would have been deprecated and
    60   * replaced by org.apache.struts.config.ForwardConfig except for the fact that
    61   * it is part of the public API that existing applications are using.</p>
    62   *
    63   * @version $Rev: 471754 $ $Date: 2005-08-14 17:24:39 -0400 (Sun, 14 Aug 2005)
    64   *          $
    65   */
    66  public class ActionForward extends ForwardConfig {
    67      /**
    68       * <p>Construct a new instance with default values.</p>
    69       */
    70      public ActionForward() {
    71          this(null, false);
    72      }
    73  
    74      /**
    75       * <p>Construct a new instance with the specified path.</p>
    76       *
    77       * @param path Path for this instance
    78       */
    79      public ActionForward(String path) {
    80          this(path, false);
    81      }
    82  
    83      /**
    84       * <p>Construct a new instance with the specified <code>path</code> and
    85       * <code>redirect</code> flag.</p>
    86       *
    87       * @param path     Path for this instance
    88       * @param redirect Redirect flag for this instance
    89       */
    90      public ActionForward(String path, boolean redirect) {
    91          super();
    92          setName(null);
    93          setPath(path);
    94          setRedirect(redirect);
    95      }
    96  
    97      /**
    98       * <p>Construct a new instance with the specified <code>name</code>,
    99       * <code>path</code> and <code>redirect</code> flag.</p>
    100      *
    101      * @param name     Name of this instance
    102      * @param path     Path for this instance
    103      * @param redirect Redirect flag for this instance
    104      */
    105     public ActionForward(String name, String path, boolean redirect) {
    106         super();
    107         setName(name);
    108         setPath(path);
    109         setRedirect(redirect);
    110     }
    111 
    112     /**
    113      * <p>Construct a new instance with the specified values.</p>
    114      *
    115      * @param name     Name of this forward
    116      * @param path     Path to which control should be forwarded or
    117      *                 redirected
    118      * @param redirect Should we do a redirect?
    119      * @param module   Module prefix, if any
    120      */
    121     public ActionForward(String name, String path, boolean redirect,
    122         String module) {
    123         super();
    124         setName(name);
    125         setPath(path);
    126         setRedirect(redirect);
    127         setModule(module);
    128     }
    129 
    130     /**
    131      * <p>Construct a new instance based on the values of another
    132      * ActionForward.</p>
    133      *
    134      * @param copyMe An ActionForward instance to copy
    135      * @since Struts 1.2.1
    136      */
    137     public ActionForward(ActionForward copyMe) {
    138         this(copyMe.getName(), copyMe.getPath(), copyMe.getRedirect(),
    139             copyMe.getModule());
    140     }
    141 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
