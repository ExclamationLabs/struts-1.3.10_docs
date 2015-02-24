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
<td align="left"><a href="class-use/GetTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/GetAttributeTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/ImportAttributeTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/GetTag.html"><strong>FRAMES</strong></a>    <a href="GetTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_classes_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag">NESTED</a> | <a href="#fields_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.tiles.taglib
 Class GetTag
------------------------------

    java.lang.Object
      javax.servlet.jsp.tagext.TagSupport
          org.apache.struts.tiles.taglib.DefinitionTagSupport
              org.apache.struts.tiles.taglib.InsertTag
                  org.apache.struts.tiles.taglib.GetTag

**All Implemented Interfaces:**  
[Serializable](http://java.sun.com/j2se/1.4.2/docs/api/java/io/Serializable.html.md?is-external=true "class or interface in java.io"), [IterationTag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/IterationTag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [Tag](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/jsp/tagext/Tag.html?is-external=true "class or interface in javax.servlet.jsp.tagext"), [ComponentConstants](../../../../../org/apache/struts/tiles/taglib/ComponentConstants.html "interface in org.apache.struts.tiles.taglib"), [PutListTagParent](../../../../../org/apache/struts/tiles/taglib/PutListTagParent.html "interface in org.apache.struts.tiles.taglib"), [PutTagParent](../../../../../org/apache/struts/tiles/taglib/PutTagParent.html "interface in org.apache.struts.tiles.taglib")

<!-- -->

**Direct Known Subclasses:**  
[ELGetTag](../../../../../org/apache/strutsel/taglib/tiles/ELGetTag.html.md "class in org.apache.strutsel.taglib.tiles")

------------------------------------------------------------------------

    public class GetTag

extends [InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib")

This is the tag handler for \<tiles:get\>, which gets content from the request scope and either includes the content or prints it, depending upon the value of the content's `direct` attribute. This tag is intended to be compatible with the same tag from Templates (David Geary). Implementation extends InsertTag for facility (no so well). The only difference is the default value of attribute 'ignore', which is `true` for this tag (default behavior of David Geary's templates).

**See Also:**  
[Serialized Form](../../../../../serialized-form.html.md#org.apache.struts.tiles.taglib.GetTag)

------------------------------------------------------------------------

<span id="nested_class_summary"></span>

**Nested Class Summary**

 <span id="nested_classes_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag"></span>

| **Nested classes/interfaces inherited from class org.apache.struts.tiles.taglib.[InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib")** |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `InsertTag.DirectStringHandler, InsertTag.InsertHandler, InsertTag.TagHandler`                                                                                                                        |

  <span id="field_summary"></span>

**Field Summary**

 <span id="fields_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag"></span>

| **Fields inherited from class org.apache.struts.tiles.taglib.[InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib")**          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` attribute,  beanName,  beanProperty,  beanScope,  cachedCurrentContext,  definitionName,  flush,  isErrorIgnored, log,  name,  pageContext,  processEndTag,  ROLE_DELIMITER,  tagHandler` |

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
| ` GetTag()`             
            Constructor.  |

  <span id="method_summary"></span>

**Method Summary**

` void`

` release()`
           Release all allocated resources.

 <span id="methods_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag"></span>

| **Methods inherited from class org.apache.struts.tiles.taglib.[InsertTag](../../../../../org/apache/struts/tiles/taglib/InsertTag.html.md "class in org.apache.struts.tiles.taglib")**                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` createTagHandler,  doEndTag,  doInclude,  doStartTag,  getBeanName,  getBeanProperty,  getBeanScope,  getDefinitionName,  getFlush,  getIgnore,  getName,  getPageContext,  processAsDefinitionOrURL,  processAttribute,  processBean,  processDefinition,  processDefinitionName,  processName,  processNestedTag,  processNestedTag,  processObjectValue,  processTypedAttribute,  processUrl,  putAttribute,  putAttribute,  releaseInternal,  setAttribute,  setBeanName,  setBeanProperty,  setBeanScope,  setComponent,  setDefinition,  setFlush,  setFlush,  setIgnore,  setName,  setPageContext,  userHasRole` |

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

 

<span id="constructor_detail"></span>

**Constructor Detail**

### GetTag

    public GetTag()

Constructor. Set default value for 'isErrorIgnored' to `true`.

<span id="method_detail"></span>

**Method Detail**

### release

    public void release()

Release all allocated resources.

**Specified by:**  
`release` in interface `Tag`

**Overrides:**  
` release` in class `InsertTag`

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
<td align="left"><a href="class-use/GetTag.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/tiles/taglib/GetAttributeTag.html.md" title="class in org.apache.struts.tiles.taglib"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/tiles/taglib/ImportAttributeTag.html" title="class in org.apache.struts.tiles.taglib"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/tiles/taglib/GetTag.html"><strong>FRAMES</strong></a>    <a href="GetTag.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: <a href="#nested_classes_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag">NESTED</a> | <a href="#fields_inherited_from_class_org.apache.struts.tiles.taglib.InsertTag">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: FIELD | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
