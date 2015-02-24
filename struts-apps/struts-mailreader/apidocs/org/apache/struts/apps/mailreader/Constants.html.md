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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/Constants.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/apps/mailreader/Constants.html"><strong>FRAMES</strong></a>    <a href="Constants.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Object">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.apps.mailreader
 Class Constants
---------------------------------

    java.lang.Object
      org.apache.struts.apps.mailreader.Constants

------------------------------------------------------------------------

    public final class Constants

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

Manifest constants for the MailReader application.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String`

` CREATE`
            The token representing a "create" task.

`static String`

` DATABASE_KEY`
            The application scope attribute under which our user database is stored.

`static String`

` DELETE`
            The token representing a "edit" task.

`static String`

` EDIT`
            The token representing a "edit" task.

`static String`

` ERROR_DATABASE_NOT_LOADED`
            A static message in case database resource is not loaded.

`static String`

` ERROR_KEY`
            The request attributes key under the WelcomeAction stores an ArrayList of error messages, if required resources are missing.

`static String`

` ERROR_MESSAGES_NOT_LOADED`
            A static message in case message resource is not loaded.

`static String`

` FAILURE`
            The token representing a "failure" result for this application.

`static String`

` LOG_CANCEL`
            The message to log when cancelling a transaction.

`static String`

` LOG_FAILURE`
            The message to log when forwarding to a 'failure' result.

`static String`

` LOG_LOGON`
            The message to log when forwarding to a 'logon' result.

`static String`

` LOG_POPULATE_FORM`
            The message to log when populating a form.

`static String`

` LOG_POPULATE_SUBSCRIPTION`
            The message to log when populating a subscription.

`static String`

` LOG_POPULATE_USER`
            The message to log when populating a user.

`static String`

` LOG_PROCESSING`
            The message to log when forwarding to a 'success' result.

`static String`

` LOG_RESULT`
            The message to log when forwarding to a result.

`static String`

` LOG_SUCCESS`
            The message to log when forwarding to a 'success' result.

`static String`

` LOG_TOKEN`
            The message to log when setting a transactional token.

`static String`

` LOG_TOKEN_CHECK`
            The message to log when checking a transactional token.

`static String`

` LOGON`
            The token representing a "logon" result for this application.

`static String`

` MSG_TRANSACTION_TOKEN`
            The resource key for an error with the transactional token.

`static String`

` PACKAGE`
            The package name for this application.

`static String`

` SAVE`
            The token representing a "save" task.

`static String`

` SUBSCRIPTION_KEY`
            The session scope attribute under which the Subscription object currently selected by our logged-in User is stored.

`static String`

` SUCCESS`
            The token representing a "success" result for this application.

`static String`

` USER_KEY`
            The session scope attribute under which the User object for the currently logged in user is stored.

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` Constants()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="CREATE"></span>

### CREATE

    public static final String CREATE

The token representing a "create" task.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.CREATE)

------------------------------------------------------------------------

<span id="DATABASE_KEY"></span>

### DATABASE\_KEY

    public static final String DATABASE_KEY

The application scope attribute under which our user database is stored.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.DATABASE_KEY)

------------------------------------------------------------------------

<span id="DELETE"></span>

### DELETE

    public static final String DELETE

The token representing a "edit" task.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.DELETE)

------------------------------------------------------------------------

<span id="EDIT"></span>

### EDIT

    public static final String EDIT

The token representing a "edit" task.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.EDIT)

------------------------------------------------------------------------

<span id="ERROR_KEY"></span>

### ERROR\_KEY

    public static final String ERROR_KEY

The request attributes key under the WelcomeAction stores an ArrayList of error messages, if required resources are missing.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.ERROR_KEY)

------------------------------------------------------------------------

<span id="FAILURE"></span>

### FAILURE

    public static final String FAILURE

The token representing a "failure" result for this application.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.FAILURE)

------------------------------------------------------------------------

<span id="LOGON"></span>

### LOGON

    public static final String LOGON

The token representing a "logon" result for this application.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOGON)

------------------------------------------------------------------------

<span id="PACKAGE"></span>

### PACKAGE

    public static final String PACKAGE

The package name for this application.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.PACKAGE)

------------------------------------------------------------------------

<span id="SAVE"></span>

### SAVE

    public static final String SAVE

The token representing a "save" task.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.SAVE)

------------------------------------------------------------------------

<span id="SUBSCRIPTION_KEY"></span>

