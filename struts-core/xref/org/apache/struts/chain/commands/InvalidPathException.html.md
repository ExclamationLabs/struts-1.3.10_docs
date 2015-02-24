[View Javadoc](../../../../../../apidocs/org/apache/struts/chain/commands/InvalidPathException.html.md)


    1   /*
    2    * $Id: InvalidPathException.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.chain.commands;
    22  
    23  
    24  /**
    25   * <p>Exception thrown when no mapping can be found for the specified
    26   * path.</p>
    27   *
    28   * @version $Rev: 471754 $ $Date: 2005-11-05 21:44:59 -0500 (Sat, 05 Nov 2005)
    29   *          $
    30   */
    31  public class InvalidPathException extends Exception {
    32      /**
    33       * Field for Path property.
    34       */
    35      private String path;
    36  
    37      /**
    38       * <p> Default, no-argument constructor. </p>
    39       */
    40      public InvalidPathException() {
    41          super();
    42      }
    43  
    44      /**
    45       * <p> Constructor to inject message and path upon instantiation. </p>
    46       *
    47       * @param message The error or warning message.
    48       * @param path    The invalid path.
    49       */
    50      public InvalidPathException(String message, String path) {
    51          super(message);
    52          this.path = path;
    53      }
    54  
    55      /**
    56       * <p> Return the invalid path causing the exception. </p>
    57       *
    58       * @return The invalid path causing the exception.
    59       */
    60      public String getPath() {
    61          return path;
    62      }
    63  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)