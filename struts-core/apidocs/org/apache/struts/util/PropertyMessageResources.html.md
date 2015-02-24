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
<td align="left"><a href="class-use/PropertyMessageResources.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ModuleUtils.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/PropertyMessageResourcesFactory.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/PropertyMessageResources.html"><strong>FRAMES</strong></a>    <a href="PropertyMessageResources.html"><strong>NO FRAMES</strong></a>    
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
 Class PropertyMessageResources
-------------------------------

    java.lang.Object
      org.apache.struts.util.MessageResources
          org.apache.struts.util.PropertyMessageResources

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io")

------------------------------------------------------------------------

    public class PropertyMessageResources

extends [MessageResources](../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util")

Concrete subclass of `MessageResources` that reads message keys and corresponding strings from named property resources in a ***similar*** manner (see *modes* below) that `java.util.PropertyResourceBundle` does. The `base` property defines the base property resource name, and must be specified.

**IMPLEMENTATION NOTE** - This class trades memory for speed by caching all messages located via generalizing the Locale under the original locale as well. This results in specific messages being stored in the message cache more than once, but improves response time on subsequent requests for the same locale + key combination.

Operating Modes
---------------

This implementation can be configured to operate in one of three modes:

-   1. **Default** - default, backwardly compatible, Struts behaviour (i.e. the way its always worked).
-   2. **JSTL** - compatible with how JSTL finds messages (fix for [STR-2925](http://issues.apache.org/struts/browse/STR-2925))
-   3. **Resource** - compatible with how Java's `PropertyResourceBundle` finds messages (fix for [STR-2077](http://issues.apache.org/struts/browse/STR-2077))

### 1. Default Mode

*Default mode* is the way this implementation has always operated. It searches for a message key for property resources in the following sequence:

          base + "_" + localeLanguage + "_" + localeCountry + "_" + localeVariant
          base + "_" + localeLanguage + "_" + localeCountry
          base + "_" + localeLanguage
          base + "_" + default locale
          base
     

This mode is the *default* and requires no additional configuration.

### 2. JSTL Mode

*JSTL mode* is compatible with how JSTL operates and the default Locale is not used when looking for a message key. *JSTL mode* searches for a message key for property resources in the following sequence:

          base + "_" + localeLanguage + "_" + localeCountry + "_" + localeVariant
          base + "_" + localeLanguage + "_" + localeCountry
          base + "_" + localeLanguage
          base
     

Configure `PropertyMessageResources` to operate in this mode by specifying a value of `JSTL` for the `mode` key in your `struts-config.xml`:

          <message-resources parameter="mypackage.MyMessageResources">
              <set-property key="mode" value="JSTL"/>
          </message-resources>
     

### 3. Resource Mode

*Resource mode* is compatible with how Java's `PropertyResourceBundle` operates. *Resource mode* searches first through the specified Locale's language, country and variant, then through the default Locale's language, country and variant and finally using just the `base`:

          base + "_" + localeLanguage + "_" + localeCountry + "_" + localeVariant
          base + "_" + localeLanguage + "_" + localeCountry
          base + "_" + localeLanguage
          base + "_" + defaultLanguage + "_" + defaultCountry + "_" + defaultVariant
          base + "_" + defaultLanguage + "_" + defaultCountry
          base + "_" + defaultLanguage
          base
     

Configure `PropertyMessageResources` to operate in this mode by specifying a value of `resource` for the `mode` key in your `struts-config.xml`:

          <message-resources parameter="mypackage.MyMessageResources">
              <set-property key="mode" value="resource"/>
          </message-resources>
     

**Version:**  
$Rev: 480549 $ $Date: 2006-11-29 06:16:15 -0600 (Wed, 29 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../serialized-form.html.md#org.apache.struts.util.PropertyMessageResources)

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  HashMap`

` locales`
           The set of locale keys for which we have already loaded messages, keyed by the value calculated in `localeKey()`.

`protected static Log`

` log`
           The `Log` instance for this class.

`protected  HashMap`

` messages`
           The cache of messages we have accumulated over time, keyed by the value calculated in `messageKey()`.

 <span id="fields_inherited_from_class_org.apache.struts.util.MessageResources"></span>

| **Fields inherited from class org.apache.struts.util.[MessageResources](../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `config,  defaultFactory,  defaultLocale, factory, formats,  returnNull`                                                                                              |

  <span id="constructor_summary"></span>

| **Constructor Summary**                                                                         |
|-------------------------------------------------------------------------------------------------|
| ` PropertyMessageResources(MessageResourcesFactory factory, String config)`                     
            Construct a new PropertyMessageResources according to the specified parameters.       |
| ` PropertyMessageResources(MessageResourcesFactory factory, String config, boolean returnNull)` 
            Construct a new PropertyMessageResources according to the specified parameters.       |

  <span id="method_summary"></span>

**Method Summary**

` String`

` getMessage(Locale locale, String key)`
           Returns a text message for the specified key, for the specified or default Locale.

`protected  void`

` loadLocale(String localeKey)`
           Load the messages associated with the specified Locale key.

` void`

` setMode(String mode)`
           Set the compatibility mode this implementation uses for message lookup.

 <span id="methods_inherited_from_class_org.apache.struts.util.MessageResources"></span>

| **Methods inherited from class org.apache.struts.util.[MessageResources](../../../../org/apache/struts/util/MessageResources.html.md "class in org.apache.struts.util")**                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` escape,  getConfig,  getFactory,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessage,  getMessageResources,  getReturnNull,  isEscape,  isPresent,  isPresent,  localeKey,  log,  log,  messageKey,  messageKey,  setEscape,  setReturnNull` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="log"></span>

### log

    protected static final Log log

The `Log` instance for this class.

------------------------------------------------------------------------

<span id="locales"></span>

### locales

    protected HashMap locales

The set of locale keys for which we have already loaded messages, keyed by the value calculated in `localeKey()`.

------------------------------------------------------------------------

<span id="messages"></span>

### messages

    protected HashMap messages

The cache of messages we have accumulated over time, keyed by the value calculated in `messageKey()`.

<span id="constructor_detail"></span>

**Constructor Detail**

### PropertyMessageResources

    public PropertyMessageResources(MessageResourcesFactory factory,
                                    String config)

Construct a new PropertyMessageResources according to the specified parameters.

**Parameters:**  
`factory` - The MessageResourcesFactory that created us

`config` - The configuration parameter for this MessageResources

------------------------------------------------------------------------

### PropertyMessageResources

    public PropertyMessageResources(MessageResourcesFactory factory,
                                    String config,
                                    boolean returnNull)

Construct a new PropertyMessageResources according to the specified parameters.

**Parameters:**  
`factory` - The MessageResourcesFactory that created us

`config` - The configuration parameter for this MessageResources

`returnNull` - The returnNull property we should initialize with

<span id="method_detail"></span>

**Method Detail**

### setMode

    public void setMode(String mode)

Set the compatibility mode this implementation uses for message lookup.

**Parameters:**  
`mode` - `JSTL` for JSTL compatibility, `resource` for PropertyResourceBundle compatibility or `default` for Struts backward compatibility.

------------------------------------------------------------------------

### getMessage

    public String getMessage(Locale locale,
                             String key)

Returns a text message for the specified key, for the specified or default Locale. A null string result will be returned by this method if no relevant message resource is found for this key or Locale, if the `returnNull` property is set. Otherwise, an appropriate error message will be returned.

This method must be implemented by a concrete subclass.

**Specified by:**  
` getMessage` in class `MessageResources`

<!-- -->

**Parameters:**  
`locale` - The requested message Locale, or `null` for the system default Locale

`key` - The message key to look up

**Returns:**  
text message for the specified key and locale

------------------------------------------------------------------------

### loadLocale

    protected void loadLocale(String localeKey)

Load the messages associated with the specified Locale key. For this implementation, the `config` property should contain a fully qualified package and resource name, separated by periods, of a series of property resources to be loaded from the class loader that created this PropertyMessageResources instance. This is exactly the same name format you would use when utilizing the `java.util.PropertyResourceBundle` class.

**Parameters:**  
`localeKey` - Locale key for the messages to be retrieved

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
<td align="left"><a href="class-use/PropertyMessageResources.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/util/ModuleUtils.html.md" title="class in org.apache.struts.util"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/util/PropertyMessageResourcesFactory.html" title="class in org.apache.struts.util"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/util/PropertyMessageResources.html"><strong>FRAMES</strong></a>    <a href="PropertyMessageResources.html"><strong>NO FRAMES</strong></a>    
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
