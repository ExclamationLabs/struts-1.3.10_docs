[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionMapping.html.md)


    1   /*
    2    * $Id: ActionMapping.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.commons.logging.Log;
    24  import org.apache.commons.logging.LogFactory;
    25  import org.apache.struts.config.ActionConfig;
    26  import org.apache.struts.config.ForwardConfig;
    27  
    28  import java.util.ArrayList;
    29  
    30  /**
    31   * <p>An <strong>ActionMapping</strong> represents the information that the
    32   * controller, <code>RequestProcessor</code>, knows about the mapping of a
    33   * particular request to an instance of a particular <code>Action</code>
    34   * class. The <code>ActionMapping</code> instance used to select a particular
    35   * <code>Action</code> is passed on to that <code>Action</code>, thereby
    36   * providing access to any custom configuration information included with the
    37   * <code>ActionMapping</code> object.</p>
    38   *
    39   * <p>Since Struts 1.1 this class extends <code>ActionConfig</code>.
    40   *
    41   * <p><strong>NOTE</strong> - This class would have been deprecated and
    42   * replaced by <code>org.apache.struts.config.ActionConfig</code> except for
    43   * the fact that it is part of the public API that existing applications are
    44   * using.</p>
    45   *
    46   * @version $Rev: 471754 $ $Date: 2005-08-26 21:58:39 -0400 (Fri, 26 Aug 2005)
    47   *          $
    48   */
    49  public class ActionMapping extends ActionConfig {
    50      /**
    51       * <p>Commons Logging instance.</p>
    52       *
    53       * @since Struts 1.2.8
    54       */
    55      private static Log log = LogFactory.getLog(ActionMapping.class);
    56  
    57      /**
    58       * <p>Find and return the <code>ForwardConfig</code> instance defining how
    59       * forwarding to the specified logical name should be handled. This is
    60       * performed by checking local and then global configurations for the
    61       * specified forwarding configuration. If no forwarding configuration can
    62       * be found, return <code>null</code>.</p>
    63       *
    64       * @param forwardName Logical name of the forwarding instance to be
    65       *                    returned
    66       * @return The local or global forward with the specified name.
    67       */
    68      public ActionForward findForward(String forwardName) {
    69          ForwardConfig config = findForwardConfig(forwardName);
    70  
    71          if (config == null) {
    72              config = getModuleConfig().findForwardConfig(forwardName);
    73          }
    74  
    75          if (config == null) {
    76              if (log.isWarnEnabled()) {
    77                  log.warn("Unable to find '" + forwardName + "' forward.");
    78              }
    79          }
    80  
    81          return ((ActionForward) config);
    82      }
    83  
    84      /**
    85       * <p>Return the logical names of all locally defined forwards for this
    86       * mapping. If there are no such forwards, a zero-length array is
    87       * returned.</p>
    88       *
    89       * @return The forward names for this action mapping.
    90       */
    91      public String[] findForwards() {
    92          ArrayList results = new ArrayList();
    93          ForwardConfig[] fcs = findForwardConfigs();
    94  
    95          for (int i = 0; i < fcs.length; i++) {
    96              results.add(fcs[i].getName());
    97          }
    98  
    99          return ((String[]) results.toArray(new String[results.size()]));
    100     }
    101 
    102     /**
    103      * <p>Create (if necessary) and return an {@link ActionForward} that
    104      * corresponds to the <code>input</code> property of this Action.</p>
    105      *
    106      * @return The input forward for this action mapping.
    107      * @since Struts 1.1
    108      */
    109     public ActionForward getInputForward() {
    110         if (getModuleConfig().getControllerConfig().getInputForward()) {
    111             return (findForward(getInput()));
    112         } else {
    113             return (new ActionForward(getInput()));
    114         }
    115     }
    116 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
