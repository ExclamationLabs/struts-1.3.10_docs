[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/bean/SizeTag.html.md)


    1   /*
    2    * $Id: SizeTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.MessageResources;
    25  
    26  import javax.servlet.jsp.JspException;
    27  import javax.servlet.jsp.PageContext;
    28  import javax.servlet.jsp.tagext.TagSupport;
    29  
    30  import java.lang.reflect.Array;
    31  
    32  import java.util.Collection;
    33  import java.util.Map;
    34  
    35  /**
    36   * Define a scripting variable that will contain the number of elements found
    37   * in a specified array, Collection, or Map.
    38   *
    39   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    40   *          $
    41   */
    42  public class SizeTag extends TagSupport {
    43      /**
    44       * The message resources for this package.
    45       */
    46      protected static MessageResources messages =
    47          MessageResources.getMessageResources(
    48              "org.apache.struts.taglib.bean.LocalStrings");
    49  
    50      // ------------------------------------------------------------- Properties
    51  
    52      /**
    53       * The actual collection to be counted.
    54       */
    55      protected Object collection = null;
    56  
    57      /**
    58       * The name of the scripting variable that will be exposed as a page scope
    59       * attribute.
    60       */
    61      protected String id = null;
    62  
    63      /**
    64       * The name of the bean owning the property to be counted.
    65       */
    66      protected String name = null;
    67  
    68      /**
    69       * The name of the property to be retrieved.
    70       */
    71      protected String property = null;
    72  
    73      /**
    74       * The scope within which to search for the specified bean.
    75       */
    76      protected String scope = null;
    77  
    78      public Object getCollection() {
    79          return (this.collection);
    80      }
    81  
    82      public void setCollection(Object collection) {
    83          this.collection = collection;
    84      }
    85  
    86      public String getId() {
    87          return (this.id);
    88      }
    89  
    90      public void setId(String id) {
    91          this.id = id;
    92      }
    93  
    94      public String getName() {
    95          return (this.name);
    96      }
    97  
    98      public void setName(String name) {
    99          this.name = name;
    100     }
    101 
    102     public String getProperty() {
    103         return (this.property);
    104     }
    105 
    106     public void setProperty(String property) {
    107         this.property = property;
    108     }
    109 
    110     public String getScope() {
    111         return (this.scope);
    112     }
    113 
    114     public void setScope(String scope) {
    115         this.scope = scope;
    116     }
    117 
    118     // --------------------------------------------------------- Public Methods
    119 
    120     /**
    121      * Retrieve the required property and expose it as a scripting variable.
    122      *
    123      * @throws JspException if a JSP exception has occurred
    124      */
    125     public int doStartTag() throws JspException {
    126         // Retrieve the required property value
    127         Object value = this.collection;
    128 
    129         if (value == null) {
    130             if (name == null) {
    131                 // Must specify either a collection attribute or a name
    132                 // attribute.
    133                 JspException e =
    134                     new JspException(messages.getMessage(
    135                             "size.noCollectionOrName"));
    136 
    137                 TagUtils.getInstance().saveException(pageContext, e);
    138                 throw e;
    139             }
    140 
    141             value =
    142                 TagUtils.getInstance().lookup(pageContext, name, property, scope);
    143         }
    144 
    145         // Identify the number of elements, based on the collection type
    146         int size = 0;
    147 
    148         if (value == null) {
    149             JspException e =
    150                 new JspException(messages.getMessage("size.collection"));
    151 
    152             TagUtils.getInstance().saveException(pageContext, e);
    153             throw e;
    154         } else if (value.getClass().isArray()) {
    155             size = Array.getLength(value);
    156         } else if (value instanceof Collection) {
    157             size = ((Collection) value).size();
    158         } else if (value instanceof Map) {
    159             size = ((Map) value).size();
    160         } else {
    161             JspException e =
    162                 new JspException(messages.getMessage("size.collection"));
    163 
    164             TagUtils.getInstance().saveException(pageContext, e);
    165             throw e;
    166         }
    167 
    168         // Expose this size as a scripting variable
    169         pageContext.setAttribute(this.id, new Integer(size),
    170             PageContext.PAGE_SCOPE);
    171 
    172         return (SKIP_BODY);
    173     }
    174 
    175     /**
    176      * Release all allocated resources.
    177      */
    178     public void release() {
    179         super.release();
    180         collection = null;
    181         id = null;
    182         name = null;
    183         property = null;
    184         scope = null;
    185     }
    186 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
