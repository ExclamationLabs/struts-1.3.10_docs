[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionMessages.html.md)


    1   /*
    2    * $Id: ActionMessages.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.action;
    22  
    23  import java.io.Serializable;
    24  
    25  import java.util.ArrayList;
    26  import java.util.Collections;
    27  import java.util.Comparator;
    28  import java.util.HashMap;
    29  import java.util.Iterator;
    30  import java.util.List;
    31  
    32  /**
    33   * <p>A class that encapsulates messages. Messages can be either global or
    34   * they are specific to a particular bean property.</p>
    35   *
    36   * <p>Each individual message is described by an <code>ActionMessage</code>
    37   * object, which contains a message key (to be looked up in an appropriate
    38   * message resources database), and up to four placeholder arguments used for
    39   * parametric substitution in the resulting message.</p>
    40   *
    41   * <p><strong>IMPLEMENTATION NOTE</strong> - It is assumed that these objects
    42   * are created and manipulated only within the context of a single thread.
    43   * Therefore, no synchronization is required for access to internal
    44   * collections.</p>
    45   *
    46   * @version $Rev: 471754 $ $Date: 2005-08-26 21:58:39 -0400 (Fri, 26 Aug 2005)
    47   *          $
    48   * @since Struts 1.1
    49   */
    50  public class ActionMessages implements Serializable {
    51      /**
    52       * <p>Compares ActionMessageItem objects.</p>
    53       */
    54      private static final Comparator ACTION_ITEM_COMPARATOR =
    55          new Comparator() {
    56              public int compare(Object o1, Object o2) {
    57                  return ((ActionMessageItem) o1).getOrder()
    58                  - ((ActionMessageItem) o2).getOrder();
    59              }
    60          };
    61  
    62      // ----------------------------------------------------- Manifest Constants
    63  
    64      /**
    65       * <p>The "property name" marker to use for global messages, as opposed to
    66       * those related to a specific property.</p>
    67       */
    68      public static final String GLOBAL_MESSAGE =
    69          "org.apache.struts.action.GLOBAL_MESSAGE";
    70  
    71      // ----------------------------------------------------- Instance Variables
    72  
    73      /**
    74       * <p>Have the messages been retrieved from this object?</p>
    75       *
    76       * <p>The controller uses this property to determine if session-scoped
    77       * messages can be removed.</p>
    78       *
    79       * @since Struts 1.2
    80       */
    81      protected boolean accessed = false;
    82  
    83      /**
    84       * <p>The accumulated set of <code>ActionMessage</code> objects
    85       * (represented as an ArrayList) for each property, keyed by property
    86       * name.</p>
    87       */
    88      protected HashMap messages = new HashMap();
    89  
    90      /**
    91       * <p>The current number of the property/key being added. This is used to
    92       * maintain the order messages are added.</p>
    93       */
    94      protected int iCount = 0;
    95  
    96      // --------------------------------------------------------- Public Methods
    97  
    98      /**
    99       * <p>Create an empty <code>ActionMessages</code> object.</p>
    100      */
    101     public ActionMessages() {
    102         super();
    103     }
    104 
    105     /**
    106      * <p>Create an <code>ActionMessages</code> object initialized with the
    107      * given messages.</p>
    108      *
    109      * @param messages The messages to be initially added to this object. This
    110      *                 parameter can be <code>null</code>.
    111      * @since Struts 1.1
    112      */
    113     public ActionMessages(ActionMessages messages) {
    114         super();
    115         this.add(messages);
    116     }
    117 
    118     /**
    119      * <p>Add a message to the set of messages for the specified property. An
    120      * order of the property/key is maintained based on the initial addition
    121      * of the property/key.</p>
    122      *
    123      * @param property Property name (or ActionMessages.GLOBAL_MESSAGE)
    124      * @param message  The message to be added
    125      */
    126     public void add(String property, ActionMessage message) {
    127         ActionMessageItem item = (ActionMessageItem) messages.get(property);
    128         List list;
    129 
    130         if (item == null) {
    131             list = new ArrayList();
    132             item = new ActionMessageItem(list, iCount++, property);
    133 
    134             messages.put(property, item);
    135         } else {
    136             list = item.getList();
    137         }
    138 
    139         list.add(message);
    140     }
    141 
    142     /**
    143      * <p>Adds the messages from the given <code>ActionMessages</code> object
    144      * to this set of messages. The messages are added in the order they are
    145      * returned from the <code>properties</code> method. If a message's
    146      * property is already in the current <code>ActionMessages</code> object,
    147      * it is added to the end of the list for that property. If a message's
    148      * property is not in the current list it is added to the end of the
    149      * properties.</p>
    150      *
    151      * @param actionMessages The <code>ActionMessages</code> object to be
    152      *                       added. This parameter can be <code>null</code>.
    153      * @since Struts 1.1
    154      */
    155     public void add(ActionMessages actionMessages) {
    156         if (actionMessages == null) {
    157             return;
    158         }
    159 
    160         // loop over properties
    161         Iterator props = actionMessages.properties();
    162 
    163         while (props.hasNext()) {
    164             String property = (String) props.next();
    165 
    166             // loop over messages for each property
    167             Iterator msgs = actionMessages.get(property);
    168 
    169             while (msgs.hasNext()) {
    170                 ActionMessage msg = (ActionMessage) msgs.next();
    171 
    172                 this.add(property, msg);
    173             }
    174         }
    175     }
    176 
    177     /**
    178      * <p>Clear all messages recorded by this object.</p>
    179      */
    180     public void clear() {
    181         messages.clear();
    182     }
    183 
    184     /**
    185      * <p>Return <code>true</code> if there are no messages recorded in this
    186      * collection, or <code>false</code> otherwise.</p>
    187      *
    188      * @return <code>true</code> if there are no messages recorded in this
    189      *         collection; <code>false</code> otherwise.
    190      * @since Struts 1.1
    191      */
    192     public boolean isEmpty() {
    193         return (messages.isEmpty());
    194     }
    195 
    196     /**
    197      * <p>Return the set of all recorded messages, without distinction by
    198      * which property the messages are associated with. If there are no
    199      * messages recorded, an empty enumeration is returned.</p>
    200      *
    201      * @return An iterator over the messages for all properties.
    202      */
    203     public Iterator get() {
    204         this.accessed = true;
    205 
    206         if (messages.isEmpty()) {
    207             return Collections.EMPTY_LIST.iterator();
    208         }
    209 
    210         ArrayList results = new ArrayList();
    211         ArrayList actionItems = new ArrayList();
    212 
    213         for (Iterator i = messages.values().iterator(); i.hasNext();) {
    214             actionItems.add(i.next());
    215         }
    216 
    217         // Sort ActionMessageItems based on the initial order the
    218         // property/key was added to ActionMessages.
    219         Collections.sort(actionItems, ACTION_ITEM_COMPARATOR);
    220 
    221         for (Iterator i = actionItems.iterator(); i.hasNext();) {
    222             ActionMessageItem ami = (ActionMessageItem) i.next();
    223 
    224             for (Iterator msgsIter = ami.getList().iterator();
    225                 msgsIter.hasNext();) {
    226                 results.add(msgsIter.next());
    227             }
    228         }
    229 
    230         return results.iterator();
    231     }
    232 
    233     /**
    234      * <p>Return the set of messages related to a specific property. If there
    235      * are no such messages, an empty enumeration is returned.</p>
    236      *
    237      * @param property Property name (or ActionMessages.GLOBAL_MESSAGE)
    238      * @return An iterator over the messages for the specified property.
    239      */
    240     public Iterator get(String property) {
    241         this.accessed = true;
    242 
    243         ActionMessageItem item = (ActionMessageItem) messages.get(property);
    244 
    245         if (item == null) {
    246             return (Collections.EMPTY_LIST.iterator());
    247         } else {
    248             return (item.getList().iterator());
    249         }
    250     }
    251 
    252     /**
    253      * <p>Returns <code>true</code> if the <code>get()</code> or
    254      * <code>get(String)</code> methods are called.</p>
    255      *
    256      * @return <code>true</code> if the messages have been accessed one or
    257      *         more times.
    258      * @since Struts 1.2
    259      */
    260     public boolean isAccessed() {
    261         return this.accessed;
    262     }
    263 
    264     /**
    265      * <p>Return the set of property names for which at least one message has
    266      * been recorded. If there are no messages, an empty <code>Iterator</code>
    267      * is returned. If you have recorded global messages, the
    268      * <code>String</code> value of <code>ActionMessages.GLOBAL_MESSAGE</code>
    269      * will be one of the returned property names.</p>
    270      *
    271      * @return An iterator over the property names for which messages exist.
    272      */
    273     public Iterator properties() {
    274         if (messages.isEmpty()) {
    275             return Collections.EMPTY_LIST.iterator();
    276         }
    277 
    278         ArrayList results = new ArrayList();
    279         ArrayList actionItems = new ArrayList();
    280 
    281         for (Iterator i = messages.values().iterator(); i.hasNext();) {
    282             actionItems.add(i.next());
    283         }
    284 
    285         // Sort ActionMessageItems based on the initial order the
    286         // property/key was added to ActionMessages.
    287         Collections.sort(actionItems, ACTION_ITEM_COMPARATOR);
    288 
    289         for (Iterator i = actionItems.iterator(); i.hasNext();) {
    290             ActionMessageItem ami = (ActionMessageItem) i.next();
    291 
    292             results.add(ami.getProperty());
    293         }
    294 
    295         return results.iterator();
    296     }
    297 
    298     /**
    299      * <p>Return the number of messages recorded for all properties (including
    300      * global messages). <strong>NOTE</strong> - it is more efficient to call
    301      * <code>isEmpty</code> if all you care about is whether or not there are
    302      * any messages at all.</p>
    303      *
    304      * @return The number of messages associated with all properties.
    305      */
    306     public int size() {
    307         int total = 0;
    308 
    309         for (Iterator i = messages.values().iterator(); i.hasNext();) {
    310             ActionMessageItem ami = (ActionMessageItem) i.next();
    311 
    312             total += ami.getList().size();
    313         }
    314 
    315         return (total);
    316     }
    317 
    318     /**
    319      * <p>Return the number of messages associated with the specified
    320      * property. </p>
    321      *
    322      * @param property Property name (or ActionMessages.GLOBAL_MESSAGE)
    323      * @return The number of messages associated with the property.
    324      */
    325     public int size(String property) {
    326         ActionMessageItem item = (ActionMessageItem) messages.get(property);
    327 
    328         return (item == null) ? 0 : item.getList().size();
    329     }
    330 
    331     /**
    332      * <p>Returns a String representation of this ActionMessages' property
    333      * name=message list mapping.</p>
    334      *
    335      * @return String representation of the messages
    336      * @see Object#toString()
    337      */
    338     public String toString() {
    339         return this.messages.toString();
    340     }
    341 
    342     /**
    343      * <p>This class is used to store a set of messages associated with a
    344      * property/key and the position it was initially added to list.</p>
    345      */
    346     protected class ActionMessageItem implements Serializable {
    347         /**
    348          * <p>The list of <code>ActionMessage</code>s.</p>
    349          */
    350         protected List list = null;
    351 
    352         /**
    353          * <p>The position in the list of messages.</p>
    354          */
    355         protected int iOrder = 0;
    356 
    357         /**
    358          * <p>The property associated with <code>ActionMessage</code>.</p>
    359          */
    360         protected String property = null;
    361 
    362         /**
    363          * <p>Construct an instance of this class.</p>
    364          *
    365          * @param list     The list of ActionMessages.
    366          * @param iOrder   The position in the list of messages.
    367          * @param property The property associated with ActionMessage.
    368          */
    369         public ActionMessageItem(List list, int iOrder, String property) {
    370             this.list = list;
    371             this.iOrder = iOrder;
    372             this.property = property;
    373         }
    374 
    375         /**
    376          * <p>Retrieve the list of messages associated with this item.</p>
    377          *
    378          * @return The list of messages associated with this item.
    379          */
    380         public List getList() {
    381             return list;
    382         }
    383 
    384         /**
    385          * <p>Set the list of messages associated with this item.</p>
    386          *
    387          * @param list The list of messages associated with this item.
    388          */
    389         public void setList(List list) {
    390             this.list = list;
    391         }
    392 
    393         /**
    394          * <p>Retrieve the position in the message list.</p>
    395          *
    396          * @return The position in the message list.
    397          */
    398         public int getOrder() {
    399             return iOrder;
    400         }
    401 
    402         /**
    403          * <p>Set the position in the message list.</p>
    404          *
    405          * @param iOrder The position in the message list.
    406          */
    407         public void setOrder(int iOrder) {
    408             this.iOrder = iOrder;
    409         }
    410 
    411         /**
    412          * <p>Retrieve the property associated with this item.</p>
    413          *
    414          * @return The property associated with this item.
    415          */
    416         public String getProperty() {
    417             return property;
    418         }
    419 
    420         /**
    421          * <p>Set the property associated with this item.</p>
    422          *
    423          * @param property The property associated with this item.
    424          */
    425         public void setProperty(String property) {
    426             this.property = property;
    427         }
    428 
    429         /**
    430          * <p>Construct a string representation of this object.</p>
    431          *
    432          * @return A string representation of this object.
    433          */
    434         public String toString() {
    435             return this.list.toString();
    436         }
    437     }
    438 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
