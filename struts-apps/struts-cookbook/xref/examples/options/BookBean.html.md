[View Javadoc](../../../apidocs/examples/options/BookBean.html.md)


    1   /*
    2    * $Id: BookBean.java 471754 2006-11-06 14:55:09Z husted $
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
    24  /**
    25   * Represents a book
    26   *
    27   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    28   */
    29  public class BookBean {
    30  
    31      // ------------------------------------------------------ Instance Variables
    32  
    33      /**
    34       * International Standard Book Number (ISBN)
    35       */
    36      private String isbn;
    37  
    38      /**
    39       * Book Title
    40       */
    41      private String title;
    42  
    43      // ------------------------------------------------------------ Constructors
    44  
    45      /**
    46       * Constructor for BookBean.
    47       * @param title the book title
    48       * @param isbn the ISBN
    49       */
    50      public BookBean(String isbn, String title) {
    51          this.isbn = isbn;
    52          this.title = title;
    53      }
    54  
    55      // ------------------------------------------------------ Property Accessors
    56  
    57      /**
    58       * Returns the ISBN.
    59       * @return the ISBN
    60       */
    61      public String getIsbn() {
    62          return this.isbn;
    63      }
    64  
    65      /**
    66       * Returns the book title
    67       * @return the title
    68       */
    69      public String getTitle() {
    70          return this.title;
    71      }
    72  
    73  
    74  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)