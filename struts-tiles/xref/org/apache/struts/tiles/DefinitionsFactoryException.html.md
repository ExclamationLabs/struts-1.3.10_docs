[View Javadoc](../../../../../apidocs/org/apache/struts/tiles/DefinitionsFactoryException.html.md)


    1   /*
    2    * $Id: DefinitionsFactoryException.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.tiles;
    24  
    25    /**
    26     * Exception thrown when an error occurs while the factory tries to
    27     * create a new instance mapper.
    28     */
    29  public class DefinitionsFactoryException extends TilesException
    30  {
    31    /**
    32      * Constructor.
    33      */
    34    public DefinitionsFactoryException()
    35      {
    36      super();
    37      this.exception = null;
    38    }
    39  
    40    /**
    41      * Constructor.
    42      * @param message The error or warning message.
    43      */
    44    public DefinitionsFactoryException(String message)
    45      {
    46      super(message);
    47      this.exception = null;
    48    }
    49  
    50  
    51    /**
    52      * Create a new <code>DefinitionsFactoryException</code> wrapping an existing exception.
    53      *
    54      * <p>The existing exception will be embedded in the new
    55      * one and its message will become the default message for
    56      * the DefinitionsFactoryException.</p>
    57      *
    58      * @param e The exception to be wrapped.
    59      */
    60    public DefinitionsFactoryException(Exception e)
    61    {
    62      super();
    63      this.exception = e;
    64    }
    65  
    66  
    67    /**
    68      * Create a new <code>DefinitionsFactoryException</code> from an existing exception.
    69      *
    70      * <p>The existing exception will be embedded in the new
    71      * one, but the new exception will have its own message.</p>
    72      *
    73      * @param message The detail message.
    74      * @param e The exception to be wrapped.
    75      */
    76    public DefinitionsFactoryException(String message, Exception e)
    77    {
    78      super(message);
    79      this.exception = e;
    80    }
    81  
    82  
    83    /**
    84      * Return a detail message for this exception.
    85      *
    86      * <p>If there is a embedded exception, and if the DefinitionsFactoryException
    87      * has no detail message of its own, this method will return
    88      * the detail message from the embedded exception.</p>
    89      *
    90      * @return The error or warning message.
    91      */
    92    public String getMessage ()
    93    {
    94      String message = super.getMessage ();
    95  
    96      if (message == null && exception != null) {
    97        return exception.getMessage();
    98      } else {
    99        return message;
    100     }
    101   }
    102 
    103 
    104   /**
    105     * Return the embedded exception, if any.
    106     * @return The embedded exception, or <code>null</code> if there is none.
    107     */
    108   public Exception getException ()
    109   {
    110     return exception;
    111   }
    112 
    113   //////////////////////////////////////////////////////////////////////
    114   // Internal state.
    115   //////////////////////////////////////////////////////////////////////
    116 
    117 
    118   /**
    119    * Any "wrapped" exception will be exposed when this is serialized.
    120    * @serial
    121    */
    122   private Exception exception;
    123 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
