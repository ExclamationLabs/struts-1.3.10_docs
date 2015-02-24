[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/nested/NestedWriteNestingTei.html.md)


    1   /*
    2    * $Id: NestedWriteNestingTei.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.nested;
    22  
    23  import javax.servlet.jsp.tagext.TagData;
    24  import javax.servlet.jsp.tagext.TagExtraInfo;
    25  import javax.servlet.jsp.tagext.VariableInfo;
    26  
    27  /**
    28   * NestedWriteNestingTei
    29   *
    30   * This class will allow the nested:writeNesting tag to actually do what the
    31   * doc says and make a scripting variable as an option (when "id" is
    32   * supplied).
    33   *
    34   * @version $Rev: 471754 $
    35   * @since Struts 1.2
    36   */
    37  public class NestedWriteNestingTei extends TagExtraInfo {
    38      /**
    39       * Return information about the scripting variables to be created.
    40       */
    41      public VariableInfo[] getVariableInfo(TagData data) {
    42          /* the id parameter */
    43          String id = data.getAttributeString("id");
    44  
    45          VariableInfo[] vi = null;
    46  
    47          if (id != null) {
    48              vi = new VariableInfo[1];
    49              vi[0] =
    50                  new VariableInfo(id, "java.lang.String", true,
    51                      VariableInfo.AT_END);
    52          } else {
    53              vi = new VariableInfo[0];
    54          }
    55  
    56          // job done
    57          return vi;
    58      }
    59  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)