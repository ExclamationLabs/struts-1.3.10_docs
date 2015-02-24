[View Javadoc](../../../../../apidocs/org/apache/struts/validator/LazyValidatorForm.html.md)


    1   /*
    2    * $Id: LazyValidatorForm.java 562121 2007-08-02 14:28:23Z niallp $
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
    21  package org.apache.struts.validator;
    22  
    23  import org.apache.commons.beanutils.DynaBean;
    24  import org.apache.commons.beanutils.LazyDynaBean;
    25  
    26  import java.util.List;
    27  import java.util.Map;
    28  
    29  /**
    30   * <p>Struts <i>Lazy</i> <code>ActionForm</code> which <i>wraps</i> a
    31   * <code>LazyDynaBean</code>.</p>
    32   *
    33   * <p>There isn't really that much to this implementation as most of the
    34   * <i>lazy</i> behaviour is in <code>LazyDynaBean</code> and <i>wrapping</i>
    35   * the <code>LazyDynaBean<code> is handled in the parent
    36   * <code>BeanValidatorForm</code>. The only thing it really does is populate
    37   * <i>indexed</i> properties which are a <code>List<code> type with a
    38   * <code>LazyDynaBean<code> in the <code>get(name, index)</code> method.</p>
    39   *
    40   * <p><i>Lazy</i> DynaBeans provide several types of <i>lazy</i>
    41   * behaviour:</p>
    42   *
    43   * <ul>
    44   *
    45   * <li><b><i>lazy</i> property addition</b> - properties which do not exist
    46   * are automatically added.</li>
    47   *
    48   * <li><b><i>lazy</i> List facilities</b> - automatically <i>grows</i> a
    49   * <code>List</code> or <code>Array</code> to accomodate the index value being
    50   * set.</li>
    51   *
    52   * <li><b><i>lazy</i> List creation</b> - automatic creation of a
    53   * <code>List</code> or <code>Array</code> for <i>indexed</i> properties, if
    54   * it doesn't exist.</li> <li><b><i>lazy</i> Map creation</b> - automatic
    55   * creation of a <code>Map</code> for <i>mapped</i> properties, if it doesn't
    56   * exist.</li>
    57   *
    58   * </ul>
    59   *
    60   * <p>Using this <i>lazy</i> <code>ActionForm</code> means that you don't have
    61   * to define the ActionForm's properties in the <code>struts-config.xml</code>.
    62   * However, a word of warning, everything in the Request gets populated into
    63   * this <code>ActionForm</code> circumventing the normal <i>firewall</i>
    64   * function of Struts forms. Therefore you should only <i>take out</i> of this
    65   * form properties you expect to be there rather than blindly populating all
    66   * the properties into the business tier.</p>
    67   *
    68   * <p>Having said that it is not necessary to pre-define properties in the
    69   * <code>struts-config.xml</code>, it is useful to sometimes do so for
    70   * <i>mapped</i> or <i>indexed</i> properties. For example, if you want to use
    71   * a different <code>Map<code> implementation from the default
    72   * <code>HashMap</code> or an array for indexed properties, rather than the
    73   * default <code>List</code> type:</p>
    74   *
    75   * <pre><code>
    76   *   &lt;form-bean name="myForm" type="org.apache.struts.validator.LazyValidatorForm"&gt;
    77   *     &lt;form-property name="myMap" type="java.util.TreeMap" /&gt;
    78   *     &lt;form-property name="myBeans" type="org.apache.commons.beanutils.LazyDynaBean[]"
    79   * /&gt;
    80   *   &lt;/form-bean&gt;
    81   * </code></pre>
    82   *
    83   * <p>Another reason for defining <i>indexed</i> properties in the
    84   * <code>struts-config.xml</code> is that if you are validating indexed
    85   * properties using the Validator and none are submitted then the indexed
    86   * property will be <code>null</code> which causes validator to fail.
    87   * Pre-defining them in the <code>struts-config.xml</code> will result in a
    88   * zero-length indexed property (array or List) being instantiated, avoiding
    89   * an issue with validator in that circumstance.</p>
    90   *
    91   * <p>This implementation validates using the ActionForm <i>name</i>. If you
    92   * require a version that validates according to the <i>path</i> then it can
    93   * be easily created in the following manner:</p>
    94   *
    95   * <pre><code>
    96   *    public class MyLazyForm extends LazyValidatorForm {
    97   *
    98   *        public MyLazyForm () {
    99   *            super();
    100  *            setPathValidation(true);
    101  *        }
    102  *
    103  *    }
    104  * </code></pre>
    105  *
    106  * <p>Rather than using this class, another alternative is to either use a
    107  * <code>LazyDynaBean</code> or custom version of <code>LazyDynaBean</code>
    108  * directly. Struts now automatically <i>wraps</i> objects which are not
    109  * <code>ActionForms</code> in a <code>BeanValidatorForm</code>. For
    110  * example:</p>
    111  *
    112  * <pre><code>
    113  *   &lt;form-bean name="myForm" type="org.apache.commons.beanutils.LazyDynaBean"&gt;
    114  *     &lt;form-property name="myBeans" type="org.apache.commons.beanutils.LazyDynaBean[]"
    115  * /&gt;
    116  *   &lt;/form-bean&gt;
    117  * </code></pre>
    118  *
    119  * @version $Rev: 562121 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    120  *          $
    121  * @see <a href="http://commons.apache.org/beanutils/apidocs/org/apache/commons/beanutils/package-summary.html.md#dynamic.lazy">Commons
    122  *      BeanUtils JavaDoc</a>
    123  * @since Struts 1.2.6
    124  */
    125 public class LazyValidatorForm extends BeanValidatorForm {
    126     // ------------------- Constructors ----------------------------------
    127 
    128     /**
    129      * Default Constructor which creates a <code>LazyDynaBean</code> to
    130      * <i>back</i> this form.
    131      */
    132     public LazyValidatorForm() {
    133         super(new LazyDynaBean());
    134     }
    135 
    136     /**
    137      */
    138     public LazyValidatorForm(DynaBean bean) {
    139         super(bean);
    140     }
    141 
    142     // ------------------- DynaBean methods ----------------------------------
    143 
    144     /**
    145      * <p>Return an indexed property value.</p>
    146      *
    147      * <p>If the "indexed" property is a <code>List</code> type then any
    148      * missing values are populated with a bean (created in the
    149      * <code>newIndexedBean(name)</code> method - in this implementation this
    150      * is a <code>LazyDynaBean</code> type.</p>
    151      */
    152     public Object get(String name, int index) {
    153         int size = size(name);
    154 
    155         // Get the indexed property
    156         Object value = dynaBean.get(name, index);
    157 
    158         // Create missing beans for Lists
    159         if (value == null) {
    160             Object indexedValue = dynaBean.get(name);
    161 
    162             if (List.class.isAssignableFrom(indexedValue.getClass())) {
    163                 for (int i = size; i <= index; i++) {
    164                     value = newIndexedBean(name);
    165                     set(name, i, value);
    166                 }
    167             }
    168         }
    169 
    170         return value;
    171     }
    172 
    173     // ------------------- Public methods ----------------------------------
    174 
    175     /**
    176      * <p>Return the <code>Map</code> containing the property values.</p>
    177      *
    178      * <p>Provided so that properties can be access using JSTL.</p>
    179      */
    180     public Map getMap() {
    181         return ((LazyDynaBean) dynaBean).getMap();
    182     }
    183 
    184     // ------------------- Protected methods ----------------------------------
    185 
    186     /**
    187      * <p>Creates new <code>DynaBean</code> instances to populate an 'indexed'
    188      * property of beans - defaults to <code>LazyDynaBean</code> type.</p>
    189      *
    190      * <p>Override this method if you require a different type of
    191      * <code>DynaBean</code>.</p>
    192      */
    193     protected DynaBean newIndexedBean(String name) {
    194         return new LazyDynaBean();
    195     }
    196 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
