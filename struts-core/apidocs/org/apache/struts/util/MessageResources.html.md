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
<td align="left"><a href="class-use/MessageResources.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/LabelValueBean.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/MessageResourcesFactory.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/MessageResources.html"><strong>FRAMES</strong></a>    <a href="MessageResources.html"><strong>NO FRAMES</strong></a>    
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
 Class MessageResources
-----------------------

    java.lang.Object
      org.apache.struts.util.MessageResources

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

<!-- -->

**Direct Known Subclasses:**  
[PropertyMessageResources](../../../../org/apache/struts/util/PropertyMessageResources.html.md "class in org.apache.struts.util")

------------------------------------------------------------------------

    public abstract class MessageResources

extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")

implements [Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

General purpose abstract class that describes an API for retrieving Locale-sensitive messages from underlying resource locations of an unspecified design, and optionally utilizing the `MessageFormat` class to produce internationalized messages with parametric replacement.

Calls to `getMessage()` variants without a `Locale` argument are presumed to be requesting a message string in the default `Locale` for this JVM.

Calls to `getMessage()` with an unknown key, or an unknown `Locale` will return `null` if the `returnNull` property is set to `true`. Otherwise, a suitable error message will be returned instead.

**IMPLEMENTATION NOTE** - Classes that extend this class must be Serializable so that instances may be used in distributable application server environments.

**Version:**  
$Rev: 471754 $ $Date: 2005-08-29 23:57:50 -0400 (Mon, 29 Aug 2005) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.util.MessageResources)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  String`

`config`
           The configuration parameter used to initialize this MessageResources.

`protected static MessageResourcesFactory`

` defaultFactory`
           The default MessageResourcesFactory used to create MessageResources instances.

`protected  Locale`

` defaultLocale`
           The default Locale for our environment.

`protected  MessageResourcesFactory`

`factory`
           The `MessageResourcesFactory` that created this instance.

`protected  HashMap`

`formats`
           The set of previously created MessageFormat objects, keyed by the key computed in `messageKey()`.

`protected static Log`

`log`
           Commons Logging instance.

`protected  boolean`

` returnNull`
           Indicate is a `null` is returned instead of an error message string when an unknown Locale or key is requested.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                 |
|-----------------------------------------------------------------------------------------|
| ` MessageResources(MessageResourcesFactory factory, String config)`                     
            Construct a new MessageResources according to the specified parameters.       |
| ` MessageResources(MessageResourcesFactory factory, String config, boolean returnNull)` 
            Construct a new MessageResources according to the specified parameters.       |

  <span id="method_summary"></span>

**Method Summary**

`protected  String`

` escape(String string)`
           Escape any single quote characters that are included in the specified message string.

` String`

` getConfig()`
           The configuration parameter used to initialize this MessageResources.

` MessageResourcesFactory`

` getFactory()`
           The `MessageResourcesFactory` that created this instance.

`abstract  String`

` getMessage(Locale locale, String key)`
           Returns a text message for the specified key, for the default Locale.

` String`

` getMessage(Locale locale, String key, Object arg0)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(Locale locale, String key, Object[] args)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(Locale locale, String key, Object arg0, Object arg1)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(Locale locale, String key, Object arg0, Object arg1, Object arg2)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(Locale locale, String key, Object arg0, Object arg1, Object arg2, Object arg3)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(String key)`
           Returns a text message for the specified key, for the default Locale.

` String`

` getMessage(String key, Object arg0)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(String key, Object[] args)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(String key, Object arg0, Object arg1)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(String key, Object arg0, Object arg1, Object arg2)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

` String`

` getMessage(String key, Object arg0, Object arg1, Object arg2, Object arg3)`
           Returns a text message after parametric replacement of the specified parameter placeholders.

`static MessageResources`

` getMessageResources(String config)`
           Create and return an instance of `MessageResources` for the created by the default `MessageResourcesFactory`.

` boolean`

` getReturnNull()`
           Indicates that a `null` is returned instead of an error message string if an unknown Locale or key is requested.

` boolean`

` isEscape()`
           Indicates whether 'escape processing' should be performed on the error message string.

` boolean`

` isPresent(Locale locale, String key)`
           Return `true` if there is a defined message for the specified key in the specified Locale.

` boolean`

` isPresent(String key)`
           Return `true` if there is a defined message for the specified key in the system default locale.

`protected  String`

` localeKey(Locale locale)`
           Compute and return a key to be used in caching information by a Locale.

` void`

` log(String message)`
           Log a message to the Writer that has been configured for our use.

` void`

