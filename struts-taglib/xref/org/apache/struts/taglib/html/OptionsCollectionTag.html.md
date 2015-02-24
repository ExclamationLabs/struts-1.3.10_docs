[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/OptionsCollectionTag.html)


    1   /*
    2    * $Id: OptionsCollectionTag.java 471754 2006-11-06 14:55:09Z husted $
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
    40   * Tag for creating multiple &lt;select&gt; options from a collection. The
    41   * collection may be part of the enclosing form, or may be independent of the
    42   * form. Each element of the collection must expose a 'label' and a 'value',
    43   * the property names of which are configurable by attributes of this tag. <p>
    44   * The collection may be an array of objects, a Collection, an Enumeration, an
    45   * Iterator, or a Map. <p> <b>NOTE</b> - This tag requires a Java2 (JDK 1.2 or
    46   * later) platform.
    47   *
    48   * @version $Rev: 471754 $ $Date: 2004-11-03 14:20:47 -0500 (Wed, 03 Nov 2004)
    49   *          $
    50   * @since Struts 1.1
    51   */
    52  public class OptionsCollectionTag extends TagSupport {
    53      // ----------------------------------------------------- Instance Variables
    54  
    55      /**
    56       * The message resources for this package.
    57       */
    58      protected static MessageResources messages =
    59          MessageResources.getMessageResources(Constants.Package
    60              + ".LocalStrings");
    61  
    62      // ------------------------------------------------------------- Properties
    63  
    64      /**
    65       * Should the label values be filtered for HTML sensitive characters?
    66       */
    67      protected boolean filter = true;
    68  
    69      /**
    70       * The name of the bean property containing the label.
    71       */
    72      protected String label = "label";
    73  
    74      /**
    75       * The name of the bean containing the values collection.
    76       */
    77      protected String name = Constants.BEAN_KEY;
    78  
    79      /**
    80       * The name of the property to use to build the values collection.
    81       */
    82      protected String property = null;
    83  
    84      /**
    85       * The style associated with this tag.
    86       */
    87      private String style = null;
    88  
    89      /**
    90       * The named style class associated with this tag.
    91       */
    92      private String styleClass = null;
    93  
    94      /**
    95       * The name of the bean property containing the value.
    96       */
    97      protected String value = "value";
    98  
    99      public boolean getFilter() {
    100         return filter;
    101     }
    102 
    103     public void setFilter(boolean filter) {
    104         this.filter = filter;
    105     }
    106 
    107     public String getLabel() {
    108         return label;
    109     }
    110 
    111     public void setLabel(String label) {
    112         this.label = label;
    113     }
    114 
    115     public String getName() {
    116         return name;
    117     }
    118 
    119     public void setName(String name) {
    120         this.name = name;
    121     }
    122 
    123     public String getProperty() {
    124         return property;
    125     }
    126 
    127     public void setProperty(String property) {
    128         this.property = property;
    129     }
    130 
    131     public String getStyle() {
    132         return style;
    133     }
    134 
    135     public void setStyle(String style) {
    136         this.style = style;
    137     }
    138 
    139     public String getStyleClass() {
    140         return styleClass;
    141     }
    142 
    143     public void setStyleClass(String styleClass) {
    144         this.styleClass = styleClass;
    145     }
    146 
    147     public String getValue() {
    148         return value;
    149     }
    150 
    151     public void setValue(String value) {
    152         this.value = value;
    153     }
    154 
    155     // --------------------------------------------------------- Public Methods
    156 
    157     /**
    158      * Process the start of this tag.
    159      *
    160      * @throws JspException if a JSP exception has occurred
    161      */
    162     public int doStartTag() throws JspException {
    163         // Acquire the select tag we are associated with
    164         SelectTag selectTag =
    165             (SelectTag) pageContext.getAttribute(Constants.SELECT_KEY);
    166 
    167         if (selectTag == null) {
    168             JspException e =
    169                 new JspException(messages.getMessage(
    170                         "optionsCollectionTag.select"));
    171 
    172             TagUtils.getInstance().saveException(pageContext, e);
    173             throw e;
    174         }
    175 
    176         // Acquire the collection containing our options
    177         Object collection =
    178             TagUtils.getInstance().lookup(pageContext, name, property, null);
    179 
    180         if (collection == null) {
    181             JspException e =
    182                 new JspException(messages.getMessage(
    183                         "optionsCollectionTag.collection"));
    184 
    185             TagUtils.getInstance().saveException(pageContext, e);
    186             throw e;
    187         }
    188 
    189         // Acquire an iterator over the options collection
    190         Iterator iter = getIterator(collection);
    191 
    192         StringBuffer sb = new StringBuffer();
    193 
    194         // Render the options
    195         while (iter.hasNext()) {
    196             Object bean = iter.next();
    197             Object beanLabel = null;
    198             Object beanValue = null;
    199 
    200             // Get the label for this option
    201             try {
    202                 beanLabel = PropertyUtils.getProperty(bean, label);
    203 
    204                 if (beanLabel == null) {
    205                     beanLabel = "";
    206                 }
    207             } catch (IllegalAccessException e) {
    208                 JspException jspe =
    209                     new JspException(messages.getMessage("getter.access",
    210                             label, bean));
    211 
    212                 TagUtils.getInstance().saveException(pageContext, jspe);
    213                 throw jspe;
    214             } catch (InvocationTargetException e) {
    215                 Throwable t = e.getTargetException();
    216                 JspException jspe =
    217                     new JspException(messages.getMessage("getter.result",
    218                             label, t.toString()));
    219 
    220                 TagUtils.getInstance().saveException(pageContext, jspe);
    221                 throw jspe;
    222             } catch (NoSuchMethodException e) {
    223                 JspException jspe =
    224                     new JspException(messages.getMessage("getter.method",
    225                             label, bean));
    226 
    227                 TagUtils.getInstance().saveException(pageContext, jspe);
    228                 throw jspe;
    229             }
    230 
    231             // Get the value for this option
    232             try {
    233                 beanValue = PropertyUtils.getProperty(bean, value);
    234 
    235                 if (beanValue == null) {
    236                     beanValue = "";
    237                 }
    238             } catch (IllegalAccessException e) {
    239                 JspException jspe =
    240                     new JspException(messages.getMessage("getter.access",
    241                             value, bean));
    242 
    243                 TagUtils.getInstance().saveException(pageContext, jspe);
    244                 throw jspe;
    245             } catch (InvocationTargetException e) {
    246                 Throwable t = e.getTargetException();
    247                 JspException jspe =
    248                     new JspException(messages.getMessage("getter.result",
    249                             value, t.toString()));
    250 
    251                 TagUtils.getInstance().saveException(pageContext, jspe);
    252                 throw jspe;
    253             } catch (NoSuchMethodException e) {
    254                 JspException jspe =
    255                     new JspException(messages.getMessage("getter.method",
    256                             value, bean));
    257 
    258                 TagUtils.getInstance().saveException(pageContext, jspe);
    259                 throw jspe;
    260             }
    261 
    262             String stringLabel = beanLabel.toString();
    263             String stringValue = beanValue.toString();
    264 
    265             // Render this option
    266             addOption(sb, stringLabel, stringValue,
    267                 selectTag.isMatched(stringValue));
    268         }
    269 
    270         TagUtils.getInstance().write(pageContext, sb.toString());
    271 
    272         return SKIP_BODY;
    273     }
    274 
    275     /**
    276      * Release any acquired resources.
    277      */
    278     public void release() {
    279         super.release();
    280         filter = true;
    281         label = "label";
    282         name = Constants.BEAN_KEY;
    283         property = null;
    284         style = null;
    285         styleClass = null;
    286         value = "value";
    287     }
    288 
    289     // ------------------------------------------------------ Protected Methods
    290 
    291     /**
    292      * Add an option element to the specified StringBuffer based on the
    293      * specified parameters. <p> Note that this tag specifically does not
    294      * support the <code>styleId</code> tag attribute, which causes the HTML
    295      * <code>id</code> attribute to be emitted.  This is because the HTML
    296      * specification states that all "id" attributes in a document have to be
    297      * unique.  This tag will likely generate more than one
    298      * <code>option</code> element element, but it cannot use the same
    299      * <code>id</code> value.  It's conceivable some sort of mechanism to
    300      * supply an array of <code>id</code> values could be devised, but that
    301      * doesn't seem to be worth the trouble.
    302      *
    303      * @param sb      StringBuffer accumulating our results
    304      * @param value   Value to be returned to the server for this option
    305      * @param label   Value to be shown to the user for this option
    306      * @param matched Should this value be marked as selected?
    307      */
    308     protected void addOption(StringBuffer sb, String label, String value,
    309         boolean matched) {
    310         sb.append("<option value=\"");
    311 
    312         if (filter) {
    313             sb.append(TagUtils.getInstance().filter(value));
    314         } else {
    315             sb.append(value);
    316         }
    317 
    318         sb.append("\"");
    319 
    320         if (matched) {
    321             sb.append(" selected=\"selected\"");
    322         }
    323 
    324         if (style != null) {
    325             sb.append(" style=\"");
    326             sb.append(style);
    327             sb.append("\"");
    328         }
    329 
    330         if (styleClass != null) {
    331             sb.append(" class=\"");
    332             sb.append(styleClass);
    333             sb.append("\"");
    334         }
    335 
    336         sb.append(">");
    337 
    338         if (filter) {
    339             sb.append(TagUtils.getInstance().filter(label));
    340         } else {
    341             sb.append(label);
    342         }
    343 
    344         sb.append("</option>\r\n");
    345     }
    346 
    347     /**
    348      * Return an iterator for the options collection.
    349      *
    350      * @param collection Collection to be iterated over
    351      * @throws JspException if an error occurs
    352      */
    353     protected Iterator getIterator(Object collection)
    354         throws JspException {
    355         if (collection.getClass().isArray()) {
    356             collection = Arrays.asList((Object[]) collection);
    357         }
    358 
    359         if (collection instanceof Collection) {
    360             return (((Collection) collection).iterator());
    361         } else if (collection instanceof Iterator) {
    362             return ((Iterator) collection);
    363         } else if (collection instanceof Map) {
    364             return (((Map) collection).entrySet().iterator());
    365         } else if (collection instanceof Enumeration) {
    366             return new IteratorAdapter((Enumeration) collection);
    367         } else {
    368             throw new JspException(messages.getMessage(
    369                     "optionsCollectionTag.iterator", collection.toString()));
    370         }
    371     }
    372 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
