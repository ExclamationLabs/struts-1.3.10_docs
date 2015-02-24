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
<td align="left"><a href="class-use/TestForwardConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/TestFormPropertyConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/TestModuleConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestForwardConfig.html"><strong>FRAMES</strong></a>    <a href="TestForwardConfig.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.config
 Class TestForwardConfig
------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.config.TestForwardConfig

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestForwardConfig

extends junit.framework.TestCase

Unit tests for ForwardConfig. Currently contains tests for methods supporting configuration inheritance.

**Version:**  
$Rev: 471754 $ $Date: 2005-05-21 19:06:53 -0400 (Sat, 21 May 2005) $

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  ForwardConfig`

` actionBaseConfig`
           A ForwardConfig we'll use to test cases where a ForwardConfig declared for an action extends a ForwardConfig declared globally, with both ForwardConfigs using the same name.

`protected  ActionConfig`

` actionConfig`
           An action mapping we'll use within tests.

`protected  ForwardConfig`

` baseConfig`
           The common base we'll use.

`protected  ModuleConfig`

` moduleConfig`
           The ModuleConfig we'll use.

`protected  ForwardConfig`

` subConfig`
           The common subForward we'll use.

  <span id="constructor_summary"></span>

| **Constructor Summary**                                |
|--------------------------------------------------------|
| ` TestForwardConfig(String name)`                      
            Construct a new instance of this test case.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` setUp()`
           Set up instance variables required by this test case.

`static junit.framework.Test`

` suite()`
           Return the tests included in this test suite.

` void`

` tearDown()`
           Tear down instance variables required by this test case.

` void`

` testCheckCircularInheritanceActionForwardExtendGlobal()`
           Test checkCircularInheritance() for circular inheritance between a forward declared in an action and a global forward.

` void`

` testCheckCircularInheritanceActionForwardExtendGlobalSameName()`
           Test checkCircularInheritance() for circular inheritance between a forward declared in an action and a global forward and both forwards have the same name.

` void`

` testCheckCircularInheritanceActionForwardsBasic()`
           Test checkCircularInheritance() for circular inheritance between forwards in an action.

` void`

` testCheckCircularInheritanceActionForwardsNoConflict()`
           Test checkCircularInheritance() for circular inheritance between forwards in an action.

` void`

` testCheckCircularInheritanceBasicGlobal()`
           Test checkCircularInheritance() for circular inheritance between global forwards.

` void`

` testCheckCircularInheritanceGlobal2Levels()`
           Test checkCircularInheritance() for circular inheritance between global forwards.

` void`

` testCheckCircularInheritanceNoConflicts()`
           Test checkCircularInheritance() for when there is no circular inheritance.

` void`

` testCheckCircularInheritanceNoExtends()`
           Make sure checkCircularInheritance() works as expected where there is no inheritance set up.

` void`

` testProcessExtendsActionExtendsActionExtendsGlobalWithSameName()`
           Test processExtends() where an action ForwardConfig extends another ForwardConfig, which in turn extends a global ForwardConfig with the same name.

` void`

` testProcessExtendsBasicExtension()`
           Test processExtends() with a basic extension.

` void`

` testProcessExtendsBasicGlobalExtension()`
           Test processExtends() with a basic extension between an action config and a global config.

` void`

` testProcessExtendsConfigured()`
           Make sure processExtends() throws an error when the config is already configured.

` void`

` testProcessExtendsGlobalExtendingAction()`
           Test processExtends() with an incorrect setup where a global config attempts to extend an action config.

` void`

` testProcessExtendsNoExtension()`
           Test processExtends() when nothing is extended.

` void`

` testProcessExtendsSameNames()`
           Test processExtends() with an action config that extends a global config with the same name.

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

<span id="moduleConfig"></span>

### moduleConfig

    protected ModuleConfig moduleConfig

The ModuleConfig we'll use.

------------------------------------------------------------------------

<span id="baseConfig"></span>

### baseConfig

    protected ForwardConfig baseConfig

The common base we'll use.

------------------------------------------------------------------------

<span id="subConfig"></span>

### subConfig

    protected ForwardConfig subConfig

The common subForward we'll use.

------------------------------------------------------------------------

<span id="actionBaseConfig"></span>

### actionBaseConfig

    protected ForwardConfig actionBaseConfig

A ForwardConfig we'll use to test cases where a ForwardConfig declared for an action extends a ForwardConfig declared globally, with both ForwardConfigs using the same name.

------------------------------------------------------------------------

<span id="actionConfig"></span>

### actionConfig

    protected ActionConfig actionConfig

An action mapping we'll use within tests.

<span id="constructor_detail"></span>

**Constructor Detail**

### TestForwardConfig

    public TestForwardConfig(String name)

Construct a new instance of this test case.

**Parameters:**  
`name` - Name of the test case

<span id="method_detail"></span>

**Method Detail**

### setUp

    public void setUp()

Set up instance variables required by this test case.

**Overrides:**  
`setUp` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### suite

    public static junit.framework.Test suite()

Return the tests included in this test suite.

------------------------------------------------------------------------

### tearDown

    public void tearDown()

Tear down instance variables required by this test case.

**Overrides:**  
`tearDown` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### testCheckCircularInheritanceNoExtends

    public void testCheckCircularInheritanceNoExtends()

Make sure checkCircularInheritance() works as expected where there is no inheritance set up.

------------------------------------------------------------------------

### testCheckCircularInheritanceNoConflicts

    public void testCheckCircularInheritanceNoConflicts()

Test checkCircularInheritance() for when there is no circular inheritance.

------------------------------------------------------------------------

### testCheckCircularInheritanceBasicGlobal

    public void testCheckCircularInheritanceBasicGlobal()

Test checkCircularInheritance() for circular inheritance between global forwards.

------------------------------------------------------------------------

### testCheckCircularInheritanceGlobal2Levels

    public void testCheckCircularInheritanceGlobal2Levels()

Test checkCircularInheritance() for circular inheritance between global forwards.

------------------------------------------------------------------------

### testCheckCircularInheritanceActionForwardsNoConflict

    public void testCheckCircularInheritanceActionForwardsNoConflict()

Test checkCircularInheritance() for circular inheritance between forwards in an action.

------------------------------------------------------------------------

### testCheckCircularInheritanceActionForwardsBasic

    public void testCheckCircularInheritanceActionForwardsBasic()

Test checkCircularInheritance() for circular inheritance between forwards in an action.

------------------------------------------------------------------------

### testCheckCircularInheritanceActionForwardExtendGlobal

    public void testCheckCircularInheritanceActionForwardExtendGlobal()

Test checkCircularInheritance() for circular inheritance between a forward declared in an action and a global forward.

------------------------------------------------------------------------

### testCheckCircularInheritanceActionForwardExtendGlobalSameName

    public void testCheckCircularInheritanceActionForwardExtendGlobalSameName()

Test checkCircularInheritance() for circular inheritance between a forward declared in an action and a global forward and both forwards have the same name.

------------------------------------------------------------------------

### testProcessExtendsConfigured

    public void testProcessExtendsConfigured()
                                      throws Exception

Make sure processExtends() throws an error when the config is already configured.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsNoExtension

    public void testProcessExtendsNoExtension()
                                       throws Exception

Test processExtends() when nothing is extended.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsBasicExtension

    public void testProcessExtendsBasicExtension()
                                          throws Exception

Test processExtends() with a basic extension.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsBasicGlobalExtension

    public void testProcessExtendsBasicGlobalExtension()
                                                throws Exception

Test processExtends() with a basic extension between an action config and a global config.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsGlobalExtendingAction

    public void testProcessExtendsGlobalExtendingAction()
                                                 throws Exception

Test processExtends() with an incorrect setup where a global config attempts to extend an action config.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsSameNames

    public void testProcessExtendsSameNames()
                                     throws Exception

Test processExtends() with an action config that extends a global config with the same name.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExtendsActionExtendsActionExtendsGlobalWithSameName

    public void testProcessExtendsActionExtendsActionExtendsGlobalWithSameName()
                                                                        throws Exception

Test processExtends() where an action ForwardConfig extends another ForwardConfig, which in turn extends a global ForwardConfig with the same name.

**Throws:**  
`Exception`

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
<td align="left"><a href="class-use/TestForwardConfig.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/config/TestFormPropertyConfig.html.md" title="class in org.apache.struts.config"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/config/TestModuleConfig.html" title="class in org.apache.struts.config"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/TestForwardConfig.html"><strong>FRAMES</strong></a>    <a href="TestForwardConfig.html"><strong>NO FRAMES</strong></a>    
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