` log(String message, Throwable throwable)`
           Log a message and exception to the Writer that has been configured for our use.

`protected  String`

` messageKey(Locale locale, String key)`
           Compute and return a key to be used in caching information by Locale and message key.

`protected  String`

` messageKey(String localeKey, String key)`
           Compute and return a key to be used in caching information by locale key and message key.

` void`

` setEscape(boolean escape)`
           Set whether 'escape processing' should be performed on the error message string.

` void`

` setReturnNull(boolean returnNull)`
           Indicates that a `null` is returned instead of an error message string if an unknown Locale or key is requested.

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="defaultFactory"></span>

### defaultFactory

    protected static MessageResourcesFactory defaultFactory

The default MessageResourcesFactory used to create MessageResources instances.

------------------------------------------------------------------------

<span id="config"></span>

### config

    protected String config

The configuration parameter used to initialize this MessageResources.

------------------------------------------------------------------------

<span id="defaultLocale"></span>

### defaultLocale

    protected Locale defaultLocale

The default Locale for our environment.

------------------------------------------------------------------------

<span id="factory"></span>

### factory

    protected MessageResourcesFactory factory

The `MessageResourcesFactory` that created this instance.

------------------------------------------------------------------------

<span id="formats"></span>

### formats

    protected HashMap formats

The set of previously created MessageFormat objects, keyed by the key computed in `messageKey()`.

------------------------------------------------------------------------

<span id="returnNull"></span>

### returnNull

    protected boolean returnNull

Indicate is a `null` is returned instead of an error message string when an unknown Locale or key is requested.

<span id="constructor_detail"></span>

**Constructor Detail**

### MessageResources

    public MessageResources(MessageResourcesFactory factory,
                            String config)

Construct a new MessageResources according to the specified parameters.

**Parameters:**  
`factory` - The MessageResourcesFactory that created us

`config` - The configuration parameter for this MessageResources

------------------------------------------------------------------------

### MessageResources

    public MessageResources(MessageResourcesFactory factory,
                            String config,
                            boolean returnNull)

Construct a new MessageResources according to the specified parameters.

**Parameters:**  
`factory` - The MessageResourcesFactory that created us

`config` - The configuration parameter for this MessageResources

`returnNull` - The returnNull property we should initialize with

<span id="method_detail"></span>

**Method Detail**

### getConfig

    public String getConfig()

The configuration parameter used to initialize this MessageResources.

**Returns:**  
parameter used to initialize this MessageResources

------------------------------------------------------------------------

### getFactory

    public MessageResourcesFactory getFactory()

The `MessageResourcesFactory` that created this instance.

**Returns:**  
`MessageResourcesFactory` that created instance

------------------------------------------------------------------------

### getReturnNull

    public boolean getReturnNull()

Indicates that a `null` is returned instead of an error message string if an unknown Locale or key is requested.

**Returns:**  
true if null is returned if unknown key or locale is requested

------------------------------------------------------------------------

### setReturnNull

    public void setReturnNull(boolean returnNull)

Indicates that a `null` is returned instead of an error message string if an unknown Locale or key is requested.

**Parameters:**  
`returnNull` - true Indicates that a `null` is returned if an unknown Locale or key is requested.

------------------------------------------------------------------------

### isEscape

    public boolean isEscape()

Indicates whether 'escape processing' should be performed on the error message string.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### setEscape

    public void setEscape(boolean escape)

Set whether 'escape processing' should be performed on the error message string.

**Since:**  
Struts 1.2.8

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key)

Returns a text message for the specified key, for the default Locale.

**Parameters:**  
`key` - The message key to look up

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key,
                             Object[] args)

Returns a text message after parametric replacement of the specified parameter placeholders.

**Parameters:**  
`key` - The message key to look up

`args` - An array of replacement parameters for placeholders

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key,
                             Object arg0)

Returns a text message after parametric replacement of the specified parameter placeholders.

**Parameters:**  
`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key,
                             Object arg0,
                             Object arg1)

Returns a text message after parametric replacement of the specified parameter placeholders.

**Parameters:**  
`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

`arg1` - The replacement for placeholder {1} in the message

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key,
                             Object arg0,
                             Object arg1,
                             Object arg2)

Returns a text message after parametric replacement of the specified parameter placeholders.

**Parameters:**  
`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

`arg1` - The replacement for placeholder {1} in the message

`arg2` - The replacement for placeholder {2} in the message

------------------------------------------------------------------------

### getMessage

    public String getMessage(String key,
                             Object arg0,
                             Object arg1,
                             Object arg2,
                             Object arg3)

Returns a text message after parametric replacement of the specified parameter placeholders.

**Parameters:**  
`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

