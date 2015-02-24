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
<td align="left"><a href="class-use/LookupDispatchAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/LocaleAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/MappingDispatchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/LookupDispatchAction.html"><strong>FRAMES</strong></a>    <a href="LookupDispatchAction.html"><strong>NO FRAMES</strong></a>    
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

org.apache.struts.actions
 Class LookupDispatchAction
---------------------------

    java.lang.Object
      org.apache.struts.action.Action
          org.apache.struts.actions.BaseAction
              org.apache.struts.actions.DispatchAction
                  org.apache.struts.actions.LookupDispatchAction

------------------------------------------------------------------------

    public abstract class LookupDispatchAction

extends [DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions")

An abstract **Action** that dispatches to the subclass mapped `execute` method. This is useful in cases where an HTML form has multiple submit buttons with the same name. The button name is specified by the `parameter` property of the corresponding ActionMapping. To configure the use of this action in your `struts-config.xml` file, create an entry like this:

       <action path="/test"
               type="org.example.MyAction"
               name="MyForm"
              scope="request"
              input="/test.jsp"
          parameter="method"/>
     

which will use the value of the request parameter named "method" to locate the corresponding key in ApplicationResources. For example, you might have the following ApplicationResources.properties:

        button.add=Add Record
        button.delete=Delete Record
      

And your JSP would have the following format for submit buttons:

       .html.md:form action="/test">
        .html.md:submit property="method">
          <bean:message key="button.add"/>
        <.html.md:submit>
        .html.md:submit property="method">
          <bean:message key="button.delete"/>
        <.html.md:submit>
      <.html.md:form>
      

Your subclass must implement both getKeyMethodMap and the methods defined in the map. An example of such implementations are:

      protected Map getKeyMethodMap() {
          Map map = new HashMap();
          map.put("button.add", "add");
          map.put("button.delete", "delete");
          return map;
      }

      public ActionForward add(ActionMapping mapping,
              ActionForm form,
              HttpServletRequest request,
              HttpServletResponse response)
              throws IOException, ServletException {
          // do add
          return mapping.findForward("success");
      }

      public ActionForward delete(ActionMapping mapping,
              ActionForm form,
              HttpServletRequest request,
              HttpServletResponse response)
              throws IOException, ServletException {
          // do delete
          return mapping.findForward("success");
      }
     

**Notes** - If duplicate values exist for the keys returned by getKeys, only the first one found will be returned. If no corresponding key is found then an exception will be thrown. You can override the method `unspecified` to provide a custom handler. If the submit was cancelled (a .html.md:cancel` button was pressed), the custom handler `cancelled` will be used instead.

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`protected  Map`

` keyMethodMap`
           Resource key to method name lookup.

`protected  Map`

` localeMap`
           Reverse lookup map from resource value to resource key.

 <span id="fields_inherited_from_class_org.apache.struts.actions.DispatchAction"></span>

| **Fields inherited from class org.apache.struts.actions.[DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clazz, log,  methods, types`                                                                                                                                              |

 <span id="fields_inherited_from_class_org.apache.struts.actions.BaseAction"></span>

| **Fields inherited from class org.apache.struts.actions.[BaseAction](../../../../org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `messages`                                                                                                                                                         |

 <span id="fields_inherited_from_class_org.apache.struts.action.Action"></span>

| **Fields inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `servlet`                                                                                                                                               |

  <span id="constructor_summary"></span>

| **Constructor Summary**   |
|---------------------------|
| ` LookupDispatchAction()` 
                            |

  <span id="method_summary"></span>

**Method Summary**

` ActionForward`

` execute(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response)`
           Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

`protected abstract  Map`

` getKeyMethodMap()`
           Provides the mapping from resource key to method name.

`protected  String`

` getLookupMapName(HttpServletRequest request, String keyName, ActionMapping mapping)`
           Lookup the method name corresponding to the client request's locale.

`protected  String`

` getMethodName(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response, String parameter)`
           Returns the method name, given a parameter's value.

 <span id="methods_inherited_from_class_org.apache.struts.actions.DispatchAction"></span>

| **Methods inherited from class org.apache.struts.actions.[DispatchAction](../../../../org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` cancelled,  dispatchMethod,  getMethod,  getParameter,  unspecified`                                                                                                      |

 <span id="methods_inherited_from_class_org.apache.struts.action.Action"></span>

| **Methods inherited from class org.apache.struts.action.[Action](../../../../org/apache/struts/action/Action.html.md "class in org.apache.struts.action")**                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` addErrors,  addMessages,  execute,  generateToken,  getErrors,  getLocale,  getMessages,  getResources,  getResources, getServlet,  isCancelled,  isTokenValid,  isTokenValid,  resetToken,  saveErrors,  saveErrors,  saveMessages,  saveMessages,  saveToken,  setLocale,  setServlet` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="localeMap"></span>

### localeMap

    protected Map localeMap

Reverse lookup map from resource value to resource key.

------------------------------------------------------------------------

<span id="keyMethodMap"></span>

### keyMethodMap

    protected Map keyMethodMap

Resource key to method name lookup.

<span id="constructor_detail"></span>

**Constructor Detail**

### LookupDispatchAction

    public LookupDispatchAction()

<span id="method_detail"></span>

**Method Detail**

### execute

    public ActionForward execute(ActionMapping mapping,
                                 ActionForm form,
                                 HttpServletRequest request,
                                 HttpServletResponse response)
                          throws Exception

Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it). Return an `ActionForward` instance describing where and how control should be forwarded, or `null` if the response has already been completed.

**Overrides:**  
` execute` in class `DispatchAction`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

`form` - The optional ActionForm bean for this request (if any)

**Returns:**  
Describes where and how control should be forwarded.

**Throws:**  
`Exception` - if an error occurs

------------------------------------------------------------------------

### getKeyMethodMap

    protected abstract Map getKeyMethodMap()

Provides the mapping from resource key to method name.

**Returns:**  
Resource key / method name map.

------------------------------------------------------------------------

### getLookupMapName

    protected String getLookupMapName(HttpServletRequest request,
                                      String keyName,
                                      ActionMapping mapping)
                               throws ServletException

Lookup the method name corresponding to the client request's locale.

**Parameters:**  
`request` - The HTTP request we are processing

`keyName` - The parameter name to use as the properties key

`mapping` - The ActionMapping used to select this instance

**Returns:**  
The method's localized name.

**Throws:**  
`ServletException` - if keyName cannot be resolved

**Since:**  
Struts 1.2.0

------------------------------------------------------------------------

### getMethodName

    protected String getMethodName(ActionMapping mapping,
                                   ActionForm form,
                                   HttpServletRequest request,
                                   HttpServletResponse response,
                                   String parameter)
                            throws Exception

Returns the method name, given a parameter's value.

**Overrides:**  
` getMethodName` in class `DispatchAction`

<!-- -->

**Parameters:**  
`mapping` - The ActionMapping used to select this instance

`form` - The optional ActionForm bean for this request (if any)

`request` - The HTTP request we are processing

`response` - The HTTP response we are creating

`parameter` - The `ActionMapping` parameter's name

**Returns:**  
The method's name.

**Throws:**  
`Exception` - if an error occurs

**Since:**  
Struts 1.2.0

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
<td align="left"><a href="class-use/LookupDispatchAction.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../org/apache/struts/actions/LocaleAction.html.md" title="class in org.apache.struts.actions"><strong>PREV CLASS</strong></a>   <a href="../../../../org/apache/struts/actions/MappingDispatchAction.html" title="class in org.apache.struts.actions"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/actions/LookupDispatchAction.html"><strong>FRAMES</strong></a>    <a href="LookupDispatchAction.html"><strong>NO FRAMES</strong></a>    
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
