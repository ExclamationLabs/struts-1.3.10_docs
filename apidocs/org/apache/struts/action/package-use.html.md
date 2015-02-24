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
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
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
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Package
 org.apache.struts.action**
---------------------------

Packages that use [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md)

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.actions**](#org.apache.struts.actions)

The actions package provides special adapters between the incoming HTTP request and the corresponding business logic. 

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.generic**](#org.apache.struts.chain.commands.generic)

Contains generic commands. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.faces.application**](#org.apache.struts.faces.application)

  

[**org.apache.struts.faces.util**](#org.apache.struts.faces.util)

  

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.plugins**](#org.apache.struts.plugins)

  

[**org.apache.struts.scripting**](#org.apache.struts.scripting)

The scripting package is the core of the Struts Scripting framework, which builds on Struts Action to allow Struts Actions be written with the scripting language of your choice. 

[**org.apache.struts.taglib**](#org.apache.struts.taglib)

  

[**org.apache.struts.taglib.html.md**](#org.apache.struts.taglib.html)

The "struts.html.md" tag library contains JSP custom tags useful in creating dynamic HTML user interfaces, including input forms. 

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.tiles.actions**](#org.apache.struts.tiles.actions)

  

[**org.apache.struts.upload**](#org.apache.struts.upload)

The upload package facilities to upload files using multi-part requests. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

[**org.apache.struts.validator.validwhen**](#org.apache.struts.validator.validwhen)

Generated classes by antlr to support the `validwhen` validator. 

 

<span id="org.apache.struts.action"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html)                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.action)**                                                                                                                                                                                                                         
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                                                                                                                  |
| **[**ActionErrors**](../../../../org/apache/struts/action/class-use/ActionErrors.html.md#org.apache.struts.action)**                                                                                                                                                                                                             
            A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`.                                                                                                                                                                                                          |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.action)**                                                                                                                                                                                                                 
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                                                                                            |
| **[**ActionForward**](../../../../org/apache/struts/action/class-use/ActionForward.html.md#org.apache.struts.action)**                                                                                                                                                                                                           
            An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.                                                                  |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.action)**                                                                                                                                                                                                           
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                                                                                             |
| **[**ActionMessage**](../../../../org/apache/struts/action/class-use/ActionMessage.html.md#org.apache.struts.action)**                                                                                                                                                                                                           
            An encapsulation of an individual message returned by the `validate` method of an `ActionForm`, consisting of a message key (to be used to look up message text in an appropriate message resources database) plus up to four placeholder objects that can be used for parametric replacement in the message text.  |
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.action)**                                                                                                                                                                                                         
            A class that encapsulates messages.                                                                                                                                                                                                                                                                                 |
| **[**ActionRedirect**](../../../../org/apache/struts/action/class-use/ActionRedirect.html.md#org.apache.struts.action)**                                                                                                                                                                                                         
             A subclass of [`ActionForward`](../../../../org/apache/struts/action/ActionForward.html.md "class in org.apache.struts.action") which is designed for use in redirecting requests, with support for adding parameters at runtime.                                                                                     |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.action)**                                                                                                                                                                                                           
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                                                                                             |
| **[**ActionServletWrapper**](../../../../org/apache/struts/action/class-use/ActionServletWrapper.html.md#org.apache.struts.action)**                                                                                                                                                                                             
            Provide a wrapper around an [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") to expose only those methods needed by other objects.                                                                                                                    |
| **[**DynaActionFormClass**](../../../../org/apache/struts/action/class-use/DynaActionFormClass.html.md#org.apache.struts.action)**                                                                                                                                                                                               
            Implementation of `DynaClass` for `DynaActionForm` classes that allow developers to define ActionForms without having to individually code all of the classes.                                                                                                                                                      |
| **[**InvalidCancelException**](../../../../org/apache/struts/action/class-use/InvalidCancelException.html.md#org.apache.struts.action)**                                                                                                                                                                                         
             Thrown when a token generated by the Cancel tag is found in the request, but the cancellable property for the Action Mapping is not set.                                                                                                                                                                           |
| **[**RequestProcessor**](../../../../org/apache/struts/action/class-use/RequestProcessor.html.md#org.apache.struts.action)**                                                                                                                                                                                                     
            **RequestProcessor** contains the processing logic that the [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") performs as it receives each servlet request from the container.                                                                         |

 

<span id="org.apache.struts.actions"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.actions](../../../../org/apache/struts/actions/package-summary.html)                                                              |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.actions)**                                                                                                                                                        
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                                                  |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.actions)**                                                                                                                                                
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                            |
| **[**ActionForward**](../../../../org/apache/struts/action/class-use/ActionForward.html.md#org.apache.struts.actions)**                                                                                                                                          
            An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.  |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.actions)**                                                                                                                                          
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                             |

 

<span id="org.apache.struts.chain"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.chain](../../../../org/apache/struts/chain/package-summary.html)                                                           |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.chain)**                                                                                                                                     
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                      |
| **[**RequestProcessor**](../../../../org/apache/struts/action/class-use/RequestProcessor.html.md#org.apache.struts.chain)**                                                                                                                               
            **RequestProcessor** contains the processing logic that the [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") performs as it receives each servlet request from the container.  |

 

<span id="org.apache.struts.chain.commands"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.chain.commands](../../../../org/apache/struts/chain/commands/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.chain.commands)**                                                                                                  
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                   |
| **[**ActionErrors**](../../../../org/apache/struts/action/class-use/ActionErrors.html.md#org.apache.struts.chain.commands)**                                                                                      
            A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`.                                                                                           |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.chain.commands)**                                                                                          
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                             |

 

<span id="org.apache.struts.chain.commands.generic"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.chain.commands.generic](../../../../org/apache/struts/chain/commands/generic/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.chain.commands.generic)**                                                                                                  
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                             |

 

<span id="org.apache.struts.chain.commands.servlet"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.chain.commands.servlet](../../../../org/apache/struts/chain/commands/servlet/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.chain.commands.servlet)**                                                                                                          
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                   |
| **[**ActionErrors**](../../../../org/apache/struts/action/class-use/ActionErrors.html.md#org.apache.struts.chain.commands.servlet)**                                                                                              
            A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`.                                                                                                           |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.chain.commands.servlet)**                                                                                                  
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                             |

 

<span id="org.apache.struts.chain.contexts"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.chain.contexts](../../../../org/apache/struts/chain/contexts/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.chain.contexts)**                                                                                                  
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                   |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.chain.contexts)**                                                                                          
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                             |
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.chain.contexts)**                                                                                  
            A class that encapsulates messages.                                                                                                                                                                  |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.chain.contexts)**                                                                                    
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                              |

 

<span id="org.apache.struts.config"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html)                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.config)**                                                                                                                                                 
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                            |
| **[**ActionFormBean**](../../../../org/apache/struts/action/class-use/ActionFormBean.html.md#org.apache.struts.config)**                                                                                                                                         
            An **ActionFormBean** is the definition of a form bean that is loaded from a `<form-bean>` element in the Struts configuration file.                                                                                                                |
| **[**ActionForward**](../../../../org/apache/struts/action/class-use/ActionForward.html.md#org.apache.struts.config)**                                                                                                                                           
            An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.  |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.config)**                                                                                                                                           
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                             |
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.config)**                                                                                                                                         
            A class that encapsulates messages.                                                                                                                                                                                                                 |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.config)**                                                                                                                                           
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                             |
| **[**DynaActionFormClass**](../../../../org/apache/struts/action/class-use/DynaActionFormClass.html.md#org.apache.struts.config)**                                                                                                                               
            Implementation of `DynaClass` for `DynaActionForm` classes that allow developers to define ActionForms without having to individually code all of the classes.                                                                                      |

 

<span id="org.apache.struts.faces.application"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.faces.application](../../../../org/apache/struts/faces/application/package-summary.html)                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.faces.application)**                                                                                                                                              
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                                                  |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.faces.application)**                                                                                                                                      
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                            |
| **[**ActionForward**](../../../../org/apache/struts/action/class-use/ActionForward.html.md#org.apache.struts.faces.application)**                                                                                                                                
            An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.  |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.faces.application)**                                                                                                                                
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                             |
| **[**InvalidCancelException**](../../../../org/apache/struts/action/class-use/InvalidCancelException.html.md#org.apache.struts.faces.application)**                                                                                                              
             Thrown when a token generated by the Cancel tag is found in the request, but the cancellable property for the Action Mapping is not set.                                                                                                           |
| **[**RequestProcessor**](../../../../org/apache/struts/action/class-use/RequestProcessor.html.md#org.apache.struts.faces.application)**                                                                                                                          
            **RequestProcessor** contains the processing logic that the [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") performs as it receives each servlet request from the container.         |

 

<span id="org.apache.struts.faces.util"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.faces.util](../../../../org/apache/struts/faces/util/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.faces.util)**                                                                                
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.      |
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.faces.util)**                                                                              
            A class that encapsulates messages.                                                                                                                                                          |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.faces.util)**                                                                                
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                      |

 

<span id="org.apache.struts.mock"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.mock](../../../../org/apache/struts/mock/package-summary.html)         |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.mock)**                                                                                                
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                       |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.mock)**                                                                                        
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                 |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.mock)**                                                                                  
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.  |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.mock)**                                                                                  
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                  |

 

<span id="org.apache.struts.plugins"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.plugins](../../../../org/apache/struts/plugins/package-summary.html)                                                                                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.plugins)**                                                                                                                                                                                                                                                                            
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                                                                                                                                                               |
| **[**PlugIn**](../../../../org/apache/struts/action/class-use/PlugIn.html.md#org.apache.struts.plugins)**                                                                                                                                                                                                                                                                                          
            A **PlugIn** is a configuration wrapper for a module-specific resource or service that needs to be notified about application startup and application shutdown events (corresponding to when the container calls `init` and `destroy` on the corresponding [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") instance).  |

 

<span id="org.apache.struts.scripting"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.scripting](../../../../org/apache/struts/scripting/package-summary.html)                                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.scripting)**                                                                                                                                                      
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                                                  |
| **[**ActionErrors**](../../../../org/apache/struts/action/class-use/ActionErrors.html.md#org.apache.struts.scripting)**                                                                                                                                          
            A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`.                                                                                                                                          |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.scripting)**                                                                                                                                              
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                            |
| **[**ActionForward**](../../../../org/apache/struts/action/class-use/ActionForward.html.md#org.apache.struts.scripting)**                                                                                                                                        
            An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.  |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.scripting)**                                                                                                                                        
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                             |
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.scripting)**                                                                                                                                      
            A class that encapsulates messages.                                                                                                                                                                                                                 |

 

<span id="org.apache.struts.taglib"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.taglib](../../../../org/apache/struts/taglib/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.taglib)**                                                                          
            A class that encapsulates messages.                                                                                                                                                  |

 

<span id="org.apache.struts.taglib.html.md"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.taglib.html](../../../../org/apache/struts/taglib/html/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.taglib.html)**                                                                                 
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.        |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.taglib.html)**                                                                                 
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                        |

 