`arg1` - The replacement for placeholder {1} in the message

`arg2` - The replacement for placeholder {2} in the message

`arg3` - The replacement for placeholder {3} in the message

------------------------------------------------------------------------

### getMessage

    public abstract String getMessage(Locale locale,
                                      String key)

Returns a text message for the specified key, for the default Locale. A null string result will be returned by this method if no relevant message resource is found for this key or Locale, if the `returnNull` property is set. Otherwise, an appropriate error message will be returned.

This method must be implemented by a concrete subclass.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

------------------------------------------------------------------------

### getMessage

    public String getMessage(Locale locale,
                             String key,
                             Object[] args)

Returns a text message after parametric replacement of the specified parameter placeholders. A null string result will be returned by this method if no resource bundle has been configured.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

`args` - An array of replacement parameters for placeholders

------------------------------------------------------------------------

### getMessage

    public String getMessage(Locale locale,
                             String key,
                             Object arg0)

Returns a text message after parametric replacement of the specified parameter placeholders. A null string result will never be returned by this method.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

------------------------------------------------------------------------

### getMessage

    public String getMessage(Locale locale,
                             String key,
                             Object arg0,
                             Object arg1)

Returns a text message after parametric replacement of the specified parameter placeholders. A null string result will never be returned by this method.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

`arg1` - The replacement for placeholder {1} in the message

------------------------------------------------------------------------

### getMessage

    public String getMessage(Locale locale,
                             String key,
                             Object arg0,
                             Object arg1,
                             Object arg2)

Returns a text message after parametric replacement of the specified parameter placeholders. A null string result will never be returned by this method.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

`arg1` - The replacement for placeholder {1} in the message

`arg2` - The replacement for placeholder {2} in the message

------------------------------------------------------------------------

### getMessage

    public String getMessage(Locale locale,
                             String key,
                             Object arg0,
                             Object arg1,
                             Object arg2,
                             Object arg3)

Returns a text message after parametric replacement of the specified parameter placeholders. A null string result will never be returned by this method.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

`arg0` - The replacement for placeholder {0} in the message

`arg1` - The replacement for placeholder {1} in the message

`arg2` - The replacement for placeholder {2} in the message

`arg3` - The replacement for placeholder {3} in the message

------------------------------------------------------------------------

### isPresent

    public boolean isPresent(String key)

Return `true` if there is a defined message for the specified key in the system default locale.

**Parameters:**  
`key` - The message key to look up

------------------------------------------------------------------------

### isPresent

    public boolean isPresent(Locale locale,
                             String key)

Return `true` if there is a defined message for the specified key in the specified Locale.

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

------------------------------------------------------------------------

### escape

    protected String escape(String string)

Escape any single quote characters that are included in the specified message string.

**Parameters:**  
`string` - The string to be escaped

------------------------------------------------------------------------

### localeKey

    protected String localeKey(Locale locale)

Compute and return a key to be used in caching information by a Locale. **NOTE** - The locale key for the default Locale in our environment is a zero length String.

**Parameters:**  
`locale` - The locale for which a key is desired

------------------------------------------------------------------------

### messageKey

    protected String messageKey(Locale locale,
                                String key)

Compute and return a key to be used in caching information by Locale and message key.

**Parameters:**  
`locale` - The Locale for which this format key is calculated

`key` - The message key for which this format key is calculated

------------------------------------------------------------------------

### messageKey

    protected String messageKey(String localeKey,
                                String key)

Compute and return a key to be used in caching information by locale key and message key.

**Parameters:**  
`localeKey` - The locale key for which this cache key is calculated

`key` - The message key for which this cache key is calculated

------------------------------------------------------------------------

### getMessageResources

    public static MessageResources getMessageResources(String config)

Create and return an instance of `MessageResources` for the created by the default `MessageResourcesFactory`.

**Parameters:**  
`config` - Configuration parameter for this message bundle.

------------------------------------------------------------------------

### log

    public void log(String message)

Log a message to the Writer that has been configured for our use.

**Parameters:**  
`message` - The message to be logged

------------------------------------------------------------------------

### log

    public void log(String message,
                    Throwable throwable)

Log a message and exception to the Writer that has been configured for our use.

**Parameters:**  
`message` - The message to be logged

`throwable` - The exception to be logged

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
<td align="left"><a href="class-use/MessageResources.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/LabelValueBean.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/MessageResourcesFactory.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/MessageResources.html"><strong>FRAMES</strong></a>    <a href="MessageResources.html"><strong>NO FRAMES</strong></a>    
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
