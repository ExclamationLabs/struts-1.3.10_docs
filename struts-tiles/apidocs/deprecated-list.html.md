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
<td align="left"> <strong>Deprecated</strong> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?deprecated-list.html"><strong>FRAMES</strong></a>    <a href="deprecated-list.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

**Deprecated API**
------------------

------------------------------------------------------------------------

**Contents**

-   [Deprecated Interfaces](#interface)
-   [Deprecated Classes](#class)
-   [Deprecated Fields](#field)
-   [Deprecated Methods](#method)

<span id="interface"></span>

| **Deprecated Interfaces**                                                                                                                              |
|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| [org.apache.struts.tiles.ComponentDefinitionsFactory](org/apache/struts/tiles/ComponentDefinitionsFactory.html.md "interface in org.apache.struts.tiles") 
            *Use DefinitionsFactory instead.*                                                                                                            |

 

<span id="class"></span>

| **Deprecated Classes**                                                                                                                                                                                                                                |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [org.apache.struts.tiles.taglib.AttributeToScopeTag](org/apache/struts/tiles/taglib/AttributeToScopeTag.html.md "class in org.apache.struts.tiles.taglib")                                                                                               
            *Is it still in use ?*                                                                                                                                                                                                                      |
| [org.apache.struts.tiles.DefinitionsUtil](org/apache/struts/tiles/DefinitionsUtil.html.md "class in org.apache.struts.tiles")                                                                                                                            
            *Use [`TilesUtil.createDefinitionsFactory(ServletContext, DefinitionsFactoryConfig)`](org/apache/struts/tiles/TilesUtil.html.md#createDefinitionsFactory(javax.servlet.ServletContext,%20org.apache.struts.tiles.DefinitionsFactoryConfig))*   |

 

<span id="field"></span>

| **Deprecated Fields**                                                                                                                                                    |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [org.apache.struts.tiles.DefinitionsUtil.NO\_DEBUG](org/apache/struts/tiles/DefinitionsUtil.html.md#NO_DEBUG)                                                               
            *This will be removed in a release after Struts 1.2.*                                                                                                          |
| [org.apache.struts.tiles.DefinitionsFactoryConfig.PARSER\_DETAILS\_PARAMETER\_NAME](org/apache/struts/tiles/DefinitionsFactoryConfig.html.md#PARSER_DETAILS_PARAMETER_NAME) 
            *This will be removed in a release after Struts 1.2.*                                                                                                          |
| [org.apache.struts.tiles.taglib.InsertTag.ROLE\_DELIMITER](org/apache/struts/tiles/taglib/InsertTag.html.md#ROLE_DELIMITER)                                                 
            *This will be removed in a release after Struts 1.2.*                                                                                                          |
| [org.apache.struts.tiles.DefinitionsFactoryConfig.TILES\_DETAILS\_PARAMETER\_NAME](org/apache/struts/tiles/DefinitionsFactoryConfig.html.md#TILES_DETAILS_PARAMETER_NAME)   
            *This will be removed in a release after Struts 1.2.*                                                                                                          |
| [org.apache.struts.tiles.DefinitionsUtil.userDebugLevel](org/apache/struts/tiles/DefinitionsUtil.html.md#userDebugLevel)                                                    
            *This will be removed in a release after Struts 1.2.*                                                                                                          |

 

<span id="method"></span>

| **Deprecated Methods**                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [org.apache.struts.tiles.DefinitionsUtil.createDefinitionsFactory(ServletContext, Map, String)](org/apache/struts/tiles/DefinitionsUtil.html.md#createDefinitionsFactory(javax.servlet.ServletContext,%20java.util.Map,%20java.lang.String))                                                                                                           
            *Use createDefinitionsFactory(ServletContext servletContext, ServletConfig servletConfig)*                                                                                                                                                                                                                                                |
| [org.apache.struts.tiles.DefinitionsUtil.getDefinitionsFactory(ServletContext)](org/apache/struts/tiles/DefinitionsUtil.html.md#getDefinitionsFactory(javax.servlet.ServletContext))                                                                                                                                                                   
            *Use [`TilesUtil.getDefinitionsFactory(ServletRequest, ServletContext)`](org/apache/struts/tiles/TilesUtil.html.md#getDefinitionsFactory(javax.servlet.ServletRequest,%20javax.servlet.ServletContext))*                                                                                                                                     |
| [org.apache.struts.tiles.ControllerSupport.perform(ComponentContext, HttpServletRequest, HttpServletResponse, ServletContext)](org/apache/struts/tiles/ControllerSupport.html.md#perform(org.apache.struts.tiles.ComponentContext,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20javax.servlet.ServletContext)) 
            *Use execute() instead. This will be removed after Struts 1.2.*                                                                                                                                                                                                                                                                           |
| [org.apache.struts.tiles.Controller.perform(ComponentContext, HttpServletRequest, HttpServletResponse, ServletContext)](org/apache/struts/tiles/Controller.html.md#perform(org.apache.struts.tiles.ComponentContext,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse,%20javax.servlet.ServletContext))               
            *Use execute() instead. This will be removed after Struts 1.2.*                                                                                                                                                                                                                                                                           |
| [org.apache.struts.tiles.actions.DefinitionDispatcherAction.printError(HttpServletResponse, String)](org/apache/struts/tiles/actions/DefinitionDispatcherAction.html.md#printError(javax.servlet.http.HttpServletResponse,%20java.lang.String))                                                                                                        
            *This will be removed after Struts 1.2.*                                                                                                                                                                                                                                                                                                  |
| [org.apache.struts.tiles.taglib.InsertTag.InsertHandler.processException(Throwable, String)](org/apache/struts/tiles/taglib/InsertTag.InsertHandler.html.md#processException(java.lang.Throwable,%20java.lang.String))                                                                                                                                 
            *This method will be removed in a release after Struts 1.2.*                                                                                                                                                                                                                                                                              |
| [org.apache.struts.tiles.TilesRequestProcessor.processTilesDefinition(String, boolean, HttpServletRequest, HttpServletResponse)](org/apache/struts/tiles/TilesRequestProcessor.html.md#processTilesDefinition(java.lang.String,%20boolean,%20javax.servlet.http.HttpServletRequest,%20javax.servlet.http.HttpServletResponse))                         
            *use processTilesDefinition(definitionName, request, response) instead. This method will be removed in a version after 1.3.0.*                                                                                                                                                                                                            |

 

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
<td align="left"> <strong>Deprecated</strong> </td>
<td align="left"><a href="index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> PREV   NEXT</td>
<td align="left"><a href="index.html.md?deprecated-list.html"><strong>FRAMES</strong></a>    <a href="deprecated-list.html"><strong>NO FRAMES</strong></a>    
<a href="allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
