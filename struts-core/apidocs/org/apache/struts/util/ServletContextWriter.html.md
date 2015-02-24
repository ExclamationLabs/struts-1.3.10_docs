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
<td align="left"><a href="class-use/ServletContextWriter.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ResponseUtils.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/TokenProcessor.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ServletContextWriter.html"><strong>FRAMES</strong></a>    <a href="ServletContextWriter.html"><strong>NO FRAMES</strong></a>    
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
 Class ServletContextWriter
---------------------------

    java.lang.Object
      java.io.Writer
          java.io.PrintWriter
              org.apache.struts.util.ServletContextWriter

**All Implemented Interfaces:**  
[Closeable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Closeable.html.md?is-external=true "class or interface in java.io"), [Flushable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Flushable.html?is-external=true "class or interface in java.io"), [Appendable](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Appendable.html?is-external=true "class or interface in java.lang")

------------------------------------------------------------------------

    public class ServletContextWriter

extends [PrintWriter](http://java.sun.com/j2se/1.4.2/docs/api/java/io/PrintWriter.html.md?is-external=true "class or interface in java.io")

A PrintWriter implementation that uses the logging facilities of a `javax.servlet.ServletContext` to output its results. Output will be buffered until a newline character is output, `flush()` is called, or until one of the `println()` methods is called. Along the way, carriage return characters are skipped.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  StringBuffer`

` buffer`
           The buffer into which we accumulate lines to be logged.

`protected  ServletContext`

` context`
           The servlet context with which we are associated.

`protected  boolean`

` error`
           The error state for this stream.

 <span id="fields_inherited_from_class_java.io.PrintWriter"></span>

| **Fields inherited from class java.io.[PrintWriter](http://java.sun.com/j2se/1.4.2/docs/api/java/io/PrintWriter.html.md?is-external=true "class or interface in java.io")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `out`                                                                                                                                                                    |

 <span id="fields_inherited_from_class_java.io.Writer"></span>

| **Fields inherited from class java.io.[Writer](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Writer.html.md?is-external=true "class or interface in java.io")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `lock`                                                                                                                                                         |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                            |
|----------------------------------------------------------------------------------------------------|
| ` ServletContextWriter(ServletContext context)`                                                    
            Construct a ServletContextWriter associated with the specified ServletContext instance.  |

  <span id="method_summary"></span>

**Method Summary**

` boolean`

` checkError()`
           Flush the stream and check for its error state.

` void`

` close()`
           Close the stream.

` void`

` flush()`
           Flush the stream.

` void`

` print(boolean b)`
           Print a boolean value.

` void`

` print(char c)`
           Print a character value.

` void`

` print(char[] c)`
           Print a character array.

` void`

` print(double d)`
           Print a double value.

` void`

` print(float f)`
           Print a float value.

` void`

` print(int i)`
           Print an integer value.

` void`

` print(long l)`
           Print a long value.

` void`

` print(Object o)`
           Print an object.

` void`

` print(String s)`
           Print a String value.

` void`

` println()`
           Terminate the current line and flush the buffer.

` void`

` println(boolean b)`
           Print a boolean value and terminate the line.

` void`

` println(char c)`
           Print a character value and terminate the line.

` void`

` println(char[] c)`
           Print a character array and terminate the line.

` void`

` println(double d)`
           Print a double value and terminate the line.

` void`

` println(float f)`
           Print a float value and terminate the line.

` void`

` println(int i)`
           Print an integer value and terminate the line.

` void`

` println(long l)`
           Print a long value and terminate the line.

` void`

` println(Object o)`
           Print an object and terminate the line.

` void`

` println(String s)`
           Print a String value and terminate the line.

` void`

` setError()`
           Set the error state for this stream.

` void`

` write(char c)`
           Write a single character to this stream.

` void`

` write(char[] buf)`
           Write an array of charaters to this stream.

` void`

` write(char[] buf, int off, int len)`
           Write the specified subset of an array of characters to this stream.

` void`

` write(int c)`
           Write a single character to this stream.

` void`

` write(String s)`
           Write a String to this stream.

` void`

` write(String s, int off, int len)`
           Write the specified portion of a String to this stream.

 <span id="methods_inherited_from_class_java.io.PrintWriter"></span>

| **Methods inherited from class java.io.[PrintWriter](http://java.sun.com/j2se/1.4.2/docs/api/java/io/PrintWriter.html.md?is-external=true "class or interface in java.io")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `append, append, append, clearError, format, format, printf, printf`                                                                                                      |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="buffer"></span>

### buffer

    protected StringBuffer buffer

The buffer into which we accumulate lines to be logged.

------------------------------------------------------------------------

<span id="context"></span>

### context

    protected ServletContext context

The servlet context with which we are associated.

------------------------------------------------------------------------

<span id="error"></span>

### error

    protected boolean error

The error state for this stream.

<span id="constructor_detail"></span>

**Constructor Detail**

### ServletContextWriter

    public ServletContextWriter(ServletContext context)

Construct a ServletContextWriter associated with the specified ServletContext instance.

**Parameters:**  
`context` - The associated servlet context

<span id="method_detail"></span>

**Method Detail**

### checkError

    public boolean checkError()

Flush the stream and check for its error state. **IMPLEMENTATION NOTE** - our associated servlet context gives no indication of problems with logging, so the only way this method will return `true` is if `setError()` is called.

**Overrides:**  
`checkError` in class `PrintWriter`

------------------------------------------------------------------------

### close

    public void close()

Close the stream.

**Specified by:**  
`close` in interface `Closeable`

**Overrides:**  
`close` in class `PrintWriter`

------------------------------------------------------------------------

### flush

    public void flush()

Flush the stream.

**Specified by:**  
`flush` in interface `Flushable`

**Overrides:**  
`flush` in class `PrintWriter`

------------------------------------------------------------------------

### print

    public void print(boolean b)

Print a boolean value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`b` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(char c)

Print a character value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`c` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(char[] c)

Print a character array.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`c` - The character array to be printed

------------------------------------------------------------------------

### print

    public void print(double d)

Print a double value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`d` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(float f)

Print a float value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`f` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(int i)

Print an integer value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`i` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(long l)

Print a long value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`l` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(Object o)

Print an object.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`o` - The value to be printed

------------------------------------------------------------------------

### print

    public void print(String s)

Print a String value.

**Overrides:**  
`print` in class `PrintWriter`

<!-- -->

**Parameters:**  
`s` - The value to be printed

------------------------------------------------------------------------

### println

    public void println()

Terminate the current line and flush the buffer.

**Overrides:**  
`println` in class `PrintWriter`

------------------------------------------------------------------------

### println

    public void println(boolean b)

Print a boolean value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`b` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(char c)

Print a character value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`c` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(char[] c)

Print a character array and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`c` - The character array to be printed

------------------------------------------------------------------------

### println

    public void println(double d)

Print a double value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`d` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(float f)

Print a float value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`f` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(int i)

Print an integer value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`i` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(long l)

Print a long value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`l` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(Object o)

Print an object and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`o` - The value to be printed

------------------------------------------------------------------------

### println

    public void println(String s)

Print a String value and terminate the line.

**Overrides:**  
`println` in class `PrintWriter`

<!-- -->

**Parameters:**  
`s` - The value to be printed

------------------------------------------------------------------------

### setError

    public void setError()

Set the error state for this stream.

**Overrides:**  
`setError` in class `PrintWriter`

------------------------------------------------------------------------

### write

    public void write(char c)

Write a single character to this stream.

**Parameters:**  
`c` - The character to be written

------------------------------------------------------------------------

### write

    public void write(int c)

Write a single character to this stream.

**Overrides:**  
`write` in class `PrintWriter`

<!-- -->

**Parameters:**  
`c` - The character to be written

------------------------------------------------------------------------

### write

    public void write(char[] buf)

Write an array of charaters to this stream.

**Overrides:**  
`write` in class `PrintWriter`

<!-- -->

**Parameters:**  
`buf` - The character array to be written

------------------------------------------------------------------------

### write

    public void write(char[] buf,
                      int off,
                      int len)

Write the specified subset of an array of characters to this stream.

**Overrides:**  
`write` in class `PrintWriter`

<!-- -->

**Parameters:**  
`buf` - The character array from which to write

`off` - The zero-relative starting offset to write

`len` - The number of characters to write

------------------------------------------------------------------------

### write

    public void write(String s)

Write a String to this stream.

**Overrides:**  
`write` in class `PrintWriter`

<!-- -->

**Parameters:**  
`s` - The string to be written

------------------------------------------------------------------------

### write

    public void write(String s,
                      int off,
                      int len)

Write the specified portion of a String to this stream.

**Overrides:**  
`write` in class `PrintWriter`

<!-- -->

**Parameters:**  
`s` - The String from which to write

`off` - The zero-relative starting offset to write

`len` - The number of characters to write

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
<td align="left"><a href="class-use/ServletContextWriter.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ResponseUtils.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/TokenProcessor.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/ServletContextWriter.html"><strong>FRAMES</strong></a>    <a href="ServletContextWriter.html"><strong>NO FRAMES</strong></a>    
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
