[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/component/CommandLinkComponent.html.md)


    1   /*
    2    * $Id: CommandLinkComponent.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.component;
    23  
    24  
    25  import javax.faces.component.UICommand;
    26  import javax.faces.context.FacesContext;
    27  import javax.faces.el.ValueBinding;
    28  
    29  
    30  /**
    31   * <p>Custom component that emulates the JSF standard component class
    32   * <code>javax.faces.component.html.md.HtmlCommandLink</code> (and its
    33   * corresponding renderer) but is not tied to a particular implementation of
    34   * renderer for <code>javax.faces.component.UIForm</code>.</p>
    35   */
    36  
    37  public class CommandLinkComponent extends UICommand {
    38  
    39  
    40      // ------------------------------------------------------------ Constructors
    41  
    42  
    43      /**
    44       * <p>Create a new {@link CommandLinkComponent} with default properties.</p>
    45       */
    46      public CommandLinkComponent() {
    47  
    48          super();
    49          setRendererType("org.apache.struts.faces.CommandLink");
    50  
    51      }
    52  
    53  
    54      // ------------------------------------------------------ Instance Variables
    55  
    56  
    57      private String accesskey = null;
    58      private String charset = null;
    59      private String dir = null;
    60      private String hreflang = null;
    61      private String lang = null;
    62      private String onblur = null;
    63      private String onclick = null;
    64      private String ondblclick = null;
    65      private String onfocus = null;
    66      private String onkeydown = null;
    67      private String onkeypress = null;
    68      private String onkeyup = null;
    69      private String onmousedown = null;
    70      private String onmousemove = null;
    71      private String onmouseout = null;
    72      private String onmouseover = null;
    73      private String onmouseup = null;
    74      private String rel = null;
    75      private String rev = null;
    76      private String style = null;
    77      private String styleClass = null;
    78      private String tabindex = null;
    79      private String target = null;
    80      private String title = null;
    81      private String type = null;
    82  
    83  
    84  
    85      // ---------------------------------------------------- Component Properties
    86  
    87  
    88      public String getAccesskey() {
    89          ValueBinding vb = getValueBinding("accesskey");
    90          if (vb != null) {
    91              return (String) vb.getValue(getFacesContext());
    92          } else {
    93              return accesskey;
    94          }
    95      }
    96  
    97      public void setAccesskey(String accesskey) {
    98          this.accesskey = accesskey;
    99      }
    100 
    101 
    102     public String getCharset() {
    103         ValueBinding vb = getValueBinding("charset");
    104         if (vb != null) {
    105             return (String) vb.getValue(getFacesContext());
    106         } else {
    107             return charset;
    108         }
    109     }
    110 
    111     public void setCharset(String charset) {
    112         this.charset = charset;
    113     }
    114 
    115 
    116     public String getDir() {
    117         ValueBinding vb = getValueBinding("dir");
    118         if (vb != null) {
    119             return (String) vb.getValue(getFacesContext());
    120         } else {
    121             return dir;
    122         }
    123     }
    124 
    125     public void setDir(String dir) {
    126         this.dir = dir;
    127     }
    128 
    129 
    130     /**
    131      * <p>Return the component family to which this component belongs.</p>
    132      */
    133     public String getFamily() {
    134 
    135         return "org.apache.struts.faces.CommandLink";
    136 
    137     }
    138 
    139 
    140     public String getHreflang() {
    141         ValueBinding vb = getValueBinding("hreflang");
    142         if (vb != null) {
    143             return (String) vb.getValue(getFacesContext());
    144         } else {
    145             return hreflang;
    146         }
    147     }
    148 
    149     public void setHreflang(String hreflang) {
    150         this.hreflang = hreflang;
    151     }
    152 
    153 
    154     public String getLang() {
    155         ValueBinding vb = getValueBinding("lang");
    156         if (vb != null) {
    157             return (String) vb.getValue(getFacesContext());
    158         } else {
    159             return lang;
    160         }
    161     }
    162 
    163     public void setLang(String lang) {
    164         this.lang = lang;
    165     }
    166 
    167 
    168     public String getOnblur() {
    169         ValueBinding vb = getValueBinding("onblur");
    170         if (vb != null) {
    171             return (String) vb.getValue(getFacesContext());
    172         } else {
    173             return onblur;
    174         }
    175     }
    176 
    177     public void setOnblur(String onblur) {
    178         this.onblur = onblur;
    179     }
    180 
    181 
    182     public String getOnclick() {
    183         ValueBinding vb = getValueBinding("onclick");
    184         if (vb != null) {
    185             return (String) vb.getValue(getFacesContext());
    186         } else {
    187             return onclick;
    188         }
    189     }
    190 
    191     public void setOnclick(String onclick) {
    192         this.onclick = onclick;
    193     }
    194 
    195 
    196     public String getOndblclick() {
    197         ValueBinding vb = getValueBinding("ondblclick");
    198         if (vb != null) {
    199             return (String) vb.getValue(getFacesContext());
    200         } else {
    201             return ondblclick;
    202         }
    203     }
    204 
    205     public void setOndblclick(String ondblclick) {
    206         this.ondblclick = ondblclick;
    207     }
    208 
    209 
    210     public String getOnfocus() {
    211         ValueBinding vb = getValueBinding("onfocus");
    212         if (vb != null) {
    213             return (String) vb.getValue(getFacesContext());
    214         } else {
    215             return onfocus;
    216         }
    217     }
    218 
    219     public void setOnfocus(String onfocus) {
    220         this.onfocus = onfocus;
    221     }
    222 
    223 
    224     public String getOnkeydown() {
    225         ValueBinding vb = getValueBinding("onkeydown");
    226         if (vb != null) {
    227             return (String) vb.getValue(getFacesContext());
    228         } else {
    229             return onkeydown;
    230         }
    231     }
    232 
    233     public void setOnkeydown(String onkeydown) {
    234         this.onkeydown = onkeydown;
    235     }
    236 
    237 
    238     public String getOnkeypress() {
    239         ValueBinding vb = getValueBinding("onkeypress");
    240         if (vb != null) {
    241             return (String) vb.getValue(getFacesContext());
    242         } else {
    243             return onkeypress;
    244         }
    245     }
    246 
    247     public void setOnkeypress(String onkeypress) {
    248         this.onkeypress = onkeypress;
    249     }
    250 
    251 
    252     public String getOnkeyup() {
    253         ValueBinding vb = getValueBinding("onkeyup");
    254         if (vb != null) {
    255             return (String) vb.getValue(getFacesContext());
    256         } else {
    257             return onkeyup;
    258         }
    259     }
    260 
    261     public void setOnkeyup(String onkeyup) {
    262         this.onkeyup = onkeyup;
    263     }
    264 
    265 
    266     public String getOnmousedown() {
    267         ValueBinding vb = getValueBinding("onmousedown");
    268         if (vb != null) {
    269             return (String) vb.getValue(getFacesContext());
    270         } else {
    271             return onmousedown;
    272         }
    273     }
    274 
    275     public void setOnmousedown(String onmousedown) {
    276         this.onmousedown = onmousedown;
    277     }
    278 
    279 
    280     public String getOnmousemove() {
    281         ValueBinding vb = getValueBinding("onmousemove");
    282         if (vb != null) {
    283             return (String) vb.getValue(getFacesContext());
    284         } else {
    285             return onmousemove;
    286         }
    287     }
    288 
    289     public void setOnmousemove(String onmousemove) {
    290         this.onmousemove = onmousemove;
    291     }
    292 
    293 
    294     public String getOnmouseout() {
    295         ValueBinding vb = getValueBinding("onmouseout");
    296         if (vb != null) {
    297             return (String) vb.getValue(getFacesContext());
    298         } else {
    299             return onmouseout;
    300         }
    301     }
    302 
    303     public void setOnmouseout(String onmouseout) {
    304         this.onmouseout = onmouseout;
    305     }
    306 
    307 
    308     public String getOnmouseover() {
    309         ValueBinding vb = getValueBinding("onmouseover");
    310         if (vb != null) {
    311             return (String) vb.getValue(getFacesContext());
    312         } else {
    313             return onmouseover;
    314         }
    315     }
    316 
    317     public void setOnmouseover(String onmouseover) {
    318         this.onmouseover = onmouseover;
    319     }
    320 
    321 
    322     public String getOnmouseup() {
    323         ValueBinding vb = getValueBinding("onmouseup");
    324         if (vb != null) {
    325             return (String) vb.getValue(getFacesContext());
    326         } else {
    327             return onmouseup;
    328         }
    329     }
    330 
    331     public void setOnmouseup(String onmouseup) {
    332         this.onmouseup = onmouseup;
    333     }
    334 
    335 
    336     public String getRel() {
    337         ValueBinding vb = getValueBinding("rel");
    338         if (vb != null) {
    339             return (String) vb.getValue(getFacesContext());
    340         } else {
    341             return rel;
    342         }
    343     }
    344 
    345     public void setRel(String rel) {
    346         this.rel = rel;
    347     }
    348 
    349 
    350     public String getRev() {
    351         ValueBinding vb = getValueBinding("rev");
    352         if (vb != null) {
    353             return (String) vb.getValue(getFacesContext());
    354         } else {
    355             return rev;
    356         }
    357     }
    358 
    359     public void setRev(String rev) {
    360         this.rev = rev;
    361     }
    362 
    363 
    364     public String getStyle() {
    365         ValueBinding vb = getValueBinding("style");
    366         if (vb != null) {
    367             return (String) vb.getValue(getFacesContext());
    368         } else {
    369             return style;
    370         }
    371     }
    372 
    373     public void setStyle(String style) {
    374         this.style = style;
    375     }
    376 
    377 
    378     public String getStyleClass() {
    379         ValueBinding vb = getValueBinding("styleClass");
    380         if (vb != null) {
    381             return (String) vb.getValue(getFacesContext());
    382         } else {
    383             return styleClass;
    384         }
    385     }
    386 
    387     public void setStyleClass(String styleClass) {
    388         this.styleClass = styleClass;
    389     }
    390 
    391 
    392     public String getTabindex() {
    393         ValueBinding vb = getValueBinding("tabindex");
    394         if (vb != null) {
    395             return (String) vb.getValue(getFacesContext());
    396         } else {
    397             return tabindex;
    398         }
    399     }
    400 
    401     public void setTabindex(String tabindex) {
    402         this.tabindex = tabindex;
    403     }
    404 
    405 
    406     public String getTarget() {
    407         ValueBinding vb = getValueBinding("target");
    408         if (vb != null) {
    409             return (String) vb.getValue(getFacesContext());
    410         } else {
    411             return target;
    412         }
    413     }
    414 
    415     public void setTarget(String target) {
    416         this.target = target;
    417     }
    418 
    419 
    420     public String getTitle() {
    421         ValueBinding vb = getValueBinding("title");
    422         if (vb != null) {
    423             return (String) vb.getValue(getFacesContext());
    424         } else {
    425             return title;
    426         }
    427     }
    428 
    429     public void setTitle(String title) {
    430         this.title = title;
    431     }
    432 
    433 
    434     public String getType() {
    435         ValueBinding vb = getValueBinding("type");
    436         if (vb != null) {
    437             return (String) vb.getValue(getFacesContext());
    438         } else {
    439             return type;
    440         }
    441     }
    442 
    443     public void setType(String type) {
    444         this.type = type;
    445     }
    446 
    447 
    448     // ---------------------------------------------------- StateManager Methods
    449 
    450 
    451     /**
    452      * <p>Restore the state of this component.</p>
    453      *
    454      * @param context <code>FacesContext</code> for the current request
    455      * @param state State object from which to restore our state
    456      */
    457     public void restoreState(FacesContext context, Object state) {
    458 
    459         Object values[] = (Object[]) state;
    460         super.restoreState(context, values[0]);
    461         accesskey = (String) values[1];
    462         charset = (String) values[2];
    463         dir = (String) values[3];
    464         hreflang = (String) values[4];
    465         lang = (String) values[5];
    466         onblur = (String) values[6];
    467         onclick = (String) values[7];
    468         ondblclick = (String) values[8];
    469         onfocus = (String) values[9];
    470         onkeydown = (String) values[10];
    471         onkeypress = (String) values[11];
    472         onkeyup = (String) values[12];
    473         onmousedown = (String) values[13];
    474         onmousemove = (String) values[14];
    475         onmouseout = (String) values[15];
    476         onmouseover = (String) values[16];
    477         onmouseup = (String) values[17];
    478         rel = (String) values[18];
    479         rev = (String) values[19];
    480         style = (String) values[20];
    481         styleClass = (String) values[21];
    482         tabindex = (String) values[22];
    483         target = (String) values[23];
    484         title = (String) values[24];
    485         type = (String) values[25];
    486 
    487     }
    488 
    489 
    490     /**
    491      * <p>Save the state of this component.</p>
    492      *
    493      * @param context <code>FacesContext</code> for the current request
    494      */
    495     public Object saveState(FacesContext context) {
    496 
    497         Object values[] = new Object[26];
    498         values[0] = super.saveState(context);
    499         values[1] = accesskey;
    500         values[2] = charset;
    501         values[3] = dir;
    502         values[4] = hreflang;
    503         values[5] = lang;
    504         values[6] = onblur;
    505         values[7] = onclick;
    506         values[8] = ondblclick;
    507         values[9] = onfocus;
    508         values[10] = onkeydown;
    509         values[11] = onkeypress;
    510         values[12] = onkeyup;
    511         values[13] = onmousedown;
    512         values[14] = onmousemove;
    513         values[15] = onmouseout;
    514         values[16] = onmouseover;
    515         values[17] = onmouseup;
    516         values[18] = rel;
    517         values[19] = rev;
    518         values[20] = style;
    519         values[21] = styleClass;
    520         values[22] = tabindex;
    521         values[23] = target;
    522         values[24] = title;
    523         values[25] = type;
    524         return values;
    525 
    526     }
    527 
    528 
    529 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
