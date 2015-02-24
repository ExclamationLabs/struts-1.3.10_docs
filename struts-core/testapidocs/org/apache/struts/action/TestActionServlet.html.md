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
<td align="left"><a href="class-use/TestActionServlet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionRedirect.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionServlet.CustomActionConfig.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionServlet.html"><strong>FRAMES</strong></a>    <a href="TestActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.action
 Class TestActionServlet
------------------------

    java.lang.Object
      junit.framework.Assert
          junit.framework.TestCase
              org.apache.struts.action.TestActionServlet

**All Implemented Interfaces:**  
junit.framework.Test

------------------------------------------------------------------------

    public class TestActionServlet

extends junit.framework.TestCase

Suite of unit tests for the `org.apache.struts.action.ActionServlet` class.

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

`static class`

`TestActionServlet.CustomActionConfig`
           Used for testing custom ActionConfig classes.

`static class`

`TestActionServlet.CustomExceptionConfig`
           Used for testing custom ExceptionConfig classes.

`static class`

`TestActionServlet.CustomFormBeanConfig`
           Used for testing custom FormBeanConfig classes.

`static class`

`TestActionServlet.CustomForwardConfig`
           Used for testing custom ForwardConfig classes.

  <span id="field_summary"></span>

**Field Summary**

`protected  ActionServlet`

` actionServlet`
           The ActionServlet we'll test.

`protected  ActionMapping`

` baseAction`
           The common action config we'll use.

`protected  ExceptionConfig`

` baseException`
           The common exception config we'll use.

`protected  FormBeanConfig`

` baseFormBean`
           The common form bean we'll use.

`protected  ActionForward`

` baseForward`
           The common action forward we'll use.

`protected  ModuleConfig`

` moduleConfig`
           The ModuleConfig we'll use.

  <span id="constructor_summary"></span>

| **Constructor Summary**                         |
|-------------------------------------------------|
| ` TestActionServlet(String theName)`            
            Defines the testcase name for JUnit.  |

  <span id="method_summary"></span>

**Method Summary**

`static void`

` main(String[] theArgs)`
           Start the tests.

` void`

` notestProcessActionConfigClassError()`
           Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

` void`

` notestProcessExceptionConfigClassError()`
           Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

` void`

` notestProcessFormBeanConfigClassError()`
           Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

` void`

` notestProcessForwardConfigClassError()`
           Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

` void`

` notestSplitAndResolvePaths()`
           Test class loader resolution and splitting.

` void`

` setUp()`
           Set up instance variables required by this test case.

`static junit.framework.Test`

` suite()`
            

` void`

` tearDown()`
           Tear down instance variables required by this test case.

` void`

` testInitDestroyInternal()`
           Verify that we can initialize and destroy our internal message resources object.

` void`

` testInitModuleActionConfigsNoExtends()`
           Test that nothing fails if there are no extensions.

` void`

` testInitModuleExceptionConfigsNoExtends()`
           Test that nothing fails if there are no extensions.

` void`

` testInitModuleExceptionConfigsNullFormType()`
           Test that initModuleExceptionConfigs throws an exception when a handler with a null key is present.

` void`

` testInitModuleFormBeansNoExtends()`
           Test that nothing fails if there are no extensions.

` void`

` testInitModuleFormBeansNullFormType()`
           Test that initModuleFormBeans throws an exception when a form with a null type is present.

` void`

` testInitModuleFormBeansNullPropType()`
           Test that initModuleFormBeans throws an exception when a form whose prop type is null is present.

` void`

` testInitModuleForwardConfigsNoExtends()`
           Test that nothing fails if there are no extensions.

` void`

` testInitModuleForwardsNullFormType()`
           Test that initModuleForwards throws an exception when a forward with a null path is present.

` void`

` testProcessActionConfigClass()`
           Make sure processActionConfigClass() returns an instance of the correct class if the base config is using a custom class.

` void`

` testProcessActionConfigClassNoExtends()`
           Make sure processActionConfigClass() returns what it was given if the action passed to it doesn't extend anything.

` void`

` testProcessActionConfigClassOverriddenSubConfigClass()`
           Test the case where the subconfig has already specified its own config class.

` void`

` testProcessActionConfigClassSubConfigCustomClass()`
           Make sure processActionConfigClass() returns the same class instance if the base config isn't using a custom class.

` void`

` testProcessActionExtension()`
           Test that processActionConfigExtension() calls processExtends()

` void`

` testProcessActionExtensionWithExceptionConfig()`
           Test that an ActionConfig's ExceptionConfig can inherit from a global ExceptionConfig.

` void`

` testProcessActionExtensionWithForwardConfig()`
           Test that an ActionConfig's ForwardConfig can inherit from a global ForwardConfig.

` void`

` testProcessExceptionConfigClass()`
           Make sure processExceptionConfigClass() returns an instance of the correct class if the base config is using a custom class.

` void`

` testProcessExceptionConfigClassNoExtends()`
           Make sure processExceptionConfigClass() returns what it was given if the handler passed to it doesn't extend anything.

` void`

` testProcessExceptionConfigClassOverriddenSubFormClass()`
           Test the case where the subconfig has already specified its own config class.

