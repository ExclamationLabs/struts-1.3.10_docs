<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](../images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](../2.x/) | [Struts 1](../1.x/)

------------------------------------------------------------------------

##### Struts 1

-   [Welcome](../index.html.md)
-   [Learning](../learning.html.md)
-   [Roadmap](../roadmap.html.md)
-   [Releases](../downloads.html.md)

##### Documentation

-   **User Guide**
-   [FAQs and HOWTOs](../faqs/index.html.md)
-   [Release Notes](../userGuide/release-notes.html.md)
-   [Javadoc](../apidocs/index.html.md)
-   [DTDDoc](../dtddoc/index.html.md)

##### Support

-   [User Mailing List](../mail.html.md)
-   [Issue Tracker (JIRA)](http://issues.apache.org/struts/)
-   [Wiki Pages](http://wiki.apache.org/struts/)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Project Documentation

-   [Project Information](../project-info.html.md)
-   [Project Reports](../project-reports.html.md)

[![Built by Maven](../images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Table_of_Contents"></span>Table of Contents
-----------------------------------------------------

-   [1. Introduction](introduction.html.md)
    -   [1.1 Forward into the Past!](introduction.html.md#history)
    -   -   [1.2.1 The Model: System State and Business Logic JavaBeans](introduction.html.md#modelConcepts)
        -   [1.2.2 The View: JSP Pages and Presentation Components](introduction.html.md#presentationConcepts)
        -   [1.2.3 The Controller: ActionServlet and ActionMapping](introduction.html.md#controllerConcepts)
    -   [1.3 Control Flow](introduction.html.md#flow)

-   [2. Building Model Components](building_model.html.md)
    -   [2.1 Overview](building_model.html.md#overview)
    -   [2.2 JavaBeans and Scope](building_model.html.md#javabeans)
    -   [2.3 ActionForm Beans](building_model.html.md#actionform)
    -   [2.4 System State Beans](building_model.html.md#system_state)
    -   [2.5 Business Logic Beans](building_model.html.md#business_logic)
-   [3. Building View Components](building_view.html.md)
    -   [3.1 Overview](building_view.html.md#overview)
    -   [3.2 Internationalization](building_view.html.md#i18n)
    -   [3.3 Forms and FormBean Interactions](building_view.html.md#form_beans)
        -   [3.3.1 Automatic Form Population](building_view.html.md#form_population)
        -   [3.3.2 Automatic Form Validation](building_view.html.md#form_validation)
        -   [3.3.3 The Struts Validator](building_view.html.md#validator)
        -   [3.3.4 Page Composition With Tiles](building_view.html.md#Tiles)
    -   [3.4 Presentation Frameworks](building_view.html.md#presentation_frameworks)
    -   [3.4 Direct Presentation Techniques](building_view.html.md#other_presentations)
        -   [3.4.1 Image Rendering Components](building_view.html.md#image_rendering)
        -   [3.4.2 Rendering Text](building_view.html.md#text_rendering)
-   [4. Building Controller Components](building_controller.html.md)
    -   [4.1 Overview](building_controller.html.md#overview)
    -   [4.2 The ActionServlet](building_controller.html.md#action_servlet)
        -   [4.2.1 Request Processor](building_controller.html.md#request_processor)
    -   [4.3 ActionForm Classes](building_controller.html.md#action_form_classes)
        -   [4.3.1 DynaActionForm Classes](building_controller.html.md#dyna_action_form_classes)
        -   [4.3.2 LazyActionForm Classes](building_controller.html.md#lazy_action_form_classes)
        -   [4.3.3 Map-backed ActionForm Classes](building_controller.html.md#map_action_form_classes)
    -   [4.4 Action Classes](building_controller.html.md#action_classes)
        -   [4.4.1 Action Class Design Guidelines](building_controller.html.md#action_design_guide)
    -   [4.5 Exception Handler](building_controller.html.md#exception_handler)
    -   [4.6 Plugin Classes](building_controller.html.md#plugin_classes)
    -   [4.7 The ActionMapping Implementation](building_controller.html.md#actionmapping)
    -   [4.8 Writing ActionMappings](building_controller.html.md#config)
        -   [4.8.1 ActionMapping Example](building_controller.html.md#action_mapping_example)
    -   [4.9 Using ActionMappings for Pages](building_controller.html.md#module_config-use_actions)
    -   [4.10 Using Wildcards in ActionMappings](building_controller.html.md#action_mapping_wildcards)
    -   [4.11 Using The Commons Logging Interface](building_controller.html.md#logging)
-   [5. Configuring Applications](configuration.html.md)
    -   [5.1 Overview](configuration.html.md#config-overview)
    -   [5.2 The Configuration File](configuration.html.md#struts-config)
        -   [5.2.1 Controller Configuration](configuration.html.md#controller_config)
        -   [5.2.2 Message Resources Configuration](configuration.html.md#resources_config)
        -   [5.2.3 PlugIn Configuration](configuration.html.md#plugin_config)
    -   [5.3 Configuring your application for modules](configuration.html.md#dd_config_modules)
        -   [5.3.1 Module Configuration Files](configuration.html.md#module_config-files)
        -   [5.3.2 Informing the Controller](configuration.html.md#module_config-inform_controller)
        -   [5.3.3 Switching Modules](configuration.html.md#module_config-switching)
    -   [5.4 The Web Application Deployment Descriptor](configuration.html.md#dd_config)
        -   [5.4.1 Configure the Action Servlet Instance](configuration.html.md#dd_config_servlet)
        -   [5.4.2 Configure the Action Servlet Mapping](configuration.html.md#dd_config_mapping)
        -   [5.4.3 Configure Struts Taglib"](configuration.html.md#dd_config_taglib)
    -   [5.5 Add Framework Components To Your Application](configuration.html.md#config_add)
    -   [5.6 Logging](configuration.html.md#config_logging)
-   6. Getting Started
    -   [6.1 Release Notes](release-notes.html.md)
        -   [Release Notes 1.3.7](release-notes-1_3_7.html.md)*(Beta)*
        -   [Release Notes 1.3.6](release-notes-1_3_6.html.md)*(Test Build)*
        -   [Release Notes 1.3.5](release-notes-1_3_5.html.md)
        -   [Release Notes 1.3.3](release-notes-1_3_3.html.md)*(Test Build)*
        -   [Release Notes 1.3.2](release-notes-1_3_2.html.md)
        -   [Release Notes 1.3.1](release-notes-1_3_1.html.md)*(Test Build)*
        -   [Release Notes 1.2.9](release-notes-1_2_9.html.md)
        -   [Release Notes 1.2.8](release-notes-1_2_8.html.md)
        -   [Release Notes 1.2.7](release-notes-1_2_7.html.md)
        -   [Release Notes 1.2.4](release-notes-1_2_4.html.md)
        -   [Release Notes 1.1](release-notes-1_1.html.md)
        -   [Release Notes 1.1-rc2](release-notes-1_1-rc2.html.md)
        -   [Release Notes 1.1-rc1](release-notes-1_1-rc1.html.md)
        -   [Release Notes 1.1-b3](release-notes-1_1-b3.html.md)
        -   [Release Notes 1.1-b2](release-notes-1_1-b2.html.md)
        -   [Release Notes 1.1-b1](release-notes-1_1-b1.html.md)
    -   [6.2 Installation](installation.html.md)
        -   [iPlanet](installation-ip.html.md)
        -   [Portal Application Server](installation-ipas.html.md)
        -   [Jetty](installation-jetty.html.md)
        -   [JRun 3.0](installation-jr30.html.md)
        -   [Orion Application Server](installation-oas.html.md)
        -   [SilverStream Application Server 3.7.1 and later](installation-sas.html.md)
        -   [Tomcat with Apache](installation-tc.html.md)
        -   [Bluestone Universal Business Server 7.2](installation-ubs72.html.md)
        -   [WebSphere Application Server 3.5 FixPack 2](installation-was352.html.md)
        -   [WAS with the Example Applcation](installation-was352-x.html.md)
        -   [Weblogic 5.1 sp8](installation-wls5.html.md)

Next: [Introduction](introduction.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