### SUBSCRIPTION\_KEY

    public static final String SUBSCRIPTION_KEY

The session scope attribute under which the Subscription object currently selected by our logged-in User is stored.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.SUBSCRIPTION_KEY)

------------------------------------------------------------------------

<span id="SUCCESS"></span>

### SUCCESS

    public static final String SUCCESS

The token representing a "success" result for this application.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.SUCCESS)

------------------------------------------------------------------------

<span id="USER_KEY"></span>

### USER\_KEY

    public static final String USER_KEY

The session scope attribute under which the User object for the currently logged in user is stored.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.USER_KEY)

------------------------------------------------------------------------

<span id="ERROR_DATABASE_NOT_LOADED"></span>

### ERROR\_DATABASE\_NOT\_LOADED

    public static final String ERROR_DATABASE_NOT_LOADED

A static message in case database resource is not loaded.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.ERROR_DATABASE_NOT_LOADED)

------------------------------------------------------------------------

<span id="ERROR_MESSAGES_NOT_LOADED"></span>

### ERROR\_MESSAGES\_NOT\_LOADED

    public static final String ERROR_MESSAGES_NOT_LOADED

A static message in case message resource is not loaded.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.ERROR_MESSAGES_NOT_LOADED)

------------------------------------------------------------------------

<span id="MSG_TRANSACTION_TOKEN"></span>

### MSG\_TRANSACTION\_TOKEN

    public static final String MSG_TRANSACTION_TOKEN

The resource key for an error with the transactional token.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.MSG_TRANSACTION_TOKEN)

------------------------------------------------------------------------

<span id="LOG_CANCEL"></span>

### LOG\_CANCEL

    public static final String LOG_CANCEL

The message to log when cancelling a transaction.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_CANCEL)

------------------------------------------------------------------------

<span id="LOG_RESULT"></span>

### LOG\_RESULT

    public static final String LOG_RESULT

The message to log when forwarding to a result.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_RESULT)

------------------------------------------------------------------------

<span id="LOG_FAILURE"></span>

### LOG\_FAILURE

    public static final String LOG_FAILURE

The message to log when forwarding to a 'failure' result.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_FAILURE)

------------------------------------------------------------------------

<span id="LOG_LOGON"></span>

### LOG\_LOGON

    public static final String LOG_LOGON

The message to log when forwarding to a 'logon' result.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_LOGON)

------------------------------------------------------------------------

<span id="LOG_POPULATE_FORM"></span>

### LOG\_POPULATE\_FORM

    public static final String LOG_POPULATE_FORM

The message to log when populating a form.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_POPULATE_FORM)

------------------------------------------------------------------------

<span id="LOG_POPULATE_SUBSCRIPTION"></span>

### LOG\_POPULATE\_SUBSCRIPTION

    public static final String LOG_POPULATE_SUBSCRIPTION

The message to log when populating a subscription.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_POPULATE_SUBSCRIPTION)

------------------------------------------------------------------------

<span id="LOG_POPULATE_USER"></span>

### LOG\_POPULATE\_USER

    public static final String LOG_POPULATE_USER

The message to log when populating a user.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_POPULATE_USER)

------------------------------------------------------------------------

<span id="LOG_PROCESSING"></span>

### LOG\_PROCESSING

    public static final String LOG_PROCESSING

The message to log when forwarding to a 'success' result.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_PROCESSING)

------------------------------------------------------------------------

<span id="LOG_SUCCESS"></span>

### LOG\_SUCCESS

    public static final String LOG_SUCCESS

The message to log when forwarding to a 'success' result.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_SUCCESS)

------------------------------------------------------------------------

<span id="LOG_TOKEN"></span>

### LOG\_TOKEN

    public static final String LOG_TOKEN

The message to log when setting a transactional token.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_TOKEN)

------------------------------------------------------------------------

<span id="LOG_TOKEN_CHECK"></span>

### LOG\_TOKEN\_CHECK

    public static final String LOG_TOKEN_CHECK

The message to log when checking a transactional token.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.apps.mailreader.Constants.LOG_TOKEN_CHECK)

<span id="constructor_detail"></span>

**Constructor Detail**

### Constants

    public Constants()

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
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/Constants.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV CLASS   NEXT CLASS</td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/apps/mailreader/Constants.html"><strong>FRAMES</strong></a>    <a href="Constants.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#methods_inherited_from_class_java.lang.Object">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | METHOD</td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