` void`

` testProcessExceptionConfigClassSubConfigCustomClass()`
           Make sure processExceptionConfigClass() returns the same class instance if the base config isn't using a custom class.

` void`

` testProcessExceptionExtension()`
           Test that processExceptionExtension() calls processExtends()

` void`

` testProcessFormBeanConfigClass()`
           Make sure processFormBeanConfigClass() returns an instance of the correct class if the base config is using a custom class.

` void`

` testProcessFormBeanConfigClassNoExtends()`
           Make sure processFormBeanConfigClass() returns what it was given if the form passed to it doesn't extend anything.

` void`

` testProcessFormBeanConfigClassOverriddenSubFormClass()`
           Test the case where the subform has already specified its own form bean config class.

` void`

` testProcessFormBeanConfigClassSubFormCustomClass()`
           Make sure processFormBeanConfigClass() returns the same class instance if the base config isn't using a custom class.

` void`

` testProcessFormBeanExtension()`
           Test that processFormBeanExtension() calls processExtends()

` void`

` testProcessForwardConfigClass()`
           Make sure processForwardConfigClass() returns an instance of the correct class if the base config is using a custom class.

` void`

` testProcessForwardConfigClassNoExtends()`
           Make sure processForwardConfigClass() returns what it was given if the forward passed to it doesn't extend anything.

` void`

` testProcessForwardConfigClassOverriddenSubConfigClass()`
           Test the case where the subconfig has already specified its own config class.

` void`

` testProcessForwardConfigClassSubConfigCustomClass()`
           Make sure processForwardConfigClass() returns the same class instance if the base config isn't using a custom class.

` void`

` testProcessForwardExtension()`
           Test that processForwardExtension() calls processExtends()

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

<span id="baseFormBean"></span>

### baseFormBean

    protected FormBeanConfig baseFormBean

The common form bean we'll use.

------------------------------------------------------------------------

<span id="baseException"></span>

### baseException

    protected ExceptionConfig baseException

The common exception config we'll use.

------------------------------------------------------------------------

<span id="baseAction"></span>

### baseAction

    protected ActionMapping baseAction

The common action config we'll use.

------------------------------------------------------------------------

<span id="baseForward"></span>

### baseForward

    protected ActionForward baseForward

The common action forward we'll use.

------------------------------------------------------------------------

<span id="actionServlet"></span>

### actionServlet

    protected ActionServlet actionServlet

The ActionServlet we'll test.

<span id="constructor_detail"></span>

**Constructor Detail**

### TestActionServlet

    public TestActionServlet(String theName)

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
               throws Exception

Set up instance variables required by this test case.

**Overrides:**  
`setUp` in class `junit.framework.TestCase`

<!-- -->

**Throws:**  
`Exception`

------------------------------------------------------------------------

### tearDown

    public void tearDown()

Tear down instance variables required by this test case.

**Overrides:**  
`tearDown` in class `junit.framework.TestCase`

------------------------------------------------------------------------

### testInitDestroyInternal

    public void testInitDestroyInternal()

Verify that we can initialize and destroy our internal message resources object.

------------------------------------------------------------------------

### notestSplitAndResolvePaths

    public void notestSplitAndResolvePaths()
                                    throws Exception

Test class loader resolution and splitting.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInitModuleFormBeansNoExtends

    public void testInitModuleFormBeansNoExtends()
                                          throws ServletException

Test that nothing fails if there are no extensions.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testInitModuleFormBeansNullFormType

    public void testInitModuleFormBeansNullFormType()
                                             throws ServletException

Test that initModuleFormBeans throws an exception when a form with a null type is present.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testInitModuleFormBeansNullPropType

    public void testInitModuleFormBeansNullPropType()
                                             throws ServletException

Test that initModuleFormBeans throws an exception when a form whose prop type is null is present.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessFormBeanExtension

    public void testProcessFormBeanExtension()
                                      throws ServletException

Test that processFormBeanExtension() calls processExtends()

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessFormBeanConfigClass

    public void testProcessFormBeanConfigClass()
                                        throws Exception

Make sure processFormBeanConfigClass() returns an instance of the correct class if the base config is using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessFormBeanConfigClassNoExtends

    public void testProcessFormBeanConfigClassNoExtends()
                                                 throws Exception

Make sure processFormBeanConfigClass() returns what it was given if the form passed to it doesn't extend anything.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessFormBeanConfigClassSubFormCustomClass

    public void testProcessFormBeanConfigClassSubFormCustomClass()
                                                          throws Exception

Make sure processFormBeanConfigClass() returns the same class instance if the base config isn't using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### notestProcessFormBeanConfigClassError

    public void notestProcessFormBeanConfigClassError()
                                               throws Exception

Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessFormBeanConfigClassOverriddenSubFormClass

    public void testProcessFormBeanConfigClassOverriddenSubFormClass()
                                                              throws Exception

Test the case where the subform has already specified its own form bean config class. If the code still attempts to create a new instance, an error will be thrown.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInitModuleExceptionConfigsNoExtends

    public void testInitModuleExceptionConfigsNoExtends()
                                                 throws ServletException

