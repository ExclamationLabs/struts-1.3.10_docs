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
<td align="left"><a href="class-use/TestDynaActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionServlet.CustomForwardConfig.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestDynaActionFormClass.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestDynaActionForm.html"><strong>FRAMES</strong></a>    <a href="TestDynaActionForm.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.action
 Class TestDynaActionForm
-------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.action.TestDynaActionFormClass
                  org.apache.struts.action.TestDynaActionForm

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestDynaActionForm

extends [TestDynaActionFormClass](../../../../org/apache/struts/action/TestDynaActionFormClass.html.md "class in org.apache.struts.action")

Suite of unit tests for the `org.apache.struts.action.DynaActionForm` class.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  DynaActionForm`

` dynaForm`
           The basic `DynaActionForm` to use for testing.

`protected  Log`

`log`
            

`protected  ActionMapping`

` mapping`
           Dummy ActionMapping for calls to reset() and validate().

`protected  ModuleConfig`

` moduleConfig`
           Dummy ModuleConfig for calls to reset() and validate().

`protected static String[]`

` properties`
           The set of property names we expect to have returned when calling `getDynaProperties()`.

 <span id="fields_inherited_from_class_org.apache.struts.action.TestDynaActionFormClass"></span>

| **Fields inherited from class org.apache.struts.action.[TestDynaActionFormClass](../../../../org/apache/struts/action/TestDynaActionFormClass.html.md "class in org.apache.struts.action")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` beanConfig,  dynaClass,  dynaProperties`                                                                                                                                                |

  <span id="constructor_summary"></span>

| **Constructor Summary**                         |
|-------------------------------------------------|
| ` TestDynaActionForm(String theName)`           
            Defines the testcase name for JUnit.  |

  <span id="method_summary"></span>

**Method Summary**

`static void`

` main(String[] theArgs)`
           Start the tests.

` void`

` setUp()`
            

`protected  void`

` setupComplexProperties()`
           Set up the complex properties that cannot be configured from the initial value expression.

`static junit.framework.Test`

` suite()`
            

` void`

` tearDown()`
            

` void`

` testBeanCreate()`
            

` void`

` testGetDescriptorArguments()`
           Corner cases on getDynaProperty invalid arguments.

`protected  void`

` testGetDescriptorBase(String name, Class type)`
           Base for testGetDescriptorXxxxx() series of tests.

` void`

` testGetDescriptorBoolean()`
           Positive getDynaProperty on property `booleanProperty`.

` void`

` testGetDescriptorDouble()`
           Positive getDynaProperty on property `doubleProperty`.

` void`

` testGetDescriptorFloat()`
           Positive getDynaProperty on property `floatProperty`.

` void`

` testGetDescriptorInt()`
           Positive getDynaProperty on property `intProperty`.

` void`

` testGetDescriptorLong()`
           Positive getDynaProperty on property `longProperty`.

` void`

` testGetDescriptors()`
           Positive test for getDynaPropertys().

` void`

` testGetDescriptorSecond()`
           Positive getDynaProperty on property `booleanSecond` that uses an "is" method as the getter.

` void`

` testGetDescriptorShort()`
           Positive getDynaProperty on property `shortProperty`.

` void`

` testGetDescriptorString()`
           Positive getDynaProperty on property `stringProperty`.

` void`

` testGetIndexedArguments()`
           Corner cases on getIndexedProperty invalid arguments.

` void`

` testGetIndexedValues()`
           Positive and negative tests on getIndexedProperty valid arguments.

` void`

` testGetMappedArguments()`
           Corner cases on getMappedProperty invalid arguments.

` void`

` testGetMappedValues()`
           Positive and negative tests on getMappedProperty valid arguments.

` void`

` testGetSimpleArguments()`
           Corner cases on getSimpleProperty invalid arguments.

` void`

` testGetSimpleBoolean()`
           Test getSimpleProperty on a boolean property.

` void`

` testGetSimpleDouble()`
           Test getSimpleProperty on a double property.

` void`

` testGetSimpleFloat()`
           Test getSimpleProperty on a float property.

` void`

` testGetSimpleInt()`
           Test getSimpleProperty on a int property.

` void`

` testGetSimpleLong()`
           Test getSimpleProperty on a long property.

` void`

` testGetSimpleShort()`
           Test getSimpleProperty on a short property.

` void`

` testGetSimpleString()`
           Test getSimpleProperty on a String property.

` void`

` testIndexedInitialize()`
            

` void`

` testMappedContains()`
           Test `contains()` method for mapped properties.

` void`

` testMappedRemove()`
           Test `remove()` method for mapped properties.

` void`

` testResetGet()`
           Test the reset method when the request method is GET.

` void`

` testResetPost()`
           Test the reset method when the request method is GET.

` void`

` testScalarInitialize()`
            

` void`

` testSetIndexedArguments()`
           Corner cases on setIndexedProperty invalid arguments.

` void`

` testSetIndexedValues()`
           Positive and negative tests on setIndexedProperty valid arguments.

` void`

` testSetMappedValues()`
           Positive and negative tests on setMappedProperty valid arguments.

` void`

` testSetSimpleBoolean()`
           Test setSimpleProperty on a boolean property.

` void`

` testSetSimpleDouble()`
           Test setSimpleProperty on a double property.

` void`

` testSetSimpleFloat()`
           Test setSimpleProperty on a float property.

` void`

` testSetSimpleInt()`
           Test setSimpleProperty on a int property.

` void`

` testSetSimpleLong()`
           Test setSimpleProperty on a long property.

` void`

` testSetSimpleShort()`
           Test setSimpleProperty on a short property.

` void`

` testSetSimpleString()`
           Test setSimpleProperty on a String property.

 <span id="methods_inherited_from_class_org.apache.struts.action.TestDynaActionFormClass"></span>

| **Methods inherited from class org.apache.struts.action.[TestDynaActionFormClass](../../../../org/apache/struts/action/TestDynaActionFormClass.html.md "class in org.apache.struts.action")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` testClassCreate,  testConfigAdd,  testConfigCreate,  testConfigDuplicate,  testConfigInitialValues,  testConfigProperties,  testConfigRemove`                                            |

 <span id="methods_inherited_from_class_junit.framework.TestCase"></span>

| **Methods inherited from class junit.framework.TestCase**                              |
|----------------------------------------------------------------------------------------|
| `countTestCases, createResult, getName, run, run, runBare, runTest, setName, toString` |

 <span id="methods_inherited_from_class_junit.framework.Assert"></span>

| **Methods inherited from class junit.framework.Assert**                                                                                                                                                                                                                                                                                                                                                                                                            |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertEquals, assertFalse, assertFalse, assertNotNull, assertNotNull, assertNotSame, assertNotSame, assertNull, assertNull, assertSame, assertSame, assertTrue, assertTrue, fail, fail` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, wait, wait, wait`                                                                                    |

 

<span id="field_detail"></span>

**Field Detail**

<span id="properties"></span>

### properties

    protected static final String[] properties

The set of property names we expect to have returned when calling `getDynaProperties()`. You should update this list when new properties are added to TestBean.

------------------------------------------------------------------------

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

Dummy ModuleConfig for calls to reset() and validate().

------------------------------------------------------------------------

<span id="dynaForm"></span>

### dynaForm

    protected DynaActionForm dynaForm

The basic `DynaActionForm` to use for testing.

------------------------------------------------------------------------

<span id="mapping"></span>

### mapping

    protected ActionMapping mapping

Dummy ActionMapping for calls to reset() and validate().

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected Log log

<span id="constructor_detail"></span>

**Constructor Detail**

### TestDynaActionForm

    public TestDynaActionForm(String theName)

Defines the testcase name for JUnit.

**Parameters:**  
`theName` - the testcase's name.

<span id="method_detail"></span>

**Method Detail**

### main

    public static void main(String[] theArgs)

Start the tests.

**Parameters:**  
`theArgs` - the arguments. Not used

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

**Returns:**  
a test suite (`TestSuite`) that includes all methods starting with "test"

------------------------------------------------------------------------

### setUp

    public void setUp()

**Overrides:**  
` setUp` in class `TestDynaActionFormClass`

------------------------------------------------------------------------

### tearDown

    public void tearDown()

**Overrides:**  
` tearDown` in class `TestDynaActionFormClass`

------------------------------------------------------------------------

### testBeanCreate

    public void testBeanCreate()

------------------------------------------------------------------------

### testIndexedInitialize

    public void testIndexedInitialize()

------------------------------------------------------------------------

### testScalarInitialize

    public void testScalarInitialize()

------------------------------------------------------------------------

### testGetDescriptorArguments

    public void testGetDescriptorArguments()

Corner cases on getDynaProperty invalid arguments.

------------------------------------------------------------------------

### testGetDescriptorBoolean

    public void testGetDescriptorBoolean()

Positive getDynaProperty on property `booleanProperty`.

------------------------------------------------------------------------

### testGetDescriptorDouble

    public void testGetDescriptorDouble()

Positive getDynaProperty on property `doubleProperty`.

------------------------------------------------------------------------

### testGetDescriptorFloat

    public void testGetDescriptorFloat()

Positive getDynaProperty on property `floatProperty`.

------------------------------------------------------------------------

### testGetDescriptorInt

    public void testGetDescriptorInt()

Positive getDynaProperty on property `intProperty`.

------------------------------------------------------------------------

### testGetDescriptorLong

    public void testGetDescriptorLong()

Positive getDynaProperty on property `longProperty`.

------------------------------------------------------------------------

### testGetDescriptorSecond

    public void testGetDescriptorSecond()

Positive getDynaProperty on property `booleanSecond` that uses an "is" method as the getter.

------------------------------------------------------------------------

### testGetDescriptorShort

    public void testGetDescriptorShort()

Positive getDynaProperty on property `shortProperty`.

------------------------------------------------------------------------

### testGetDescriptorString

    public void testGetDescriptorString()

Positive getDynaProperty on property `stringProperty`.

------------------------------------------------------------------------

### testGetDescriptors

    public void testGetDescriptors()

Positive test for getDynaPropertys(). Each property name listed in `properties` should be returned exactly once.

------------------------------------------------------------------------

### testGetIndexedArguments

    public void testGetIndexedArguments()

Corner cases on getIndexedProperty invalid arguments.

------------------------------------------------------------------------

### testGetIndexedValues

    public void testGetIndexedValues()

Positive and negative tests on getIndexedProperty valid arguments.

------------------------------------------------------------------------

### testGetMappedArguments

    public void testGetMappedArguments()

Corner cases on getMappedProperty invalid arguments.

------------------------------------------------------------------------

### testGetMappedValues

    public void testGetMappedValues()

Positive and negative tests on getMappedProperty valid arguments.

------------------------------------------------------------------------

### testGetSimpleArguments

    public void testGetSimpleArguments()

Corner cases on getSimpleProperty invalid arguments.

------------------------------------------------------------------------

### testGetSimpleBoolean

    public void testGetSimpleBoolean()

Test getSimpleProperty on a boolean property.

------------------------------------------------------------------------

### testGetSimpleDouble

    public void testGetSimpleDouble()

Test getSimpleProperty on a double property.

------------------------------------------------------------------------

### testGetSimpleFloat

    public void testGetSimpleFloat()

Test getSimpleProperty on a float property.

------------------------------------------------------------------------

### testGetSimpleInt

    public void testGetSimpleInt()

Test getSimpleProperty on a int property.

------------------------------------------------------------------------

### testGetSimpleLong

    public void testGetSimpleLong()

Test getSimpleProperty on a long property.

------------------------------------------------------------------------

### testGetSimpleShort

    public void testGetSimpleShort()

Test getSimpleProperty on a short property.

------------------------------------------------------------------------

### testGetSimpleString

    public void testGetSimpleString()

Test getSimpleProperty on a String property.

------------------------------------------------------------------------

### testMappedContains

    public void testMappedContains()

Test `contains()` method for mapped properties.

------------------------------------------------------------------------

### testMappedRemove

    public void testMappedRemove()

Test `remove()` method for mapped properties.

------------------------------------------------------------------------

### testResetGet

    public void testResetGet()

Test the reset method when the request method is GET.

------------------------------------------------------------------------

### testResetPost

    public void testResetPost()

Test the reset method when the request method is GET.

------------------------------------------------------------------------

### testSetIndexedArguments

    public void testSetIndexedArguments()

Corner cases on setIndexedProperty invalid arguments.

------------------------------------------------------------------------

### testSetIndexedValues

    public void testSetIndexedValues()

Positive and negative tests on setIndexedProperty valid arguments.

------------------------------------------------------------------------

### testSetMappedValues

    public void testSetMappedValues()

Positive and negative tests on setMappedProperty valid arguments.

------------------------------------------------------------------------

### testSetSimpleBoolean

    public void testSetSimpleBoolean()

Test setSimpleProperty on a boolean property.

------------------------------------------------------------------------

### testSetSimpleDouble

    public void testSetSimpleDouble()

Test setSimpleProperty on a double property.

------------------------------------------------------------------------

### testSetSimpleFloat

    public void testSetSimpleFloat()

Test setSimpleProperty on a float property.

------------------------------------------------------------------------

### testSetSimpleInt

    public void testSetSimpleInt()

Test setSimpleProperty on a int property.

------------------------------------------------------------------------

### testSetSimpleLong

    public void testSetSimpleLong()

Test setSimpleProperty on a long property.

------------------------------------------------------------------------

### testSetSimpleShort

    public void testSetSimpleShort()

Test setSimpleProperty on a short property.

------------------------------------------------------------------------

### testSetSimpleString

    public void testSetSimpleString()

Test setSimpleProperty on a String property.

------------------------------------------------------------------------

### setupComplexProperties

    protected void setupComplexProperties()

Set up the complex properties that cannot be configured from the initial value expression.

------------------------------------------------------------------------

### testGetDescriptorBase

    protected void testGetDescriptorBase(String name,
                                         Class type)

Base for testGetDescriptorXxxxx() series of tests.

**Parameters:**  
`name` - Name of the property to be retrieved

`type` - Expected class type of this property

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
<td align="left"><a href="class-use/TestDynaActionForm.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionServlet.CustomForwardConfig.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestDynaActionFormClass.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestDynaActionForm.html"><strong>FRAMES</strong></a>    <a href="TestDynaActionForm.html"><strong>NO FRAMES</strong></a>    
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
