[View Javadoc](../../../../../../apidocs/org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md)


    1   /*
    2    * $Id: DefinitionTagSupport.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.tiles.taglib;
    22  
    23  import java.io.Serializable;
    24  import javax.servlet.jsp.tagext.TagSupport;
    25  
    26  /**
    27   * Common base class for tags dealing with Tiles definitions.
    28   * This class defines properties used in Definition Tags.
    29   * It also extends TagSupport.
    30   */
    31  public class DefinitionTagSupport extends TagSupport implements Serializable {
    32      /**
    33       * Associated Controller type
    34       */
    35      protected String controllerType;
    36      /**
    37       * Associated Controller name (classname or url)
    38       */
    39      protected String controllerName;
    40      /**
    41       * Role associated to definition.
    42       */
    43      protected String role;
    44      /**
    45       * Uri of page assoicated to this definition.
    46       */
    47      protected String page;
    48  
    49      /**
    50       * Release class properties.
    51       */
    52      public void release() {
    53          super.release();
    54          controllerType = null;
    55          controllerName = null;
    56          role = null;
    57          page = null;
    58      }
    59  
    60      /**
    61       * Get controller type.
    62       * Type can be 'classname', 'url'.
    63       *
    64       * @return Controller type.
    65       */
    66      public String getControllerType() {
    67          return controllerType;
    68      }
    69  
    70      /**
    71       * Get controller name.
    72       * Name denotes a fully qualified classname, or an url.
    73       * Exact type can be specified with {@link #setControllerType}.
    74       *
    75       * @return Controller name.
    76       */
    77      public String getControllerName() {
    78          return controllerName;
    79      }
    80  
    81      /**
    82       * Set associated controller type.
    83       * Type denotes a fully qualified classname.
    84       *
    85       * @param controllerType Type of associated controller.
    86       */
    87      public void setControllerType(String controllerType) {
    88          this.controllerType = controllerType;
    89      }
    90  
    91      /**
    92       * Set associated controller name.
    93       * Name denotes a fully qualified classname, or an url.
    94       * Exact type can be specified with {@link #setControllerType}.
    95       *
    96       * @param controller Controller classname or url.
    97       */
    98      public void setController(String controller) {
    99          setControllerName(controller);
    100     }
    101 
    102     /**
    103      * Set associated controller name.
    104      * Name denote a fully qualified classname, or an url.
    105      * Exact type can be specified with setControllerType.
    106      *
    107      * @param controller Controller classname or url
    108      */
    109     public void setControllerName(String controller) {
    110         this.controllerName = controller;
    111     }
    112 
    113     /**
    114      * Set associated controller name as an url, and controller
    115      * type as "url".
    116      * Name must be an url (not checked).
    117      * Convenience method.
    118      *
    119      * @param controller Controller url
    120      */
    121     public void setControllerUrl(String controller) {
    122         setControllerName(controller);
    123         setControllerType("url");
    124     }
    125 
    126     /**
    127      * Set associated controller name as a classtype and controller
    128      * type as "classname".
    129      * Name denotes a fully qualified classname.
    130      * Convenience method.
    131      *
    132      * @param controller Controller classname.
    133      */
    134     public void setControllerClass(String controller) {
    135         setControllerName(controller);
    136         setControllerType("classname");
    137     }
    138 
    139     /**
    140      * Get associated role.
    141      *
    142      * @return Associated role.
    143      */
    144     public String getRole() {
    145         return role;
    146     }
    147 
    148     /**
    149      * Set associated role.
    150      *
    151      * @param role Associated role.
    152      */
    153     public void setRole(String role) {
    154         this.role = role;
    155     }
    156 
    157     /**
    158      * Set the page.
    159      *
    160      * @param page Page.
    161      */
    162     public void setPage(String page) {
    163         this.page = page;
    164     }
    165 
    166     /**
    167      * Get the page.
    168      *
    169      * @return Page.
    170      */
    171     public String getPage() {
    172         return page;
    173     }
    174 
    175     /**
    176      * Get the template.
    177      * Same as getPage().
    178      *
    179      * @return Template.
    180      */
    181     public String getTemplate() {
    182         return page;
    183     }
    184 
    185     /**
    186      * Set the template.
    187      * Same as setPage().
    188      *
    189      * @param template Template.
    190      */
    191     public void setTemplate(String template) {
    192         this.page = template;
    193     }
    194 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
