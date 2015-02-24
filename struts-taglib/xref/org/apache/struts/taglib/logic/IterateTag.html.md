[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/logic/IterateTag.html.md)


    1   /*
    2    * $Id: IterateTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.logic;
    22  
    23  import org.apache.struts.taglib.TagUtils;
    24  import org.apache.struts.util.IteratorAdapter;
    25  import org.apache.struts.util.MessageResources;
    26  
    27  import javax.servlet.jsp.JspException;
    28  import javax.servlet.jsp.tagext.BodyTagSupport;
    29  
    30  import java.lang.reflect.Array;
    31  
    32  import java.util.ArrayList;
    33  import java.util.Arrays;
    34  import java.util.Collection;
    35  import java.util.Enumeration;
    36  import java.util.Iterator;
    37  import java.util.Map;
    38  
    39  /**
    40   * Custom tag that iterates the elements of a collection, which can be either
    41   * an attribute or the property of an attribute.  The collection can be any of
    42   * the following:  an array of objects, an Enumeration, an Iterator, a
    43   * Collection (which includes Lists, Sets and Vectors), or a Map (which
    44   * includes Hashtables) whose elements will be iterated over.
    45   *
    46   * @version $Rev: 471754 $ $Date: 2004-11-03 14:20:47 -0500 (Wed, 03 Nov 2004)
    47   *          $
    48   */
    49  public class IterateTag extends BodyTagSupport {
    50      /**
    51       * The message resources for this package.
    52       */
    53      protected static MessageResources messages =
    54          MessageResources.getMessageResources(
    55              "org.apache.struts.taglib.logic.LocalStrings");
    56  
    57      // ----------------------------------------------------- Instance Variables
    58  
    59      /**
    60       * Iterator of the elements of this collection, while we are actually
    61       * running.
    62       */
    63      protected Iterator iterator = null;
    64  
    65      /**
    66       * The number of elements we have already rendered.
    67       */
    68      protected int lengthCount = 0;
    69  
    70      /**
    71       * The actual length value (calculated in the start tag).
    72       */
    73      protected int lengthValue = 0;
    74  
    75      /**
    76       * The actual offset value (calculated in the start tag).
    77       */
    78      protected int offsetValue = 0;
    79  
    80      /**
    81       * Has this tag instance been started?
    82       */
    83      protected boolean started = false;
    84  
    85      // ------------------------------------------------------------- Properties
    86  
    87      /**
    88       * The collection over which we will be iterating.
    89       */
    90      protected Object collection = null;
    91  
    92      /**
    93       * The name of the scripting variable to be exposed.
    94       */
    95      protected String id = null;
    96  
    97      /**
    98       * The name of the scripting variable to be exposed as the current index.
    99       */
    100     protected String indexId = null;
    101 
    102     /**
    103      * The length value or attribute name (<=0 means no limit).
    104      */
    105     protected String length = null;
    106 
    107     /**
    108      * The name of the collection or owning bean.
    109      */
    110     protected String name = null;
    111 
    112     /**
    113      * The starting offset (zero relative).
    114      */
    115     protected String offset = null;
    116 
    117     /**
    118      * The property name containing the collection.
    119      */
    120     protected String property = null;
    121 
    122     /**
    123      * The scope of the bean specified by the name property, if any.
    124      */
    125     protected String scope = null;
    126 
    127     /**
    128      * The Java class of each exposed element of the collection.
    129      */
    130     protected String type = null;
    131 
    132     public Object getCollection() {
    133         return (this.collection);
    134     }
    135 
    136     public void setCollection(Object collection) {
    137         this.collection = collection;
    138     }
    139 
    140     public String getId() {
    141         return (this.id);
    142     }
    143 
    144     public void setId(String id) {
    145         this.id = id;
    146     }
    147 
    148     /**
    149      * <p>Return the zero-relative index of the current iteration through the
    150      * loop.  If you specify an <code>offset</code>, the first iteration
    151      * through the loop will have that value; otherwise, the first iteration
    152      * will return zero.</p>
    153      *
    154      * <p>This property is read-only, and gives nested custom tags access to
    155      * this information.  Therefore, it is <strong>only</strong> valid in
    156      * between calls to <code>doStartTag()</code> and <code>doEndTag()</code>.
    157      * </p>
    158      */
    159     public int getIndex() {
    160         if (started) {
    161             return ((offsetValue + lengthCount) - 1);
    162         } else {
    163             return (0);
    164         }
    165     }
    166 
    167     public String getIndexId() {
    168         return (this.indexId);
    169     }
    170 
    171     public void setIndexId(String indexId) {
    172         this.indexId = indexId;
    173     }
    174 
    175     public String getLength() {
    176         return (this.length);
    177     }
    178 
    179     public void setLength(String length) {
    180         this.length = length;
    181     }
    182 
    183     public String getName() {
    184         return (this.name);
    185     }
    186 
    187     public void setName(String name) {
    188         this.name = name;
    189     }
    190 
    191     public String getOffset() {
    192         return (this.offset);
    193     }
    194 
    195     public void setOffset(String offset) {
    196         this.offset = offset;
    197     }
    198 
    199     public String getProperty() {
    200         return (this.property);
    201     }
    202 
    203     public void setProperty(String property) {
    204         this.property = property;
    205     }
    206 
    207     public String getScope() {
    208         return (this.scope);
    209     }
    210 
    211     public void setScope(String scope) {
    212         this.scope = scope;
    213     }
    214 
    215     public String getType() {
    216         return (this.type);
    217     }
    218 
    219     public void setType(String type) {
    220         this.type = type;
    221     }
    222 
    223     // --------------------------------------------------------- Public Methods
    224 
    225     /**
    226      * Construct an iterator for the specified collection, and begin looping
    227      * through the body once per element.
    228      *
    229      * @throws JspException if a JSP exception has occurred
    230      */
    231     public int doStartTag() throws JspException {
    232         // Acquire the collection we are going to iterate over
    233         Object collection = this.collection;
    234 
    235         if (collection == null) {
    236             collection =
    237                 TagUtils.getInstance().lookup(pageContext, name, property,
    238                     scope);
    239         }
    240 
    241         if (collection == null) {
    242             JspException e =
    243                 new JspException(messages.getMessage("iterate.collection"));
    244 
    245             TagUtils.getInstance().saveException(pageContext, e);
    246             throw e;
    247         }
    248 
    249         // Construct an iterator for this collection
    250         if (collection.getClass().isArray()) {
    251             try {
    252                 // If we're lucky, it is an array of objects
    253                 // that we can iterate over with no copying
    254                 iterator = Arrays.asList((Object[]) collection).iterator();
    255             } catch (ClassCastException e) {
    256                 // Rats -- it is an array of primitives
    257                 int length = Array.getLength(collection);
    258                 ArrayList c = new ArrayList(length);
    259 
    260                 for (int i = 0; i < length; i++) {
    261                     c.add(Array.get(collection, i));
    262                 }
    263 
    264                 iterator = c.iterator();
    265             }
    266         } else if (collection instanceof Collection) {
    267             iterator = ((Collection) collection).iterator();
    268         } else if (collection instanceof Iterator) {
    269             iterator = (Iterator) collection;
    270         } else if (collection instanceof Map) {
    271             iterator = ((Map) collection).entrySet().iterator();
    272         } else if (collection instanceof Enumeration) {
    273             iterator = new IteratorAdapter((Enumeration) collection);
    274         } else {
    275             JspException e =
    276                 new JspException(messages.getMessage("iterate.iterator"));
    277 
    278             TagUtils.getInstance().saveException(pageContext, e);
    279             throw e;
    280         }
    281 
    282         // Calculate the starting offset
    283         if (offset == null) {
    284             offsetValue = 0;
    285         } else {
    286             try {
    287                 offsetValue = Integer.parseInt(offset);
    288             } catch (NumberFormatException e) {
    289                 Integer offsetObject =
    290                     (Integer) TagUtils.getInstance().lookup(pageContext,
    291                         offset, null);
    292 
    293                 if (offsetObject == null) {
    294                     offsetValue = 0;
    295                 } else {
    296                     offsetValue = offsetObject.intValue();
    297                 }
    298             }
    299         }
    300 
    301         if (offsetValue < 0) {
    302             offsetValue = 0;
    303         }
    304 
    305         // Calculate the rendering length
    306         if (length == null) {
    307             lengthValue = 0;
    308         } else {
    309             try {
    310                 lengthValue = Integer.parseInt(length);
    311             } catch (NumberFormatException e) {
    312                 Integer lengthObject =
    313                     (Integer) TagUtils.getInstance().lookup(pageContext,
    314                         length, null);
    315 
    316                 if (lengthObject == null) {
    317                     lengthValue = 0;
    318                 } else {
    319                     lengthValue = lengthObject.intValue();
    320                 }
    321             }
    322         }
    323 
    324         if (lengthValue < 0) {
    325             lengthValue = 0;
    326         }
    327 
    328         lengthCount = 0;
    329 
    330         // Skip the leading elements up to the starting offset
    331         for (int i = 0; i < offsetValue; i++) {
    332             if (iterator.hasNext()) {
    333                 iterator.next();
    334             }
    335         }
    336 
    337         // Store the first value and evaluate, or skip the body if none
    338         if (iterator.hasNext()) {
    339             Object element = iterator.next();
    340 
    341             if (element == null) {
    342                 pageContext.removeAttribute(id);
    343             } else {
    344                 pageContext.setAttribute(id, element);
    345             }
    346 
    347             lengthCount++;
    348             started = true;
    349 
    350             if (indexId != null) {
    351                 pageContext.setAttribute(indexId, new Integer(getIndex()));
    352             }
    353 
    354             return (EVAL_BODY_TAG);
    355         } else {
    356             return (SKIP_BODY);
    357         }
    358     }
    359 
    360     /**
    361      * Make the next collection element available and loop, or finish the
    362      * iterations if there are no more elements.
    363      *
    364      * @throws JspException if a JSP exception has occurred
    365      */
    366     public int doAfterBody() throws JspException {
    367         // Render the output from this iteration to the output stream
    368         if (bodyContent != null) {
    369             TagUtils.getInstance().writePrevious(pageContext,
    370                 bodyContent.getString());
    371             bodyContent.clearBody();
    372         }
    373 
    374         // Decide whether to iterate or quit
    375         if ((lengthValue > 0) && (lengthCount >= lengthValue)) {
    376             return (SKIP_BODY);
    377         }
    378 
    379         if (iterator.hasNext()) {
    380             Object element = iterator.next();
    381 
    382             if (element == null) {
    383                 pageContext.removeAttribute(id);
    384             } else {
    385                 pageContext.setAttribute(id, element);
    386             }
    387 
    388             lengthCount++;
    389 
    390             if (indexId != null) {
    391                 pageContext.setAttribute(indexId, new Integer(getIndex()));
    392             }
    393 
    394             return (EVAL_BODY_TAG);
    395         } else {
    396             return (SKIP_BODY);
    397         }
    398     }
    399 
    400     /**
    401      * Clean up after processing this enumeration.
    402      *
    403      * @throws JspException if a JSP exception has occurred
    404      */
    405     public int doEndTag() throws JspException {
    406         // Clean up our started state
    407         started = false;
    408         iterator = null;
    409 
    410         // Continue processing this page
    411         return (EVAL_PAGE);
    412     }
    413 
    414     /**
    415      * Release all allocated resources.
    416      */
    417     public void release() {
    418         super.release();
    419 
    420         iterator = null;
    421         lengthCount = 0;
    422         lengthValue = 0;
    423         offsetValue = 0;
    424 
    425         id = null;
    426         collection = null;
    427         length = null;
    428         name = null;
    429         offset = null;
    430         property = null;
    431         scope = null;
    432         started = false;
    433     }
    434 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
