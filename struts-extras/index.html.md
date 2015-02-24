<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Extras

-   **Welcome**

##### FAQs and HOWTOs

-   [Dispatching And Validating](dispatchValidator.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Welcome_to_Struts_Extras"></span>Welcome to Struts Extras
-------------------------------------------------------------------

<span id="welcome"></span>
Struts Extras provides several popular but non-essential classes, including:

ActionDispatcher
An Action helper class that dispatches to a public method in an Action.
BaseAction
BaseAction is provided as an intermediate class for shared funtionality between Action and any stock implementation provided in this package.
DigestingPlugIn
An implementation of PlugIn which can be configured to instantiate a graph of objects using the Commons Digester and place the root object of that graph into the Application context.
DispatchAction
This Action is useful for developers who prefer to combine many similar actions into a single Action class, in order to simplify their application design.
DownloadAction
This is an abstract base class that minimizes the amount of special coding that needs to be written to download a file.
DynaValidatorActionForm
This class differs from the core DynaValidatorForm in that the key passed into the validator is the action element's 'path' attribute from the struts-config.xml which should match the form element's name attribute in the validation.xml.
EventActionDispatcher
An Action helper class that dispatches to to one of the public methods that are named in the parameter attribute of the corresponding ActionMapping and matches a submission parameter.
EventDispatchAction
An Action that dispatches to to one of the public methods that are named in the parameter attribute of the corresponding ActionMapping and matches a submission parameter
ForwardAction
An Action that forwards to the context-relative URI specified by the parameter property of our associated ActionMapping.
IncludeAction
An Action that includes the context-relative URI specified by the parameter property of our associated ActionMapping.
LocaleAction
Implementation of Action that changes the user's Locale and forwards to a page, based on request level parameters that are set (language, country, and page).
LookupDispatchAction
An abstract Action that dispatches to the subclass mapped execute method. This is useful in cases where an HTML form has multiple submit buttons with the same name
MappingDispatchAction
An abstract Action that dispatches to a public method that is named by the parameter attribute of the corresponding ActionMapping.
ModuleConfigVerifier
Convenient implementation of PlugIn that performs as many verification tests on the information stored in the ModuleConfig for this module as is practical.
SwitchAction
A standard Action that switches to a new module and then forwards control to a URI (specified in a number of possible ways) within the new module.
ValidatorActionForm
This class differs from the core ValidatorForm in that the key passed into the validator is the action element's 'path' attribute from the struts-config.xml which should match the form element's name attribute in the validation.xml.
Many of the "extra" classes are simple, and the easiest way to learn how to use one of them, can be to review the [Javadocs](apidocs/index.html.md) and [source code.](http://svn.apache.org/viewvc/struts/struts1/trunk/extras/src/main/java/org/apache/struts/)

> Note that there is not an "extras" package, per se. Each of the "extra" classes uses a relevant package from the core distribution, such as Action, Plugins, or Validator.

In some cases, you may like to use these classes as a starting point for your own custom versions. In that case, feel free to adopt and adapt the source, following the provisions of the [Apache License.](http://www.apache.org/licenses/)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


