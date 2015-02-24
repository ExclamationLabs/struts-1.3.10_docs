[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/BaseHandlerTag.html)


    1   /*
    2    * $Id: BaseHandlerTag.java 479633 2006-11-27 14:25:35Z pbenedict $
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
    23  import org.apache.commons.beanutils.BeanUtils;
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.struts.Globals;
    27  import org.apache.struts.action.ActionMessages;
    28  import org.apache.struts.taglib.TagUtils;
    29  import org.apache.struts.taglib.logic.IterateTag;
    30  import org.apache.struts.util.MessageResources;
    31  import org.apache.struts.util.RequestUtils;
    32  
    33  import javax.servlet.jsp.JspException;
    34  import javax.servlet.jsp.PageContext;
    35  import javax.servlet.jsp.tagext.BodyTagSupport;
    36  
    37  import java.lang.reflect.InvocationTargetException;
    38  import java.lang.reflect.Method;
    39  
    40  /**
    41   * Base class for tags that render form elements capable of including
    42   * JavaScript event handlers and/or CSS Style attributes. This class does not
    43   * implement the doStartTag() or doEndTag() methods. Subclasses should provide
    44   * appropriate implementations of these.
    45   *
    46   * @version $Rev: 479633 $ $Date: 2006-11-27 08:25:35 -0600 (Mon, 27 Nov 2006) $
    47   */
    48  public abstract class BaseHandlerTag extends BodyTagSupport {
    49      /**
    50       * Commons Logging instance.
    51       */
    52      private static Log log = LogFactory.getLog(BaseHandlerTag.class);
    53  
    54      // ----------------------------------------------------- Instance Variables
    55  
    56      /**
    57       * The message resources for this package.
    58       */
    59      protected static MessageResources messages =
    60          MessageResources.getMessageResources(Constants.Package
    61              + ".LocalStrings");
    62  
    63      //  Navigation Management
    64  
    65      /**
    66       * Access key character.
    67       */
    68      protected String accesskey = null;
    69  
    70      /**
    71       * Tab index value.
    72       */
    73      protected String tabindex = null;
    74  
    75      //  Indexing ability for Iterate
    76  
    77      /**
    78       * Whether to created indexed names for fields
    79       *
    80       * @since Struts 1.1
    81       */
    82      protected boolean indexed = false;
    83  
    84      //  Mouse Events
    85  
    86      /**
    87       * Mouse click event.
    88       */
    89      private String onclick = null;
    90  
    91      /**
    92       * Mouse double click event.
    93       */
    94      private String ondblclick = null;
    95  
    96      /**
    97       * Mouse over component event.
    98       */
    99      private String onmouseover = null;
    100 
    101     /**
    102      * Mouse exit component event.
    103      */
    104     private String onmouseout = null;
    105 
    106     /**
    107      * Mouse moved over component event.
    108      */
    109     private String onmousemove = null;
    110 
    111     /**
    112      * Mouse pressed on component event.
    113      */
    114     private String onmousedown = null;
    115 
    116     /**
    117      * Mouse released on component event.
    118      */
    119     private String onmouseup = null;
    120 
    121     //  Keyboard Events
    122 
    123     /**
    124      * Key down in component event.
    125      */
    126     private String onkeydown = null;
    127 
    128     /**
    129      * Key released in component event.
    130      */
    131     private String onkeyup = null;
    132 
    133     /**
    134      * Key down and up together in component event.
    135      */
    136     private String onkeypress = null;
    137 
    138     // Text Events
    139 
    140     /**
    141      * Text selected in component event.
    142      */
    143     private String onselect = null;
    144 
    145     /**
    146      * Content changed after component lost focus event.
    147      */
    148     private String onchange = null;
    149 
    150     // Focus Events and States
    151 
    152     /**
    153      * Component lost focus event.
    154      */
    155     private String onblur = null;
    156 
    157     /**
    158      * Component has received focus event.
    159      */
    160     private String onfocus = null;
    161 
    162     /**
    163      * Component is disabled.
    164      */
    165     private boolean disabled = false;
    166 
    167     /**
    168      * Indicates whether 'disabled' is a valid attribute
    169      */
    170     protected boolean doDisabled = true;
    171 
    172     /**
    173      * Component is readonly.
    174      */
    175     private boolean readonly = false;
    176 
    177     /**
    178      * <p>Indicates whether 'readonly' is a valid attribute.</p>
    179      *
    180      * <p>According to the HTML 4.0 Specification &lt;readonly&gt; is valid
    181      * for &lt;input type="text"&gt;, &lt;input type="password"&gt; and
    182      * &lt;textarea"&gt; elements. Therefore, except for those tags this value
    183      * is set to <code>false</code>.</p>
    184      */
    185     protected boolean doReadonly = false;
    186 
    187     // CSS Style Support
    188 
    189     /**
    190      * Style attribute associated with component.
    191      */
    192     private String style = null;
    193 
    194     /**
    195      * Named Style class associated with component.
    196      */
    197     private String styleClass = null;
    198 
    199     /**
    200      * Identifier associated with component.
    201      */
    202     private String styleId = null;
    203 
    204     /**
    205      * The request attribute key for our error messages (if any).
    206      */
    207     private String errorKey = Globals.ERROR_KEY;
    208 
    209     /**
    210      * Style attribute associated with component when errors exist.
    211      */
    212     private String errorStyle = null;
    213 
    214     /**
    215      * Named Style class associated with component when errors exist.
    216      */
    217     private String errorStyleClass = null;
    218 
    219     /**
    220      * Identifier associated with component when errors exist.
    221      */
    222     private String errorStyleId = null;
    223 
    224     // Other Common Attributes
    225 
    226     /**
    227      * The alternate text of this element.
    228      */
    229     private String alt = null;
    230 
    231     /**
    232      * The message resources key of the alternate text.
    233      */
    234     private String altKey = null;
    235 
    236     /**
    237      * The name of the message resources bundle for message lookups.
    238      */
    239     private String bundle = null;
    240 
    241     /**
    242      * The name of the session attribute key for our locale.
    243      */
    244     private String locale = Globals.LOCALE_KEY;
    245     
    246     /**
    247      * The advisory title of this element.
    248      */
    249     private String title = null;
    250 
    251     /**
    252      * The language code of this element.
    253      */
    254     private String lang = null;
    255     
    256     /**
    257      * The direction for weak/neutral text of this element.
    258      */
    259     private String dir = null;
    260 
    261     /**
    262      * The message resources key of the advisory title.
    263      */
    264     private String titleKey = null;
    265     private Class loopTagClass = null;
    266     private Method loopTagGetStatus = null;
    267     private Class loopTagStatusClass = null;
    268     private Method loopTagStatusGetIndex = null;
    269     private boolean triedJstlInit = false;
    270     private boolean triedJstlSuccess = false;
    271 
    272     // ------------------------------------------------------------- Properties
    273     //  Navigation Management
    274 
    275     /**
    276      * Sets the accessKey character.
    277      */
    278     public void setAccesskey(String accessKey) {
    279         this.accesskey = accessKey;
    280     }
    281 
    282     /**
    283      * Returns the accessKey character.
    284      */
    285     public String getAccesskey() {
    286         return (this.accesskey);
    287     }
    288 
    289     /**
    290      * Sets the tabIndex value.
    291      */
    292     public void setTabindex(String tabIndex) {
    293         this.tabindex = tabIndex;
    294     }
    295 
    296     /**
    297      * Returns the tabIndex value.
    298      */
    299     public String getTabindex() {
    300         return (this.tabindex);
    301     }
    302 
    303     //  Indexing ability for Iterate [since Struts 1.1]
    304 
    305     /**
    306      * Sets the indexed value.
    307      *
    308      * @since Struts 1.1
    309      */
    310     public void setIndexed(boolean indexed) {
    311         this.indexed = indexed;
    312     }
    313 
    314     /**
    315      * Returns the indexed value.
    316      *
    317      * @since Struts 1.1
    318      */
    319     public boolean getIndexed() {
    320         return (this.indexed);
    321     }
    322 
    323     // Mouse Events
    324 
    325     /**
    326      * Sets the onClick event handler.
    327      */
    328     public void setOnclick(String onClick) {
    329         this.onclick = onClick;
    330     }
    331 
    332     /**
    333      * Returns the onClick event handler.
    334      */
    335     public String getOnclick() {
    336         return onclick;
    337     }
    338 
    339     /**
    340      * Sets the onDblClick event handler.
    341      */
    342     public void setOndblclick(String onDblClick) {
    343         this.ondblclick = onDblClick;
    344     }
    345 
    346     /**
    347      * Returns the onDblClick event handler.
    348      */
    349     public String getOndblclick() {
    350         return ondblclick;
    351     }
    352 
    353     /**
    354      * Sets the onMouseDown event handler.
    355      */
    356     public void setOnmousedown(String onMouseDown) {
    357         this.onmousedown = onMouseDown;
    358     }
    359 
    360     /**
    361      * Returns the onMouseDown event handler.
    362      */
    363     public String getOnmousedown() {
    364         return onmousedown;
    365     }
    366 
    367     /**
    368      * Sets the onMouseUp event handler.
    369      */
    370     public void setOnmouseup(String onMouseUp) {
    371         this.onmouseup = onMouseUp;
    372     }
    373 
    374     /**
    375      * Returns the onMouseUp event handler.
    376      */
    377     public String getOnmouseup() {
    378         return onmouseup;
    379     }
    380 
    381     /**
    382      * Sets the onMouseMove event handler.
    383      */
    384     public void setOnmousemove(String onMouseMove) {
    385         this.onmousemove = onMouseMove;
    386     }
    387 
    388     /**
    389      * Returns the onMouseMove event handler.
    390      */
    391     public String getOnmousemove() {
    392         return onmousemove;
    393     }
    394 
    395     /**
    396      * Sets the onMouseOver event handler.
    397      */
    398     public void setOnmouseover(String onMouseOver) {
    399         this.onmouseover = onMouseOver;
    400     }
    401 
    402     /**
    403      * Returns the onMouseOver event handler.
    404      */
    405     public String getOnmouseover() {
    406         return onmouseover;
    407     }
    408 
    409     /**
    410      * Sets the onMouseOut event handler.
    411      */
    412     public void setOnmouseout(String onMouseOut) {
    413         this.onmouseout = onMouseOut;
    414     }
    415 
    416     /**
    417      * Returns the onMouseOut event handler.
    418      */
    419     public String getOnmouseout() {
    420         return onmouseout;
    421     }
    422 
    423     // Keyboard Events
    424 
    425     /**
    426      * Sets the onKeyDown event handler.
    427      */
    428     public void setOnkeydown(String onKeyDown) {
    429         this.onkeydown = onKeyDown;
    430     }
    431 
    432     /**
    433      * Returns the onKeyDown event handler.
    434      */
    435     public String getOnkeydown() {
    436         return onkeydown;
    437     }
    438 
    439     /**
    440      * Sets the onKeyUp event handler.
    441      */
    442     public void setOnkeyup(String onKeyUp) {
    443         this.onkeyup = onKeyUp;
    444     }
    445 
    446     /**
    447      * Returns the onKeyUp event handler.
    448      */
    449     public String getOnkeyup() {
    450         return onkeyup;
    451     }
    452 
    453     /**
    454      * Sets the onKeyPress event handler.
    455      */
    456     public void setOnkeypress(String onKeyPress) {
    457         this.onkeypress = onKeyPress;
    458     }
    459 
    460     /**
    461      * Returns the onKeyPress event handler.
    462      */
    463     public String getOnkeypress() {
    464         return onkeypress;
    465     }
    466 
    467     // Text Events
    468 
    469     /**
    470      * Sets the onChange event handler.
    471      */
    472     public void setOnchange(String onChange) {
    473         this.onchange = onChange;
    474     }
    475 
    476     /**
    477      * Returns the onChange event handler.
    478      */
    479     public String getOnchange() {
    480         return onchange;
    481     }
    482 
    483     /**
    484      * Sets the onSelect event handler.
    485      */
    486     public void setOnselect(String onSelect) {
    487         this.onselect = onSelect;
    488     }
    489 
    490     /**
    491      * Returns the onSelect event handler.
    492      */
    493     public String getOnselect() {
    494         return onselect;
    495     }
    496 
    497     // Focus Events and States
    498 
    499     /**
    500      * Sets the onBlur event handler.
    501      */
    502     public void setOnblur(String onBlur) {
    503         this.onblur = onBlur;
    504     }
    505 
    506     /**
    507      * Returns the onBlur event handler.
    508      */
    509     public String getOnblur() {
    510         return onblur;
    511     }
    512 
    513     /**
    514      * Sets the onFocus event handler.
    515      */
    516     public void setOnfocus(String onFocus) {
    517         this.onfocus = onFocus;
    518     }
    519 
    520     /**
    521      * Returns the onFocus event handler.
    522      */
    523     public String getOnfocus() {
    524         return onfocus;
    525     }
    526 
    527     /**
    528      * Sets the disabled event handler.
    529      */
    530     public void setDisabled(boolean disabled) {
    531         this.disabled = disabled;
    532     }
    533 
    534     /**
    535      * Returns the disabled event handler.
    536      */
    537     public boolean getDisabled() {
    538         return disabled;
    539     }
    540 
    541     /**
    542      * Sets the readonly event handler.
    543      */
    544     public void setReadonly(boolean readonly) {
    545         this.readonly = readonly;
    546     }
    547 
    548     /**
    549      * Returns the readonly event handler.
    550      */
    551     public boolean getReadonly() {
    552         return readonly;
    553     }
    554 
    555     // CSS Style Support
    556 
    557     /**
    558      * Sets the style attribute.
    559      */
    560     public void setStyle(String style) {
    561         this.style = style;
    562     }
    563 
    564     /**
    565      * Returns the style attribute.
    566      */
    567     public String getStyle() {
    568         return style;
    569     }
    570 
    571     /**
    572      * Sets the style class attribute.
    573      */
    574     public void setStyleClass(String styleClass) {
    575         this.styleClass = styleClass;
    576     }
    577 
    578     /**
    579      * Returns the style class attribute.
    580      */
    581     public String getStyleClass() {
    582         return styleClass;
    583     }
    584 
    585     /**
    586      * Sets the style id attribute.
    587      */
    588     public void setStyleId(String styleId) {
    589         this.styleId = styleId;
    590     }
    591 
    592     /**
    593      * Returns the style id attribute.
    594      */
    595     public String getStyleId() {
    596         return styleId;
    597     }
    598 
    599     /**
    600      * Returns the error key attribute.
    601      */
    602     public String getErrorKey() {
    603         return errorKey;
    604     }
    605 
    606     /**
    607      * Sets the error key attribute.
    608      */
    609     public void setErrorKey(String errorKey) {
    610         this.errorKey = errorKey;
    611     }
    612 
    613     /**
    614      * Returns the error style attribute.
    615      */
    616     public String getErrorStyle() {
    617         return errorStyle;
    618     }
    619 
    620     /**
    621      * Sets the error style attribute.
    622      */
    623     public void setErrorStyle(String errorStyle) {
    624         this.errorStyle = errorStyle;
    625     }
    626 
    627     /**
    628      * Returns the error style class attribute.
    629      */
    630     public String getErrorStyleClass() {
    631         return errorStyleClass;
    632     }
    633 
    634     /**
    635      * Sets the error style class attribute.
    636      */
    637     public void setErrorStyleClass(String errorStyleClass) {
    638         this.errorStyleClass = errorStyleClass;
    639     }
    640 
    641     /**
    642      * Returns the error style id attribute.
    643      */
    644     public String getErrorStyleId() {
    645         return errorStyleId;
    646     }
    647 
    648     /**
    649      * Sets the error style id attribute.
    650      */
    651     public void setErrorStyleId(String errorStyleId) {
    652         this.errorStyleId = errorStyleId;
    653     }
    654 
    655     // Other Common Elements
    656 
    657     /**
    658      * Returns the alternate text attribute.
    659      */
    660     public String getAlt() {
    661         return alt;
    662     }
    663 
    664     /**
    665      * Sets the alternate text attribute.
    666      */
    667     public void setAlt(String alt) {
    668         this.alt = alt;
    669     }
    670 
    671     /**
    672      * Returns the message resources key of the alternate text.
    673      */
    674     public String getAltKey() {
    675         return altKey;
    676     }
    677 
    678     /**
    679      * Sets the message resources key of the alternate text.
    680      */
    681     public void setAltKey(String altKey) {
    682         this.altKey = altKey;
    683     }
    684 
    685     /**
    686      * Returns the name of the message resources bundle to use.
    687      */
    688     public String getBundle() {
    689         return bundle;
    690     }
    691 
    692     /**
    693      * Sets the name of the message resources bundle to use.
    694      */
    695     public void setBundle(String bundle) {
    696         this.bundle = bundle;
    697     }
    698 
    699     /**
    700      * Returns the name of the session attribute for our locale.
    701      */
    702     public String getLocale() {
    703         return locale;
    704     }
    705 
    706     /**
    707      * Sets the name of the session attribute for our locale.
    708      */
    709     public void setLocale(String locale) {
    710         this.locale = locale;
    711     }
    712 
    713     /**
    714      * Returns the advisory title attribute.
    715      */
    716     public String getTitle() {
    717         return title;
    718     }
    719 
    720     /**
    721      * Sets the advisory title attribute.
    722      */
    723     public void setTitle(String title) {
    724         this.title = title;
    725     }
    726 
    727     /**
    728      * Returns the message resources key of the advisory title.
    729      */
    730     public String getTitleKey() {
    731         return titleKey;
    732     }
    733 
    734     /**
    735      * Sets the message resources key of the advisory title.
    736      */
    737     public void setTitleKey(String titleKey) {
    738         this.titleKey = titleKey;
    739     }
    740 
    741     /**
    742      * Returns the language code of this element.
    743      * 
    744      * @since Struts 1.3.6
    745      */
    746     public String getLang() {
    747         return this.lang;
    748     }
    749 
    750     /**
    751      * Sets the language code of this element.
    752      * 
    753      * @since Struts 1.3.6
    754      */
    755     public void setLang(String lang) {
    756         this.lang = lang;
    757     }
    758 
    759     /**
    760      * Returns the direction for weak/neutral text this element.
    761      * 
    762      * @since Struts 1.3.6
    763      */
    764     public String getDir() {
    765         return this.dir;
    766     }
    767 
    768     /**
    769      * Sets the direction for weak/neutral text of this element.
    770      * 
    771      * @since Struts 1.3.6
    772      */
    773     public void setDir(String dir) {
    774         this.dir = dir;
    775     }
    776 
    777     // --------------------------------------------------------- Public Methods
    778 
    779     /**
    780      * Release any acquired resources.
    781      */
    782     public void release() {
    783         super.release();
    784         accesskey = null;
    785         alt = null;
    786         altKey = null;
    787         bundle = null;
    788         dir = null;
    789         errorKey = Globals.ERROR_KEY;
    790         errorStyle = null;
    791         errorStyleClass = null;
    792         errorStyleId = null;
    793         indexed = false;
    794         lang = null;
    795         locale = Globals.LOCALE_KEY;
    796         onclick = null;
    797         ondblclick = null;
    798         onmouseover = null;
    799         onmouseout = null;
    800         onmousemove = null;
    801         onmousedown = null;
    802         onmouseup = null;
    803         onkeydown = null;
    804         onkeyup = null;
    805         onkeypress = null;
    806         onselect = null;
    807         onchange = null;
    808         onblur = null;
    809         onfocus = null;
    810         disabled = false;
    811         readonly = false;
    812         style = null;
    813         styleClass = null;
    814         styleId = null;
    815         tabindex = null;
    816         title = null;
    817         titleKey = null;
    818     }
    819 
    820     // ------------------------------------------------------ Protected Methods
    821 
    822     /**
    823      * Return the text specified by the literal value or the message resources
    824      * key, if any; otherwise return <code>null</code>.
    825      *
    826      * @param literal Literal text value or <code>null</code>
    827      * @param key     Message resources key or <code>null</code>
    828      * @throws JspException if both arguments are non-null
    829      */
    830     protected String message(String literal, String key)
    831         throws JspException {
    832         if (literal != null) {
    833             if (key != null) {
    834                 JspException e =
    835                     new JspException(messages.getMessage("common.both"));
    836 
    837                 TagUtils.getInstance().saveException(pageContext, e);
    838                 throw e;
    839             } else {
    840                 return (literal);
    841             }
    842         } else {
    843             if (key != null) {
    844                 return TagUtils.getInstance().message(pageContext, getBundle(),
    845                     getLocale(), key);
    846             } else {
    847                 return null;
    848             }
    849         }
    850     }
    851 
    852     private Integer getJstlLoopIndex() {
    853         if (!triedJstlInit) {
    854             triedJstlInit = true;
    855 
    856             try {
    857                 loopTagClass =
    858                     RequestUtils.applicationClass(
    859                         "javax.servlet.jsp.jstl.core.LoopTag");
    860 
    861                 loopTagGetStatus =
    862                     loopTagClass.getDeclaredMethod("getLoopStatus", null);
    863 
    864                 loopTagStatusClass =
    865                     RequestUtils.applicationClass(
    866                         "javax.servlet.jsp.jstl.core.LoopTagStatus");
    867 
    868                 loopTagStatusGetIndex =
    869                     loopTagStatusClass.getDeclaredMethod("getIndex", null);
    870 
    871                 triedJstlSuccess = true;
    872             } catch (ClassNotFoundException ex) {
    873                 // These just mean that JSTL isn't loaded, so ignore
    874             } catch (NoSuchMethodException ex) {
    875             }
    876         }
    877 
    878         if (triedJstlSuccess) {
    879             try {
    880                 Object loopTag =
    881                     findAncestorWithClass(this, loopTagClass);
    882 
    883                 if (loopTag == null) {
    884                     return null;
    885                 }
    886 
    887                 Object status = loopTagGetStatus.invoke(loopTag, null);
    888 
    889                 return (Integer) loopTagStatusGetIndex.invoke(status, null);
    890             } catch (IllegalAccessException ex) {
    891                 log.error(ex.getMessage(), ex);
    892             } catch (IllegalArgumentException ex) {
    893                 log.error(ex.getMessage(), ex);
    894             } catch (InvocationTargetException ex) {
    895                 log.error(ex.getMessage(), ex);
    896             } catch (NullPointerException ex) {
    897                 log.error(ex.getMessage(), ex);
    898             } catch (ExceptionInInitializerError ex) {
    899                 log.error(ex.getMessage(), ex);
    900             }
    901         }
    902 
    903         return null;
    904     }
    905 
    906     /**
    907      * Appends bean name with index in brackets for tags with 'true' value in
    908      * 'indexed' attribute.
    909      *
    910      * @param handlers The StringBuffer that output will be appended to.
    911      * @throws JspException if 'indexed' tag used outside of iterate tag.
    912      */
    913     protected void prepareIndex(StringBuffer handlers, String name)
    914         throws JspException {
    915         if (name != null) {
    916             handlers.append(name);
    917         }
    918 
    919         handlers.append("[");
    920         handlers.append(getIndexValue());
    921         handlers.append("]");
    922 
    923         if (name != null) {
    924             handlers.append(".");
    925         }
    926     }
    927 
    928     /**
    929      * Returns the index value for tags with 'true' value in 'indexed'
    930      * attribute.
    931      *
    932      * @return the index value.
    933      * @throws JspException if 'indexed' tag used outside of iterate tag.
    934      */
    935     protected int getIndexValue()
    936         throws JspException {
    937         // look for outer iterate tag
    938         IterateTag iterateTag =
    939             (IterateTag) findAncestorWithClass(this, IterateTag.class);
    940 
    941         if (iterateTag != null) {
    942             return iterateTag.getIndex();
    943         }
    944 
    945         // Look for JSTL loops
    946         Integer i = getJstlLoopIndex();
    947 
    948         if (i != null) {
    949             return i.intValue();
    950         }
    951 
    952         // this tag should be nested in an IterateTag or JSTL loop tag, if it's not, throw exception
    953         JspException e =
    954             new JspException(messages.getMessage("indexed.noEnclosingIterate"));
    955 
    956         TagUtils.getInstance().saveException(pageContext, e);
    957         throw e;
    958     }
    959 
    960     /**
    961      * Prepares the style attributes for inclusion in the component's HTML
    962      * tag.
    963      *
    964      * @return The prepared String for inclusion in the HTML tag.
    965      * @throws JspException if invalid attributes are specified
    966      */
    967     protected String prepareStyles()
    968         throws JspException {
    969         StringBuffer styles = new StringBuffer();
    970 
    971         boolean errorsExist = doErrorsExist();
    972 
    973         if (errorsExist && (getErrorStyleId() != null)) {
    974             prepareAttribute(styles, "id", getErrorStyleId());
    975         } else {
    976             prepareAttribute(styles, "id", getStyleId());
    977         }
    978 
    979         if (errorsExist && (getErrorStyle() != null)) {
    980             prepareAttribute(styles, "style", getErrorStyle());
    981         } else {
    982             prepareAttribute(styles, "style", getStyle());
    983         }
    984 
    985         if (errorsExist && (getErrorStyleClass() != null)) {
    986             prepareAttribute(styles, "class", getErrorStyleClass());
    987         } else {
    988             prepareAttribute(styles, "class", getStyleClass());
    989         }
    990 
    991         prepareAttribute(styles, "title", message(getTitle(), getTitleKey()));
    992         prepareAttribute(styles, "alt", message(getAlt(), getAltKey()));
    993         prepareInternationalization(styles);
    994 
    995         return styles.toString();
    996     }
    997 
    998     /**
    999      * Determine if there are errors for the component.
    1000      *
    1001      * @return Whether errors exist.
    1002      */
    1003     protected boolean doErrorsExist()
    1004         throws JspException {
    1005         boolean errorsExist = false;
    1006 
    1007         if ((getErrorStyleId() != null) || (getErrorStyle() != null)
    1008             || (getErrorStyleClass() != null)) {
    1009             String actualName = prepareName();
    1010 
    1011             if (actualName != null) {
    1012                 ActionMessages errors =
    1013                     TagUtils.getInstance().getActionMessages(pageContext,
    1014                         errorKey);
    1015 
    1016                 errorsExist = ((errors != null)
    1017                     && (errors.size(actualName) > 0));
    1018             }
    1019         }
    1020 
    1021         return errorsExist;
    1022     }
    1023 
    1024     /**
    1025      * Prepares the actual name of the component.
    1026      *
    1027      * @return The actual component name.
    1028      */
    1029     protected String prepareName()
    1030         throws JspException {
    1031         return null;
    1032     }
    1033     
    1034     /**
    1035      * Prepares the event handlers for inclusion in the component's HTML tag.
    1036      *
    1037      * @return The prepared String for inclusion in the HTML tag.
    1038      */
    1039     protected String prepareEventHandlers() {
    1040         StringBuffer handlers = new StringBuffer();
    1041 
    1042         prepareMouseEvents(handlers);
    1043         prepareKeyEvents(handlers);
    1044         prepareTextEvents(handlers);
    1045         prepareFocusEvents(handlers);
    1046 
    1047         return handlers.toString();
    1048     }
    1049 
    1050     /**
    1051      * Prepares the mouse event handlers, appending them to the the given
    1052      * StringBuffer.
    1053      *
    1054      * @param handlers The StringBuffer that output will be appended to.
    1055      */
    1056     protected void prepareMouseEvents(StringBuffer handlers) {
    1057         prepareAttribute(handlers, "onclick", getOnclick());
    1058         prepareAttribute(handlers, "ondblclick", getOndblclick());
    1059         prepareAttribute(handlers, "onmouseover", getOnmouseover());
    1060         prepareAttribute(handlers, "onmouseout", getOnmouseout());
    1061         prepareAttribute(handlers, "onmousemove", getOnmousemove());
    1062         prepareAttribute(handlers, "onmousedown", getOnmousedown());
    1063         prepareAttribute(handlers, "onmouseup", getOnmouseup());
    1064     }
    1065 
    1066     /**
    1067      * Prepares the keyboard event handlers, appending them to the the given
    1068      * StringBuffer.
    1069      *
    1070      * @param handlers The StringBuffer that output will be appended to.
    1071      */
    1072     protected void prepareKeyEvents(StringBuffer handlers) {
    1073         prepareAttribute(handlers, "onkeydown", getOnkeydown());
    1074         prepareAttribute(handlers, "onkeyup", getOnkeyup());
    1075         prepareAttribute(handlers, "onkeypress", getOnkeypress());
    1076     }
    1077 
    1078     /**
    1079      * Prepares the text event handlers, appending them to the the given
    1080      * StringBuffer.
    1081      *
    1082      * @param handlers The StringBuffer that output will be appended to.
    1083      */
    1084     protected void prepareTextEvents(StringBuffer handlers) {
    1085         prepareAttribute(handlers, "onselect", getOnselect());
    1086         prepareAttribute(handlers, "onchange", getOnchange());
    1087     }
    1088 
    1089     /**
    1090      * Prepares the focus event handlers, appending them to the the given
    1091      * StringBuffer.
    1092      *
    1093      * @param handlers The StringBuffer that output will be appended to.
    1094      */
    1095     protected void prepareFocusEvents(StringBuffer handlers) {
    1096         prepareAttribute(handlers, "onblur", getOnblur());
    1097         prepareAttribute(handlers, "onfocus", getOnfocus());
    1098 
    1099         // Get the parent FormTag (if necessary)
    1100         FormTag formTag = null;
    1101 
    1102         if ((doDisabled && !getDisabled()) || (doReadonly && !getReadonly())) {
    1103             formTag =
    1104                 (FormTag) pageContext.getAttribute(Constants.FORM_KEY,
    1105                     PageContext.REQUEST_SCOPE);
    1106         }
    1107 
    1108         // Format Disabled
    1109         if (doDisabled) {
    1110             boolean formDisabled =
    1111                 (formTag == null) ? false : formTag.isDisabled();
    1112 
    1113             if (formDisabled || getDisabled()) {
    1114                 handlers.append(" disabled=\"disabled\"");
    1115             }
    1116         }
    1117 
    1118         // Format Read Only
    1119         if (doReadonly) {
    1120             boolean formReadOnly =
    1121                 (formTag == null) ? false : formTag.isReadonly();
    1122 
    1123             if (formReadOnly || getReadonly()) {
    1124                 handlers.append(" readonly=\"readonly\"");
    1125             }
    1126         }
    1127     }
    1128 
    1129     /**
    1130      * Prepares the internationalization attribtes, appending them to the the given
    1131      * StringBuffer.
    1132      *
    1133      * @param handlers The StringBuffer that output will be appended to.
    1134      * @since Struts 1.3.6
    1135      */
    1136     protected void prepareInternationalization(StringBuffer handlers) {
    1137         prepareAttribute(handlers, "lang", getLang());
    1138         prepareAttribute(handlers, "dir", getDir());
    1139     }
    1140 
    1141     /**
    1142      * 'Hook' to enable tags to be extended and additional attributes added.
    1143      *
    1144      * @param handlers The StringBuffer that output will be appended to.
    1145      */
    1146     protected void prepareOtherAttributes(StringBuffer handlers) {
    1147     }
    1148 
    1149     /**
    1150      * Prepares an attribute if the value is not null, appending it to the the
    1151      * given StringBuffer.
    1152      *
    1153      * @param handlers The StringBuffer that output will be appended to.
    1154      */
    1155     protected void prepareAttribute(StringBuffer handlers, String name,
    1156         Object value) {
    1157         if (value != null) {
    1158             handlers.append(" ");
    1159             handlers.append(name);
    1160             handlers.append("=\"");
    1161             handlers.append(value);
    1162             handlers.append("\"");
    1163         }
    1164     }
    1165 
    1166     /**
    1167      * Allows HTML tags to find out if they're nested within an
    1168      * %lt.html.md:html&gt; tag that has xhtml set to true.
    1169      *
    1170      * @return true if the tag is nested within an.html.md tag with xhtml set to
    1171      *         true, false otherwise.
    1172      * @since Struts 1.1
    1173      */
    1174     protected boolean is.html.md() {
    1175         return TagUtils.getInstance().is.html.md(this.pageContext);
    1176     }
    1177 
    1178     /**
    1179      * Returns the closing brace for an input element depending on .html.md
    1180      * status.  The tag must be nested within an %lt.html.md:html&gt; tag that
    1181      * has .html.md set to true.
    1182      *
    1183      * @return String - &gt; if .html.md is false, /&gt; if xhtml is true
    1184      * @since Struts 1.1
    1185      */
    1186     protected String getElementClose() {
    1187         return this.is.html.md() ? " />" : ">";
    1188     }
    1189 
    1190     /**
    1191      * Searches all scopes for the bean and calls BeanUtils.getProperty() with
    1192      * the given arguments and converts any exceptions into JspException.
    1193      *
    1194      * @param beanName The name of the object to get the property from.
    1195      * @param property The name of the property to get.
    1196      * @return The value of the property.
    1197      * @throws JspException
    1198      * @since Struts 1.1
    1199      */
    1200     protected String lookupProperty(String beanName, String property)
    1201         throws JspException {
    1202         Object bean =
    1203             TagUtils.getInstance().lookup(this.pageContext, beanName, null);
    1204 
    1205         if (bean == null) {
    1206             throw new JspException(messages.getMessage("getter.bean", beanName));
    1207         }
    1208 
    1209         try {
    1210             return BeanUtils.getProperty(bean, property);
    1211         } catch (IllegalAccessException e) {
    1212             throw new JspException(messages.getMessage("getter.access",
    1213                     property, beanName));
    1214         } catch (InvocationTargetException e) {
    1215             Throwable t = e.getTargetException();
    1216 
    1217             throw new JspException(messages.getMessage("getter.result",
    1218                     property, t.toString()));
    1219         } catch (NoSuchMethodException e) {
    1220             throw new JspException(messages.getMessage("getter.method",
    1221                     property, beanName));
    1222         }
    1223     }
    1224 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
