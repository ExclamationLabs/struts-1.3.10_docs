[View Javadoc](../../../../../../apidocs/org/apache/strutsel/taglib/utils/EvalHelper.html.md)


    1   /*
    2    * $Id: EvalHelper.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.strutsel.taglib.utils;
    22  
    23  import org.apache.taglibs.standard.lang.support.ExpressionEvaluatorManager;
    24  
    25  import javax.servlet.jsp.JspException;
    26  import javax.servlet.jsp.PageContext;
    27  import javax.servlet.jsp.tagext.Tag;
    28  
    29  /**
    30   * This class is used in the <code>evaluateExpressions</code> method of each
    31   * Tag class.  It is used to process the original attribute value through the
    32   * JSTL EL engine to produce an evaluated value.  It provides functions to
    33   * evaluate the expression assuming it is an Object, String, Integer, or
    34   * Boolean result.
    35   */
    36  public final class EvalHelper {
    37      private EvalHelper() {
    38      }
    39  
    40      /**
    41       * Evaluates the attribute value in the JSTL EL engine, returning the raw
    42       * Object value of the evaluated expression.  If the original expression
    43       * is null, or the resulting value is null, it will return null.
    44       */
    45      public static Object eval(String attrName, String attrValue, Tag tagObject,
    46          PageContext pageContext)
    47          throws JspException {
    48          Object result = null;
    49  
    50          if (attrValue != null) {
    51              result =
    52                  ExpressionEvaluatorManager.evaluate(attrName, attrValue,
    53                      Object.class, tagObject, pageContext);
    54          }
    55  
    56          return (result);
    57      }
    58  
    59      /**
    60       * Evaluates the attribute value in the JSTL EL engine, assuming the
    61       * resulting value is a String object.  If the original expression is
    62       * null, or the resulting value is null, it will return null.
    63       */
    64      public static String evalString(String attrName, String attrValue,
    65          Tag tagObject, PageContext pageContext)
    66          throws JspException {
    67          Object result = null;
    68  
    69          if (attrValue != null) {
    70              result =
    71                  ExpressionEvaluatorManager.evaluate(attrName, attrValue,
    72                      String.class, tagObject, pageContext);
    73          }
    74  
    75          return ((String) result);
    76      }
    77  
    78      /**
    79       * Evaluates the attribute value in the JSTL EL engine, assuming the
    80       * resulting value is an Integer object.  If the original expression is
    81       * null, or the resulting value is null, it will return null.
    82       */
    83      public static Integer evalInteger(String attrName, String attrValue,
    84          Tag tagObject, PageContext pageContext)
    85          throws JspException {
    86          Object result = null;
    87  
    88          if (attrValue != null) {
    89              result =
    90                  ExpressionEvaluatorManager.evaluate(attrName, attrValue,
    91                      Integer.class, tagObject, pageContext);
    92          }
    93  
    94          return ((Integer) result);
    95      }
    96  
    97      /**
    98       * Evaluates the attribute value in the JSTL EL engine, assuming the
    99       * resulting value is an Boolean object.  If the original expression is
    100      * null, or the resulting value is null, it will return null.
    101      */
    102     public static Boolean evalBoolean(String attrName, String attrValue,
    103         Tag tagObject, PageContext pageContext)
    104         throws JspException {
    105         Object result = null;
    106 
    107         if (attrValue != null) {
    108             result =
    109                 ExpressionEvaluatorManager.evaluate(attrName, attrValue,
    110                     Boolean.class, tagObject, pageContext);
    111         }
    112 
    113         return ((Boolean) result);
    114     }
    115 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
