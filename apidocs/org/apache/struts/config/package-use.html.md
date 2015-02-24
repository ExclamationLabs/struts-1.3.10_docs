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
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Uses of Package
 org.apache.struts.config**
---------------------------

Packages that use [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md)

[**org.apache.struts.action**](#org.apache.struts.action)

The action package is the core of the struts framework, providing the "Controller" aspect of a MVC model. 

[**org.apache.struts.chain**](#org.apache.struts.chain)

Contains the new `ComposableRequestProcessor` which was introduced in Struts 1.3. 

[**org.apache.struts.chain.commands**](#org.apache.struts.chain.commands)

Configurable commands that may be placed within the request processor. 

[**org.apache.struts.chain.commands.servlet**](#org.apache.struts.chain.commands.servlet)

Commands which are particular to servlet processing. 

[**org.apache.struts.chain.contexts**](#org.apache.struts.chain.contexts)

This package provides objects that encapsulate access to the request and session-scoped resources to service command processing. 

[**org.apache.struts.config**](#org.apache.struts.config)

The "config" package contains configuration objects that correspond to elements that may be specified in the `struts-config.xml` module configuration file. 

[**org.apache.struts.config.impl**](#org.apache.struts.config.impl)

Provides default implementation classes for the configuration objects. 

[**org.apache.struts.faces.application**](#org.apache.struts.faces.application)

  

[**org.apache.struts.faces.component**](#org.apache.struts.faces.component)

  

[**org.apache.struts.faces.util**](#org.apache.struts.faces.util)

  

[**org.apache.struts.mock**](#org.apache.struts.mock)

Mock objects of the Struts Framework. 

[**org.apache.struts.plugins**](#org.apache.struts.plugins)

  

[**org.apache.struts.taglib**](#org.apache.struts.taglib)

  

[**org.apache.struts.taglib.html.md**](#org.apache.struts.taglib.html)

The "struts.html.md" tag library contains JSP custom tags useful in creating dynamic HTML user interfaces, including input forms. 

[**org.apache.struts.tiles**](#org.apache.struts.tiles)

The Tiles taglib and framework allows building web pages by assembling reusable pieces of pages, called Tiles. 

[**org.apache.struts.upload**](#org.apache.struts.upload)

The upload package facilities to upload files using multi-part requests. 

[**org.apache.struts.util**](#org.apache.struts.util)

The Utilities package provides a variety of families of classes, to solve problems that are commonly encountered in building web applications. 

[**org.apache.struts.validator**](#org.apache.struts.validator)

The validator package provides a series of classes to validate `ActionForm` type of input. 

 

<span id="org.apache.struts.action"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.action](../../../../org/apache/struts/action/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.action)**                                                                              
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                              |
| **[**BaseConfig**](../../../../org/apache/struts/config/class-use/BaseConfig.html.md#org.apache.struts.action)**                                                                                  
             A abstract base class for all config classes.                                                                                                                                       |
| **[**ExceptionConfig**](../../../../org/apache/struts/config/class-use/ExceptionConfig.html.md#org.apache.struts.action)**                                                                        
            A JavaBean representing the configuration information of an `<exception>` element from a Struts configuration file.                                                                  |
| **[**FormBeanConfig**](../../../../org/apache/struts/config/class-use/FormBeanConfig.html.md#org.apache.struts.action)**                                                                          
            A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.                                                                     |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.action)**                                                                            
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                     |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.action)**                                                                              
            The collection of static configuration information that describes a Struts-based module.                                                                                             |

 

<span id="org.apache.struts.chain"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.chain](../../../../org/apache/struts/chain/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.chain)**                                                                             
            The collection of static configuration information that describes a Struts-based module.                                                                                           |

 

<span id="org.apache.struts.chain.commands"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.chain.commands](../../../../org/apache/struts/chain/commands/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.chain.commands)**                                                                                      
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                                              |
| **[**ExceptionConfig**](../../../../org/apache/struts/config/class-use/ExceptionConfig.html.md#org.apache.struts.chain.commands)**                                                                                
            A JavaBean representing the configuration information of an `<exception>` element from a Struts configuration file.                                                                                  |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.chain.commands)**                                                                                    
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                                     |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.chain.commands)**                                                                                      
            The collection of static configuration information that describes a Struts-based module.                                                                                                             |

 

<span id="org.apache.struts.chain.commands.servlet"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.chain.commands.servlet](../../../../org/apache/struts/chain/commands/servlet/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.chain.commands.servlet)**                                                                                              
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                                                              |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.chain.commands.servlet)**                                                                                            
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                                                     |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.chain.commands.servlet)**                                                                                              
            The collection of static configuration information that describes a Struts-based module.                                                                                                                             |

 

<span id="org.apache.struts.chain.contexts"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.chain.contexts](../../../../org/apache/struts/chain/contexts/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.chain.contexts)**                                                                                      
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                                              |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.chain.contexts)**                                                                                    
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                                     |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.chain.contexts)**                                                                                      
            The collection of static configuration information that describes a Struts-based module.                                                                                                             |

 

<span id="org.apache.struts.config"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.config)**                                                                              
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                              |
| **[**BaseConfig**](../../../../org/apache/struts/config/class-use/BaseConfig.html.md#org.apache.struts.config)**                                                                                  
             A abstract base class for all config classes.                                                                                                                                       |
| **[**ConfigHelperInterface**](../../../../org/apache/struts/config/class-use/ConfigHelperInterface.html.md#org.apache.struts.config)**                                                            
             NOTE: THIS CLASS IS UNDER ACTIVE DEVELOPMENT.                                                                                                                                       |
| **[**ControllerConfig**](../../../../org/apache/struts/config/class-use/ControllerConfig.html.md#org.apache.struts.config)**                                                                      
            A JavaBean representing the configuration information of a `<controller>` element in a Struts configuration file.                                                                    |
| **[**ExceptionConfig**](../../../../org/apache/struts/config/class-use/ExceptionConfig.html.md#org.apache.struts.config)**                                                                        
            A JavaBean representing the configuration information of an `<exception>` element from a Struts configuration file.                                                                  |
| **[**FormBeanConfig**](../../../../org/apache/struts/config/class-use/FormBeanConfig.html.md#org.apache.struts.config)**                                                                          
            A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.                                                                     |
| **[**FormPropertyConfig**](../../../../org/apache/struts/config/class-use/FormPropertyConfig.html.md#org.apache.struts.config)**                                                                  
            A JavaBean representing the configuration information of a `<form-property>` element in a Struts configuration file.                                                                 |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.config)**                                                                            
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                     |
| **[**MessageResourcesConfig**](../../../../org/apache/struts/config/class-use/MessageResourcesConfig.html.md#org.apache.struts.config)**                                                          
            A JavaBean representing the configuration information of a `<message-resources>` element in a Struts configuration file.                                                             |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.config)**                                                                              
            The collection of static configuration information that describes a Struts-based module.                                                                                             |
| **[**ModuleConfigFactory**](../../../../org/apache/struts/config/class-use/ModuleConfigFactory.html.md#org.apache.struts.config)**                                                                
            A factory interface for creating [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config")s.                                  |
| **[**PlugInConfig**](../../../../org/apache/struts/config/class-use/PlugInConfig.html.md#org.apache.struts.config)**                                                                              
            A JavaBean representing the configuration information of a `<plug-in>` element in a Struts configuration file.                                                                       |

 

<span id="org.apache.struts.config.impl"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.config.impl](../../../../org/apache/struts/config/impl/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.config.impl)**                                                                                   
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                                        |
| **[**ActionConfigMatcher**](../../../../org/apache/struts/config/class-use/ActionConfigMatcher.html.md#org.apache.struts.config.impl)**                                                                     
             Matches paths against pre-compiled wildcard expressions pulled from action configs.                                                                                                           |
| **[**BaseConfig**](../../../../org/apache/struts/config/class-use/BaseConfig.html.md#org.apache.struts.config.impl)**                                                                                       
             A abstract base class for all config classes.                                                                                                                                                 |
| **[**ControllerConfig**](../../../../org/apache/struts/config/class-use/ControllerConfig.html.md#org.apache.struts.config.impl)**                                                                           
            A JavaBean representing the configuration information of a `<controller>` element in a Struts configuration file.                                                                              |
| **[**ExceptionConfig**](../../../../org/apache/struts/config/class-use/ExceptionConfig.html.md#org.apache.struts.config.impl)**                                                                             
            A JavaBean representing the configuration information of an `<exception>` element from a Struts configuration file.                                                                            |
| **[**FormBeanConfig**](../../../../org/apache/struts/config/class-use/FormBeanConfig.html.md#org.apache.struts.config.impl)**                                                                               
            A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.                                                                               |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.config.impl)**                                                                                 
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                               |
| **[**MessageResourcesConfig**](../../../../org/apache/struts/config/class-use/MessageResourcesConfig.html.md#org.apache.struts.config.impl)**                                                               
            A JavaBean representing the configuration information of a `<message-resources>` element in a Struts configuration file.                                                                       |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.config.impl)**                                                                                   
            The collection of static configuration information that describes a Struts-based module.                                                                                                       |
| **[**ModuleConfigFactory**](../../../../org/apache/struts/config/class-use/ModuleConfigFactory.html.md#org.apache.struts.config.impl)**                                                                     
            A factory interface for creating [`ModuleConfig`](../../../../org/apache/struts/config/ModuleConfig.html.md "interface in org.apache.struts.config")s.                                            |
| **[**PlugInConfig**](../../../../org/apache/struts/config/class-use/PlugInConfig.html.md#org.apache.struts.config.impl)**                                                                                   
            A JavaBean representing the configuration information of a `<plug-in>` element in a Struts configuration file.                                                                                 |

 

<span id="org.apache.struts.faces.application"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.faces.application](../../../../org/apache/struts/faces/application/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.faces.application)**                                                                                       
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                                           |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.faces.application)**                                                                                         
            The collection of static configuration information that describes a Struts-based module.                                                                                                                   |

 

<span id="org.apache.struts.faces.component"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.faces.component](../../../../org/apache/struts/faces/component/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.faces.component)**                                                                                       
            The collection of static configuration information that describes a Struts-based module.                                                                                                               |

 

<span id="org.apache.struts.faces.util"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.faces.util](../../../../org/apache/struts/faces/util/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.faces.util)**                                                                                  
            The collection of static configuration information that describes a Struts-based module.                                                                                                     |

 

<span id="org.apache.struts.mock"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.mock](../../../../org/apache/struts/mock/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.mock)**                                                                            
            The collection of static configuration information that describes a Struts-based module.                                                                                         |

 

<span id="org.apache.struts.plugins"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.plugins](../../../../org/apache/struts/plugins/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.plugins)**                                                                               
            The collection of static configuration information that describes a Struts-based module.                                                                                               |

 

<span id="org.apache.struts.taglib"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.taglib](../../../../org/apache/struts/taglib/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.taglib)**                                                                              
            The collection of static configuration information that describes a Struts-based module.                                                                                             |

 

<span id="org.apache.struts.taglib.html.md"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.taglib.html](../../../../org/apache/struts/taglib/html/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.taglib.html)**                                                                                   
            The collection of static configuration information that describes a Struts-based module.                                                                                                       |

 

<span id="org.apache.struts.tiles"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.tiles](../../../../org/apache/struts/tiles/package-summary.html) |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.tiles)**                                                                           
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                   |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.tiles)**                                                                             
            The collection of static configuration information that describes a Struts-based module.                                                                                           |
| **[**PlugInConfig**](../../../../org/apache/struts/config/class-use/PlugInConfig.html.md#org.apache.struts.tiles)**                                                                             
            A JavaBean representing the configuration information of a `<plug-in>` element in a Struts configuration file.                                                                     |

 

<span id="org.apache.struts.upload"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.upload](../../../../org/apache/struts/upload/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.upload)**                                                                              
            The collection of static configuration information that describes a Struts-based module.                                                                                             |

 

<span id="org.apache.struts.util"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.util](../../../../org/apache/struts/util/package-summary.html) |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**ActionConfig**](../../../../org/apache/struts/config/class-use/ActionConfig.html.md#org.apache.struts.util)**                                                                            
            A JavaBean representing the configuration information of an `<action>` element from a Struts module configuration file.                                                          |
| **[**FormBeanConfig**](../../../../org/apache/struts/config/class-use/FormBeanConfig.html.md#org.apache.struts.util)**                                                                        
            A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.                                                                 |
| **[**ForwardConfig**](../../../../org/apache/struts/config/class-use/ForwardConfig.html.md#org.apache.struts.util)**                                                                          
            A JavaBean representing the configuration information of a `<forward>` element from a Struts configuration file.                                                                 |
| **[**MessageResourcesConfig**](../../../../org/apache/struts/config/class-use/MessageResourcesConfig.html.md#org.apache.struts.util)**                                                        
            A JavaBean representing the configuration information of a `<message-resources>` element in a Struts configuration file.                                                         |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.util)**                                                                            
            The collection of static configuration information that describes a Struts-based module.                                                                                         |

 

<span id="org.apache.struts.validator"></span>

| Classes in [org.apache.struts.config](../../../../org/apache/struts/config/package-summary.html.md) used by [org.apache.struts.validator](../../../../org/apache/struts/validator/package-summary.html) |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **[**FormBeanConfig**](../../../../org/apache/struts/config/class-use/FormBeanConfig.html.md#org.apache.struts.validator)**                                                                             
            A JavaBean representing the configuration information of a `<form-bean>` element in a Struts configuration file.                                                                           |
| **[**ModuleConfig**](../../../../org/apache/struts/config/class-use/ModuleConfig.html.md#org.apache.struts.validator)**                                                                                 
            The collection of static configuration information that describes a Struts-based module.                                                                                                   |

 

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
<td align="left"><a href="../../../../index.html.md?org/apache/struts/config/package-use.html"><strong>FRAMES</strong></a>    <a href="package-use.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
