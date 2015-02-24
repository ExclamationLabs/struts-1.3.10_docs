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
<td align="left"><a href="../../../../org/apache/struts/tiles/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/TestTilesPlugin.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/CustomI18nFactorySet.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TestTilesPlugin.html"><strong>FRAMES</strong></a>    <a href="TestTilesPlugin.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.tiles
 Class TestTilesPlugin
-----------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.mock.TestMockBase
                  org.apache.struts.tiles.TestTilesPlugin

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestTilesPlugin

extends org.apache.struts.mock.TestMockBase

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  org.apache.struts.mock.MockActionServlet`

` actionServlet`
            

`protected  ModuleConfig`

`module1`
            

`protected  ModuleConfig`

`module2`
            

 <span id="fields_inherited_from_class_org.apache.struts.mock.TestMockBase"></span>

| **Fields inherited from class org.apache.struts.mock.TestMockBase**                                        |
|------------------------------------------------------------------------------------------------------------|
| `config, context, moduleConfig, moduleConfig2, moduleConfig3, page, principal, request, response, session` |

  <span id="constructor_summary"></span>

| **Constructor Summary**         |
|---------------------------------|
| ` TestTilesPlugin(String name)` 
                                  |

  <span id="method_summary"></span>

**Method Summary**

` ModuleConfig`

` createModuleConfig(String moduleName, String configFileName, boolean moduleAware)`
           Create a module configuration

` void`

` initModulePlugIns(ModuleConfig moduleConfig)`
           Fake call to init module plugins

`static void`

` main(String[] args)`
            

` void`

`setUp()`
            

`static junit.framework.Test`

`suite()`
            

` void`

` tearDown()`
            

` void`

` testI18FactorySet_A()`
           Test I18nFactorySet.

` void`

` testI18FactorySet_B()`
           Test I18nFactorySet.

` void`

` testMultiFactory()`
           Test multi factory creation when moduleAware=true.

` void`

` testSingleSharedFactory()`
           Test single factory creation when moduleAware=false.

 <span id="methods_inherited_from_class_org.apache.struts.mock.TestMockBase"></span>

| **Methods inherited from class org.apache.struts.mock.TestMockBase**      |
|---------------------------------------------------------------------------|
| `setUpDefaultApp, setUpSecondApp, setUpThirdApp, testUtilBaseEnvironment` |

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

<span id="module1"></span>

### module1

    protected ModuleConfig module1

------------------------------------------------------------------------

<span id="module2"></span>

### module2

    protected ModuleConfig module2

------------------------------------------------------------------------

<span id="actionServlet"></span>

### actionServlet

    protected org.apache.struts.mock.MockActionServlet actionServlet

<span id="constructor_detail"></span>

**Constructor Detail**

### TestTilesPlugin

    public TestTilesPlugin(String name)

<span id="method_detail"></span>

**Method Detail**

### main

    public static void main(String[] args)

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

------------------------------------------------------------------------

### setUp

    public void setUp()

**Overrides:**  
`setUp` in class `org.apache.struts.mock.TestMockBase`

------------------------------------------------------------------------

### tearDown

    public void tearDown()

**Overrides:**  
`tearDown` in class `org.apache.struts.mock.TestMockBase`

------------------------------------------------------------------------

### createModuleConfig

    public ModuleConfig createModuleConfig(String moduleName,
                                           String configFileName,
                                           boolean moduleAware)

Create a module configuration

**Parameters:**  
`moduleName` -

------------------------------------------------------------------------

### initModulePlugIns

    public void initModulePlugIns(ModuleConfig moduleConfig)

Fake call to init module plugins

**Parameters:**  
`moduleConfig` -

------------------------------------------------------------------------

### testMultiFactory

    public void testMultiFactory()

Test multi factory creation when moduleAware=true.

------------------------------------------------------------------------

### testSingleSharedFactory

    public void testSingleSharedFactory()

Test single factory creation when moduleAware=false.

------------------------------------------------------------------------

### testI18FactorySet\_A

    public void testI18FactorySet_A()

Test I18nFactorySet.

------------------------------------------------------------------------

### testI18FactorySet\_B

    public void testI18FactorySet_B()

Test I18nFactorySet.

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
<td align="left"><a href="../../../../org/apache/struts/tiles/package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/TestTilesPlugin.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/tiles/CustomI18nFactorySet.html.md" title="class in org.apache.struts.tiles"><strong>PREV CLASS</strong></a>   NEXT CLASS</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/tiles/TestTilesPlugin.html"><strong>FRAMES</strong></a>    <a href="TestTilesPlugin.html"><strong>NO FRAMES</strong></a>    
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
