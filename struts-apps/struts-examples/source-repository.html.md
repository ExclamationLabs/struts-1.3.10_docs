<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](../../images/struts.gif)](../../)</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](../2.x/) | [Struts 1](../1.x/) | [Apache](http://www.apache.org) | [Struts 1](../../1.x/) | [Struts 2](../../2.x/)

------------------------------------------------------------------------

##### Struts Apps

-   [Welcome](index.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Quick Links

-   [Apache Struts Home](../../)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
    -   [About](index.html.md)
    -   [Continuous Integration](integration.html.md)
    -   [Dependencies](dependencies.html.md)
    -   [Dependency Convergence](dependency-convergence.html.md)
    -   [Issue Tracking](issue-tracking.html.md)
    -   [Mailing Lists](mail-lists.html.md)
    -   [Plugin Management](plugin-management.html.md)
    -   [Project License](license.html.md)
    -   [Project Plugins](plugins.html.md)
    -   [Project Summary](project-summary.html.md)
    -   [Project Team](team-list.html.md)
    -   **Source Repository**
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

Overview
--------

This project uses [Subversion](http://subversion.tigris.org/) to manage its source code. Instructions on Subversion use can be found at <http://svnbook.red-bean.com/>.

Web Access
----------

The following is a link to the online source repository.

    http://svn.apache.org/repos/asf/struts/struts1/trunk/apps/examples/

Anonymous access
----------------

The source can be checked out anonymously from SVN with this command:

    $ svn checkout http://svn.apache.org/repos/asf/struts/struts1/trunk/apps/examples/ struts-examples

Developer access
----------------

Everyone can access the Subversion repository via HTTP, but Committers must checkout the Subversion repository via HTTPS.

    $ svn checkout https://svn.apache.org/repos/asf/struts/struts1/trunk/apps/examples/ struts-examples

To commit changes to the repository, execute the following command to commit your changes (svn will prompt you for your password)

    $ svn commit --username your-username -m "A message"

Access from behind a firewall
-----------------------------

For those users who are stuck behind a corporate firewall which is blocking HTTP access to the Subversion repository, you can try to access it via the developer connection:

    $ svn checkout https://svn.apache.org/repos/asf/struts/struts1/trunk/apps/examples/ struts-examples

Access through a proxy
----------------------

The Subversion client can go through a proxy, if you configure it to do so. First, edit your "servers" configuration file to indicate which proxy to use. The file's location depends on your operating system. On Linux or Unix it is located in the directory "~/.subversion". On Windows it is in "%APPDATA%\\Subversion". (Try "echo %APPDATA%", note this is a hidden directory.)

There are comments in the file explaining what to do. If you don't have that file, get the latest Subversion client and run any command; this will cause the configuration directory and template files to be created.

Example: Edit the 'servers' file and add something like:

    [global]
    http-proxy-host = your.proxy.name
    http-proxy-port = 3128

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


