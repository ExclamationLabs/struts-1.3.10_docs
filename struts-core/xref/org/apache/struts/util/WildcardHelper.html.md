[View Javadoc](../../../../../apidocs/org/apache/struts/util/WildcardHelper.html.md)


    1   /*
    2    * $Id: WildcardHelper.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import java.util.Map;
    24  
    25  /**
    26   * This class is an utility class that perform wilcard-patterns matching and
    27   * isolation taken from Apache Cocoon.
    28   *
    29   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    30   *          $
    31   * @since Struts 1.2
    32   */
    33  public class WildcardHelper {
    34      /**
    35       * The int representing '*' in the pattern <code>int []</code>.
    36       */
    37      protected static final int MATCH_FILE = -1;
    38  
    39      /**
    40       * The int representing '**' in the pattern <code>int []</code>.
    41       */
    42      protected static final int MATCH_PATH = -2;
    43  
    44      /**
    45       * The int representing begin in the pattern <code>int []</code>.
    46       */
    47      protected static final int MATCH_BEGIN = -4;
    48  
    49      /**
    50       * The int representing end in pattern <code>int []</code>.
    51       */
    52      protected static final int MATCH_THEEND = -5;
    53  
    54      /**
    55       * The int value that terminates the pattern <code>int []</code>.
    56       */
    57      protected static final int MATCH_END = -3;
    58  
    59      /**
    60       * <p> Translate the given <code>String</code> into a <code>int []</code>
    61       * representing the pattern matchable by this class. <br> This function
    62       * translates a <code>String</code> into an int array converting the
    63       * special '*' and '\' characters. <br> Here is how the conversion
    64       * algorithm works:</p>
    65       *
    66       * <ul>
    67       *
    68       * <li>The '*' character is converted to MATCH_FILE, meaning that zero or
    69       * more characters (excluding the path separator '/') are to be
    70       * matched.</li>
    71       *
    72       * <li>The '**' sequence is converted to MATCH_PATH, meaning that zero or
    73       * more characters (including the path separator '/') are to be
    74       * matched.</li>
    75       *
    76       * <li>The '\' character is used as an escape sequence ('\*' is translated
    77       * in '*', not in MATCH_FILE). If an exact '\' character is to be matched
    78       * the source string must contain a '\\'. sequence.</li>
    79       *
    80       * </ul>
    81       *
    82       * <p>When more than two '*' characters, not separated by another
    83       * character, are found their value is considered as '**' (MATCH_PATH).
    84       * <br> The array is always terminated by a special value (MATCH_END).
    85       * <br> All MATCH* values are less than zero, while normal characters are
    86       * equal or greater.</p>
    87       *
    88       * @param data The string to translate.
    89       * @return The encoded string as an int array, terminated by the MATCH_END
    90       *         value (don't consider the array length).
    91       * @throws NullPointerException If data is null.
    92       */
    93      public int[] compilePattern(String data) {
    94          // Prepare the arrays
    95          int[] expr = new int[data.length() + 2];
    96          char[] buff = data.toCharArray();
    97  
    98          // Prepare variables for the translation loop
    99          int y = 0;
    100         boolean slash = false;
    101 
    102         // Must start from beginning
    103         expr[y++] = MATCH_BEGIN;
    104 
    105         if (buff.length > 0) {
    106             if (buff[0] == '\\') {
    107                 slash = true;
    108             } else if (buff[0] == '*') {
    109                 expr[y++] = MATCH_FILE;
    110             } else {
    111                 expr[y++] = buff[0];
    112             }
    113 
    114             // Main translation loop
    115             for (int x = 1; x < buff.length; x++) {
    116                 // If the previous char was '\' simply copy this char.
    117                 if (slash) {
    118                     expr[y++] = buff[x];
    119                     slash = false;
    120 
    121                     // If the previous char was not '\' we have to do a bunch of
    122                     // checks
    123                 } else {
    124                     // If this char is '\' declare that and continue
    125                     if (buff[x] == '\\') {
    126                         slash = true;
    127 
    128                         // If this char is '*' check the previous one
    129                     } else if (buff[x] == '*') {
    130                         // If the previous character als was '*' match a path
    131                         if (expr[y - 1] <= MATCH_FILE) {
    132                             expr[y - 1] = MATCH_PATH;
    133                         } else {
    134                             expr[y++] = MATCH_FILE;
    135                         }
    136                     } else {
    137                         expr[y++] = buff[x];
    138                     }
    139                 }
    140             }
    141         }
    142 
    143         // Must match end at the end
    144         expr[y] = MATCH_THEEND;
    145 
    146         return expr;
    147     }
    148 
    149     /**
    150      * Match a pattern agains a string and isolates wildcard replacement into
    151      * a <code>Stack</code>.
    152      *
    153      * @param map  The map to store matched values
    154      * @param data The string to match
    155      * @param expr The compiled wildcard expression
    156      * @return True if a match
    157      * @throws NullPointerException If any parameters are null
    158      */
    159     public boolean match(Map map, String data, int[] expr) {
    160         if (map == null) {
    161             throw new NullPointerException("No map provided");
    162         }
    163 
    164         if (data == null) {
    165             throw new NullPointerException("No data provided");
    166         }
    167 
    168         if (expr == null) {
    169             throw new NullPointerException("No pattern expression provided");
    170         }
    171 
    172         char[] buff = data.toCharArray();
    173 
    174         // Allocate the result buffer
    175         char[] rslt = new char[expr.length + buff.length];
    176 
    177         // The previous and current position of the expression character
    178         // (MATCH_*)
    179         int charpos = 0;
    180 
    181         // The position in the expression, input, translation and result arrays
    182         int exprpos = 0;
    183         int buffpos = 0;
    184         int rsltpos = 0;
    185         int offset = -1;
    186 
    187         // The matching count
    188         int mcount = 0;
    189 
    190         // We want the complete data be in {0}
    191         map.put(Integer.toString(mcount), data);
    192 
    193         // First check for MATCH_BEGIN
    194         boolean matchBegin = false;
    195 
    196         if (expr[charpos] == MATCH_BEGIN) {
    197             matchBegin = true;
    198             exprpos = ++charpos;
    199         }
    200 
    201         // Search the fist expression character (except MATCH_BEGIN - already
    202         // skipped)
    203         while (expr[charpos] >= 0) {
    204             charpos++;
    205         }
    206 
    207         // The expression charater (MATCH_*)
    208         int exprchr = expr[charpos];
    209 
    210         while (true) {
    211             // Check if the data in the expression array before the current
    212             // expression character matches the data in the input buffer
    213             if (matchBegin) {
    214                 if (!matchArray(expr, exprpos, charpos, buff, buffpos)) {
    215                     return (false);
    216                 }
    217 
    218                 matchBegin = false;
    219             } else {
    220                 offset = indexOfArray(expr, exprpos, charpos, buff, buffpos);
    221 
    222                 if (offset < 0) {
    223                     return (false);
    224                 }
    225             }
    226 
    227             // Check for MATCH_BEGIN
    228             if (matchBegin) {
    229                 if (offset != 0) {
    230                     return (false);
    231                 }
    232 
    233                 matchBegin = false;
    234             }
    235 
    236             // Advance buffpos
    237             buffpos += (charpos - exprpos);
    238 
    239             // Check for END's
    240             if (exprchr == MATCH_END) {
    241                 if (rsltpos > 0) {
    242                     map.put(Integer.toString(++mcount),
    243                         new String(rslt, 0, rsltpos));
    244                 }
    245 
    246                 // Don't care about rest of input buffer
    247                 return (true);
    248             } else if (exprchr == MATCH_THEEND) {
    249                 if (rsltpos > 0) {
    250                     map.put(Integer.toString(++mcount),
    251                         new String(rslt, 0, rsltpos));
    252                 }
    253 
    254                 // Check that we reach buffer's end
    255                 return (buffpos == buff.length);
    256             }
    257 
    258             // Search the next expression character
    259             exprpos = ++charpos;
    260 
    261             while (expr[charpos] >= 0) {
    262                 charpos++;
    263             }
    264 
    265             int prevchr = exprchr;
    266 
    267             exprchr = expr[charpos];
    268 
    269             // We have here prevchr == * or **.
    270             offset =
    271                 (prevchr == MATCH_FILE)
    272                 ? indexOfArray(expr, exprpos, charpos, buff, buffpos)
    273                 : lastIndexOfArray(expr, exprpos, charpos, buff, buffpos);
    274 
    275             if (offset < 0) {
    276                 return (false);
    277             }
    278 
    279             // Copy the data from the source buffer into the result buffer
    280             // to substitute the expression character
    281             if (prevchr == MATCH_PATH) {
    282                 while (buffpos < offset) {
    283                     rslt[rsltpos++] = buff[buffpos++];
    284                 }
    285             } else {
    286                 // Matching file, don't copy '/'
    287                 while (buffpos < offset) {
    288                     if (buff[buffpos] == '/') {
    289                         return (false);
    290                     }
    291 
    292                     rslt[rsltpos++] = buff[buffpos++];
    293                 }
    294             }
    295 
    296             map.put(Integer.toString(++mcount), new String(rslt, 0, rsltpos));
    297             rsltpos = 0;
    298         }
    299     }
    300 
    301     /**
    302      * Get the offset of a part of an int array within a char array. <br> This
    303      * method return the index in d of the first occurrence after dpos of that
    304      * part of array specified by r, starting at rpos and terminating at
    305      * rend.
    306      *
    307      * @param r    The array containing the data that need to be matched in
    308      *             d.
    309      * @param rpos The index of the first character in r to look for.
    310      * @param rend The index of the last character in r to look for plus 1.
    311      * @param d    The array of char that should contain a part of r.
    312      * @param dpos The starting offset in d for the matching.
    313      * @return The offset in d of the part of r matched in d or -1 if that was
    314      *         not found.
    315      */
    316     protected int indexOfArray(int[] r, int rpos, int rend, char[] d,
    317         int dpos) {
    318         // Check if pos and len are legal
    319         if (rend < rpos) {
    320             throw new IllegalArgumentException("rend < rpos");
    321         }
    322 
    323         // If we need to match a zero length string return current dpos
    324         if (rend == rpos) {
    325             return (d.length); //?? dpos?
    326         }
    327 
    328         // If we need to match a 1 char length string do it simply
    329         if ((rend - rpos) == 1) {
    330             // Search for the specified character
    331             for (int x = dpos; x < d.length; x++) {
    332                 if (r[rpos] == d[x]) {
    333                     return (x);
    334                 }
    335             }
    336         }
    337 
    338         // Main string matching loop. It gets executed if the characters to
    339         // match are less then the characters left in the d buffer
    340         while (((dpos + rend) - rpos) <= d.length) {
    341             // Set current startpoint in d
    342             int y = dpos;
    343 
    344             // Check every character in d for equity. If the string is matched
    345             // return dpos
    346             for (int x = rpos; x <= rend; x++) {
    347                 if (x == rend) {
    348                     return (dpos);
    349                 }
    350 
    351                 if (r[x] != d[y++]) {
    352                     break;
    353                 }
    354             }
    355 
    356             // Increase dpos to search for the same string at next offset
    357             dpos++;
    358         }
    359 
    360         // The remaining chars in d buffer were not enough or the string
    361         // wasn't matched
    362         return (-1);
    363     }
    364 
    365     /**
    366      * Get the offset of a last occurance of an int array within a char array.
    367      * <br> This method return the index in d of the last occurrence after
    368      * dpos of that part of array specified by r, starting at rpos and
    369      * terminating at rend.
    370      *
    371      * @param r    The array containing the data that need to be matched in
    372      *             d.
    373      * @param rpos The index of the first character in r to look for.
    374      * @param rend The index of the last character in r to look for plus 1.
    375      * @param d    The array of char that should contain a part of r.
    376      * @param dpos The starting offset in d for the matching.
    377      * @return The offset in d of the last part of r matched in d or -1 if
    378      *         that was not found.
    379      */
    380     protected int lastIndexOfArray(int[] r, int rpos, int rend, char[] d,
    381         int dpos) {
    382         // Check if pos and len are legal
    383         if (rend < rpos) {
    384             throw new IllegalArgumentException("rend < rpos");
    385         }
    386 
    387         // If we need to match a zero length string return current dpos
    388         if (rend == rpos) {
    389             return (d.length); //?? dpos?
    390         }
    391 
    392         // If we need to match a 1 char length string do it simply
    393         if ((rend - rpos) == 1) {
    394             // Search for the specified character
    395             for (int x = d.length - 1; x > dpos; x--) {
    396                 if (r[rpos] == d[x]) {
    397                     return (x);
    398                 }
    399             }
    400         }
    401 
    402         // Main string matching loop. It gets executed if the characters to
    403         // match are less then the characters left in the d buffer
    404         int l = d.length - (rend - rpos);
    405 
    406         while (l >= dpos) {
    407             // Set current startpoint in d
    408             int y = l;
    409 
    410             // Check every character in d for equity. If the string is matched
    411             // return dpos
    412             for (int x = rpos; x <= rend; x++) {
    413                 if (x == rend) {
    414                     return (l);
    415                 }
    416 
    417                 if (r[x] != d[y++]) {
    418                     break;
    419                 }
    420             }
    421 
    422             // Decrease l to search for the same string at next offset
    423             l--;
    424         }
    425 
    426         // The remaining chars in d buffer were not enough or the string
    427         // wasn't matched
    428         return (-1);
    429     }
    430 
    431     /**
    432      * Matches elements of array r from rpos to rend with array d, starting
    433      * from dpos. <br> This method return true if elements of array r from
    434      * rpos to rend equals elements of array d starting from dpos to
    435      * dpos+(rend-rpos).
    436      *
    437      * @param r    The array containing the data that need to be matched in
    438      *             d.
    439      * @param rpos The index of the first character in r to look for.
    440      * @param rend The index of the last character in r to look for.
    441      * @param d    The array of char that should start from a part of r.
    442      * @param dpos The starting offset in d for the matching.
    443      * @return true if array d starts from portion of array r.
    444      */
    445     protected boolean matchArray(int[] r, int rpos, int rend, char[] d,
    446         int dpos) {
    447         if ((d.length - dpos) < (rend - rpos)) {
    448             return (false);
    449         }
    450 
    451         for (int i = rpos; i < rend; i++) {
    452             if (r[i] != d[dpos++]) {
    453                 return (false);
    454             }
    455         }
    456 
    457         return (true);
    458     }
    459 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
