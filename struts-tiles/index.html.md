<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Tiles

-   **Welcome**
-   [FAQ](faq.html.md)
-   [Installation](installation.html.md)
-   [User Guide](userGuide.html.md)
-   [Creating Templates](examples.html.md)
-   [Taglib Reference](tagreference.html.md)

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

<span id="Welcome_To_Struts_Tiles"></span>Welcome To Struts Tiles
-----------------------------------------------------------------

Welcome to the Struts Tiles component.Tiles is a templating system. (Include on steriods.) It can be used to create a common look and feel for a web application. Tiles can also be used to create reusable view components. This site will help you get started with Tiles.

Tiles can also be used without Struts. A new release of Tiles, Tiles 2, is being prepared. If you would like to use Tiles without Struts, see the new [Apache Tiles 2 project.](http://tiles.apache.org/) The focus of this site is using Tiles *with* Struts.

<span id="Tiles_Features"></span>Tiles Features
-----------------------------------------------

-   Screen definitions
    -   Create a screen by assembling ***Tiles*** : header, footer, menu, body, etc.
    -   Definitions can take place :
        -   in a centralized XML file
        -   directly in JSP pages
        -   programatically in Actions
    -   Definitions provide an inheritance mechanism : a definition can extend another one, and override parameters.
-   Layouts
    -   Define common page layouts and reuse them across your website.
    -   Define menu layouts, and use them by passing lists of items and links.
    -   Define a portal layout, use it by passing a list of ***Tiles*** (pages) to show.
    -   Reuse existing layouts, or define your own.
-   Dynamic page building
    -   Tiles can be gathered dynamically during page reload. It is possible to change any attribute: layout, list of Tiles in portal, list of menu items, etc.
-   Reuse of ***Tiles*** / Components
    -   If well defined, a ***Tile*** can be reused across multiple applications.
    -   Dynamic attributes are used to parameterize ***Tiles***.
    -   It is possible to define a library of reusable ***Tiles***.
    -   Build a page by assembling predefined components, giving them appropriate parameters.
-   Internationalization (i18n)
-   -   It is possible to load different tiles according to Locale.
    -   A mechanism similar to Java properties files is used for definitions files: you can have one definition file per Locale. The appropriate definition is loaded according to the current Locale.
-   Multi-channels
-   -   It is possible to load different Tiles according to a key.
    -   For example, the key could represent user privileges, browser type, arbitrary name stored in session, etc.
    -   A mechanism similar to Java properties files is used for definitions files: you can have one definition file per key. The appropriate definition is loaded according to the key.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


