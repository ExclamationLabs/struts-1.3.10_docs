[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/ComponentConstants.html.md)


    1   /*
    2    * $Id: ComponentConstants.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.tiles.taglib;
    23  
    24  import org.apache.struts.Globals;
    25  
    26  /**
    27   * Constants used by Tiles/Components.
    28   */
    29  public interface ComponentConstants {
    30  
    31      /** Name used to store Tile/Component context. */
    32      public static final String COMPONENT_CONTEXT = "org.apache.struts.taglib.tiles.CompContext";
    33  
    34      public static final int COMPONENT_SCOPE = 8;
    35      public static final String LOCALE_KEY = Globals.LOCALE_KEY;
    36      public static final String EXCEPTION_KEY = Globals.EXCEPTION_KEY;
    37  
    38  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)