Test that nothing fails if there are no extensions.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testInitModuleExceptionConfigsNullFormType

    public void testInitModuleExceptionConfigsNullFormType()
                                                    throws ServletException

Test that initModuleExceptionConfigs throws an exception when a handler with a null key is present.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessExceptionExtension

    public void testProcessExceptionExtension()
                                       throws ServletException

Test that processExceptionExtension() calls processExtends()

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessExceptionConfigClass

    public void testProcessExceptionConfigClass()
                                         throws Exception

Make sure processExceptionConfigClass() returns an instance of the correct class if the base config is using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExceptionConfigClassNoExtends

    public void testProcessExceptionConfigClassNoExtends()
                                                  throws Exception

Make sure processExceptionConfigClass() returns what it was given if the handler passed to it doesn't extend anything.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExceptionConfigClassSubConfigCustomClass

    public void testProcessExceptionConfigClassSubConfigCustomClass()
                                                             throws Exception

Make sure processExceptionConfigClass() returns the same class instance if the base config isn't using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### notestProcessExceptionConfigClassError

    public void notestProcessExceptionConfigClassError()
                                                throws Exception

Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessExceptionConfigClassOverriddenSubFormClass

    public void testProcessExceptionConfigClassOverriddenSubFormClass()
                                                               throws Exception

Test the case where the subconfig has already specified its own config class. If the code still attempts to create a new instance, an error will be thrown.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInitModuleForwardConfigsNoExtends

    public void testInitModuleForwardConfigsNoExtends()
                                               throws ServletException

Test that nothing fails if there are no extensions.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testInitModuleForwardsNullFormType

    public void testInitModuleForwardsNullFormType()
                                            throws ServletException

Test that initModuleForwards throws an exception when a forward with a null path is present.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessForwardExtension

    public void testProcessForwardExtension()
                                     throws ServletException

Test that processForwardExtension() calls processExtends()

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessForwardConfigClass

    public void testProcessForwardConfigClass()
                                       throws Exception

Make sure processForwardConfigClass() returns an instance of the correct class if the base config is using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessForwardConfigClassNoExtends

    public void testProcessForwardConfigClassNoExtends()
                                                throws Exception

Make sure processForwardConfigClass() returns what it was given if the forward passed to it doesn't extend anything.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessForwardConfigClassSubConfigCustomClass

    public void testProcessForwardConfigClassSubConfigCustomClass()
                                                           throws Exception

Make sure processForwardConfigClass() returns the same class instance if the base config isn't using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### notestProcessForwardConfigClassError

    public void notestProcessForwardConfigClassError()
                                              throws Exception

Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessForwardConfigClassOverriddenSubConfigClass

    public void testProcessForwardConfigClassOverriddenSubConfigClass()
                                                               throws Exception

Test the case where the subconfig has already specified its own config class. If the code still attempts to create a new instance, an error will be thrown.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testInitModuleActionConfigsNoExtends

    public void testInitModuleActionConfigsNoExtends()
                                              throws ServletException

Test that nothing fails if there are no extensions.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessActionExtension

    public void testProcessActionExtension()
                                    throws ServletException

Test that processActionConfigExtension() calls processExtends()

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessActionExtensionWithForwardConfig

    public void testProcessActionExtensionWithForwardConfig()
                                                     throws ServletException

Test that an ActionConfig's ForwardConfig can inherit from a global ForwardConfig.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessActionExtensionWithExceptionConfig

    public void testProcessActionExtensionWithExceptionConfig()
                                                       throws ServletException

Test that an ActionConfig's ExceptionConfig can inherit from a global ExceptionConfig.

**Throws:**  
`ServletException`

------------------------------------------------------------------------

### testProcessActionConfigClass

    public void testProcessActionConfigClass()
                                      throws Exception

Make sure processActionConfigClass() returns an instance of the correct class if the base config is using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessActionConfigClassNoExtends

    public void testProcessActionConfigClassNoExtends()
                                               throws Exception

Make sure processActionConfigClass() returns what it was given if the action passed to it doesn't extend anything.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessActionConfigClassSubConfigCustomClass

    public void testProcessActionConfigClassSubConfigCustomClass()
                                                          throws Exception

Make sure processActionConfigClass() returns the same class instance if the base config isn't using a custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### notestProcessActionConfigClassError

    public void notestProcessActionConfigClassError()
                                             throws Exception

Make sure the code throws the correct exception when it can't create an instance of the base config's custom class.

**Throws:**  
`Exception`

------------------------------------------------------------------------

### testProcessActionConfigClassOverriddenSubConfigClass

    public void testProcessActionConfigClassOverriddenSubConfigClass()
                                                              throws Exception

Test the case where the subconfig has already specified its own config class. If the code still attempts to create a new instance, an error will be thrown.

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
<td align="left"><a href="class-use/TestActionServlet.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/action/TestActionRedirect.html.md" title="class in org.apache.struts.action"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/action/TestActionServlet.CustomActionConfig.html" title="class in org.apache.struts.action"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/TestActionServlet.html"><strong>FRAMES</strong></a>    <a href="TestActionServlet.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
