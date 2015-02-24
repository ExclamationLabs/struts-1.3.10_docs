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
<td align="left"><a href="class-use/InsertTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InitDefinitionsTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.DirectStringHandler.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/InsertTag.html"><strong>FRAMES</strong></a>    <a href="InsertTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_class_summary">NESTED</a> | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.taglib
 Class InsertTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.tiles.taglib.DefinitionTagSupport
              org.apache.struts.tiles.taglib.InsertTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html "interface in org.apache.struts.tiles.taglib"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib"), [PutTagParent](../../../../../org/apache/struts/tiles/taglib/PutTagParent.html "interface in org.apache.struts.tiles.taglib")

<!-- -->

**Direct Known Subclasses:**  
[ELInsertTag](../../../../../org/apache/strutsel/taglib/tiles/ELInsertTag.html.md "class in org.apache.strutsel.taglib.tiles"), [GetTag](../../../../../org/apache/struts/tiles/taglib/GetTag.html "class in org.apache.struts.tiles.taglib")

------------------------------------------------------------------------

    public class InsertTag

extends [DefinitionTagSupport](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib")

implements [PutTagParent](../../../../../org/apache/struts/tiles/taglib/PutTagParent.html.md "interface in org.apache.struts.tiles.taglib"), [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html "interface in org.apache.struts.tiles.taglib"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib")

This is the tag handler for \<tiles:insert\>, which includes a template. The tag's body content consists of \<tiles:put\> tags, which are accessed by \<tiles:get\> in the template.

**Version:**  
$Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.taglib.InsertTag)

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

`protected  class`

`InsertTag.DirectStringHandler`
           Handle insert direct string.

`protected  class`

`InsertTag.InsertHandler`
           Real handler, after attribute resolution.

`protected static interface`

`InsertTag.TagHandler`
           Inner Interface.

  <span id="field_summary"></span>

**Field Summary**

`protected  String`

` attribute`
           Name of attribute from which to read page name to include.

`protected  String`

` beanName`
           Name of bean used as entity to include.

`protected  String`

` beanProperty`
           Name of bean property, if any.

`protected  String`

` beanScope`
           Scope of bean, if any.

`protected  ComponentContext`

` cachedCurrentContext`
           Current component context.

`protected  String`

` definitionName`
           Name of component instance to include.

`protected  boolean`

` flush`
           Flush attribute value.

`protected  boolean`

` isErrorIgnored`
           Are errors ignored.

`protected static Log`

`log`
           Commons Logging instance.

`protected  String`

` name`
           Name to insert.

`protected  PageContext`

` pageContext`
           Trick to allows inner classes to access pageContext.

`protected  boolean`

` processEndTag`
           Does the end tag need to be processed.

`static String`

` ROLE_DELIMITER`
           **Deprecated.** *This will be removed in a release after Struts 1.2.*

`protected  InsertTag.TagHandler`

` tagHandler`
           Final handler of tag methods.

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

| **Fields inherited from class org.apache.struts.tiles.taglib.[DefinitionTagSupport](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib")** |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` controllerName,  controllerType,  page,  role`                                                                                                                                                         |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Fields inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                                                                                                                                                                                                                    |

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.ComponentConstants"></span>

| **Fields inherited from interface org.apache.struts.tiles.taglib.[ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html.md "interface in org.apache.struts.tiles.taglib")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` COMPONENT_CONTEXT,  COMPONENT_SCOPE,  EXCEPTION_KEY,  LOCALE_KEY`                                                                                                                                          |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.IterationTag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_AGAIN`                                                                                                                                                                                                               |

 <span id="fields_inherited_from_class_javax.servlet.jsp.tagext.Tag"></span>

| **Fields inherited from interface javax.servlet.jsp.tagext.[Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `EVAL_BODY_INCLUDE, EVAL_PAGE, SKIP_BODY, SKIP_PAGE`                                                                                                                                                          |

  <span id="constructor_summary"></span>

| **Constructor Summary** |
|-------------------------|
| ` InsertTag()`          
                          |

  <span id="method_summary"></span>

**Method Summary**

` InsertTag.TagHandler`

` createTagHandler()`
           Process tag attribute and create corresponding tag handler.

` int`

` doEndTag()`
           Process the end tag by including the template.

`protected  void`

` doInclude(String page, boolean flush)`
           Do an include of specified page.

` int`

` doStartTag()`
           Process the start tag by checking tag's attributes and creating appropriate handler.

` String`

` getBeanName()`
           Get bean name.

` String`

` getBeanProperty()`
           Get bean property.

` String`

` getBeanScope()`
           Get bean scope.

` String`

` getDefinitionName()`
           Get definition name.

` boolean`

` getFlush()`
           Get flush.

` boolean`

` getIgnore()`
           Get ignore.

` String`

` getName()`
           Get name.

` PageContext`

` getPageContext()`
           Get the pageContext property.

` InsertTag.TagHandler`

` processAsDefinitionOrURL(String name)`
           Try to process name as a definition, or as an URL if not found.

` InsertTag.TagHandler`

` processAttribute(String name)`
           Process tag attribute "attribute".

`protected  InsertTag.TagHandler`

` processBean(String beanName, String beanProperty, String beanScope)`
           Process a bean.

`protected  InsertTag.TagHandler`

` processDefinition(ComponentDefinition definition)`
           End of Process tag attribute "definition".

`protected  InsertTag.TagHandler`

` processDefinitionName(String name)`
           Process tag attribute "definition".

` InsertTag.TagHandler`

` processName(String name)`
           Process name.

` void`

` processNestedTag(PutListTag nestedTag)`
           Process nested &lg;putList\> tag.

` void`

` processNestedTag(PutTag nestedTag)`
           Process nested &lg;put\> tag.

` InsertTag.TagHandler`

` processObjectValue(Object value)`
           Process an object retrieved as a bean or attribute.

` InsertTag.TagHandler`

` processTypedAttribute(AttributeDefinition value)`
           Process typed attribute according to its type.

` InsertTag.TagHandler`

` processUrl(String url)`
           Process the url.

` void`

` putAttribute(PutListTag nestedTag)`
           Method calls by nested &lg;putList\> tags.

` void`

` putAttribute(String name, Object value)`
           Add a body attribute.

` void`

` release()`
           Reset member values for reuse.

`protected  void`

` releaseInternal()`
           Reset internal member values for reuse.

` void`

` setAttribute(String value)`
           Set attribute.

` void`

` setBeanName(String value)`
           Set bean name.

` void`

` setBeanProperty(String value)`
           Set bean property.

` void`

` setBeanScope(String value)`
           Set bean scope.

` void`

` setComponent(String name)`
           Set component.

` void`

` setDefinition(String name)`
           Set definition.

` void`

` setFlush(boolean flush)`
           Set flush.

` void`

` setFlush(String flush)`
           Set flush.

` void`

` setIgnore(boolean ignore)`
           Set ignore.

` void`

` setName(String value)`
           Set name.

` void`

` setPageContext(PageContext pc)`
           Set the current page context.

`static boolean`

` userHasRole(HttpServletRequest request, String role)`
           Parse the list of roles and return `true` or `false` based on whether the user has that role or not.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.DefinitionTagSupport"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[DefinitionTagSupport](../../../../../org/apache/struts/tiles/taglib/DefinitionTagSupport.html.md "class in org.apache.struts.tiles.taglib")**    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` getControllerName,  getControllerType,  getPage,  getRole,  getTemplate,  setController,  setControllerClass,  setControllerName,  setControllerType,  setControllerUrl,  setPage,  setRole,  setTemplate` |

 <span id="methods_inherited_from_class_javax.servlet.jsp.tagext.TagSupport"></span>

| **Methods inherited from class javax.servlet.jsp.tagext.[TagSupport](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/TagSupport.html.md?is-external=true "class or interface in javax.servlet.jsp.tagext")** |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `doAfterBody, findAncestorWithClass, getId, getParent, getValue, getValues, removeValue, setId, setParent, setValue`                                                                                                     |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

<span id="ROLE_DELIMITER"></span>

### ROLE\_DELIMITER

    public static final String ROLE_DELIMITER

**Deprecated.** *This will be removed in a release after Struts 1.2.*

The role delimiter.

**See Also:**  
[Constant Field Values](../../../../../constant-values.html.md#org.apache.struts.tiles.taglib.InsertTag.ROLE_DELIMITER)

------------------------------------------------------------------------

<span id="log"></span>

### log

    protected static Log log

Commons Logging instance.

------------------------------------------------------------------------

<span id="flush"></span>

### flush

    protected boolean flush

Flush attribute value.

------------------------------------------------------------------------

<span id="name"></span>

### name

    protected String name

Name to insert.

------------------------------------------------------------------------

<span id="attribute"></span>

### attribute

    protected String attribute

Name of attribute from which to read page name to include.

------------------------------------------------------------------------

<span id="beanName"></span>

### beanName

    protected String beanName

Name of bean used as entity to include.

------------------------------------------------------------------------

<span id="beanProperty"></span>

### beanProperty

    protected String beanProperty

Name of bean property, if any.

------------------------------------------------------------------------

<span id="beanScope"></span>

### beanScope

    protected String beanScope

Scope of bean, if any.

------------------------------------------------------------------------

<span id="isErrorIgnored"></span>

### isErrorIgnored

    protected boolean isErrorIgnored

Are errors ignored. This is the property for attribute 'ignore'. Default value is false, which throw an exception. Only 'attribute not found' errors are ignored.

------------------------------------------------------------------------

<span id="definitionName"></span>

### definitionName

    protected String definitionName

Name of component instance to include.

------------------------------------------------------------------------

<span id="processEndTag"></span>

### processEndTag

    protected boolean processEndTag

Does the end tag need to be processed. Default value is true. Boolean set in case of ignored errors.

------------------------------------------------------------------------

<span id="cachedCurrentContext"></span>

### cachedCurrentContext

    protected ComponentContext cachedCurrentContext

Current component context.

------------------------------------------------------------------------

<span id="tagHandler"></span>

### tagHandler

    protected InsertTag.TagHandler tagHandler

Final handler of tag methods.

------------------------------------------------------------------------

<span id="pageContext"></span>

### pageContext

    protected PageContext pageContext

Trick to allows inner classes to access pageContext.

<span id="constructor_detail"></span>

**Constructor Detail**

### InsertTag

    public InsertTag()

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

Reset member values for reuse. This method calls super.release(), which invokes TagSupport.release(), which typically does nothing.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `DefinitionTagSupport`

------------------------------------------------------------------------

### releaseInternal

    protected void releaseInternal()

Reset internal member values for reuse.

------------------------------------------------------------------------

### setPageContext

    public void setPageContext(PageContext pc)

Set the current page context. Called by the page implementation prior to doStartTag().

Needed to allow inner classes to access pageContext.

**Specified by:**  
`setPageContext` in interface `Tag`

**Overrides:**  
`setPageContext` in class `TagSupport`

------------------------------------------------------------------------

### getPageContext

    public PageContext getPageContext()

Get the pageContext property.

------------------------------------------------------------------------

### setName

    public void setName(String value)

Set name.

------------------------------------------------------------------------

### getName

    public String getName()

Get name.

------------------------------------------------------------------------

### setComponent

    public void setComponent(String name)

Set component.

------------------------------------------------------------------------

### setDefinition

    public void setDefinition(String name)

Set definition.

------------------------------------------------------------------------

### getDefinitionName

    public String getDefinitionName()

Get definition name.

------------------------------------------------------------------------

### setAttribute

    public void setAttribute(String value)

Set attribute.

------------------------------------------------------------------------

### setBeanName

    public void setBeanName(String value)

Set bean name.

------------------------------------------------------------------------

### getBeanName

    public String getBeanName()

Get bean name.

------------------------------------------------------------------------

### setBeanProperty

    public void setBeanProperty(String value)

Set bean property.

------------------------------------------------------------------------

### getBeanProperty

    public String getBeanProperty()

Get bean property.

------------------------------------------------------------------------

### setBeanScope

    public void setBeanScope(String value)

Set bean scope.

------------------------------------------------------------------------

### getBeanScope

    public String getBeanScope()

Get bean scope.

------------------------------------------------------------------------

### setFlush

    public void setFlush(boolean flush)

Set flush.

------------------------------------------------------------------------

### getFlush

    public boolean getFlush()

Get flush.

------------------------------------------------------------------------

### setFlush

    public void setFlush(String flush)

Set flush. Method added for compatibility with JSP1.1

------------------------------------------------------------------------

### setIgnore

    public void setIgnore(boolean ignore)

Set ignore.

------------------------------------------------------------------------

### getIgnore

    public boolean getIgnore()

Get ignore.

------------------------------------------------------------------------

### putAttribute

    public void putAttribute(String name,
                             Object value)

Add a body attribute. Erase any attribute with same name previously set.

------------------------------------------------------------------------

### processNestedTag

    public void processNestedTag(PutTag nestedTag)
                          throws JspException

Process nested &lg;put\> tag. Method calls by nested &lg;put\> tags. Nested list is added to current list. If role is defined, it is checked immediately.

**Specified by:**  
` processNestedTag` in interface `PutTagParent`

<!-- -->

**Parameters:**  
`nestedTag` - Nested tag to process.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### processNestedTag

    public void processNestedTag(PutListTag nestedTag)
                          throws JspException

Process nested &lg;putList\> tag. Method calls by nested &lg;putList\> tags. Nested list is added to sub-component attributes If role is defined, it is checked immediately.

**Specified by:**  
` processNestedTag` in interface `PutListTagParent`

<!-- -->

**Parameters:**  
`nestedTag` - Nested PutTag defining the attribute.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### putAttribute

    public void putAttribute(PutListTag nestedTag)
                      throws JspException

Method calls by nested &lg;putList\> tags. A new list is added to current insert object.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doStartTag

    public int doStartTag()
                   throws JspException

Process the start tag by checking tag's attributes and creating appropriate handler. Possible handlers :

-   URL
-   definition
-   direct String

Handlers also contain sub-component context.

**Specified by:**  
`doStartTag` in interface `Tag`

**Overrides:**  
`doStartTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### doEndTag

    public int doEndTag()
                 throws JspException

Process the end tag by including the template. Simply call the handler doEndTag

**Specified by:**  
`doEndTag` in interface `Tag`

**Overrides:**  
`doEndTag` in class `TagSupport`

<!-- -->

**Throws:**  
`JspException`

------------------------------------------------------------------------

### createTagHandler

    public InsertTag.TagHandler createTagHandler()
                                          throws JspException

Process tag attribute and create corresponding tag handler.

**Throws:**  
`JspException`

------------------------------------------------------------------------

### processObjectValue

    public InsertTag.TagHandler processObjectValue(Object value)
                                            throws JspException

Process an object retrieved as a bean or attribute. Object can be a typed attribute, a String, or anything else. If typed attribute, use associated type. Otherwise, apply toString() on object, and use returned string as a name.

**Throws:**  
`JspException` - - Throws by underlying nested call to processDefinitionName()

------------------------------------------------------------------------

### processName

    public InsertTag.TagHandler processName(String name)
                                     throws JspException

Process name. Search in following order :

-   Component context - if found, process it as value.
-   definitions factory
-   URL

**Returns:**  
appropriate tag handler.

**Throws:**  
`JspException` - - Throws by underlying nested call to processDefinitionName()

------------------------------------------------------------------------

### processUrl

    public InsertTag.TagHandler processUrl(String url)
                                    throws JspException

Process the url.

**Throws:**  
`JspException` - If failed to create controller

------------------------------------------------------------------------

### processDefinitionName

    protected InsertTag.TagHandler processDefinitionName(String name)
                                                  throws JspException

Process tag attribute "definition". First, search definition in the factory, then create handler from this definition.

**Parameters:**  
`name` - Name of the definition.

**Returns:**  
Appropriate TagHandler.

**Throws:**  
`JspException-` - NoSuchDefinitionException No Definition found for name.

`JspException-` - FactoryNotFoundException Can't find Definitions factory.

`JspException-` - DefinedComponentFactoryException General error in factory.

`JspException` - InstantiationException Can't create requested controller

------------------------------------------------------------------------

### processDefinition

    protected InsertTag.TagHandler processDefinition(ComponentDefinition definition)
                                              throws JspException

End of Process tag attribute "definition". Overload definition with tag attributes "template" and "role". Then, create appropriate tag handler.

**Parameters:**  
`definition` - Definition to process.

**Returns:**  
Appropriate TagHandler.

**Throws:**  
`JspException` - InstantiationException Can't create requested controller

------------------------------------------------------------------------

### processBean

    protected InsertTag.TagHandler processBean(String beanName,
                                               String beanProperty,
                                               String beanScope)
                                        throws JspException

Process a bean. Get bean value, eventually using property and scope. Found value is process by processObjectValue().

**Parameters:**  
`beanName` - Name of the bean

`beanProperty` - Property in the bean, or null.

`beanScope` - bean scope, or null.

**Returns:**  
Appropriate TagHandler.

**Throws:**  
`JspException` - - NoSuchDefinitionException No value associated to bean.

`JspException` - an error occur while reading bean, or no definition found.

`JspException` - - Throws by underlying nested call to processDefinitionName()

------------------------------------------------------------------------

### processAttribute

    public InsertTag.TagHandler processAttribute(String name)
                                          throws JspException

Process tag attribute "attribute". Get value from component attribute. Found value is process by processObjectValue().

**Parameters:**  
`name` - Name of the attribute.

**Returns:**  
Appropriate TagHandler.

**Throws:**  
`JspException` - - NoSuchDefinitionException No Definition found for name.

`JspException` - - Throws by underlying nested call to processDefinitionName()

------------------------------------------------------------------------

### processAsDefinitionOrURL

    public InsertTag.TagHandler processAsDefinitionOrURL(String name)
                                                  throws JspException

Try to process name as a definition, or as an URL if not found.

**Parameters:**  
`name` - Name to process.

**Returns:**  
appropriate TagHandler

**Throws:**  
`JspException` - InstantiationException Can't create requested controller

------------------------------------------------------------------------

### processTypedAttribute

    public InsertTag.TagHandler processTypedAttribute(AttributeDefinition value)
                                               throws JspException

Process typed attribute according to its type.

**Parameters:**  
`value` - Typed attribute to process.

**Returns:**  
appropriate TagHandler.

**Throws:**  
`JspException` - - Throws by underlying nested call to processDefinitionName()

------------------------------------------------------------------------

### doInclude

    protected void doInclude(String page,
                             boolean flush)
                      throws ServletException,
                             IOException

Do an include of specified page. This method is used internally to do all includes from this class. It delegates the include call to the TilesUtil.doInclude().

**Parameters:**  
`page` - The page that will be included

`flush` - If the writer should be flushed before the include

**Throws:**  
`ServletException` - - Thrown by call to pageContext.include()

`IOException` - - Thrown by call to pageContext.include()

------------------------------------------------------------------------

### userHasRole

    public static boolean userHasRole(HttpServletRequest request,
                                      String role)

Parse the list of roles and return `true` or `false` based on whether the user has that role or not.

**Parameters:**  
`role` - Comma-delimited list of roles.

`request` - The request.

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
<td align="left"><a href="class-use/InsertTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/InitDefinitionsTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/InsertTag.DirectStringHandler.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/InsertTag.html"><strong>FRAMES</strong></a>    <a href="InsertTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
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
