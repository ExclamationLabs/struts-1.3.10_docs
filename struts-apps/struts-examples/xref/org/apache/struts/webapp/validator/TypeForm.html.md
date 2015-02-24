[View Javadoc](../../../../../../apidocs/org/apache/struts/webapp/validator/TypeForm.html.md)


    1   /*
    2    * $Id: TypeForm.java 471754 2006-11-06 14:55:09Z husted $
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
    23  package org.apache.struts.webapp.validator;
    24  
    25  import java.io.Serializable;
    26  import java.util.ArrayList;
    27  import java.util.List;
    28  import javax.servlet.http.HttpServletRequest;
    29  import org.apache.struts.action.ActionMapping;
    30  import org.apache.struts.util.LabelValueBean;
    31  import org.apache.struts.validator.ValidatorForm;
    32  
    33  
    34  /**
    35   * Form bean for the user type page.
    36   *
    37  */
    38  public final class TypeForm extends ValidatorForm implements Serializable {
    39      private String action = null;
    40      private String name = null;  //Used to test Multiform per page validation when property name is 'name'
    41      private String sByte = null;
    42      private String sShort = null;
    43      private String sInteger = null;
    44      private String sIntRange = null;
    45      private String sLong = null;
    46      private String sFloat = null;
    47      private String sFloatRange = null;
    48      private String sDouble = null;
    49      private String sDate = null;
    50      private String sCreditCard = null;
    51      private String sEmail = null;
    52      private String sUrl = null;
    53      private String sMask = null;
    54      private String sMinMaxLength = null;
    55      private String sSatisfaction = null;
    56      private String[] sOsList = null;
    57      private String sOverallSatisfaction = null;
    58      private String sWouldRecommend = null;
    59      private String[] sUsedLanguages = null;
    60  
    61      private List lNames = initNames();
    62  
    63    public String getAction() {
    64   return action;
    65     }
    66  
    67     public void setAction(String action) {
    68         this.action = action;
    69     }
    70  
    71    public String getName() {
    72   return name;
    73     }
    74  
    75     public void setName(String name) {
    76         this.name = name;
    77     }
    78  
    79       public String getByte() {
    80         return sByte;
    81      }
    82  
    83      public void setByte(String sByte) {
    84          this.sByte = sByte;
    85      }
    86  
    87      public String getShort() {
    88         return sShort;
    89      }
    90  
    91      public void setShort(String sShort) {
    92          this.sShort = sShort;
    93      }
    94  
    95      public String getInteger() {
    96         return sInteger;
    97      }
    98  
    99      public void setInteger(String sInteger) {
    100         this.sInteger = sInteger;
    101     }
    102 
    103     public String getIntRange() {
    104         return sIntRange;
    105     }
    106 
    107     public void setIntRange(String sIntRange) {
    108         this.sIntRange = sIntRange;
    109     }
    110 
    111     public String getLong() {
    112        return sLong;
    113     }
    114 
    115     public void setLong(String sLong) {
    116         this.sLong = sLong;
    117     }
    118 
    119     public String getFloat() {
    120        return sFloat;
    121     }
    122 
    123     public void setFloat(String sFloat) {
    124         this.sFloat = sFloat;
    125     }
    126 
    127    /**
    128     * Float field with range checking
    129     * @return
    130     */
    131     public String getFloatRange() {
    132        return sFloatRange;
    133     }
    134 
    135    /**
    136     * Float field with range checking
    137     * @param sFloatRange
    138     */
    139     public void setFloatRange(String sFloatRange) {
    140           this.sFloatRange = sFloatRange;
    141     }
    142 
    143     public String getDouble() {
    144        return sDouble;
    145     }
    146 
    147     public void setDouble(String sDouble) {
    148         this.sDouble = sDouble;
    149     }
    150 
    151     public String getDate() {
    152        return sDate;
    153     }
    154 
    155     public void setDate(String sDate) {
    156         this.sDate = sDate;
    157     }
    158 
    159     public String getCreditCard() {
    160        return sCreditCard;
    161     }
    162 
    163     public void setCreditCard(String sCreditCard) {
    164         this.sCreditCard = sCreditCard;
    165     }
    166     public String getMinMaxLength() {
    167         return sMinMaxLength;
    168     }
    169 
    170     public void setMinMaxLength(String sMinMaxLength) {
    171         this.sMinMaxLength = sMinMaxLength;
    172     }
    173 
    174     public String getUrl() {
    175         return sUrl;
    176     }
    177 
    178     public void setUrl(String sUrl) {
    179         this.sUrl = sUrl;
    180     }
    181 
    182     public String getEmail() {
    183         return sEmail;
    184     }
    185 
    186     public void setEmail(String sEmail) {
    187         this.sEmail = sEmail;
    188     }
    189 
    190     public String getMask() {
    191         return sMask;
    192     }
    193 
    194     public void setMask(String sMask) {
    195         this.sMask = sMask;
    196     }
    197 
    198     public String getSatisfaction() {
    199        return sSatisfaction;
    200     }
    201 
    202     public void setSatisfaction(String sSatisfaction) {
    203         this.sSatisfaction = sSatisfaction;
    204     }
    205 
    206     public String[] getOsList() {
    207        return sOsList;
    208     }
    209 
    210     public void setOsList(String[] anOsList) {
    211         this.sOsList = anOsList;
    212     }
    213 
    214     public String getOverallSatisfaction() {
    215        return sOverallSatisfaction;
    216     }
    217 
    218     public void setOverallSatisfaction(String anOverallSatisfaction) {
    219         this.sOverallSatisfaction = anOverallSatisfaction;
    220     }
    221 
    222     public String getWouldRecommend() {
    223        return sWouldRecommend;
    224     }
    225 
    226     public void setWouldRecommend(String anWouldRecommend) {
    227         this.sWouldRecommend = anWouldRecommend;
    228     }
    229 
    230     public String[] getUsedLanguages() {
    231        return sUsedLanguages;
    232     }
    233 
    234     public void setUsedLanguages(String[] anUsedLanguages) {
    235         this.sUsedLanguages = anUsedLanguages;
    236     }
    237 
    238     public List getNameList() {
    239        return lNames;
    240     }
    241 
    242     public void setNameList(List lNames) {
    243        this.lNames = lNames;
    244     }
    245 
    246     /**
    247      * Reset all properties to their default values.
    248      *
    249      * @param mapping The mapping used to select this instance
    250      * @param request The servlet request we are processing
    251      */
    252     public void reset(ActionMapping mapping, HttpServletRequest request) {
    253        String reset = (String)request.getAttribute("typeForm.reset");
    254        if ((null != reset)|| ("true".equals(reset))) {
    255            action = null;
    256            sByte = null;
    257            sShort = null;
    258            sInteger = null;
    259            sIntRange = null;
    260            sLong = null;
    261            sFloat = null;
    262            sFloatRange = null;
    263            sDouble = null;
    264            sDate = null;
    265            sCreditCard = null;
    266            sMinMaxLength = null;
    267            sEmail = null;
    268            sUrl = null;
    269            sMask = null;
    270            sSatisfaction = null;
    271            sOsList = null;
    272            sOverallSatisfaction = null;
    273            sUsedLanguages = null;
    274        }
    275        //lNames = initNames();
    276     }
    277 
    278     /**
    279      * Initialize list.
    280      * @return empty list of LabelValueBeans
    281     */
    282     private static List initNames() {
    283        List lResults = new ArrayList();
    284 
    285        for (int i = 0; i < 3; i++) {
    286           lResults.add(new LabelValueBean(null, null));
    287        }
    288 
    289        return lResults;
    290     }
    291 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
