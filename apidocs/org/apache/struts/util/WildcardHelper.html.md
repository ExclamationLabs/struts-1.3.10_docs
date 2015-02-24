------------------------------------------------------------------------

<span id="navbar_top"></span> [](#skip-navbar_top "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_top_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/WildcardHelper.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/util/TokenProcessor.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/WildcardHelper.html"><strong>FRAMES</strong></a>    <a href="WildcardHelper.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.util
 Class WildcardHelper
----------------------

    java.lang.Object
      org.apache.struts.util.WildcardHelper

------------------------------------------------------------------------

    public class WildcardHelper

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

This class is an utility class that perform wilcard-patterns matching and isolation taken from Apache Cocoon.

**Since:**  
Struts 1.2

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected static int`

` MATCH_BEGIN`
           The int representing begin in the pattern `int []`.

`protected static int`

`MATCH_END`
           The int value that terminates the pattern `int []`.

`protected static int`

` MATCH_FILE`
           The int representing '\*' in the pattern `int []`.

`protected static int`

` MATCH_PATH`
           The int representing '\*\*' in the pattern `int []`.

`protected static int`

` MATCH_THEEND`
           The int representing end in pattern `int []`.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` WildcardHelper()`     
                          |

  <span id="method_summary"></span>

**Method Summary**

` int[]`

` compilePattern(String data)`
            Translate the given `String` into a `int []` representing the pattern matchable by this class.

`protected  int`

` indexOfArray(int[] r, int rpos, int rend, char[] d, int dpos)`
           Get the offset of a part of an int array within a char array.

`protected  int`

` lastIndexOfArray(int[] r, int rpos, int rend, char[] d, int dpos)`
           Get the offset of a last occurance of an int array within a char array.

` boolean`

` match(Map map, String data, int[] expr)`
           Match a pattern agains a string and isolates wildcard replacement into a `Stack`.

`protected  boolean`

` matchArray(int[] r, int rpos, int rend, char[] d, int dpos)`
           Matches elements of array r from rpos to rend with array d, starting from dpos.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="MATCH_FILE"></span>

### MATCH\_FILE

    protected static final int MATCH_FILE

The int representing '\*' in the pattern `int []`.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.util.WildcardHelper.MATCH_FILE)

------------------------------------------------------------------------

<span id="MATCH_PATH"></span>

### MATCH\_PATH

    protected static final int MATCH_PATH

The int representing '\*\*' in the pattern `int []`.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.util.WildcardHelper.MATCH_PATH)

------------------------------------------------------------------------

<span id="MATCH_BEGIN"></span>

### MATCH\_BEGIN

    protected static final int MATCH_BEGIN

The int representing begin in the pattern `int []`.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.util.WildcardHelper.MATCH_BEGIN)

------------------------------------------------------------------------

<span id="MATCH_THEEND"></span>

### MATCH\_THEEND

    protected static final int MATCH_THEEND

The int representing end in pattern `int []`.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.util.WildcardHelper.MATCH_THEEND)

------------------------------------------------------------------------

<span id="MATCH_END"></span>

### MATCH\_END

    protected static final int MATCH_END

The int value that terminates the pattern `int []`.

**See Also:**  
[Constant Field Values](../../../../constant-values.html.md#org.apache.struts.util.WildcardHelper.MATCH_END)

<span id="constructor_detail"></span>

**Constructor Detail**

### WildcardHelper

    public WildcardHelper()

<span id="method_detail"></span>

**Method Detail**

### compilePattern

    public int[] compilePattern(String data)

Translate the given `String` into a `int []` representing the pattern matchable by this class.
 This function translates a `String` into an int array converting the special '\*' and '\\' characters.
 Here is how the conversion algorithm works:

-   The '\*' character is converted to MATCH\_FILE, meaning that zero or more characters (excluding the path separator '/') are to be matched.
-   The '\*\*' sequence is converted to MATCH\_PATH, meaning that zero or more characters (including the path separator '/') are to be matched.
-   The '\\' character is used as an escape sequence ('\\\*' is translated in '\*', not in MATCH\_FILE). If an exact '\\' character is to be matched the source string must contain a '\\\\'. sequence.

When more than two '\*' characters, not separated by another character, are found their value is considered as '\*\*' (MATCH\_PATH).
 The array is always terminated by a special value (MATCH\_END).
 All MATCH\* values are less than zero, while normal characters are equal or greater.

**Parameters:**  
`data` - The string to translate.

**Returns:**  
The encoded string as an int array, terminated by the MATCH\_END value (don't consider the array length).

**Throws:**  
`NullPointerException` - If data is null.

------------------------------------------------------------------------

### match

    public boolean match(Map map,
                         String data,
                         int[] expr)

Match a pattern agains a string and isolates wildcard replacement into a `Stack`.

**Parameters:**  
`map` - The map to store matched values

`data` - The string to match

`expr` - The compiled wildcard expression

**Returns:**  
True if a match

**Throws:**  
`NullPointerException` - If any parameters are null

------------------------------------------------------------------------

### indexOfArray

    protected int indexOfArray(int[] r,
                               int rpos,
                               int rend,
                               char[] d,
                               int dpos)

Get the offset of a part of an int array within a char array.
 This method return the index in d of the first occurrence after dpos of that part of array specified by r, starting at rpos and terminating at rend.

**Parameters:**  
`r` - The array containing the data that need to be matched in d.

`rpos` - The index of the first character in r to look for.

`rend` - The index of the last character in r to look for plus 1.

`d` - The array of char that should contain a part of r.

`dpos` - The starting offset in d for the matching.

**Returns:**  
The offset in d of the part of r matched in d or -1 if that was not found.

------------------------------------------------------------------------

### lastIndexOfArray

    protected int lastIndexOfArray(int[] r,
                                   int rpos,
                                   int rend,
                                   char[] d,
                                   int dpos)

Get the offset of a last occurance of an int array within a char array.
 This method return the index in d of the last occurrence after dpos of that part of array specified by r, starting at rpos and terminating at rend.

**Parameters:**  
`r` - The array containing the data that need to be matched in d.

`rpos` - The index of the first character in r to look for.

`rend` - The index of the last character in r to look for plus 1.

`d` - The array of char that should contain a part of r.

`dpos` - The starting offset in d for the matching.

**Returns:**  
The offset in d of the last part of r matched in d or -1 if that was not found.

------------------------------------------------------------------------

### matchArray

    protected boolean matchArray(int[] r,
                                 int rpos,
                                 int rend,
                                 char[] d,
                                 int dpos)

Matches elements of array r from rpos to rend with array d, starting from dpos.
 This method return true if elements of array r from rpos to rend equals elements of array d starting from dpos to dpos+(rend-rpos).

**Parameters:**  
`r` - The array containing the data that need to be matched in d.

`rpos` - The index of the first character in r to look for.

`rend` - The index of the last character in r to look for.

`d` - The array of char that should start from a part of r.

`dpos` - The starting offset in d for the matching.

**Returns:**  
true if array d starts from portion of array r.

------------------------------------------------------------------------

<span id="navbar_bottom"></span> [](#skip-navbar_bottom "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_bottom_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/WildcardHelper.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../org/apache/struts/util/TokenProcessor.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/WildcardHelper.html"><strong>FRAMES</strong></a>    <a href="WildcardHelper.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
