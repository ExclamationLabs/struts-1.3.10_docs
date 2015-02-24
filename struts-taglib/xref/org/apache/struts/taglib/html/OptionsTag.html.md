[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/OptionsTag.html)


    1   /*
    2    * $Id: OptionsTag.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.html.md;
    22  
    23  import org.apache.commons.beanutils.PropertyUtils;
    24  import org.apache.struts.taglib.TagUtils;
    25  import org.apache.struts.util.IteratorAdapter;
    26  import org.apache.struts.util.MessageResources;
    27  
    28  import javax.servlet.jsp.JspException;
    29  import javax.servlet.jsp.tagext.TagSupport;
    30  
    31  import java.lang.reflect.InvocationTargetException;
    32  
    33  import java.util.Arrays;
    34  import java.util.Collection;
    35  import java.util.Enumeration;
    36  import java.util.Iterator;
    37  import java.util.Map;
    38  
    39  /**
    40   * Tag for creating multiple &lt;select&gt; options from a collection.  The
    41   * associated values displayed to the user may optionally be specified by a
    42   * second collection, or will be the same as the values themselves.  Each
    43   * collection may be an array of objects, a Collection, an Enumeration, an
    44   * Iterator, or a Map. <b>NOTE</b> - This tag requires a Java2 (JDK 1.2 or
    45   * later) platform.
    46   */
    47  public class OptionsTag extends TagSupport {
    48      /**
    49       * The message resources for this package.
    50       */
    51      protected static MessageResources messages =
    52          MessageResources.getMessageResources(Constants.Package
    53              + ".LocalStrings");
    54  
    55      /**
    56       * The name of the collection containing beans that have properties to
    57       * provide both the values and the labels (identified by the
    58       * <code>property</code> and <code>labelProperty</code> attributes).
    59       */
    60      protected String collection = null;
    61  
    62      /**
    63       * Should the label values be filtered for HTML sensitive characters?
    64       */
    65      protected boolean filter = true;
    66  
    67      /**
    68       * The name of the bean containing the labels collection.
    69       */
    70      protected String labelName = null;
    71  
    72      /**
    73       * The bean property containing the labels collection.
    74       */
    75      protected String labelProperty = null;
    76  
    77      /**
    78       * The name of the bean containing the values collection.
    79       */
    80      protected String name = null;
    81  
    82      /**
    83       * The name of the property to use to build the values collection.
    84       */
    85      protected String property = null;
    86  
    87      /**
    88       * The style associated with this tag.
    89       */
    90      private String style = null;
    91  
    92      /**
    93       * The named style class associated with this tag.
    94       */
    95      private String styleClass = null;
    96  
    97      public String getCollection() {
    98          return (this.collection);
    99      }
    100 
    101     public void setCollection(String collection) {
    102         this.collection = collection;
    103     }
    104 
    105     public boolean getFilter() {
    106         return filter;
    107     }
    108 
    109     public void setFilter(boolean filter) {
    110         this.filter = filter;
    111     }
    112 
    113     public String getLabelName() {
    114         return labelName;
    115     }
    116 
    117     public void setLabelName(String labelName) {
    118         this.labelName = labelName;
    119     }
    120 
    121     public String getLabelProperty() {
    122         return labelProperty;
    123     }
    124 
    125     public void setLabelProperty(String labelProperty) {
    126         this.labelProperty = labelProperty;
    127     }
    128 
    129     public String getName() {
    130         return name;
    131     }
    132 
    133     public void setName(String name) {
    134         this.name = name;
    135     }
    136 
    137     public String getProperty() {
    138         return property;
    139     }
    140 
    141     public void setProperty(String property) {
    142         this.property = property;
    143     }
    144 
    145     public String getStyle() {
    146         return style;
    147     }
    148 
    149     public void setStyle(String style) {
    150         this.style = style;
    151     }
    152 
    153     public String getStyleClass() {
    154         return styleClass;
    155     }
    156 
    157     public void setStyleClass(String styleClass) {
    158         this.styleClass = styleClass;
    159     }
    160 
    161     /**
    162      * Process the start of this tag.
    163      *
    164      * @throws JspException if a JSP exception has occurred
    165      */
    166     public int doStartTag() throws JspException {
    167         return SKIP_BODY;
    168     }
    169 
    170     /**
    171      * Process the end of this tag.
    172      *
    173      * @throws JspException if a JSP exception has occurred
    174      */
    175     public int doEndTag() throws JspException {
    176         // Acquire the select tag we are associated with
    177         SelectTag selectTag =
    178             (SelectTag) pageContext.getAttribute(Constants.SELECT_KEY);
    179 
    180         if (selectTag == null) {
    181             throw new JspException(messages.getMessage("optionsTag.select"));
    182         }
    183 
    184         StringBuffer sb = new StringBuffer();
    185 
    186         // If a collection was specified, use that mode to render options
    187         if (collection != null) {
    188             Iterator collIterator = getIterator(collection, null);
    189 
    190             while (collIterator.hasNext()) {
    191                 Object bean = collIterator.next();
    192                 Object value = null;
    193                 Object label = null;
    194 
    195                 try {
    196                     value = PropertyUtils.getProperty(bean, property);
    197 
    198                     if (value == null) {
    199                         value = "";
    200                     }
    201                 } catch (IllegalAccessException e) {
    202                     throw new JspException(messages.getMessage(
    203                             "getter.access", property, collection));
    204                 } catch (InvocationTargetException e) {
    205                     Throwable t = e.getTargetException();
    206 
    207                     throw new JspException(messages.getMessage(
    208                             "getter.result", property, t.toString()));
    209                 } catch (NoSuchMethodException e) {
    210                     throw new JspException(messages.getMessage(
    211                             "getter.method", property, collection));
    212                 }
    213 
    214                 try {
    215                     if (labelProperty != null) {
    216                         label = PropertyUtils.getProperty(bean, labelProperty);
    217                     } else {
    218                         label = value;
    219                     }
    220 
    221                     if (label == null) {
    222                         label = "";
    223                     }
    224                 } catch (IllegalAccessException e) {
    225                     throw new JspException(messages.getMessage(
    226                             "getter.access", labelProperty, collection));
    227                 } catch (InvocationTargetException e) {
    228                     Throwable t = e.getTargetException();
    229 
    230                     throw new JspException(messages.getMessage(
    231                             "getter.result", labelProperty, t.toString()));
    232                 } catch (NoSuchMethodException e) {
    233                     throw new JspException(messages.getMessage(
    234                             "getter.method", labelProperty, collection));
    235                 }
    236 
    237                 String stringValue = value.toString();
    238 
    239                 addOption(sb, stringValue, label.toString(),
    240                     selectTag.isMatched(stringValue));
    241             }
    242         }
    243         // Otherwise, use the separate iterators mode to render options
    244         else {
    245             // Construct iterators for the values and labels collections
    246             Iterator valuesIterator = getIterator(name, property);
    247             Iterator labelsIterator = null;
    248 
    249             if ((labelName != null) || (labelProperty != null)) {
    250                 labelsIterator = getIterator(labelName, labelProperty);
    251             }
    252 
    253             // Render the options tags for each element of the values coll.
    254             while (valuesIterator.hasNext()) {
    255                 Object valueObject = valuesIterator.next();
    256 
    257                 if (valueObject == null) {
    258                     valueObject = "";
    259                 }
    260 
    261                 String value = valueObject.toString();
    262                 String label = value;
    263 
    264                 if ((labelsIterator != null) && labelsIterator.hasNext()) {
    265                     Object labelObject = labelsIterator.next();
    266 
    267                     if (labelObject == null) {
    268                         labelObject = "";
    269                     }
    270 
    271                     label = labelObject.toString();
    272                 }
    273 
    274                 addOption(sb, value, label, selectTag.isMatched(value));
    275             }
    276         }
    277 
    278         TagUtils.getInstance().write(pageContext, sb.toString());
    279 
    280         return EVAL_PAGE;
    281     }
    282 
    283     /**
    284      * Release any acquired resources.
    285      */
    286     public void release() {
    287         super.release();
    288         collection = null;
    289         filter = true;
    290         labelName = null;
    291         labelProperty = null;
    292         name = null;
    293         property = null;
    294         style = null;
    295         styleClass = null;
    296     }
    297 
    298     // ------------------------------------------------------ Protected Methods
    299 
    300     /**
    301      * Add an option element to the specified StringBuffer based on the
    302      * specified parameters. <p> Note that this tag specifically does not
    303      * support the <code>styleId</code> tag attribute, which causes the HTML
    304      * <code>id</code> attribute to be emitted.  This is because the HTML
    305      * specification states that all "id" attributes in a document have to be
    306      * unique.  This tag will likely generate more than one
    307      * <code>option</code> element element, but it cannot use the same
    308      * <code>id</code> value.  It's conceivable some sort of mechanism to
    309      * supply an array of <code>id</code> values could be devised, but that
    310      * doesn't seem to be worth the trouble.
    311      *
    312      * @param sb      StringBuffer accumulating our results
    313      * @param value   Value to be returned to the server for this option
    314      * @param label   Value to be shown to the user for this option
    315      * @param matched Should this value be marked as selected?
    316      */
    317     protected void addOption(StringBuffer sb, String value, String label,
    318         boolean matched) {
    319         sb.append("<option value=\"");
    320 
    321         if (filter) {
    322             sb.append(TagUtils.getInstance().filter(value));
    323         } else {
    324             sb.append(value);
    325         }
    326 
    327         sb.append("\"");
    328 
    329         if (matched) {
    330             sb.append(" selected=\"selected\"");
    331         }
    332 
    333         if (style != null) {
    334             sb.append(" style=\"");
    335             sb.append(style);
    336             sb.append("\"");
    337         }
    338 
    339         if (styleClass != null) {
    340             sb.append(" class=\"");
    341             sb.append(styleClass);
    342             sb.append("\"");
    343         }
    344 
    345         sb.append(">");
    346 
    347         if (filter) {
    348             sb.append(TagUtils.getInstance().filter(label));
    349         } else {
    350             sb.append(label);
    351         }
    352 
    353         sb.append("</option>\r\n");
    354     }
    355 
    356     /**
    357      * Return an iterator for the option labels or values, based on our
    358      * configured properties.
    359      *
    360      * @param name     Name of the bean attribute (if any)
    361      * @param property Name of the bean property (if any)
    362      * @throws JspException if an error occurs
    363      */
    364     protected Iterator getIterator(String name, String property)
    365         throws JspException {
    366         // Identify the bean containing our collection
    367         String beanName = name;
    368 
    369         if (beanName == null) {
    370             beanName = Constants.BEAN_KEY;
    371         }
    372 
    373         Object bean =
    374             TagUtils.getInstance().lookup(pageContext, beanName, null);
    375 
    376         if (bean == null) {
    377             throw new JspException(messages.getMessage("getter.bean", beanName));
    378         }
    379 
    380         // Identify the collection itself
    381         Object collection = bean;
    382 
    383         if (property != null) {
    384             try {
    385                 collection = PropertyUtils.getProperty(bean, property);
    386 
    387                 if (collection == null) {
    388                     throw new JspException(messages.getMessage(
    389                             "getter.property", property));
    390                 }
    391             } catch (IllegalAccessException e) {
    392                 throw new JspException(messages.getMessage("getter.access",
    393                         property, name));
    394             } catch (InvocationTargetException e) {
    395                 Throwable t = e.getTargetException();
    396 
    397                 throw new JspException(messages.getMessage("getter.result",
    398                         property, t.toString()));
    399             } catch (NoSuchMethodException e) {
    400                 throw new JspException(messages.getMessage("getter.method",
    401                         property, name));
    402             }
    403         }
    404 
    405         // Construct and return an appropriate iterator
    406         if (collection.getClass().isArray()) {
    407             collection = Arrays.asList((Object[]) collection);
    408         }
    409 
    410         if (collection instanceof Collection) {
    411             return (((Collection) collection).iterator());
    412         } else if (collection instanceof Iterator) {
    413             return ((Iterator) collection);
    414         } else if (collection instanceof Map) {
    415             return (((Map) collection).entrySet().iterator());
    416         } else if (collection instanceof Enumeration) {
    417             return new IteratorAdapter((Enumeration) collection);
    418         } else {
    419             throw new JspException(messages.getMessage("optionsTag.iterator",
    420                     collection.toString()));
    421         }
    422     }
    423 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
