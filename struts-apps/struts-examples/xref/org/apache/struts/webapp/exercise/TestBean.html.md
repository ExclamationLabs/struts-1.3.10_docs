[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/exercise/TestBean.html.md)


    1   /*
    2    * $Id: TestBean.java 471754 2006-11-06 14:55:09Z husted $
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
    22  
    23  package org.apache.struts.webapp.exercise;
    24  
    25  
    26  import java.util.ArrayList;
    27  import java.util.Collection;
    28  import java.util.HashMap;
    29  import java.util.List;
    30  import java.util.Map;
    31  import java.util.Vector;
    32  import javax.servlet.http.HttpServletRequest;
    33  import org.apache.struts.action.ActionForm;
    34  import org.apache.struts.action.ActionMapping;
    35  import org.apache.struts.util.LabelValueBean;
    36  
    37  
    38  /**
    39   * General purpose test bean for Struts custom tag tests.
    40   *
    41   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    42   */
    43  
    44  public class TestBean extends ActionForm {
    45  
    46  
    47      // ------------------------------------------------------------- Properties
    48  
    49  
    50      /**
    51       * A collection property where the elements of the collection are
    52       * of type <code>LabelValueBean</code>.
    53       */
    54      private Collection beanCollection = null;
    55  
    56      public Collection getBeanCollection() {
    57          if (beanCollection == null) {
    58              Vector entries = new Vector(10);
    59  
    60              entries.add(new LabelValueBean("Label 0", "Value 0"));
    61              entries.add(new LabelValueBean("Label 1", "Value 1"));
    62              entries.add(new LabelValueBean("Label 2", "Value 2"));
    63              entries.add(new LabelValueBean("Label 3", "Value 3"));
    64              entries.add(new LabelValueBean("Label 4", "Value 4"));
    65              entries.add(new LabelValueBean("Label 5", "Value 5"));
    66              entries.add(new LabelValueBean("Label 6", "Value 6"));
    67              entries.add(new LabelValueBean("Label 7", "Value 7"));
    68              entries.add(new LabelValueBean("Label 8", "Value 8"));
    69              entries.add(new LabelValueBean("Label 9", "Value 9"));
    70  
    71              beanCollection = entries;
    72          }
    73  
    74          return (beanCollection);
    75      }
    76  
    77      public void setBeanCollection(Collection beanCollection) {
    78          this.beanCollection = beanCollection;
    79      }
    80  
    81  
    82      /**
    83       * A multiple-String SELECT element using a bean collection.
    84       */
    85      private String[] beanCollectionSelect = { "Value 1", "Value 3",
    86                                                "Value 5" };
    87  
    88      public String[] getBeanCollectionSelect() {
    89          return (this.beanCollectionSelect);
    90      }
    91  
    92      public void setBeanCollectionSelect(String beanCollectionSelect[]) {
    93          this.beanCollectionSelect = beanCollectionSelect;
    94      }
    95  
    96  
    97      /**
    98       * A boolean property whose initial value is true.
    99       */
    100     private boolean booleanProperty = true;
    101 
    102     public boolean getBooleanProperty() {
    103         return (booleanProperty);
    104     }
    105 
    106     public void setBooleanProperty(boolean booleanProperty) {
    107         this.booleanProperty = booleanProperty;
    108     }
    109 
    110 
    111     /**
    112      * A multiple-String SELECT element using a collection.
    113      */
    114     private String[] collectionSelect = { "Value 2", "Value 4",
    115                                           "Value 6" };
    116 
    117     public String[] getCollectionSelect() {
    118         return (this.collectionSelect);
    119     }
    120 
    121     public void setCollectionSelect(String collectionSelect[]) {
    122         this.collectionSelect = collectionSelect;
    123     }
    124 
    125 
    126     /**
    127      * A double property.
    128      */
    129     private double doubleProperty = 321.0;
    130 
    131     public double getDoubleProperty() {
    132         return (this.doubleProperty);
    133     }
    134 
    135     public void setDoubleProperty(double doubleProperty) {
    136         this.doubleProperty = doubleProperty;
    137     }
    138 
    139 
    140     /**
    141      * A boolean property whose initial value is false
    142      */
    143     private boolean falseProperty = false;
    144 
    145     public boolean getFalseProperty() {
    146         return (falseProperty);
    147     }
    148 
    149     public void setFalseProperty(boolean falseProperty) {
    150         this.falseProperty = falseProperty;
    151     }
    152 
    153 
    154     /**
    155      * A float property.
    156      */
    157     private float floatProperty = (float) 123.0;
    158 
    159     public float getFloatProperty() {
    160         return (this.floatProperty);
    161     }
    162 
    163     public void setFloatProperty(float floatProperty) {
    164         this.floatProperty = floatProperty;
    165     }
    166 
    167 
    168     /**
    169      * Integer arrays that are accessed as an array as well as indexed.
    170      */
    171     private int intArray[] = { 0, 10, 20, 30, 40 };
    172 
    173     public int[] getIntArray() {
    174         return (this.intArray);
    175     }
    176 
    177     public void setIntArray(int intArray[]) {
    178         this.intArray = intArray;
    179     }
    180 
    181     private int intIndexed[] = { 0, 10, 20, 30, 40 };
    182 
    183     public int getIntIndexed(int index) {
    184         return (intIndexed[index]);
    185     }
    186 
    187     public void setIntIndexed(int index, int value) {
    188         intIndexed[index] = value;
    189     }
    190 
    191 
    192     private int intMultibox[] = new int[0];
    193 
    194     public int[] getIntMultibox() {
    195         return (this.intMultibox);
    196     }
    197 
    198     public void setIntMultibox(int intMultibox[]) {
    199         this.intMultibox = intMultibox;
    200     }
    201 
    202     /**
    203      * An integer property.
    204      */
    205     private int intProperty = 123;
    206 
    207     public int getIntProperty() {
    208         return (this.intProperty);
    209     }
    210 
    211     public void setIntProperty(int intProperty) {
    212         this.intProperty = intProperty;
    213     }
    214 
    215 
    216     /**
    217      * A long property.
    218      */
    219     private long longProperty = 321;
    220 
    221     public long getLongProperty() {
    222         return (this.longProperty);
    223     }
    224 
    225     public void setLongProperty(long longProperty) {
    226         this.longProperty = longProperty;
    227     }
    228 
    229 
    230     /**
    231      * A multiple-String SELECT element.
    232      */
    233     private String[] multipleSelect = { "Multiple 3", "Multiple 5",
    234                                         "Multiple 7" };
    235 
    236     public String[] getMultipleSelect() {
    237         return (this.multipleSelect);
    238     }
    239 
    240     public void setMultipleSelect(String multipleSelect[]) {
    241         this.multipleSelect = multipleSelect;
    242     }
    243 
    244 
    245     /**
    246      * A nested reference to another test bean (populated as needed).
    247      */
    248     private TestBean nested = null;
    249 
    250     public TestBean getNested() {
    251         if (nested == null)
    252             nested = new TestBean();
    253         return (nested);
    254     }
    255 
    256 
    257     /**
    258      * A String property with an initial value of null.
    259      */
    260     private String nullProperty = null;
    261 
    262     public String getNullProperty() {
    263         return (this.nullProperty);
    264     }
    265 
    266     public void setNullProperty(String nullProperty) {
    267         this.nullProperty = nullProperty;
    268     }
    269 
    270 
    271     /**
    272      * A short property.
    273      */
    274     private short shortProperty = (short) 987;
    275 
    276     public short getShortProperty() {
    277         return (this.shortProperty);
    278     }
    279 
    280     public void setShortProperty(short shortProperty) {
    281         this.shortProperty = shortProperty;
    282     }
    283 
    284 
    285     /**
    286      * A single-String value for a SELECT element.
    287      */
    288     private String singleSelect = "Single 5";
    289 
    290     public String getSingleSelect() {
    291         return (this.singleSelect);
    292     }
    293 
    294     public void setSingleSelect(String singleSelect) {
    295         this.singleSelect = singleSelect;
    296     }
    297 
    298 
    299     /**
    300      * String arrays that are accessed as an array as well as indexed.
    301      */
    302     private String stringArray[] =
    303     { "String 0", "String 1", "String 2", "String 3", "String 4" };
    304 
    305     public String[] getStringArray() {
    306         return (this.stringArray);
    307     }
    308 
    309     public void setStringArray(String stringArray[]) {
    310         this.stringArray = stringArray;
    311     }
    312 
    313     private String stringIndexed[] =
    314     { "String 0", "String 1", "String 2", "String 3", "String 4" };
    315 
    316     public String getStringIndexed(int index) {
    317         return (stringIndexed[index]);
    318     }
    319 
    320     public void setStringIndexed(int index, String value) {
    321         stringIndexed[index] = value;
    322     }
    323 
    324 
    325     private String stringMultibox[] = new String[0];
    326 
    327     public String[] getStringMultibox() {
    328         return (this.stringMultibox);
    329     }
    330 
    331     public void setStringMultibox(String stringMultibox[]) {
    332         this.stringMultibox = stringMultibox;
    333     }
    334 
    335     /**
    336      * A String property.
    337      */
    338     private String stringProperty = "This is a string";
    339 
    340     public String getStringProperty() {
    341         return (this.stringProperty);
    342     }
    343 
    344     public void setStringProperty(String stringProperty) {
    345         this.stringProperty = stringProperty;
    346     }
    347 
    348     /**
    349      * An empty String property.
    350      */
    351     private String emptyStringProperty = "";
    352 
    353     public String getEmptyStringProperty() {
    354         return (this.emptyStringProperty);
    355     }
    356 
    357     public void setEmptyStringProperty(String emptyStringProperty) {
    358         this.emptyStringProperty = emptyStringProperty;
    359     }
    360 
    361 
    362     /**
    363      * A single-String value for a SELECT element based on resource strings.
    364      */
    365     private String resourcesSelect = "Resources 2";
    366 
    367     public String getResourcesSelect() {
    368         return (this.resourcesSelect);
    369     }
    370 
    371     public void setResourcesSelect(String resourcesSelect) {
    372         this.resourcesSelect = resourcesSelect;
    373     }
    374 
    375 
    376     /**
    377      * A property that allows a null value but is still used in a SELECT.
    378      */
    379     private String withNulls = null;
    380 
    381     public String getWithNulls() {
    382         return (this.withNulls);
    383     }
    384 
    385     public void setWithNulls(String withNulls) {
    386         this.withNulls = withNulls;
    387     }
    388 
    389 
    390     /**
    391      * A List property.
    392      */
    393     private List listProperty = null;
    394 
    395     public List getListProperty() {
    396         if (listProperty == null) {
    397             listProperty = new ArrayList();
    398             listProperty.add("dummy");
    399         }
    400         return listProperty;
    401     }
    402 
    403     public void setListProperty(List listProperty) {
    404         this.listProperty = listProperty;
    405     }
    406 
    407     /**
    408      * An empty List property.
    409      */
    410     private List emptyListProperty = null;
    411 
    412     public List getEmptyListProperty() {
    413         if (emptyListProperty == null) {
    414             emptyListProperty = new ArrayList();
    415         }
    416         return emptyListProperty;
    417     }
    418 
    419     public void setEmptyListProperty(List emptyListProperty) {
    420         this.emptyListProperty = emptyListProperty;
    421     }
    422 
    423 
    424     /**
    425      * A Map property.
    426      */
    427     private Map mapProperty = null;
    428 
    429     public Map getMapProperty() {
    430         if (mapProperty == null) {
    431             mapProperty = new HashMap();
    432             mapProperty.put("dummy", "dummy");
    433         }
    434         return mapProperty;
    435     }
    436 
    437     public void setMapProperty(Map mapProperty) {
    438         this.mapProperty = mapProperty;
    439     }
    440 
    441     /**
    442      * An empty Map property.
    443      */
    444     private Map emptyMapProperty = null;
    445 
    446     public Map getEmptyMapProperty() {
    447         if (emptyMapProperty == null) {
    448             emptyMapProperty = new HashMap();
    449         }
    450         return emptyMapProperty;
    451     }
    452 
    453     public void setEmptyMapProperty(Map emptyMapProperty) {
    454         this.emptyMapProperty = emptyMapProperty;
    455     }
    456 
    457 
    458     // --------------------------------------------------------- Public Methods
    459 
    460 
    461     /**
    462      * Reset the properties that will be received as input.
    463      */
    464     public void reset(ActionMapping mapping, HttpServletRequest request) {
    465 
    466         booleanProperty = false;
    467         collectionSelect = new String[0];
    468         intMultibox = new int[0];
    469         multipleSelect = new String[0];
    470         stringMultibox = new String[0];
    471         if (nested != null)
    472             nested.reset(mapping, request);
    473 
    474     }
    475 
    476 
    477 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
