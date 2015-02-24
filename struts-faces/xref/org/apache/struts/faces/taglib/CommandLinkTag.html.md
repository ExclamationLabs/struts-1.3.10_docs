[View Javadoc](../../../../../../apidocs/org/apache/struts/faces/taglib/CommandLinkTag.html.md)


    1   /*
    2    * $Id: CommandLinkTag.java 471754 2006-11-06 14:55:09Z husted $
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
    22  package org.apache.struts.faces.taglib;
    23  
    24  
    25  import javax.faces.component.ActionSource;
    26  import javax.faces.component.UIComponent;
    27  import javax.faces.context.FacesContext;
    28  import javax.faces.el.MethodBinding;
    29  import javax.faces.event.ActionEvent;
    30  
    31  
    32  /**
    33   * <p>Render a <code>CommandLinkComponent</code> inside a
    34   * Struts-Faces <code>FormComponent</code>.</p>
    35   *
    36   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    37   */
    38  
    39  public class CommandLinkTag extends AbstractFacesTag {
    40  
    41  
    42      // ------------------------------------------------------ Instance Variables
    43  
    44  
    45      private String accesskey = null;
    46      private String action = null;
    47      private String actionListener = null;
    48      private String charset = null;
    49      private String dir = null;
    50      private String hreflang = null;
    51      private String immediate = null;
    52      private String lang = null;
    53      private String onblur = null;
    54      private String onclick = null;
    55      private String ondblclick = null;
    56      private String onfocus = null;
    57      private String onkeydown = null;
    58      private String onkeypress = null;
    59      private String onkeyup = null;
    60      private String onmousedown = null;
    61      private String onmousemove = null;
    62      private String onmouseout = null;
    63      private String onmouseover = null;
    64      private String onmouseup = null;
    65      private String rel = null;
    66      private String rev = null;
    67      private String style = null;
    68      private String styleClass = null;
    69      private String tabindex = null;
    70      private String target = null;
    71      private String title = null;
    72      private String type = null;
    73  
    74  
    75      // ---------------------------------------------------------- Tag Attributes
    76  
    77  
    78      public void setAccesskey(String accesskey) {
    79          this.accesskey = accesskey;
    80      }
    81  
    82  
    83      public void setAction(String action) {
    84          this.action = action;
    85      }
    86  
    87  
    88      public void setactionListener(String actionListener) {
    89          this.actionListener = actionListener;
    90      }
    91  
    92  
    93      public void setCharset(String charset) {
    94          this.charset = charset;
    95      }
    96  
    97  
    98      public void setDir(String dir) {
    99          this.dir = dir;
    100     }
    101 
    102 
    103     public void setHreflang(String hreflang) {
    104         this.hreflang = hreflang;
    105     }
    106 
    107 
    108     public void setImmediate(String immediate) {
    109         this.immediate = immediate;
    110     }
    111 
    112 
    113     public void setLang(String lang) {
    114         this.lang = lang;
    115     }
    116 
    117 
    118     public void setOnblur(String onblur) {
    119         this.onblur = onblur;
    120     }
    121 
    122 
    123     public void setOnclick(String onclick) {
    124         this.onclick = onclick;
    125     }
    126 
    127 
    128     public void setOndblclick(String ondblclick) {
    129         this.ondblclick = ondblclick;
    130     }
    131 
    132 
    133     public void setOnfocus(String onfocus) {
    134         this.onfocus = onfocus;
    135     }
    136 
    137 
    138     public void setOnkeydown(String onkeydown) {
    139         this.onkeydown = onkeydown;
    140     }
    141 
    142 
    143     public void setOnkeypress(String onkeypress) {
    144         this.onkeypress = onkeypress;
    145     }
    146 
    147 
    148     public void setOnkeyup(String onkeyup) {
    149         this.onkeyup = onkeyup;
    150     }
    151 
    152 
    153     public void setOnmousedown(String onmousedown) {
    154         this.onmousedown = onmousedown;
    155     }
    156 
    157 
    158     public void setOnmousemove(String onmousemove) {
    159         this.onmousemove = onmousemove;
    160     }
    161 
    162 
    163     public void setOnmouseout(String onmouseout) {
    164         this.onmouseout = onmouseout;
    165     }
    166 
    167 
    168     public void setOnmouseover(String onmouseover) {
    169         this.onmouseover = onmouseover;
    170     }
    171 
    172 
    173     public void setOnmouseup(String onmouseup) {
    174         this.onmouseup = onmouseup;
    175     }
    176 
    177 
    178     public void setRel(String rel) {
    179         this.rel = rel;
    180     }
    181 
    182 
    183     public void setRev(String rev) {
    184         this.rev = rev;
    185     }
    186 
    187 
    188     public void setStyle(String style) {
    189         this.style = style;
    190     }
    191 
    192 
    193     public void setStyleClass(String styleClass) {
    194         this.styleClass = styleClass;
    195     }
    196 
    197 
    198     public void setTabindex(String tabindex) {
    199         this.tabindex = tabindex;
    200     }
    201 
    202 
    203     public void setTarget(String target) {
    204         this.target = target;
    205     }
    206 
    207 
    208     public void setTitle(String title) {
    209         this.title = title;
    210     }
    211 
    212 
    213     public void setType(String type) {
    214         this.type = type;
    215     }
    216 
    217 
    218     // ------------------------------------------------------------- Tag Methods
    219 
    220 
    221     /**
    222      * <p>Release any allocated resources.</p>
    223      */
    224     public void release() {
    225 
    226         super.release();
    227         accesskey = null;
    228         action = null;
    229         actionListener = null;
    230         charset = null;
    231         dir = null;
    232         hreflang = null;
    233         immediate = null;
    234         lang = null;
    235         onblur = null;
    236         onclick = null;
    237         ondblclick = null;
    238         onfocus = null;
    239         onkeydown = null;
    240         onkeypress = null;
    241         onkeyup = null;
    242         onmousedown = null;
    243         onmousemove = null;
    244         onmouseout = null;
    245         onmouseover = null;
    246         onmouseup = null;
    247         rel = null;
    248         rev = null;
    249         style = null;
    250         styleClass = null;
    251         tabindex = null;
    252         target = null;
    253         title = null;
    254         type = null;
    255 
    256     }
    257 
    258 
    259     // ---------------------------------------------------------- Public Methods
    260 
    261 
    262     /**
    263      * <p>Return the type of component to be created for this tag.</p>
    264      */
    265     public String getComponentType() {
    266 
    267         return ("org.apache.struts.faces.CommandLink");
    268 
    269     }
    270 
    271 
    272     /**
    273      * <p>Return the <code>rendererType</code> to be used for rendering
    274      * our component.</p>
    275      */
    276     public String getRendererType() {
    277 
    278         return ("org.apache.struts.faces.CommandLink");
    279 
    280     }
    281 
    282 
    283     // ------------------------------------------------------- Protected Methods
    284 
    285 
    286     /**
    287      * <p>Override attributes set on this tag instance.</p>
    288      *
    289      * @param component Component whose attributes should be overridden
    290      */
    291     protected void setProperties(UIComponent component) {
    292 
    293         super.setProperties(component);
    294         if (action != null) {
    295             if (isValueReference(action)) {
    296                 MethodBinding mb = FacesContext.getCurrentInstance().
    297                     getApplication().createMethodBinding(action, null);
    298                 ((ActionSource) component).setAction(mb);
    299             } else {
    300                 final String outcome = action;
    301                 MethodBinding mb = new ConstantMethodBinding(outcome);
    302                 ((ActionSource) component).setAction(mb);
    303             }
    304         }
    305         if (actionListener != null) {
    306             if (isValueReference(actionListener)) {
    307                 Class[] args = {ActionEvent.class};
    308                 MethodBinding mb = FacesContext.getCurrentInstance().
    309                 getApplication().createMethodBinding(actionListener, args);
    310                 ((ActionSource) component).setActionListener(mb);
    311             }
    312         }
    313         setStringAttribute(component, "accesskey", accesskey);
    314         setStringAttribute(component, "charset", charset);
    315         setStringAttribute(component, "dir", dir);
    316         setStringAttribute(component, "hreflang", hreflang);
    317         setBooleanAttribute(component, "immediate", immediate);
    318         setStringAttribute(component, "lang", lang);
    319         setStringAttribute(component, "onblur", onblur);
    320         setStringAttribute(component, "onclick", onclick);
    321         setStringAttribute(component, "ondblclick", ondblclick);
    322         setStringAttribute(component, "onfocus", onfocus);
    323         setStringAttribute(component, "onkeydown", onkeydown);
    324         setStringAttribute(component, "onkeypress", onkeypress);
    325         setStringAttribute(component, "onkeyup", onkeyup);
    326         setStringAttribute(component, "onmousedown", onmousedown);
    327         setStringAttribute(component, "onmousemove", onmousemove);
    328         setStringAttribute(component, "onmouseout", onmouseout);
    329         setStringAttribute(component, "onmouseover", onmouseover);
    330         setStringAttribute(component, "onmouseup", onmouseup);
    331         setStringAttribute(component, "rel", rel);
    332         setStringAttribute(component, "rev", rev);
    333         setStringAttribute(component, "style", style);
    334         setStringAttribute(component, "styleClass", styleClass);
    335         setStringAttribute(component, "tabindex", tabindex);
    336         setStringAttribute(component, "target", target);
    337         setStringAttribute(component, "title", title);
    338         setStringAttribute(component, "type", type);
    339 
    340     }
    341 
    342 
    343 }
    344 
    345 
    346 // Private MethodBinding Implementation To Return A Constant Value
    347 
    348 class ConstantMethodBinding extends MethodBinding {
    349 
    350     public ConstantMethodBinding(String outcome) {
    351         this.outcome = outcome;
    352     }
    353 
    354     private String outcome = null;
    355 
    356     public Object invoke(FacesContext context, Object params[]) {
    357         return (this.outcome);
    358     }
    359 
    360     public Class getType(FacesContext context) {
    361         return (String.class);
    362     }
    363 
    364 
    365 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
