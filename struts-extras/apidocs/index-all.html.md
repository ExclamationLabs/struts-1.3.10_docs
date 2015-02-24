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
<td align="left"><a href="./overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="./overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="./deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"> <strong>Index</strong> </td>
<td align="left"><a href="./help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="./index.html.md?index-all.html"><strong>FRAMES</strong></a>    <a href="index-all.html"><strong>NO FRAMES</strong></a>    
<a href="./allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span> [A](#_A_) [B](#_B_) [C](#_C_) [D](#_D_) [E](#_E_) [F](#_F_) [G](#_G_) [I](#_I_) [K](#_K_) [L](#_L_) [M](#_M_) [N](#_N_) [O](#_O_) [P](#_P_) [R](#_R_) [S](#_S_) [T](#_T_) [U](#_U_) [V](#_V_)

------------------------------------------------------------------------

**A**
-----

[**ActionDispatcher**](./org/apache/struts/actions/ActionDispatcher.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
Action *helper* class that dispatches to a public method in an Action.

[**ActionDispatcher(Action)**](./org/apache/struts/actions/ActionDispatcher.html.md#ActionDispatcher(org.apache.struts.action.Action)) - Constructor for class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Construct an instance of this class from the supplied parameters.

[**ActionDispatcher(Action, int)**](./org/apache/struts/actions/ActionDispatcher.html.md#ActionDispatcher(org.apache.struts.action.Action,%20int)) - Constructor for class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Construct an instance of this class from the supplied parameters.

[**actionInstance**](./org/apache/struts/actions/ActionDispatcher.html.md#actionInstance) - Variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
The associated Action to dispatch to.

[**applyRuleSets(Digester)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#applyRuleSets(org.apache.commons.digester.Digester)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Instantiate any `RuleSet` classes defined in the `rulesets` property and use them to add rules to our `Digester`.

------------------------------------------------------------------------

**B**
-----

[**BaseAction**](./org/apache/struts/actions/BaseAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
BaseAction is provided as an intermediate class for shared funtionality between `Action` and any stock implementation provided in this package.

[**BaseAction()**](./org/apache/struts/actions/BaseAction.html.md#BaseAction()) - Constructor for class org.apache.struts.actions.[BaseAction](./org/apache/struts/actions/BaseAction.html "class in org.apache.struts.actions")  
 

------------------------------------------------------------------------

**C**
-----

[**cancelled(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/ActionDispatcher.html.md#cancelled(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Dispatches to the target class' cancelled method, if present, otherwise returns null.

[**cancelled(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/DispatchAction.html.md#cancelled(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Method which is dispatched to when the request is a cancel button submit.

[**clazz**](./org/apache/struts/actions/ActionDispatcher.html.md#clazz) - Variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
The Class instance of this `DispatchAction` class.

[**clazz**](./org/apache/struts/actions/DispatchAction.html.md#clazz) - Variable in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
The Class instance of this `DispatchAction` class.

[**config**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#config) - Variable in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
The [`ModuleConfig`](http://struts.apache.org/apidocs/org/apache/struts/config/ModuleConfig.html.md?is-external=true "class or interface in org.apache.struts.config") instance for our module.

[**configPath**](./org/apache/struts/plugins/DigestingPlugIn.html.md#configPath) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**configSource**](./org/apache/struts/plugins/DigestingPlugIn.html.md#configSource) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**copy(InputStream, OutputStream)**](./org/apache/struts/actions/DownloadAction.html.md#copy(java.io.InputStream,%20java.io.OutputStream)) - Method in class org.apache.struts.actions.[DownloadAction](./org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions")  
Copy bytes from an `InputStream` to an `OutputStream`.

------------------------------------------------------------------------

**D**
-----

[**DEFAULT\_BUFFER\_SIZE**](./org/apache/struts/actions/DownloadAction.html.md#DEFAULT_BUFFER_SIZE) - Static variable in class org.apache.struts.actions.[DownloadAction](./org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions")  
If the `getBufferSize()` method is not overridden, this is the buffer size that will be used to transfer the data to the servlet output stream.

[**DEFAULT\_FLAVOR**](./org/apache/struts/actions/ActionDispatcher.html.md#DEFAULT_FLAVOR) - Static variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Indicates "default" dispatch flavor.

[**destroy()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#destroy()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Receive notification that our owning module is being shut down.

[**destroy()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#destroy()) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Receive notification that our owning module is being shut down.

[**digesterFromXml(String, String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#digesterFromXml(java.lang.String,%20java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Instantiate a Digester from an XML input stream using the Commons `DigesterLoader`.

[**digesterPath**](./org/apache/struts/plugins/DigestingPlugIn.html.md#digesterPath) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**digesterSource**](./org/apache/struts/plugins/DigestingPlugIn.html.md#digesterSource) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**DigestingPlugIn**](./org/apache/struts/plugins/DigestingPlugIn.html.md "class in org.apache.struts.plugins") - Class in [org.apache.struts.plugins](./org/apache/struts/plugins/package-summary.html)  
An implementation of `PlugIn` which can be configured to instantiate a graph of objects using the Commons Digester and place the root object of that graph into the Application context.

[**DigestingPlugIn()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#DigestingPlugIn()) - Constructor for class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Constructor for DigestingPlugIn.

[**DISPATCH\_FLAVOR**](./org/apache/struts/actions/ActionDispatcher.html.md#DISPATCH_FLAVOR) - Static variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Indicates flavor compatible with DispatchAction.

[**DispatchAction**](./org/apache/struts/actions/DispatchAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An abstract **Action** that dispatches to a public method that is named by the request parameter whose name is specified by the `parameter` property of the corresponding ActionMapping.

[**DispatchAction()**](./org/apache/struts/actions/DispatchAction.html.md#DispatchAction()) - Constructor for class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
 

[**dispatchMethod(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/ActionDispatcher.html.md#dispatchMethod(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Dispatch to the specified method.

[**dispatchMethod(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String, Method)**](./org/apache/struts/actions/ActionDispatcher.html.md#dispatchMethod(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String,%20java.lang.reflect.Method)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Dispatch to the specified method.

[**dispatchMethod(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/DispatchAction.html.md#dispatchMethod(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Dispatch to the specified method.

[**DownloadAction**](./org/apache/struts/actions/DownloadAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
This is an abstract base class that minimizes the amount of special coding that needs to be written to download a file.

[**DownloadAction()**](./org/apache/struts/actions/DownloadAction.html.md#DownloadAction()) - Constructor for class org.apache.struts.actions.[DownloadAction](./org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions")  
 

[**DownloadAction.FileStreamInfo**](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a file from the disk.

[**DownloadAction.FileStreamInfo(String, File)**](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md#DownloadAction.FileStreamInfo(java.lang.String,%20java.io.File)) - Constructor for class org.apache.struts.actions.[DownloadAction.FileStreamInfo](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html "class in org.apache.struts.actions")  
Constructs an instance of this class, based on the supplied parameters.

[**DownloadAction.ResourceStreamInfo**](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
A concrete implementation of the `StreamInfo` interface which simplifies the downloading of a web application resource.

[**DownloadAction.ResourceStreamInfo(String, ServletContext, String)**](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html.md#DownloadAction.ResourceStreamInfo(java.lang.String,%20javax.servlet.ServletContext,%20java.lang.String)) - Constructor for class org.apache.struts.actions.[DownloadAction.ResourceStreamInfo](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html "class in org.apache.struts.actions")  
Constructs an instance of this class, based on the supplied parameters.

[**DownloadAction.StreamInfo**](./org/apache/struts/actions/DownloadAction.StreamInfo.html.md "interface in org.apache.struts.actions") - Interface in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
The information on a file, or other stream, to be downloaded by the `DownloadAction`.

[**DynaValidatorActionForm**](./org/apache/struts/validator/DynaValidatorActionForm.html.md "class in org.apache.struts.validator") - Class in [org.apache.struts.validator](./org/apache/struts/validator/package-summary.html)  
This class extends **DynaValidatorForm** and provides basic field validation based on an XML file.

[**DynaValidatorActionForm()**](./org/apache/struts/validator/DynaValidatorActionForm.html.md#DynaValidatorActionForm()) - Constructor for class org.apache.struts.validator.[DynaValidatorActionForm](./org/apache/struts/validator/DynaValidatorActionForm.html "class in org.apache.struts.validator")  
 

------------------------------------------------------------------------

**E**
-----

[**EventActionDispatcher**](./org/apache/struts/actions/EventActionDispatcher.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An Action helper class that dispatches to to one of the public methods that are named in the `parameter` attribute of the corresponding ActionMapping and matches a submission parameter.

[**EventActionDispatcher(Action)**](./org/apache/struts/actions/EventActionDispatcher.html.md#EventActionDispatcher(org.apache.struts.action.Action)) - Constructor for class org.apache.struts.actions.[EventActionDispatcher](./org/apache/struts/actions/EventActionDispatcher.html "class in org.apache.struts.actions")  
Constructs a new object for the specified action.

[**EventDispatchAction**](./org/apache/struts/actions/EventDispatchAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An **Action** that dispatches to to one of the public methods that are named in the `parameter` attribute of the corresponding ActionMapping and matches a submission parameter.

[**EventDispatchAction()**](./org/apache/struts/actions/EventDispatchAction.html.md#EventDispatchAction()) - Constructor for class org.apache.struts.actions.[EventDispatchAction](./org/apache/struts/actions/EventDispatchAction.html "class in org.apache.struts.actions")  
 

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/ActionDispatcher.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/DispatchAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/DownloadAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[DownloadAction](./org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/ForwardAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[ForwardAction](./org/apache/struts/actions/ForwardAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/IncludeAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[IncludeAction](./org/apache/struts/actions/IncludeAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/LocaleAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[LocaleAction](./org/apache/struts/actions/LocaleAction.html "class in org.apache.struts.actions")  
Change the user's [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util") based on [`ActionForm`](http://struts.apache.org/apidocs/org/apache/struts/action/ActionForm.html?is-external=true "class or interface in org.apache.struts.action") properties.

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/LookupDispatchAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/MappingDispatchAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[MappingDispatchAction](./org/apache/struts/actions/MappingDispatchAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

[**execute(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/SwitchAction.html.md#execute(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[SwitchAction](./org/apache/struts/actions/SwitchAction.html "class in org.apache.struts.actions")  
Process the specified HTTP request, and create the corresponding HTTP response (or forward to another web component that will create it).

------------------------------------------------------------------------

**F**
-----

[**flavor**](./org/apache/struts/actions/ActionDispatcher.html.md#flavor) - Variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Indicates dispatch *flavor*.

[**ForwardAction**](./org/apache/struts/actions/ForwardAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An **Action** that forwards to the context-relative URI specified by the `parameter` property of our associated `ActionMapping`.

[**ForwardAction()**](./org/apache/struts/actions/ForwardAction.html.md#ForwardAction()) - Constructor for class org.apache.struts.actions.[ForwardAction](./org/apache/struts/actions/ForwardAction.html "class in org.apache.struts.actions")  
 

------------------------------------------------------------------------

**G**
-----

[**getBufferSize()**](./org/apache/struts/actions/DownloadAction.html.md#getBufferSize()) - Method in class org.apache.struts.actions.[DownloadAction](./org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions")  
Returns the size of the buffer to be used in transferring the data to the servlet output stream.

[**getClassPathURL(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getClassPathURL(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Given a string, return a URL to a classpath resource of that name.

[**getConfigPath()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getConfigPath()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getConfigSource()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getConfigSource()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getConfigURL(String, String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getConfigURL(java.lang.String,%20java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Look up a resource path using one of a set of known path resolution mechanisms and return a URL to the resource.

[**getContentType()**](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md#getContentType()) - Method in class org.apache.struts.actions.[DownloadAction.FileStreamInfo](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html "class in org.apache.struts.actions")  
Returns the content type of the stream to be downloaded.

[**getContentType()**](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html.md#getContentType()) - Method in class org.apache.struts.actions.[DownloadAction.ResourceStreamInfo](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html "class in org.apache.struts.actions")  
Returns the content type of the stream to be downloaded.

[**getContentType()**](./org/apache/struts/actions/DownloadAction.StreamInfo.html.md#getContentType()) - Method in interface org.apache.struts.actions.[DownloadAction.StreamInfo](./org/apache/struts/actions/DownloadAction.StreamInfo.html "interface in org.apache.struts.actions")  
Returns the content type of the stream to be downloaded.

[**getDigesterPath()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getDigesterPath()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getDigesterSource()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getDigesterSource()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getFileURL(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getFileURL(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Given a string, return a URL to a Filesystem resource of that name.

[**getInputStream()**](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html.md#getInputStream()) - Method in class org.apache.struts.actions.[DownloadAction.FileStreamInfo](./org/apache/struts/actions/DownloadAction.FileStreamInfo.html "class in org.apache.struts.actions")  
Returns an input stream on the file to be downloaded.

[**getInputStream()**](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html.md#getInputStream()) - Method in class org.apache.struts.actions.[DownloadAction.ResourceStreamInfo](./org/apache/struts/actions/DownloadAction.ResourceStreamInfo.html "class in org.apache.struts.actions")  
Returns an input stream on the resource to be downloaded.

[**getInputStream()**](./org/apache/struts/actions/DownloadAction.StreamInfo.html.md#getInputStream()) - Method in interface org.apache.struts.actions.[DownloadAction.StreamInfo](./org/apache/struts/actions/DownloadAction.StreamInfo.html "interface in org.apache.struts.actions")  
Returns an input stream on the content to be downloaded.

[**getKey()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getKey()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getKeyMethodMap()**](./org/apache/struts/actions/LookupDispatchAction.html.md#getKeyMethodMap()) - Method in class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
Provides the mapping from resource key to method name.

[**getLookupMapName(HttpServletRequest, String, ActionMapping)**](./org/apache/struts/actions/LookupDispatchAction.html.md#getLookupMapName(javax.servlet.http.HttpServletRequest,%20java.lang.String,%20org.apache.struts.action.ActionMapping)) - Method in class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
Lookup the method name corresponding to the client request's locale.

[**getMethod(String)**](./org/apache/struts/actions/ActionDispatcher.html.md#getMethod(java.lang.String)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Introspect the current class to identify a method of the specified name that accepts the same parameter types as the `execute` method does.

[**getMethod(String)**](./org/apache/struts/actions/DispatchAction.html.md#getMethod(java.lang.String)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Introspect the current class to identify a method of the specified name that accepts the same parameter types as the `execute` method does.

[**getMethodName(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/ActionDispatcher.html.md#getMethodName(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Returns the method name, given a parameter's value.

[**getMethodName(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/DispatchAction.html.md#getMethodName(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Returns the method name, given a parameter's value.

[**getMethodName(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/EventActionDispatcher.html.md#getMethodName(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[EventActionDispatcher](./org/apache/struts/actions/EventActionDispatcher.html "class in org.apache.struts.actions")  
Returns the method name, given a parameter's value.

[**getMethodName(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/EventDispatchAction.html.md#getMethodName(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[EventDispatchAction](./org/apache/struts/actions/EventDispatchAction.html "class in org.apache.struts.actions")  
Returns the method name, given a parameter's value.

[**getMethodName(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/LookupDispatchAction.html.md#getMethodName(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
Returns the method name, given a parameter's value.

[**getMethodName(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse, String)**](./org/apache/struts/actions/MappingDispatchAction.html.md#getMethodName(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20java.lang.String)) - Method in class org.apache.struts.actions.[MappingDispatchAction](./org/apache/struts/actions/MappingDispatchAction.html "class in org.apache.struts.actions")  
Returns the method name, given a parameter's value.

[**getParameter(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/ActionDispatcher.html.md#getParameter(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Returns the parameter value as influenced by the selected [`ActionDispatcher.flavor`](./org/apache/struts/actions/ActionDispatcher.html.md#flavor) specified for this `ActionDispatcher`.

[**getParameter(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/DispatchAction.html.md#getParameter(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Returns the parameter value.

[**getParameter(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/MappingDispatchAction.html.md#getParameter(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[MappingDispatchAction](./org/apache/struts/actions/MappingDispatchAction.html "class in org.apache.struts.actions")  
Returns the parameter value.

[**getPush()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getPush()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getRulesets()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getRulesets()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**getServletContextURL(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#getServletContextURL(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Given a string, return a URL to a Servlet Context resource of that name.

[**getStreamInfo(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/DownloadAction.html.md#getStreamInfo(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[DownloadAction](./org/apache/struts/actions/DownloadAction.html "class in org.apache.struts.actions")  
Returns the information on the file, or other stream, to be downloaded by this action.

[**getValidationKey(ActionMapping, HttpServletRequest)**](./org/apache/struts/validator/DynaValidatorActionForm.html.md#getValidationKey(org.apache.struts.action.ActionMapping,%20javax.servlet.http.HttpServletRequest)) - Method in class org.apache.struts.validator.[DynaValidatorActionForm](./org/apache/struts/validator/DynaValidatorActionForm.html "class in org.apache.struts.validator")  
Returns the Validation key.

[**getValidationKey(ActionMapping, HttpServletRequest)**](./org/apache/struts/validator/ValidatorActionForm.html.md#getValidationKey(org.apache.struts.action.ActionMapping,%20javax.servlet.http.HttpServletRequest)) - Method in class org.apache.struts.validator.[ValidatorActionForm](./org/apache/struts/validator/ValidatorActionForm.html "class in org.apache.struts.validator")  
Returns the Validation key.

------------------------------------------------------------------------

**I**
-----

[**IncludeAction**](./org/apache/struts/actions/IncludeAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An **Action** that includes the context-relative URI specified by the `parameter` property of our associated `ActionMapping`.

[**IncludeAction()**](./org/apache/struts/actions/IncludeAction.html.md#IncludeAction()) - Constructor for class org.apache.struts.actions.[IncludeAction](./org/apache/struts/actions/IncludeAction.html "class in org.apache.struts.actions")  
 

[**init(ActionServlet, ModuleConfig)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#init(org.apache.struts.action.ActionServlet,%20org.apache.struts.config.ModuleConfig)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Initialize a `Digester` and use it to parse a configuration file, resulting in a root object which will be placed into the ServletContext.

[**init(ActionServlet, ModuleConfig)**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#init(org.apache.struts.action.ActionServlet,%20org.apache.struts.config.ModuleConfig)) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
 

[**initializeDigester()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#initializeDigester()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Initialize the `Digester` which will be used to process the main configuration.

[**isCancelled(HttpServletRequest)**](./org/apache/struts/actions/ActionDispatcher.html.md#isCancelled(javax.servlet.http.HttpServletRequest)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Returns `true` if the current form's cancel button was pressed.

[**isFatal()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#isFatal()) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Return the "configuation errors are fatal" flag.

------------------------------------------------------------------------

**K**
-----

[**key**](./org/apache/struts/plugins/DigestingPlugIn.html.md#key) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**keyMethodMap**](./org/apache/struts/actions/LookupDispatchAction.html.md#keyMethodMap) - Variable in class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
Resource key to method name lookup.

------------------------------------------------------------------------

**L**
-----

[**LocaleAction**](./org/apache/struts/actions/LocaleAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
Implementation of **Action** that changes the user's [`Locale`](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Locale.html.md?is-external=true "class or interface in java.util") and forwards to a page, based on request level parameters that are set (language, country, & page).

[**LocaleAction()**](./org/apache/struts/actions/LocaleAction.html.md#LocaleAction()) - Constructor for class org.apache.struts.actions.[LocaleAction](./org/apache/struts/actions/LocaleAction.html "class in org.apache.struts.actions")  
 

[**localeMap**](./org/apache/struts/actions/LookupDispatchAction.html.md#localeMap) - Variable in class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
Reverse lookup map from resource value to resource key.

[**log**](./org/apache/struts/actions/ActionDispatcher.html.md#log) - Static variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Commons Logging instance.

[**log**](./org/apache/struts/actions/DispatchAction.html.md#log) - Static variable in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Commons Logging instance.

[**log**](./org/apache/struts/actions/SwitchAction.html.md#log) - Static variable in class org.apache.struts.actions.[SwitchAction](./org/apache/struts/actions/SwitchAction.html "class in org.apache.struts.actions")  
Commons Logging instance.

[**LookupDispatchAction**](./org/apache/struts/actions/LookupDispatchAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An abstract **Action** that dispatches to the subclass mapped `execute` method.

[**LookupDispatchAction()**](./org/apache/struts/actions/LookupDispatchAction.html.md#LookupDispatchAction()) - Constructor for class org.apache.struts.actions.[LookupDispatchAction](./org/apache/struts/actions/LookupDispatchAction.html "class in org.apache.struts.actions")  
 

------------------------------------------------------------------------

**M**
-----

[**MAPPING\_FLAVOR**](./org/apache/struts/actions/ActionDispatcher.html.md#MAPPING_FLAVOR) - Static variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Indicates "mapping" dispatch flavor.

[**MappingDispatchAction**](./org/apache/struts/actions/MappingDispatchAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
An abstract **Action** that dispatches to a public method that is named by the `parameter` attribute of the corresponding ActionMapping.

[**MappingDispatchAction()**](./org/apache/struts/actions/MappingDispatchAction.html.md#MappingDispatchAction()) - Constructor for class org.apache.struts.actions.[MappingDispatchAction](./org/apache/struts/actions/MappingDispatchAction.html "class in org.apache.struts.actions")  
 

[**messages**](./org/apache/struts/actions/ActionDispatcher.html.md#messages) - Static variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
The message resources for this package.

[**messages**](./org/apache/struts/actions/BaseAction.html.md#messages) - Static variable in class org.apache.struts.actions.[BaseAction](./org/apache/struts/actions/BaseAction.html "class in org.apache.struts.actions")  
The message resources for this package.

[**methods**](./org/apache/struts/actions/ActionDispatcher.html.md#methods) - Variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
The set of Method objects we have introspected for this class, keyed by method name.

[**methods**](./org/apache/struts/actions/DispatchAction.html.md#methods) - Variable in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
The set of Method objects we have introspected for this class, keyed by method name.

[**moduleConfig**](./org/apache/struts/plugins/DigestingPlugIn.html.md#moduleConfig) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**ModuleConfigVerifier**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md "class in org.apache.struts.plugins") - Class in [org.apache.struts.plugins](./org/apache/struts/plugins/package-summary.html)  
Convenient implementation of [`PlugIn`](http://struts.apache.org/apidocs/org/apache/struts/action/PlugIn.html.md?is-external=true "class or interface in org.apache.struts.action") that performs as many verification tests on the information stored in the [`ModuleConfig`](http://struts.apache.org/apidocs/org/apache/struts/config/ModuleConfig.html?is-external=true "class or interface in org.apache.struts.config") for this module as is practical.

[**ModuleConfigVerifier()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#ModuleConfigVerifier()) - Constructor for class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
 

------------------------------------------------------------------------

**N**
-----

[**newDigesterInstance()**](./org/apache/struts/plugins/DigestingPlugIn.html.md#newDigesterInstance()) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Instantiate a `Digester`.

------------------------------------------------------------------------

**O**
-----

[**org.apache.struts.actions**](./org/apache/struts/actions/package-summary.html.md) - package org.apache.struts.actions  
The actions package provides special adapters between the incoming HTTP request and the corresponding business logic.

[**org.apache.struts.plugins**](./org/apache/struts/plugins/package-summary.html.md) - package org.apache.struts.plugins  
 

[**org.apache.struts.validator**](./org/apache/struts/validator/package-summary.html.md) - package org.apache.struts.validator  
 

------------------------------------------------------------------------

**P**
-----

[**push**](./org/apache/struts/plugins/DigestingPlugIn.html.md#push) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

------------------------------------------------------------------------

**R**
-----

[**rulesets**](./org/apache/struts/plugins/DigestingPlugIn.html.md#rulesets) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

------------------------------------------------------------------------

**S**
-----

[**servlet**](./org/apache/struts/plugins/DigestingPlugIn.html.md#servlet) - Variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**servlet**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#servlet) - Variable in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
The [`ActionServlet`](http://struts.apache.org/apidocs/org/apache/struts/action/ActionServlet.html.md?is-external=true "class or interface in org.apache.struts.action") instance we are associated with.

[**setConfigPath(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setConfigPath(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**setConfigSource(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setConfigSource(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
Set the source of the config file.

[**setDigesterPath(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setDigesterPath(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
The path to a Digester XML configuration file, relative to the `digesterSource` property.

[**setDigesterSource(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setDigesterSource(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
The lookup mechanism to be used to resolve `digesterPath` (optional).

[**setFatal(boolean)**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#setFatal(boolean)) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Set the "configuration errors are fatal" flag.

[**setKey(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setKey(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**setPush(boolean)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setPush(boolean)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
If set to `true`, this PlugIn will be pushed onto the Digester stack before the digester `parse` method is called.

[**setRulesets(String)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#setRulesets(java.lang.String)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
A comma-delimited list of one or more classes which implement `org.apache.commons.digester.RuleSet`.

[**SOURCE\_CLASSPATH**](./org/apache/struts/plugins/DigestingPlugIn.html.md#SOURCE_CLASSPATH) - Static variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**SOURCE\_FILE**](./org/apache/struts/plugins/DigestingPlugIn.html.md#SOURCE_FILE) - Static variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**SOURCE\_SERVLET**](./org/apache/struts/plugins/DigestingPlugIn.html.md#SOURCE_SERVLET) - Static variable in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
 

[**storeGeneratedObject(Object)**](./org/apache/struts/plugins/DigestingPlugIn.html.md#storeGeneratedObject(java.lang.Object)) - Method in class org.apache.struts.plugins.[DigestingPlugIn](./org/apache/struts/plugins/DigestingPlugIn.html "class in org.apache.struts.plugins")  
This method is called after the Digester runs to store the generated object somewhere.

[**SwitchAction**](./org/apache/struts/actions/SwitchAction.html.md "class in org.apache.struts.actions") - Class in [org.apache.struts.actions](./org/apache/struts/actions/package-summary.html)  
A standard **Action** that switches to a new module and then forwards control to a URI (specified in a number of possible ways) within the new module.

[**SwitchAction()**](./org/apache/struts/actions/SwitchAction.html.md#SwitchAction()) - Constructor for class org.apache.struts.actions.[SwitchAction](./org/apache/struts/actions/SwitchAction.html "class in org.apache.struts.actions")  
 

------------------------------------------------------------------------

**T**
-----

[**types**](./org/apache/struts/actions/ActionDispatcher.html.md#types) - Variable in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
The set of argument type classes for the reflected method call.

[**types**](./org/apache/struts/actions/DispatchAction.html.md#types) - Variable in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
The set of argument type classes for the reflected method call.

------------------------------------------------------------------------

**U**
-----

[**unspecified(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/ActionDispatcher.html.md#unspecified(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[ActionDispatcher](./org/apache/struts/actions/ActionDispatcher.html "class in org.apache.struts.actions")  
Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException.

[**unspecified(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/DispatchAction.html.md#unspecified(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[DispatchAction](./org/apache/struts/actions/DispatchAction.html "class in org.apache.struts.actions")  
Method which is dispatched to when there is no value for specified request parameter included in the request.

[**unspecified(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/EventActionDispatcher.html.md#unspecified(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[EventActionDispatcher](./org/apache/struts/actions/EventActionDispatcher.html "class in org.apache.struts.actions")  
Dispatches to the target class' `unspecified` method, if present, otherwise throws a ServletException.

[**unspecified(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/EventDispatchAction.html.md#unspecified(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[EventDispatchAction](./org/apache/struts/actions/EventDispatchAction.html "class in org.apache.struts.actions")  
Method which is dispatched to when there is no value for specified request parameter included in the request.

[**unspecified(ActionMapping, ActionForm, HttpServletRequest, HttpServletResponse)**](./org/apache/struts/actions/MappingDispatchAction.html.md#unspecified(org.apache.struts.action.ActionMapping,%20org.apache.struts.action.ActionForm,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse)) - Method in class org.apache.struts.actions.[MappingDispatchAction](./org/apache/struts/actions/MappingDispatchAction.html "class in org.apache.struts.actions")  
Method which is dispatched to when there is no value for the parameter in the ActionMapping.

------------------------------------------------------------------------

**V**
-----

[**ValidatorActionForm**](./org/apache/struts/validator/ValidatorActionForm.html.md "class in org.apache.struts.validator") - Class in [org.apache.struts.validator](./org/apache/struts/validator/package-summary.html)  
This class extends **ValidatorForm** and provides basic field validation based on an XML file.

[**ValidatorActionForm()**](./org/apache/struts/validator/ValidatorActionForm.html.md#ValidatorActionForm()) - Constructor for class org.apache.struts.validator.[ValidatorActionForm](./org/apache/struts/validator/ValidatorActionForm.html "class in org.apache.struts.validator")  
 

[**verifyActionMappingClass()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#verifyActionMappingClass()) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Return `true` if information returned by `config.getActionMappingClass` is all valid; otherwise, log error messages and return `false`.

[**verifyForwardConfigs()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#verifyForwardConfigs()) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Return `true` if information returned by `config.findForwardConfigs` is all valid; otherwise, log error messages and return `false`.

[**verifyMessageResourcesConfigs()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#verifyMessageResourcesConfigs()) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Return `true` if information returned by `config.findMessageResourcesConfigs` is all valid; otherwise, log error messages and return `false`.

[**verifyPlugInConfigs()**](./org/apache/struts/plugins/ModuleConfigVerifier.html.md#verifyPlugInConfigs()) - Method in class org.apache.struts.plugins.[ModuleConfigVerifier](./org/apache/struts/plugins/ModuleConfigVerifier.html "class in org.apache.struts.plugins")  
Return `true` if information returned by `config.findPluginConfigs` is all valid; otherwise, log error messages and return `false`.

------------------------------------------------------------------------

[A](#_A_) [B](#_B_) [C](#_C_) [D](#_D_) [E](#_E_) [F](#_F_) [G](#_G_) [I](#_I_) [K](#_K_) [L](#_L_) [M](#_M_) [N](#_N_) [O](#_O_) [P](#_P_) [R](#_R_) [S](#_S_) [T](#_T_) [U](#_U_) [V](#_V_) <span id="navbar_bottom"></span> [](#skip-navbar_bottom "Skip navigation links")

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
<td align="left"><a href="./overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left">Package </td>
<td align="left">Class </td>
<td align="left">Use </td>
<td align="left"><a href="./overview-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="./deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"> <strong>Index</strong> </td>
<td align="left"><a href="./help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="./index.html.md?index-all.html"><strong>FRAMES</strong></a>    <a href="index-all.html"><strong>NO FRAMES</strong></a>    
<a href="./allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
