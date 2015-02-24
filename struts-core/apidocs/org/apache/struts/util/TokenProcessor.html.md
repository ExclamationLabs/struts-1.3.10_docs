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
<td align="left"><a href="class-use/TokenProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ServletContextWriter.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/WildcardHelper.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/TokenProcessor.html"><strong>FRAMES</strong></a>    <a href="TokenProcessor.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.util
 Class TokenProcessor
----------------------

    java.lang.Object
      org.apache.struts.util.TokenProcessor

------------------------------------------------------------------------

    public class TokenProcessor

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

TokenProcessor is responsible for handling all token related functionality. The methods in this class are synchronized to protect token processing from multiple threads. Servlet containers are allowed to return a different HttpSession object for two threads accessing the same session so it is not possible to synchronize on the session.

**Since:**  
Struts 1.1

------------------------------------------------------------------------

<span id="constructor_summary"></span>

**Constructor Summary**

`protected`

` TokenProcessor()`
           Protected constructor for TokenProcessor.

  <span id="method_summary"></span>

**Method Summary**

` String`

` generateToken(HttpServletRequest request)`
           Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

` String`

` generateToken(String id)`
           Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

`static TokenProcessor`

` getInstance()`
           Retrieves the singleton instance of this class.

` boolean`

` isTokenValid(HttpServletRequest request)`
           Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it.

` boolean`

` isTokenValid(HttpServletRequest request, boolean reset)`
           Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it.

` void`

` resetToken(HttpServletRequest request)`
           Reset the saved transaction token in the user's session.

` void`

` saveToken(HttpServletRequest request)`
           Save a new transaction token in the user's current session, creating a new session if necessary.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="constructor_detail"></span>

**Constructor Detail**

### TokenProcessor

    protected TokenProcessor()

Protected constructor for TokenProcessor. Use TokenProcessor.getInstance() to obtain a reference to the processor.

<span id="method_detail"></span>

**Method Detail**

### getInstance

    public static TokenProcessor getInstance()

Retrieves the singleton instance of this class.

------------------------------------------------------------------------

### isTokenValid

    public boolean isTokenValid(HttpServletRequest request)

Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it. Returns `false` under any of the following circumstances:

-   No session associated with this request
-   No transaction token saved in the session
-   No transaction token included as a request parameter
-   The included transaction token value does not match the transaction token in the user's session

**Parameters:**  
`request` - The servlet request we are processing

------------------------------------------------------------------------

### isTokenValid

    public boolean isTokenValid(HttpServletRequest request,
                                boolean reset)

Return `true` if there is a transaction token stored in the user's current session, and the value submitted as a request parameter with this action matches it. Returns `false`

-   No session associated with this request
-   No transaction token saved in the session
-   No transaction token included as a request parameter
-   The included transaction token value does not match the transaction token in the user's session

**Parameters:**  
`request` - The servlet request we are processing

`reset` - Should we reset the token after checking it?

------------------------------------------------------------------------

### resetToken

    public void resetToken(HttpServletRequest request)

Reset the saved transaction token in the user's session. This indicates that transactional token checking will not be needed on the next request that is submitted.

**Parameters:**  
`request` - The servlet request we are processing

------------------------------------------------------------------------

### saveToken

    public void saveToken(HttpServletRequest request)

Save a new transaction token in the user's current session, creating a new session if necessary.

**Parameters:**  
`request` - The servlet request we are processing

------------------------------------------------------------------------

### generateToken

    public String generateToken(HttpServletRequest request)

Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

**Parameters:**  
`request` - The request we are processing

------------------------------------------------------------------------

### generateToken

    public String generateToken(String id)

Generate a new transaction token, to be used for enforcing a single request for a particular transaction.

**Parameters:**  
`id` - a unique Identifier for the session or other context in which this token is to be used.

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
<td align="left"><a href="class-use/TokenProcessor.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ServletContextWriter.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/WildcardHelper.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/TokenProcessor.html"><strong>FRAMES</strong></a>    <a href="TokenProcessor.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | FIELD | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