<span id="org.apache.struts.tiles"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.tiles](../../../../org/apache/struts/tiles/package-summary.html)                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.tiles)**                                                                                                                                                                                                                                                                                            
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                                                                                                                                                                                    |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.tiles)**                                                                                                                                                                                                                                                                              
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                                                                                                                                                               |
| **[**PlugIn**](../../../../org/apache/struts/action/class-use/PlugIn.html.md#org.apache.struts.tiles)**                                                                                                                                                                                                                                                                                            
            A **PlugIn** is a configuration wrapper for a module-specific resource or service that needs to be notified about application startup and application shutdown events (corresponding to when the container calls `init` and `destroy` on the corresponding [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") instance).  |
| **[**RequestProcessor**](../../../../org/apache/struts/action/class-use/RequestProcessor.html.md#org.apache.struts.tiles)**                                                                                                                                                                                                                                                                        
            **RequestProcessor** contains the processing logic that the [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") performs as it receives each servlet request from the container.                                                                                                                                           |

 

<span id="org.apache.struts.tiles.actions"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.tiles.actions](../../../../org/apache/struts/tiles/actions/package-summary.html)                                                  |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**Action**](../../../../org/apache/struts/action/class-use/Action.html.md#org.apache.struts.tiles.actions)**                                                                                                                                                  
            An **Action** is an adapter between the contents of an incoming HTTP request and the corresponding business logic that should be executed to process this request.                                                                                  |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.tiles.actions)**                                                                                                                                          
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                            |
| **[**ActionForward**](../../../../org/apache/struts/action/class-use/ActionForward.html.md#org.apache.struts.tiles.actions)**                                                                                                                                    
            An **ActionForward** represents a destination to which the controller, RequestProcessor, might be directed to perform a RequestDispatcher.forward or HttpServletResponse.sendRedirect to, as a result of processing activities of an Action class.  |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.tiles.actions)**                                                                                                                                    
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                             |

 

<span id="org.apache.struts.upload"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.upload](../../../../org/apache/struts/upload/package-summary.html)     |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.upload)**                                                                                
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.  |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.upload)**                                                                                
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                  |

 

