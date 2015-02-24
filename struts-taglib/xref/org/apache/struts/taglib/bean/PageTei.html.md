[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/PageTei.html.md)


    1   /*
    2    * $Id: PageTei.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.bean;
    22  
    23  import javax.servlet.jsp.tagext.TagData;
    24  import javax.servlet.jsp.tagext.TagExtraInfo;
    25  import javax.servlet.jsp.tagext.VariableInfo;
    26  
    27  /**
    28   * Implementation of <code>TagExtraInfo</code> for the <b>page</b> tag,
    29   * identifying the scripting object(s) to be made visible.
    30   *
    31   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    32   *          $
    33   */
    34  public class PageTei extends TagExtraInfo {
    35      /**
    36       * Return information about the scripting variables to be created.
    37       */
    38      public VariableInfo[] getVariableInfo(TagData data) {
    39          String type = null;
    40          String property = data.getAttributeString("property");
    41  
    42          if ("application".equalsIgnoreCase(property)) {
    43              type = "javax.servlet.ServletContext";
    44          } else if ("config".equalsIgnoreCase(property)) {
    45              type = "javax.servlet.ServletConfig";
    46          } else if ("request".equalsIgnoreCase(property)) {
    47              type = "javax.servlet.ServletRequest";
    48          } else if ("response".equalsIgnoreCase(property)) {
    49              type = "javax.servlet.ServletResponse";
    50          } else if ("session".equalsIgnoreCase(property)) {
    51              type = "javax.servlet.http.HttpSession";
    52          } else {
    53              type = "java.lang.Object";
    54          }
    55  
    56          return new VariableInfo[] {
    57              new VariableInfo(data.getAttributeString("id"), type, true,
    58                  VariableInfo.AT_BEGIN)
    59          };
    60      }
    61  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)