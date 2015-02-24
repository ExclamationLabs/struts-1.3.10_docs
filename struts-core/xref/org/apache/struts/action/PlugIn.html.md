[View Javadoc](../../../../../apidocs/org/apache/struts/action/PlugIn.html.md)


    1   /*
    2    * $Id: PlugIn.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.config.ModuleConfig;
    24  
    25  import javax.servlet.ServletException;
    26  
    27  /**
    28   * <p>A <strong>PlugIn</strong> is a configuration wrapper for a
    29   * module-specific resource or service that needs to be notified about
    30   * application startup and application shutdown events (corresponding to when
    31   * the container calls <code>init</code> and <code>destroy</code> on the
    32   * corresponding {@link ActionServlet} instance). <code>PlugIn</code> objects
    33   * can be configured in the <code>struts-config.xml</code> file, without the
    34   * need to subclass {@link ActionServlet} simply to perform application
    35   * lifecycle activities.</p>
    36   *
    37   * <p>Implementations of this interface must supply a zero-argument
    38   * constructor for use by {@link ActionServlet}. Configuration can be
    39   * accomplished by providing standard JavaBeans property setter methods, which
    40   * will all have been called before the <code>init()</code> method is
    41   * invoked.</p>
    42   *
    43   * <p>This interface can be applied to any class, including an Action
    44   * subclass. </p>
    45   *
    46   * @version $Rev: 471754 $ $Date: 2005-05-14 01:09:32 -0400 (Sat, 14 May 2005)
    47   *          $
    48   * @since Struts 1.1
    49   */
    50  public interface PlugIn {
    51      /**
    52       * <p>Receive notification that our owning module is being shut down.</p>
    53       */
    54      void destroy();
    55  
    56      /**
    57       * <p>Receive notification that the specified module is being started
    58       * up.</p>
    59       *
    60       * @param servlet ActionServlet that is managing all the modules in this
    61       *                web application
    62       * @param config  ModuleConfig for the module with which this plug-in is
    63       *                associated
    64       * @throws ServletException if this <code>PlugIn</code> cannot be
    65       *                          successfully initialized
    66       */
    67      void init(ActionServlet servlet, ModuleConfig config)
    68          throws ServletException;
    69  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)