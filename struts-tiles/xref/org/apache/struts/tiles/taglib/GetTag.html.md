[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/GetTag.html.md)


    1   /*
    2    * $Id: GetTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.tiles.taglib;
    24  
    25  /**
    26   * This is the tag handler for &lt;tiles:get&gt;, which gets
    27   * content from the request scope and either includes the content or prints
    28   * it, depending upon the value of the content's <code>direct</code> attribute.
    29   *
    30   * This tag is intended to be compatible with the same tag from Templates (David Geary).
    31   * Implementation extends InsertTag for facility (no so well).
    32   * The only difference is the default value of attribute 'ignore', which is <code>true</code>
    33   * for this tag (default behavior of David Geary's templates).
    34   */
    35  public class GetTag extends InsertTag {
    36  
    37  
    38      /**
    39       * Constructor.
    40       * Set default value for 'isErrorIgnored' to <code>true</code>.
    41       */
    42      public GetTag() {
    43          isErrorIgnored = true;
    44      }
    45  
    46      /**
    47       * Release all allocated resources.
    48       */
    49      public void release() {
    50  
    51          super.release();
    52          isErrorIgnored = true;
    53      }
    54  
    55  
    56  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
