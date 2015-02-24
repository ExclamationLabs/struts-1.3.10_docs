[View Javadoc](../../../../../../../apidocs/org/apache/struts/webapp/el/exercise/TestBean.html.md)


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
    22  package org.apache.struts.webapp.el.exercise;
    23  
    24  
    25  import org.apache.struts.action.ActionForm;
    26  import org.apache.struts.action.ActionMapping;
    27  import org.apache.struts.util.LabelValueBean;
    28  
    29  import javax.servlet.http.HttpServletRequest;
    30  import java.util.Collection;
    31  import java.util.Vector;
    32  
    33  
    34  /**
    35   * General purpose test bean for Struts custom tag tests.
    36   *
    37   * @author Craig R. McClanahan
    38   * @author Martin F N Cooper
    39   * @version $Rev: 471754 $ $Date: 2004-10-16 13:04:52 -0400 (Sat, 16 Oct 2004)
    40   *          $
    41   */
    42  
    43  public class TestBean extends ActionForm {
    44  
    45      // ------------------------------------------------------------- Properties
    46  
    47  
    48      /**
    49       * A collection property where the elements of the collection are of type
    50       * <code>LabelValueBean</code>.
    51       */
    52      private Collection beanCollection = null;
    53  
    54      public Collection getBeanCollection() {
    55          if (beanCollection == null) {
    56              Vector entries = new Vector(10);
    57  
    58              entries.add(new LabelValueBean("Label 0", "Value 0"));
    59              entries.add(new LabelValueBean("Label 1", "Value 1"));
    60              entries.add(new LabelValueBean("Label 2", "Value 2"));
    61              entries.add(new LabelValueBean("Label 3", "Value 3"));
    62              entries.add(new LabelValueBean("Label 4", "Value 4"));
    63              entries.add(new LabelValueBean("Label 5", "Value 5"));
    64              entries.add(new LabelValueBean("Label 6", "Value 6"));
    65              entries.add(new LabelValueBean("Label 7", "Value 7"));
    66              entries.add(new LabelValueBean("Label 8", "Value 8"));
    67              entries.add(new LabelValueBean("Label 9", "Value 9"));
    68  
    69              beanCollection = entries;
    70          }
    71  
    72          return (beanCollection);
    73      }
    74  
    75      public void setBeanCollection(Collection beanCollection) {
    76          this.beanCollection = beanCollection;
    77      }
    78  
    79  
    80      /**
    81       * A multiple-String SELECT element using a bean collection.
    82       */
    83      private String[] beanCollectionSelect = { "Value 1", "Value 3",
    84              "Value 5" };
    85  
    86      public String[] getBeanCollectionSelect() {
    87          return (this.beanCollectionSelect);
    88      }
    89  
    90      public void setBeanCollectionSelect(String beanCollectionSelect[]) {
    91          this.beanCollectionSelect = beanCollectionSelect;
    92      }
    93  
    94  
    95      /**
    96       * A boolean property whose initial value is true.
    97       */
    98      private boolean booleanProperty = true;
    99  
    100     public boolean getBooleanProperty() {
    101         return (booleanProperty);
    102     }
    103 
    104     public void setBooleanProperty(boolean booleanProperty) {
    105         this.booleanProperty = booleanProperty;
    106     }
    107 
    108 
    109     /**
    110      * A multiple-String SELECT element using a collection.
    111      */
    112     private String[] collectionSelect = { "Value 2", "Value 4",
    113             "Value 6" };
    114 
    115     public String[] getCollectionSelect() {
    116         return (this.collectionSelect);
    117     }
    118 
    119     public void setCollectionSelect(String collectionSelect[]) {
    120         this.collectionSelect = collectionSelect;
    121     }
    122 
    123 
    124     /**
    125      * A double property.
    126      */
    127     private double doubleProperty = 321.0;
    128 
    129     public double getDoubleProperty() {
    130         return (this.doubleProperty);
    131     }
    132 
    133     public void setDoubleProperty(double doubleProperty) {
    134         this.doubleProperty = doubleProperty;
    135     }
    136 
    137 
    138     /**
    139      * A boolean property whose initial value is false
    140      */
    141     private boolean falseProperty = false;
    142 
    143     public boolean getFalseProperty() {
    144         return (falseProperty);
    145     }
    146 
    147     public void setFalseProperty(boolean falseProperty) {
    148         this.falseProperty = falseProperty;
    149     }
    150 
    151 
    152     /**
    153      * A float property.
    154      */
    155     private float floatProperty = (float) 123.0;
    156 
    157     public float getFloatProperty() {
    158         return (this.floatProperty);
    159     }
    160 
    161     public void setFloatProperty(float floatProperty) {
    162         this.floatProperty = floatProperty;
    163     }
    164 
    165 
    166     /**
    167      * Integer arrays that are accessed as an array as well as indexed.
    168      */
    169     private int intArray[] = { 0, 10, 20, 30, 40 };
    170 
    171     public int[] getIntArray() {
    172         return (this.intArray);
    173     }
    174 
    175     public void setIntArray(int intArray[]) {
    176         this.intArray = intArray;
    177     }
    178 
    179     private int intIndexed[] = { 0, 10, 20, 30, 40 };
    180 
    181     public int getIntIndexed(int index) {
    182         return (intIndexed[index]);
    183     }
    184 
    185     public void setIntIndexed(int index, int value) {
    186         intIndexed[index] = value;
    187     }
    188 
    189 
    190     private int intMultibox[] = new int[0];
    191 
    192     public int[] getIntMultibox() {
    193         return (this.intMultibox);
    194     }
    195 
    196     public void setIntMultibox(int intMultibox[]) {
    197         this.intMultibox = intMultibox;
    198     }
    199 
    200     /**
    201      * An integer property.
    202      */
    203     private int intProperty = 123;
    204 
    205     public int getIntProperty() {
    206         return (this.intProperty);
    207     }
    208 
    209     public void setIntProperty(int intProperty) {
    210         this.intProperty = intProperty;
    211     }
    212 
    213 
    214     /**
    215      * A long property.
    216      */
    217     private long longProperty = 321;
    218 
    219     public long getLongProperty() {
    220         return (this.longProperty);
    221     }
    222 
    223     public void setLongProperty(long longProperty) {
    224         this.longProperty = longProperty;
    225     }
    226 
    227 
    228     /**
    229      * A multiple-String SELECT element.
    230      */
    231     private String[] multipleSelect = { "Multiple 3", "Multiple 5",
    232             "Multiple 7" };
    233 
    234     public String[] getMultipleSelect() {
    235         return (this.multipleSelect);
    236     }
    237 
    238     public void setMultipleSelect(String multipleSelect[]) {
    239         this.multipleSelect = multipleSelect;
    240     }
    241 
    242 
    243     /**
    244      * A nested reference to another test bean (populated as needed).
    245      */
    246     private TestBean nested = null;
    247 
    248     public TestBean getNested() {
    249         if (nested == null) {
    250             nested = new TestBean();
    251         }
    252         return (nested);
    253     }
    254 
    255 
    256     /**
    257      * A String property with an initial value of null.
    258      */
    259     private String nullProperty = null;
    260 
    261     public String getNullProperty() {
    262         return (this.nullProperty);
    263     }
    264 
    265     public void setNullProperty(String nullProperty) {
    266         this.nullProperty = nullProperty;
    267     }
    268 
    269 
    270     /**
    271      * A short property.
    272      */
    273     private short shortProperty = (short) 987;
    274 
    275     public short getShortProperty() {
    276         return (this.shortProperty);
    277     }
    278 
    279     public void setShortProperty(short shortProperty) {
    280         this.shortProperty = shortProperty;
    281     }
    282 
    283 
    284     /**
    285      * A single-String value for a SELECT element.
    286      */
    287     private String singleSelect = "Single 5";
    288 
    289     public String getSingleSelect() {
    290         return (this.singleSelect);
    291     }
    292 
    293     public void setSingleSelect(String singleSelect) {
    294         this.singleSelect = singleSelect;
    295     }
    296 
    297 
    298     /**
    299      * String arrays that are accessed as an array as well as indexed.
    300      */
    301     private String stringArray[] =
    302             { "String 0", "String 1", "String 2", "String 3", "String 4" };
    303 
    304     public String[] getStringArray() {
    305         return (this.stringArray);
    306     }
    307 
    308     public void setStringArray(String stringArray[]) {
    309         this.stringArray = stringArray;
    310     }
    311 
    312     private String stringIndexed[] =
    313             { "String 0", "String 1", "String 2", "String 3", "String 4" };
    314 
    315     public String getStringIndexed(int index) {
    316         return (stringIndexed[index]);
    317     }
    318 
    319     public void setStringIndexed(int index, String value) {
    320         stringIndexed[index] = value;
    321     }
    322 
    323     private String indexedStrings[] =
    324             { "alpha", "beta", "gamma", "delta", "epsilon" };
    325 
    326     public String[] getIndexedStrings() {
    327         return (indexedStrings);
    328     }
    329 
    330     private String stringMultibox[] = new String[0];
    331 
    332     public String[] getStringMultibox() {
    333         return (this.stringMultibox);
    334     }
    335 
    336     public void setStringMultibox(String stringMultibox[]) {
    337         this.stringMultibox = stringMultibox;
    338     }
    339 
    340     /**
    341      * A String property.
    342      */
    343     private String stringProperty = "This is a string";
    344 
    345     public String getStringProperty() {
    346         return (this.stringProperty);
    347     }
    348 
    349     public void setStringProperty(String stringProperty) {
    350         this.stringProperty = stringProperty;
    351     }
    352 
    353     /**
    354      * An empty String property.
    355      */
    356     private String emptyStringProperty = "";
    357 
    358     public String getEmptyStringProperty() {
    359         return (this.emptyStringProperty);
    360     }
    361 
    362     public void setEmptyStringProperty(String emptyStringProperty) {
    363         this.emptyStringProperty = emptyStringProperty;
    364     }
    365 
    366     /**
    367      * A list of coordinate objects.
    368      */
    369     private Coord[] coords =
    370             { new Coord(0, 0), new Coord(0, 1), new Coord(1, 1),
    371                     new Coord(2, 0),
    372                     new Coord(2, 1)
    373             };
    374 
    375     public Coord[]  getCoords() {
    376         return (coords);
    377     }
    378 
    379     public Coord getCoord(int index) {
    380         return (coords[index]);
    381     }
    382 
    383     public void setCoord(int index, Coord coord) {
    384         coords[index] = coord;
    385     }
    386 
    387     /**
    388      * A list of images.
    389      */
    390     public String images[] = { "T1.gif", "T2.gif" };
    391 
    392     public String[] getImages() {
    393         return (images);
    394     }
    395 
    396     private Coord[] imageCoords = { new Coord(0, 0), new Coord(0, 0) };
    397 
    398     public Coord[]  getImageCoords() {
    399         return (imageCoords);
    400     }
    401 
    402     public Coord getImageCoord(int index) {
    403         return (imageCoords[index]);
    404     }
    405 
    406     public void setImageCoord(int index, Coord coord) {
    407         imageCoords[index] = coord;
    408     }
    409 
    410     /**
    411      * A property that allows a null value but is still used in a SELECT.
    412      */
    413     private String withNulls = null;
    414 
    415     public String getWithNulls() {
    416         return (this.withNulls);
    417     }
    418 
    419     public void setWithNulls(String withNulls) {
    420         this.withNulls = withNulls;
    421     }
    422 
    423     // --------------------------------------------------------- Public Methods
    424 
    425 
    426     /**
    427      * Reset the properties that will be received as input.
    428      */
    429     public void reset(ActionMapping mapping, HttpServletRequest request) {
    430 
    431         booleanProperty = false;
    432         collectionSelect = new String[0];
    433         intMultibox = new int[0];
    434         multipleSelect = new String[0];
    435         stringMultibox = new String[0];
    436         if (nested != null) {
    437             nested.reset(mapping, request);
    438         }
    439 
    440     }
    441 
    442 
    443 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