<span id="org.apache.struts.util"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.util](../../../../org/apache/struts/util/package-summary.html)                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.util)**                                                                                                                                                                                                                   
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                                                                                            |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.util)**                                                                                                                                                                                                             
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                                                                                             |
| **[**ActionMessage**](../../../../org/apache/struts/action/class-use/ActionMessage.html.md#org.apache.struts.util)**                                                                                                                                                                                                             
            An encapsulation of an individual message returned by the `validate` method of an `ActionForm`, consisting of a message key (to be used to look up message text in an appropriate message resources database) plus up to four placeholder objects that can be used for parametric replacement in the message text.  |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.util)**                                                                                                                                                                                                             
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                                                                                             |

 

<span id="org.apache.struts.validator"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.validator](../../../../org/apache/struts/validator/package-summary.html)                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionErrors**](../../../../org/apache/struts/action/class-use/ActionErrors.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                            
            A class that encapsulates the error messages being reported by the `validate()` method of an `ActionForm`.                                                                                                                                                                                                                                                                            |
| **[**ActionForm**](../../../../org/apache/struts/action/class-use/ActionForm.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                                
            An **ActionForm** is a JavaBean optionally associated with one or more `ActionMappings`.                                                                                                                                                                                                                                                                                              |
| **[**ActionMapping**](../../../../org/apache/struts/action/class-use/ActionMapping.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                          
            An **ActionMapping** represents the information that the controller, `RequestProcessor`, knows about the mapping of a particular request to an instance of a particular `Action` class.                                                                                                                                                                                               |
| **[**ActionMessage**](../../../../org/apache/struts/action/class-use/ActionMessage.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                          
            An encapsulation of an individual message returned by the `validate` method of an `ActionForm`, consisting of a message key (to be used to look up message text in an appropriate message resources database) plus up to four placeholder objects that can be used for parametric replacement in the message text.                                                                    |
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                        
            A class that encapsulates messages.                                                                                                                                                                                                                                                                                                                                                   |
| **[**ActionServlet**](../../../../org/apache/struts/action/class-use/ActionServlet.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                          
            **ActionServlet** provides the "controller" in the Model-View-Controller (MVC) design pattern for web applications that is commonly known as "Model 2".                                                                                                                                                                                                                               |
| **[**DynaActionForm**](../../../../org/apache/struts/action/class-use/DynaActionForm.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                        
            Specialized subclass of `ActionForm` that allows the creation of form beans with dynamic sets of properties, without requiring the developer to create a Java class for each type of form bean.                                                                                                                                                                                       |
| **[**PlugIn**](../../../../org/apache/struts/action/class-use/PlugIn.html.md#org.apache.struts.validator)**                                                                                                                                                                                                                                                                                        
            A **PlugIn** is a configuration wrapper for a module-specific resource or service that needs to be notified about application startup and application shutdown events (corresponding to when the container calls `init` and `destroy` on the corresponding [`ActionServlet`](../../../../org/apache/struts/action/ActionServlet.html.md "class in org.apache.struts.action") instance).  |

 

<span id="org.apache.struts.validator.validwhen"></span>

| Classes in [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html.md) used by [org.apache.struts.validator.validwhen](../../../../org/apache/struts/validator/validwhen/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionMessages**](../../../../org/apache/struts/action/class-use/ActionMessages.html.md#org.apache.struts.validator.validwhen)**                                                                                       
            A class that encapsulates messages.                                                                                                                                                                            |

 

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
<td align="left">Class </td>
<td align="left"> <strong>Use</strong> </td>
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
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="../../../../index.html.md?org/apache/struts/action/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
