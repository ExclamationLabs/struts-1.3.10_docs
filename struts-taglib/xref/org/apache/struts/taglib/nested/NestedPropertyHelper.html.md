[View Javadoc](../../../../../../apidocs/org/apache/struts/taglib/nested/NestedPropertyHelper.html.md)


    1   /*
    2    * $Id: NestedPropertyHelper.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.taglib.nested;
    22  
    23  import org.apache.struts.taglib.html.md.Constants;
    24  import org.apache.struts.taglib.html.md.FormTag;
    25  
    26  import javax.servlet.http.HttpServletRequest;
    27  import javax.servlet.jsp.tagext.Tag;
    28  
    29  import java.util.StringTokenizer;
    30  
    31  /**
    32   * <p>A simple helper class that does everything that needs to be done to get
    33   * the nested tag extension to work. The tags will pass in their relative
    34   * properties and this class will leverage the accessibility of the request
    35   * object to calculate the nested references and manage them from a central
    36   * place.</p>
    37   *
    38   * <p>The helper method {@link #setNestedProperties} takes a reference to the
    39   * tag itself so all the simpler tags can have their references managed from a
    40   * central location. From here, the reference to a provided name is also
    41   * preserved for use.</p>
    42   *
    43   * <p>With all tags keeping track of themselves, we only have to seek to the
    44   * next level, or parent tag, were a tag will append a dot and it's own
    45   * property.</p>
    46   *
    47   * @version $Rev: 471754 $ $Date: 2004-10-16 12:38:42 -0400 (Sat, 16 Oct 2004)
    48   *          $
    49   * @since Struts 1.1
    50   */
    51  public class NestedPropertyHelper {
    52      /* key that the tags can rely on to set the details against */
    53      public static final String NESTED_INCLUDES_KEY = "<nested-includes-key/>";
    54  
    55      /**
    56       * Returns the current nesting property from the request object.
    57       *
    58       * @param request object to fetch the property reference from
    59       * @return String of the bean name to nest against
    60       */
    61      public static final String getCurrentProperty(HttpServletRequest request) {
    62          // get the old one if any
    63          NestedReference nr =
    64              (NestedReference) request.getAttribute(NESTED_INCLUDES_KEY);
    65  
    66          // return null or the property
    67          return (nr == null) ? null : nr.getNestedProperty();
    68      }
    69  
    70      /**
    71       * <p>Returns the bean name from the request object that the properties
    72       * are nesting against.</p>
    73       *
    74       * <p>The requirement of the tag itself could be removed in the future,
    75       * but is required if support for the .html.md:form> tag is maintained.</p>
    76       *
    77       * @param request object to fetch the bean reference from
    78       * @param nested  tag from which to start the search from
    79       * @return the string of the bean name to be nesting against
    80       */
    81      public static final String getCurrentName(HttpServletRequest request,
    82          NestedNameSupport nested) {
    83          // get the old one if any
    84          NestedReference nr =
    85              (NestedReference) request.getAttribute(NESTED_INCLUDES_KEY);
    86  
    87          // return null or the property
    88          if (nr != null) {
    89              return nr.getBeanName();
    90          } else {
    91              // need to look for a form tag...
    92              Tag tag = (Tag) nested;
    93              Tag formTag = null;
    94  
    95              // loop all parent tags until we get one that can be nested against
    96              do {
    97                  tag = tag.getParent();
    98  
    99                  if ((tag != null) && tag instanceof FormTag) {
    100                     formTag = tag;
    101                 }
    102             } while ((formTag == null) && (tag != null));
    103 
    104             if (formTag == null) {
    105                 return "";
    106             }
    107 
    108             // return the form's name
    109             return ((FormTag) formTag).getBeanName();
    110         }
    111     }
    112 
    113     /**
    114      * Get the adjusted property. Apply the provided property, to the property
    115      * already stored in the request object.
    116      *
    117      * @param request  to pull the reference from
    118      * @param property to retrieve the evaluated nested property with
    119      * @return String of the final nested property reference.
    120      */
    121     public static final String getAdjustedProperty(HttpServletRequest request,
    122         String property) {
    123         // get the old one if any
    124         String parent = getCurrentProperty(request);
    125 
    126         return calculateRelativeProperty(property, parent);
    127     }
    128 
    129     /**
    130      * Sets the provided property into the request object for reference by the
    131      * other nested tags.
    132      *
    133      * @param request  object to set the new property into
    134      * @param property String to set the property to
    135      */
    136     public static final void setProperty(HttpServletRequest request,
    137         String property) {
    138         // get the old one if any
    139         NestedReference nr = referenceInstance(request);
    140 
    141         nr.setNestedProperty(property);
    142     }
    143 
    144     /**
    145      * Sets the provided name into the request object for reference by the
    146      * other nested tags.
    147      *
    148      * @param request object to set the new name into
    149      * @param name    String to set the name to
    150      */
    151     public static final void setName(HttpServletRequest request, String name) {
    152         // get the old one if any
    153         NestedReference nr = referenceInstance(request);
    154 
    155         nr.setBeanName(name);
    156     }
    157 
    158     /**
    159      * Deletes the nested reference from the request object.
    160      *
    161      * @param request object to remove the reference from
    162      */
    163     public static final void deleteReference(HttpServletRequest request) {
    164         // delete the reference
    165         request.removeAttribute(NESTED_INCLUDES_KEY);
    166     }
    167 
    168     /**
    169      * Helper method that will set all the relevant nesting properties for the
    170      * provided tag reference depending on the implementation.
    171      *
    172      * @param request object to pull references from
    173      * @param tag     to set the nesting values into
    174      */
    175     public static void setNestedProperties(HttpServletRequest request,
    176         NestedPropertySupport tag) {
    177         boolean adjustProperty = true;
    178 
    179         /* if the tag implements NestedNameSupport, set the name for the tag also */
    180         if (tag instanceof NestedNameSupport) {
    181             NestedNameSupport nameTag = (NestedNameSupport) tag;
    182 
    183             if ((nameTag.getName() == null)
    184                 || Constants.BEAN_KEY.equals(nameTag.getName())) {
    185                 nameTag.setName(getCurrentName(request, (NestedNameSupport) tag));
    186             } else {
    187                 adjustProperty = false;
    188             }
    189         }
    190 
    191         /* get and set the relative property, adjust if required */
    192         String property = tag.getProperty();
    193 
    194         if (adjustProperty) {
    195             property = getAdjustedProperty(request, property);
    196         }
    197 
    198         tag.setProperty(property);
    199     }
    200 
    201     /**
    202      * Pulls the current nesting reference from the request object, and if
    203      * there isn't one there, then it will create one and set it.
    204      *
    205      * @param request object to manipulate the reference into
    206      * @return current nesting reference as stored in the request object
    207      */
    208     private static final NestedReference referenceInstance(
    209         HttpServletRequest request) {
    210         /* get the old one if any */
    211         NestedReference nr =
    212             (NestedReference) request.getAttribute(NESTED_INCLUDES_KEY);
    213 
    214         // make a new one if required
    215         if (nr == null) {
    216             nr = new NestedReference();
    217             request.setAttribute(NESTED_INCLUDES_KEY, nr);
    218         }
    219 
    220         // return the reference
    221         return nr;
    222     }
    223 
    224     /* This property, providing the property to be appended, and the parent tag
    225     * to append the property to, will calculate the stepping of the property
    226     * and return the qualified nested property
    227     *
    228     * @param property the property which is to be appended nesting style
    229     * @param parent the "dot notated" string representing the structure
    230     * @return qualified nested property that the property param is to the parent
    231     */
    232     private static String calculateRelativeProperty(String property,
    233         String parent) {
    234         if (parent == null) {
    235             parent = "";
    236         }
    237 
    238         if (property == null) {
    239             property = "";
    240         }
    241 
    242         /* Special case... reference my parent's nested property.
    243         Otherwise impossible for things like indexed properties */
    244         if ("./".equals(property) || "this/".equals(property)) {
    245             return parent;
    246         }
    247 
    248         /* remove the stepping from the property */
    249         String stepping;
    250 
    251         /* isolate a parent reference */
    252         if (property.endsWith("/")) {
    253             stepping = property;
    254             property = "";
    255         } else {
    256             stepping = property.substring(0, property.lastIndexOf('/') + 1);
    257 
    258             /* isolate the property */
    259             property =
    260                 property.substring(property.lastIndexOf('/') + 1,
    261                     property.length());
    262         }
    263 
    264         if (stepping.startsWith("/")) {
    265             /* return from root */
    266             return property;
    267         } else {
    268             /* tokenize the nested property */
    269             StringTokenizer proT = new StringTokenizer(parent, ".");
    270             int propCount = proT.countTokens();
    271 
    272             /* tokenize the stepping */
    273             StringTokenizer strT = new StringTokenizer(stepping, "/");
    274             int count = strT.countTokens();
    275 
    276             if (count >= propCount) {
    277                 /* return from root */
    278                 return property;
    279             } else {
    280                 /* append the tokens up to the token difference */
    281                 count = propCount - count;
    282 
    283                 StringBuffer result = new StringBuffer();
    284 
    285                 for (int i = 0; i < count; i++) {
    286                     result.append(proT.nextToken());
    287                     result.append('.');
    288                 }
    289 
    290                 result.append(property);
    291 
    292                 /* parent reference will have a dot on the end. Leave it off */
    293                 if (result.charAt(result.length() - 1) == '.') {
    294                     return result.substring(0, result.length() - 1);
    295                 } else {
    296                     return result.toString();
    297                 }
    298             }
    299         }
    300     }
    301 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
