[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/util/MessagesMap.html.md)


    1   /*
    2    * $Id: MessagesMap.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.util;
    23  
    24  
    25  import java.util.Collection;
    26  import java.util.Locale;
    27  import java.util.Map;
    28  import java.util.Set;
    29  
    30  import org.apache.struts.util.MessageResources;
    31  
    32  
    33  /**
    34   * <p>A limited immutable <code>Map</code> implementation that wraps the
    35   * <code>MessageResources</code> instance for the specified
    36   * <code>Locale</code>.  Exposing the messages as a <code>Map</code>
    37   * makes them easily accessible via value binding expressions, as
    38   * well as JSP 2.0 expression language expressions.
    39   */
    40  
    41  public class MessagesMap implements Map {
    42  
    43  
    44      // ------------------------------------------------------------ Constructors
    45  
    46  
    47      /**
    48       * <p>Construct a new {@link MessagesMap} instance that wraps the
    49       * specified <code>MessageResources</code> instance, and returns messages
    50       * for the specified <code>Locale</code>.</p>
    51       *
    52       * @param messages <code>MessageResources</code> instance to wrap
    53       * @param locale <code>Locale</code> for which to retrieve messages,
    54       *  or <code>null</code> for the system default <code>Locale</code>
    55       *
    56       * @exception NullPointerException if <code>messages</code>
    57       *  is <code>null</code>
    58       */
    59      public MessagesMap(MessageResources messages, Locale locale) {
    60  
    61          super();
    62          if (messages == null) {
    63              throw new NullPointerException();
    64          }
    65          this.messages = messages;
    66          this.locale = locale;
    67  
    68      }
    69  
    70  
    71      // ------------------------------------------------------ Instance Variables
    72  
    73  
    74      /**
    75       * <p>The <code>Locale</code> for which to return messages, or
    76       * <code>null</code> for the system default <code>Locale</code>.</p>
    77       */
    78      private Locale locale = null;
    79  
    80  
    81      /**
    82       * <p>The <code>MessageResources</code> being wrapped by this
    83       * {@link MessagesMap}.</p>
    84       */
    85      private MessageResources messages = null;
    86  
    87  
    88      // ---------------------------------------------------------- Public Methods
    89  
    90  
    91      /**
    92       * <p>The <code>clear()</code> method is not supported.</p>
    93       */
    94      public void clear() {
    95  
    96          throw new UnsupportedOperationException();
    97  
    98      }
    99  
    100 
    101     /**
    102      * <p>Return <code>true</code> if there is a message for the
    103      * specified key.</p>
    104      *
    105      * @param key Message key to evaluate
    106      */
    107     public boolean containsKey(Object key) {
    108 
    109         if (key == null) {
    110             return (false);
    111         } else {
    112             return (messages.isPresent(locale, key.toString()));
    113         }
    114 
    115     }
    116 
    117 
    118     /**
    119      * <p>The <code>containsValue()</code> method is not supported.</p>
    120      *
    121      * @param value Value to evaluate
    122      */
    123     public boolean containsValue(Object value) {
    124 
    125         throw new UnsupportedOperationException();
    126 
    127     }
    128 
    129 
    130     /**
    131      * <p>The <code>entrySet()</code> method is not supported.</p>
    132      */
    133     public Set entrySet() {
    134 
    135         throw new UnsupportedOperationException();
    136 
    137     }
    138 
    139 
    140     /**
    141      * <p>The <code>equals</code> method checks whether equal
    142      * <code>MessageResources</code> and <code>Locale</code> are
    143      * being wrapped.</p>
    144      *
    145      * @param o The object to be compared
    146      */
    147     public boolean equals(Object o) {
    148 
    149         if (!(o instanceof MessagesMap)) {
    150             return (false);
    151         }
    152         MessagesMap other = (MessagesMap) o;
    153         if (!messages.equals(other.getMessages())) {
    154             return (false);
    155         }
    156         if (locale == null) {
    157             return (other.getLocale() == null);
    158         } else {
    159             return (locale.equals(other.getLocale()));
    160         }
    161 
    162     }
    163 
    164 
    165     /**
    166      * <p>Return the message string for the specified key.</p>
    167      *
    168      * @param key Key for message to return
    169      */
    170     public Object get(Object key) {
    171 
    172         if (key == null) {
    173             return ("??????");
    174         } else {
    175             return (messages.getMessage(locale, key.toString()));
    176         }
    177 
    178     }
    179 
    180 
    181     /**
    182      * <p>The <code>hashCode()</code> method returns values that will
    183      * be identical if the <code>equals</code> method returns <code>true</code>.
    184      * </p>
    185      */
    186     public int hashCode() {
    187 
    188         int value = messages.hashCode();
    189         if (locale != null) {
    190             value = value ^ locale.hashCode();
    191         }
    192         return (value);
    193 
    194     }
    195 
    196 
    197     /**
    198      * <p>The <code>isEmpty()</code> method returns <code>false</code>, on the
    199      * assumption that there is always at least one message available.</p>
    200      */
    201     public boolean isEmpty() {
    202 
    203         return (false);
    204 
    205     }
    206 
    207 
    208     /**
    209      * <p>The <code>keySet()</code> method is not supported.</p>
    210      */
    211     public Set keySet() {
    212 
    213         throw new UnsupportedOperationException();
    214 
    215     }
    216 
    217 
    218     /**
    219      * <p>The <code>put()</code> method is not supported.</p>
    220      *
    221      * @param key Key to store
    222      * @param value Value to store
    223      */
    224     public Object put(Object key, Object value) {
    225 
    226         throw new UnsupportedOperationException();
    227 
    228     }
    229 
    230 
    231     /**
    232      * <p>The <code>putAll()</code> method is not supported.</p>
    233      *
    234      * @param map Keys and values to store
    235      */
    236     public void putAll(Map map) {
    237 
    238         throw new UnsupportedOperationException();
    239 
    240     }
    241 
    242 
    243     /**
    244      * <p>The <code>remove()</code> method is not supported.</p>
    245      *
    246      * @param key Key to remove
    247      */
    248     public Object remove(Object key) {
    249 
    250         throw new UnsupportedOperationException();
    251 
    252     }
    253 
    254 
    255     /**
    256      * <p>The <code>size()</code> method is not supported.</p>
    257      */
    258     public int size() {
    259 
    260         throw new UnsupportedOperationException();
    261 
    262     }
    263 
    264 
    265     /**
    266      * <p>The <code>values()</code> method is not supported.</p>
    267      */
    268     public Collection values() {
    269 
    270         throw new UnsupportedOperationException();
    271 
    272     }
    273 
    274 
    275     // --------------------------------------------------------- Package Methods
    276 
    277 
    278     /**
    279      * <p>Return the <code>Locale</code> we object we are wrapping.</p>
    280      */
    281     Locale getLocale() {
    282 
    283         return (this.locale);
    284 
    285     }
    286 
    287 
    288     /**
    289      * <p>Return the <code>MessageResources</code> object we are wrapping.</p>
    290      */
    291     MessageResources getMessages() {
    292 
    293         return (this.messages);
    294 
    295     }
    296 
    297 
    298 
    299 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
