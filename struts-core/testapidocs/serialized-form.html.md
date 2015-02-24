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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

Serialized Form
===============

------------------------------------------------------------------------

**Package** **org.apache.struts.action**

<span id="org.apache.struts.action.ActionErrors"></span>

**Class [org.apache.struts.action.ActionErrors](../apidocs/org/apache/struts/action/ActionErrors.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionMessages](../apidocs/org/apache/struts/action/ActionMessages.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.ActionForm"></span>

**Class [org.apache.struts.action.ActionForm](../apidocs/org/apache/struts/action/ActionForm.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.action.ActionFormBean"></span>

**Class [org.apache.struts.action.ActionFormBean](../apidocs/org/apache/struts/action/ActionFormBean.html.md?is-external=true "class or interface in org.apache.struts.action") extends [FormBeanConfig](../apidocs/org/apache/struts/config/FormBeanConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.action.ActionForward"></span>

**Class [org.apache.struts.action.ActionForward](../apidocs/org/apache/struts/action/ActionForward.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ForwardConfig](../apidocs/org/apache/struts/config/ForwardConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.action.ActionMapping"></span>

**Class [org.apache.struts.action.ActionMapping](../apidocs/org/apache/struts/action/ActionMapping.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionConfig](../apidocs/org/apache/struts/config/ActionConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="org.apache.struts.action.ActionMessage"></span>

**Class [org.apache.struts.action.ActionMessage](../apidocs/org/apache/struts/action/ActionMessage.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### key

    String key

------------------------------------------------------------------------

### values

    Object[] values

------------------------------------------------------------------------

### resource

    boolean resource

<span id="org.apache.struts.action.ActionMessages"></span>

**Class [org.apache.struts.action.ActionMessages](../apidocs/org/apache/struts/action/ActionMessages.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### accessed

    boolean accessed

------------------------------------------------------------------------

### messages

    HashMap<K,V> messages

------------------------------------------------------------------------

### iCount

    int iCount

<span id="org.apache.struts.action.ActionMessages.ActionMessageItem"></span>

**Class [org.apache.struts.action.ActionMessages.ActionMessageItem](../apidocs/org/apache/struts/action/ActionMessages.ActionMessageItem.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### list

    List<E> list

------------------------------------------------------------------------

### iOrder

    int iOrder

------------------------------------------------------------------------

### property

    String property

<span id="org.apache.struts.action.ActionRedirect"></span>

**Class [org.apache.struts.action.ActionRedirect](../apidocs/org/apache/struts/action/ActionRedirect.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionForward](../apidocs/org/apache/struts/action/ActionForward.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### parameterValues

    Map<K,V> parameterValues

------------------------------------------------------------------------

### anchorValue

    String anchorValue

<span id="org.apache.struts.action.ActionServlet"></span>

**Class [org.apache.struts.action.ActionServlet](../apidocs/org/apache/struts/action/ActionServlet.html.md?is-external=true "class or interface in org.apache.struts.action") extends [HttpServlet](http://java.sun.com/j2ee/1.4/docs/api/javax/servlet/http/HttpServlet.html?is-external=true "class or interface in javax.servlet.http") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    String config

------------------------------------------------------------------------

### chainConfig

    String chainConfig

------------------------------------------------------------------------

### configDigester

    org.apache.commons.digester.Digester configDigester

------------------------------------------------------------------------

### convertNull

    boolean convertNull

------------------------------------------------------------------------

### internal

    MessageResources internal

------------------------------------------------------------------------

### internalName

    String internalName

------------------------------------------------------------------------

### registrations

    String[] registrations

------------------------------------------------------------------------

### servletMapping

    String servletMapping

------------------------------------------------------------------------

### servletName

    String servletName

<span id="org.apache.struts.action.ActionServletWrapper"></span>

**Class [org.apache.struts.action.ActionServletWrapper](../apidocs/org/apache/struts/action/ActionServletWrapper.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.action.DynaActionForm"></span>

**Class [org.apache.struts.action.DynaActionForm](../apidocs/org/apache/struts/action/DynaActionForm.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionForm](../apidocs/org/apache/struts/action/ActionForm.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### dynaClass

    DynaActionFormClass dynaClass

------------------------------------------------------------------------

### dynaValues

    HashMap<K,V> dynaValues

<span id="org.apache.struts.action.DynaActionFormClass"></span>

**Class [org.apache.struts.action.DynaActionFormClass](../apidocs/org/apache/struts/action/DynaActionFormClass.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    FormBeanConfig config

------------------------------------------------------------------------

### name

    String name

------------------------------------------------------------------------

### properties

    DynaProperty[] properties

------------------------------------------------------------------------

### propertiesMap

    HashMap<K,V> propertiesMap

<span id="org.apache.struts.action.ForwardingActionForward"></span>

**Class [org.apache.struts.action.ForwardingActionForward](../apidocs/org/apache/struts/action/ForwardingActionForward.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionForward](../apidocs/org/apache/struts/action/ActionForward.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.InvalidCancelException"></span>

**Class [org.apache.struts.action.InvalidCancelException](../apidocs/org/apache/struts/action/InvalidCancelException.html.md?is-external=true "class or interface in org.apache.struts.action") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.action.RedirectingActionForward"></span>

**Class [org.apache.struts.action.RedirectingActionForward](../apidocs/org/apache/struts/action/RedirectingActionForward.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionForward](../apidocs/org/apache/struts/action/ActionForward.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.RequestActionMapping"></span>

**Class [org.apache.struts.action.RequestActionMapping](../apidocs/org/apache/struts/action/RequestActionMapping.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionMapping](../apidocs/org/apache/struts/action/ActionMapping.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.SessionActionMapping"></span>

**Class [org.apache.struts.action.SessionActionMapping](../apidocs/org/apache/struts/action/SessionActionMapping.html.md?is-external=true "class or interface in org.apache.struts.action") extends [ActionMapping](../apidocs/org/apache/struts/action/ActionMapping.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="org.apache.struts.action.TestActionServlet.CustomActionConfig"></span>

**Class [org.apache.struts.action.TestActionServlet.CustomActionConfig](org/apache/struts/action/TestActionServlet.CustomActionConfig.html.md "class in org.apache.struts.action") extends [ActionConfig](../apidocs/org/apache/struts/config/ActionConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### processExtendsCalled

    boolean processExtendsCalled

<span id="org.apache.struts.action.TestActionServlet.CustomExceptionConfig"></span>

**Class [org.apache.struts.action.TestActionServlet.CustomExceptionConfig](org/apache/struts/action/TestActionServlet.CustomExceptionConfig.html.md "class in org.apache.struts.action") extends [ExceptionConfig](../apidocs/org/apache/struts/config/ExceptionConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### processExtendsCalled

    boolean processExtendsCalled

<span id="org.apache.struts.action.TestActionServlet.CustomFormBeanConfig"></span>

**Class [org.apache.struts.action.TestActionServlet.CustomFormBeanConfig](org/apache/struts/action/TestActionServlet.CustomFormBeanConfig.html.md "class in org.apache.struts.action") extends [FormBeanConfig](../apidocs/org/apache/struts/config/FormBeanConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### processExtendsCalled

    boolean processExtendsCalled

<span id="org.apache.struts.action.TestActionServlet.CustomForwardConfig"></span>

**Class [org.apache.struts.action.TestActionServlet.CustomForwardConfig](org/apache/struts/action/TestActionServlet.CustomForwardConfig.html.md "class in org.apache.struts.action") extends [ForwardConfig](../apidocs/org/apache/struts/config/ForwardConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### processExtendsCalled

    boolean processExtendsCalled

------------------------------------------------------------------------

**Package** **org.apache.struts.config**

<span id="org.apache.struts.config.ActionConfig"></span>

**Class [org.apache.struts.config.ActionConfig](../apidocs/org/apache/struts/config/ActionConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### exceptions

    HashMap<K,V> exceptions

------------------------------------------------------------------------

### forwards

    HashMap<K,V> forwards

------------------------------------------------------------------------

### moduleConfig

    ModuleConfig moduleConfig

------------------------------------------------------------------------

### attribute

    String attribute

------------------------------------------------------------------------

### actionId

    String actionId

------------------------------------------------------------------------

### inherit

    String inherit

------------------------------------------------------------------------

### cancellableSet

    boolean cancellableSet

------------------------------------------------------------------------

### cancellable

    boolean cancellable

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

------------------------------------------------------------------------

### forward

    String forward

------------------------------------------------------------------------

### include

    String include

------------------------------------------------------------------------

### input

    String input

------------------------------------------------------------------------

### multipartClass

    String multipartClass

------------------------------------------------------------------------

### name

    String name

------------------------------------------------------------------------

### parameter

    String parameter

------------------------------------------------------------------------

### path

    String path

------------------------------------------------------------------------

### prefix

    String prefix

------------------------------------------------------------------------

### roles

    String roles

------------------------------------------------------------------------

### roleNames

    String[] roleNames

------------------------------------------------------------------------

### scope

    String scope

------------------------------------------------------------------------

### suffix

    String suffix

------------------------------------------------------------------------

### type

    String type

------------------------------------------------------------------------

### unknown

    boolean unknown

------------------------------------------------------------------------

### validateSet

    boolean validateSet

------------------------------------------------------------------------

### validate

    boolean validate

------------------------------------------------------------------------

### command

    String command

------------------------------------------------------------------------

### catalog

    String catalog

<span id="org.apache.struts.config.ActionConfigMatcher"></span>

**Class [org.apache.struts.config.ActionConfigMatcher](../apidocs/org/apache/struts/config/ActionConfigMatcher.html.md?is-external=true "class or interface in org.apache.struts.config") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### compiledPaths

    List<E> compiledPaths

<span id="org.apache.struts.config.BaseConfig"></span>

**Class [org.apache.struts.config.BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### configured

    boolean configured

------------------------------------------------------------------------

### properties

    Properties properties

<span id="org.apache.struts.config.ControllerConfig"></span>

**Class [org.apache.struts.config.ControllerConfig](../apidocs/org/apache/struts/config/ControllerConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bufferSize

    int bufferSize

------------------------------------------------------------------------

### contentType

    String contentType

------------------------------------------------------------------------

### catalog

    String catalog

------------------------------------------------------------------------

### command

    String command

------------------------------------------------------------------------

### forwardPattern

    String forwardPattern

------------------------------------------------------------------------

### inputForward

    boolean inputForward

------------------------------------------------------------------------

### locale

    boolean locale

------------------------------------------------------------------------

### maxFileSize

    String maxFileSize

------------------------------------------------------------------------

### memFileSize

    String memFileSize

------------------------------------------------------------------------

### multipartClass

    String multipartClass

------------------------------------------------------------------------

### nocache

    boolean nocache

------------------------------------------------------------------------

### pagePattern

    String pagePattern

------------------------------------------------------------------------

### processorClass

    String processorClass

------------------------------------------------------------------------

### tempDir

    String tempDir

<span id="org.apache.struts.config.CustomMappingTest"></span>

**Class [org.apache.struts.config.CustomMappingTest](org/apache/struts/config/CustomMappingTest.html.md "class in org.apache.struts.config") extends [ActionMapping](../apidocs/org/apache/struts/action/ActionMapping.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### pub

    boolean pub

<span id="org.apache.struts.config.ExceptionConfig"></span>

**Class [org.apache.struts.config.ExceptionConfig](../apidocs/org/apache/struts/config/ExceptionConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### bundle

    String bundle

------------------------------------------------------------------------

### inherit

    String inherit

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

------------------------------------------------------------------------

### handler

    String handler

------------------------------------------------------------------------

### key

    String key

------------------------------------------------------------------------

### path

    String path

------------------------------------------------------------------------

### scope

    String scope

------------------------------------------------------------------------

### type

    String type

<span id="org.apache.struts.config.FormBeanConfig"></span>

**Class [org.apache.struts.config.FormBeanConfig](../apidocs/org/apache/struts/config/FormBeanConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### formProperties

    HashMap<K,V> formProperties

------------------------------------------------------------------------

### lock

    String lock

------------------------------------------------------------------------

### dynamic

    boolean dynamic

------------------------------------------------------------------------

### inherit

    String inherit

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

------------------------------------------------------------------------

### name

    String name

------------------------------------------------------------------------

### type

    String type

------------------------------------------------------------------------

### restricted

    boolean restricted

<span id="org.apache.struts.config.FormPropertyConfig"></span>

**Class [org.apache.struts.config.FormPropertyConfig](../apidocs/org/apache/struts/config/FormPropertyConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### initial

    String initial

------------------------------------------------------------------------

### name

    String name

------------------------------------------------------------------------

### reset

    String reset

------------------------------------------------------------------------

### size

    int size

------------------------------------------------------------------------

### type

    String type

<span id="org.apache.struts.config.ForwardConfig"></span>

**Class [org.apache.struts.config.ForwardConfig](../apidocs/org/apache/struts/config/ForwardConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### inherit

    String inherit

------------------------------------------------------------------------

### extensionProcessed

    boolean extensionProcessed

------------------------------------------------------------------------

### name

    String name

------------------------------------------------------------------------

### path

    String path

------------------------------------------------------------------------

### module

    String module

------------------------------------------------------------------------

### redirect

    boolean redirect

------------------------------------------------------------------------

### command

    String command

------------------------------------------------------------------------

### catalog

    String catalog

<span id="org.apache.struts.config.MessageResourcesConfig"></span>

**Class [org.apache.struts.config.MessageResourcesConfig](../apidocs/org/apache/struts/config/MessageResourcesConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [BaseConfig](../apidocs/org/apache/struts/config/BaseConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### factory

    String factory

------------------------------------------------------------------------

### key

    String key

------------------------------------------------------------------------

### nullValue

    boolean nullValue

------------------------------------------------------------------------

### escape

    boolean escape

------------------------------------------------------------------------

### parameter

    String parameter

<span id="org.apache.struts.config.PlugInConfig"></span>

**Class [org.apache.struts.config.PlugInConfig](../apidocs/org/apache/struts/config/PlugInConfig.html.md?is-external=true "class or interface in org.apache.struts.config") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### configured

    boolean configured

------------------------------------------------------------------------

### properties

    Map<K,V> properties

------------------------------------------------------------------------

### className

    String className

<span id="org.apache.struts.config.TestActionConfig.CustomActionConfig"></span>

**Class [org.apache.struts.config.TestActionConfig.CustomActionConfig](org/apache/struts/config/TestActionConfig.CustomActionConfig.html.md "class in org.apache.struts.config") extends [ActionConfig](../apidocs/org/apache/struts/config/ActionConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### processExtendsCalled

    boolean processExtendsCalled

<span id="org.apache.struts.config.TestFormBeanConfig.CustomFormBeanConfig"></span>

**Class [org.apache.struts.config.TestFormBeanConfig.CustomFormBeanConfig](org/apache/struts/config/TestFormBeanConfig.CustomFormBeanConfig.html.md "class in org.apache.struts.config") extends [FormBeanConfig](../apidocs/org/apache/struts/config/FormBeanConfig.html?is-external=true "class or interface in org.apache.struts.config") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### processExtendsCalled

    boolean processExtendsCalled

------------------------------------------------------------------------

**Package** **org.apache.struts.util**

<span id="org.apache.struts.util.ImageButtonBean"></span>

**Class [org.apache.struts.util.ImageButtonBean](../apidocs/org/apache/struts/util/ImageButtonBean.html.md?is-external=true "class or interface in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### x

    String x

------------------------------------------------------------------------

### y

    String y

<span id="org.apache.struts.util.LabelValueBean"></span>

**Class [org.apache.struts.util.LabelValueBean](../apidocs/org/apache/struts/util/LabelValueBean.html.md?is-external=true "class or interface in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### label

    String label

------------------------------------------------------------------------

### value

    String value

<span id="org.apache.struts.util.MessageResources"></span>

**Class [org.apache.struts.util.MessageResources](../apidocs/org/apache/struts/util/MessageResources.html.md?is-external=true "class or interface in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    String config

------------------------------------------------------------------------

### defaultLocale

    Locale defaultLocale

------------------------------------------------------------------------

### factory

    MessageResourcesFactory factory

------------------------------------------------------------------------

### formats

    HashMap<K,V> formats

------------------------------------------------------------------------

### returnNull

    boolean returnNull

------------------------------------------------------------------------

### escape

    boolean escape

<span id="org.apache.struts.util.MessageResourcesFactory"></span>

**Class [org.apache.struts.util.MessageResourcesFactory](../apidocs/org/apache/struts/util/MessageResourcesFactory.html.md?is-external=true "class or interface in org.apache.struts.util") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### config

    MessageResourcesConfig config

------------------------------------------------------------------------

### returnNull

    boolean returnNull

<span id="org.apache.struts.util.ModuleException"></span>

**Class [org.apache.struts.util.ModuleException](../apidocs/org/apache/struts/util/ModuleException.html.md?is-external=true "class or interface in org.apache.struts.util") extends [Exception](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Exception.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### property

    String property

------------------------------------------------------------------------

### message

    ActionMessage message

<span id="org.apache.struts.util.PropertyMessageResources"></span>

**Class [org.apache.struts.util.PropertyMessageResources](../apidocs/org/apache/struts/util/PropertyMessageResources.html.md?is-external=true "class or interface in org.apache.struts.util") extends [MessageResources](../apidocs/org/apache/struts/util/MessageResources.html?is-external=true "class or interface in org.apache.struts.util") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### locales

    HashMap<K,V> locales

------------------------------------------------------------------------

### messages

    HashMap<K,V> messages

------------------------------------------------------------------------

### mode

    int mode

<span id="org.apache.struts.util.PropertyMessageResourcesFactory"></span>

**Class [org.apache.struts.util.PropertyMessageResourcesFactory](../apidocs/org/apache/struts/util/PropertyMessageResourcesFactory.html.md?is-external=true "class or interface in org.apache.struts.util") extends [MessageResourcesFactory](../apidocs/org/apache/struts/util/MessageResourcesFactory.html?is-external=true "class or interface in org.apache.struts.util") implements Serializable**

------------------------------------------------------------------------

**Package** **org.apache.struts.validator**

<span id="org.apache.struts.validator.BeanValidatorForm"></span>

**Class [org.apache.struts.validator.BeanValidatorForm](../apidocs/org/apache/struts/validator/BeanValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator") extends [ValidatorForm](../apidocs/org/apache/struts/validator/ValidatorForm.html?is-external=true "class or interface in org.apache.struts.validator") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### dynaBean

    DynaBean dynaBean

------------------------------------------------------------------------

### pathValidation

    boolean pathValidation

------------------------------------------------------------------------

### strutsConfigFormName

    String strutsConfigFormName

<span id="org.apache.struts.validator.DynaValidatorForm"></span>

**Class [org.apache.struts.validator.DynaValidatorForm](../apidocs/org/apache/struts/validator/DynaValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator") extends [DynaActionForm](../apidocs/org/apache/struts/action/DynaActionForm.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### validatorResults

    ValidatorResults validatorResults

------------------------------------------------------------------------

### page

    int page

<span id="org.apache.struts.validator.FieldChecks"></span>

**Class [org.apache.struts.validator.FieldChecks](../apidocs/org/apache/struts/validator/FieldChecks.html.md?is-external=true "class or interface in org.apache.struts.validator") extends [Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html?is-external=true "class or interface in java.lang") implements Serializable**

<span id="org.apache.struts.validator.LazyValidatorForm"></span>

**Class [org.apache.struts.validator.LazyValidatorForm](../apidocs/org/apache/struts/validator/LazyValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator") extends [BeanValidatorForm](../apidocs/org/apache/struts/validator/BeanValidatorForm.html?is-external=true "class or interface in org.apache.struts.validator") implements Serializable**

<span id="org.apache.struts.validator.ValidatorForm"></span>

**Class [org.apache.struts.validator.ValidatorForm](../apidocs/org/apache/struts/validator/ValidatorForm.html.md?is-external=true "class or interface in org.apache.struts.validator") extends [ActionForm](../apidocs/org/apache/struts/action/ActionForm.html?is-external=true "class or interface in org.apache.struts.action") implements Serializable**

<span id="serializedForm"></span>

**Serialized Fields**

### validatorResults

    ValidatorResults validatorResults

------------------------------------------------------------------------

### page

    int page

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
<td align="left"><a href="overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?serialized-form.html"><strong>FRAMES</strong></a>    <a href="serialized-form.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
