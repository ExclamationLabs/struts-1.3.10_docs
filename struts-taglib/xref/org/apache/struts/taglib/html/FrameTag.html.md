[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib.html.md/FrameTag.html)


    1   /*
    2    * $Id: FrameTag.java 471754 2006-11-06 14:55:09Z husted $
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
    23  import org.apache.struts.taglib.TagUtils;
    24  
    25  import javax.servlet.jsp.JspException;
    26  
    27  /**
    28   * Generate an HTML <code>&lt;frame&gt;</code> tag with similar capabilities
    29   * as those the <code>&lt.html.md:link&gt;</code> tag provides for hyperlink
    30   * elements.  The <code>src</code> element is rendered using the same
    31   * technique that {@link LinkTag} uses to render the <code>href</code>
    32   * attribute of a hyperlink.  Additionall, the HTML 4.0 frame tag attributes
    33   * <code>noresize</code>, <code>scrolling</code>, <code>marginheight</code>,
    34   * <code>marginwidth</code>, <code>frameborder</code>, and
    35   * <code>longdesc</code> are supported. The frame <code>name</code> attribute
    36   * is rendered based on the <code>frameName</code> property.
    37   *
    38   * Note that the value of <code>longdesc</code> is intended to be a URI, but
    39   * currently no rewriting is supported.  The attribute is set directly from
    40   * the property value.
    41   *
    42   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    43   *          $
    44   * @since Struts 1.1
    45   */
    46  public class FrameTag extends LinkTag {
    47      // ------------------------------------------------------------- Properties
    48  
    49      /**
    50       * The frameborder attribute that should be rendered (1, 0).
    51       */
    52      protected String frameborder = null;
    53  
    54      /**
    55       * The <code>name</code> attribute that should be rendered for this
    56       * frame.
    57       */
    58      protected String frameName = null;
    59  
    60      /**
    61       * URI of a long description of this frame (complements title).
    62       */
    63      protected String longdesc = null;
    64  
    65      /**
    66       * The margin height in pixels, or zero for no setting.
    67       */
    68      protected Integer marginheight = null;
    69  
    70      /**
    71       * The margin width in pixels, or null for no setting.
    72       */
    73      protected Integer marginwidth = null;
    74  
    75      /**
    76       * Should users be disallowed to resize the frame?
    77       */
    78      protected boolean noresize = false;
    79  
    80      /**
    81       * What type of scrolling should be supported (yes, no, auto)?
    82       */
    83      protected String scrolling = null;
    84  
    85      public String getFrameborder() {
    86          return (this.frameborder);
    87      }
    88  
    89      public void setFrameborder(String frameborder) {
    90          this.frameborder = frameborder;
    91      }
    92  
    93      public String getFrameName() {
    94          return (this.frameName);
    95      }
    96  
    97      public void setFrameName(String frameName) {
    98          this.frameName = frameName;
    99      }
    100 
    101     public String getLongdesc() {
    102         return (this.longdesc);
    103     }
    104 
    105     public void setLongdesc(String longdesc) {
    106         this.longdesc = longdesc;
    107     }
    108 
    109     public Integer getMarginheight() {
    110         return (this.marginheight);
    111     }
    112 
    113     public void setMarginheight(Integer marginheight) {
    114         this.marginheight = marginheight;
    115     }
    116 
    117     public Integer getMarginwidth() {
    118         return (this.marginwidth);
    119     }
    120 
    121     public void setMarginwidth(Integer marginwidth) {
    122         this.marginwidth = marginwidth;
    123     }
    124 
    125     public boolean getNoresize() {
    126         return (this.noresize);
    127     }
    128 
    129     public void setNoresize(boolean noresize) {
    130         this.noresize = noresize;
    131     }
    132 
    133     public String getScrolling() {
    134         return (this.scrolling);
    135     }
    136 
    137     public void setScrolling(String scrolling) {
    138         this.scrolling = scrolling;
    139     }
    140 
    141     // --------------------------------------------------------- Public Methods
    142 
    143     /**
    144      * Render the appropriately encoded URI.
    145      *
    146      * @throws JspException if a JSP exception has occurred
    147      */
    148     public int doEndTag() throws JspException {
    149         // Print this element to our output writer
    150         StringBuffer results = new StringBuffer("<frame");
    151 
    152         prepareAttribute(results, "src", calculateURL());
    153         prepareAttribute(results, "name", getFrameName());
    154 
    155         if (noresize) {
    156             results.append(" noresize=\"noresize\"");
    157         }
    158 
    159         prepareAttribute(results, "scrolling", getScrolling());
    160         prepareAttribute(results, "marginheight", getMarginheight());
    161         prepareAttribute(results, "marginwidth", getMarginwidth());
    162         prepareAttribute(results, "frameborder", getFrameborder());
    163         prepareAttribute(results, "longdesc", getLongdesc());
    164         results.append(prepareStyles());
    165         prepareOtherAttributes(results);
    166         results.append(getElementClose());
    167         TagUtils.getInstance().write(pageContext, results.toString());
    168 
    169         return (EVAL_PAGE);
    170     }
    171 
    172     /**
    173      * Release any acquired resources.
    174      */
    175     public void release() {
    176         super.release();
    177         frameborder = null;
    178         frameName = null;
    179         longdesc = null;
    180         marginheight = null;
    181         marginwidth = null;
    182         noresize = false;
    183         scrolling = null;
    184     }
    185 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
