<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Taglib

-   [Welcome](index.html.md)

##### FAQs and HOWTOs

-   [Taglib FAQ](faq.html.md)
-   [Building View Components](building_view.html.md)
-   [Indexed Properties](indexedprops.html.md)

##### Struts Taglib Guides

-   [Bean](dev_bean.html.md)
-   [HTML](dev.html.md.html)
-   [Logic](dev_logic.html.md)
-   [Nested](dev_nested.html.md)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Related Resources

-   [Display Tag](http://displaytag.sourceforge.net/)
-   .html.md2](http://www.rabago.net/struts/html2/)
-   [JSTL](http://java.sun.com/products/jsp/jstl/)
-   [JSF](http://java.sun.com/j2ee/javaserverfaces/)
-   [Struts Layout](http://struts.application-servers.com)
-   [Struts Menu](http://struts-menu.sourceforge.net/)

##### Quick Links

-   [Javadoc](apidocs/index.html.md)
-   [Struts 1](../index.html.md)

##### Project Documentation

-   [Project Information](project-info.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="Secure_Socket_Layer_and_Web_Applications"></span>Secure Socket Layer and Web Applications
---------------------------------------------------------------------------------------------------

<span id="overview"></span>
### <span id="Overview"></span>Overview

Many web applications, especially those deployed for e-commerce, necessitate the transmission of sensitive data between the web server and the client browser. This data may include passwords, credit card numbers, bank account numbers or any other information that users would not want to divulge to the general public. To protect sensitive data during transmission, application developers typically use the Secure Sockets Layer (SSL) and its companion protocol, HTTP over Secure Sockets Layer (HTTPS). HTTPS employs SSL to protect data by encrypting it at the source, be it the server or the client, and decrypting it at the destination. This prevents anyone monitoring Internet data transmissions from easily capturing this data. The client and server exchange public keys to enable encryption and decryption to occur.

The encryption/decryption process comes at a performance price, however. The throughput of data for a web server transmitting via HTTPS is often as little as one-tenth that of data transmission via HTTP. For this reason, it is undesirable to deploy an entire web application under SSL. For fastest performance, it is best to deploy a web application under HTTP and employ HTTPS only for those pages and processes that transmit sensitive data.

<span id="mixing"></span>
### <span id="Mixing_Protocols_in_Web_Applications"></span>Mixing Protocols in Web Applications

Switching back and forth between the two protocols can require hard-coding the protocol and full URL in every link to each resource in the web application. This creates an ongoing maintenance headache for developers each time a server name changes or secure protocol requirements change for resources in the web app.

Another significant hazard is that there is nothing to prevent a user from specifying the wrong protocol by manually entering a URL into the browser. The penalty for manually specifying HTTPS for a page or servlet that does not require HTTPS is reduced performance. Far worse is the penalty for manually specifying HTTP for non-secure access of a page that does require HTTPS: public exposure of sensitive data.

<span id="help"></span>
### <span id="Help_from_Deployment_Descriptor"></span>Help from Deployment Descriptor

To help overcome the problem of non-secure access of sensitive data, the Java Servlet Specification (versions 2.2 and 2.3) defines the transport-guarantee element of the web.xml deployment descriptor file. The transport-guarantee element must specify one of three types of protection for communication between client and server: NONE, INTEGRAL, or CONFIDENTIAL. For most containers a specification of INTEGRAL or CONFIDENTIAL is treated as a requirement for SSL usage. Web application containers will prevent users from accessing web resources over HTTP if they have been so specified.

The implementation for blocking HTTP access to web resources specified as INTEGRAL or CONFIDENTIAL varies from container to container. If a user attempts to access such a resource over HTTP, some containers will present that user with an error message instructing them to use the HTTPS protocol for accessing the requested resource. Other containers will actually redirect the request using the HTTPS protocol, but then continue using the HTTPS protocol for all subsequent requests, even those for resources with a transport-guarantee specification of NONE.

<span id="sslext"></span>
### <span id="The_sslext_Extension"></span>The sslext Extension

An extension to version 1.1, named sslext, helps solve many of the HTTP/HTTPS switching issues. It extends the ActionConfig class, RequestProcessor, and Plugin classes to define a framework where developers may specify the transmission protocol behavior for Struts applications. Within the Struts configuration file, developers specify which action requests require HTTPS transmission and which should use HTTP. Developers can also specify whether to redirect "improperly-protocoled" requests to the correct protocol.

In addition to these extensions, the \.html.md:link\> and the \<html:form\> tags have been extended. In these extensions, the Struts actions specified in either of these tags are analyzed to determine the protocol that should be used in requesting that action. The HTML generated by these tags will specify the proper protocol. An additional custom tag is defined for allowing users to specify the transmission protocol for an individual JSP. This is most often used for form-based authentication pages.

The sslext library may be obtained from <http://sslext.sourceforge.net>

<span id="legacy"></span>
### <span id="Legacy_Browser_Issue"></span>Legacy Browser Issue

One additional complication faced by developers of web applications is that some browsers (e.g. pre-6.0 versions of Netscape Navigator) will treat requests to different protocols and ports on the same server as requests to different domains. This causes these browsers to initiate a new session each time a different protocol or port is specified in a request. This problem can only be solved at the container level. Some containers have a "session domain" or "cookie domain" configuration parameter to allow the session to be shared across different servers in the same domain. As an example, the Weblogic Server has a "CookieDomain" property configured in its weblogic.xml deployment descriptor. Thankfully, the effects of this problem are diminishing as people upgrade their browsers to the current versions.

<span id="containers"></span>
### <span id="Configuring_Containers_for_SSL"></span>Configuring Containers for SSL

The procedure for configuring SSL for a container will be specific to that container. The procedure for enabling SSL for Tomcat can be found [here](http://tomcat.apache.org/tomcat-5.5-doc/ssl-howto.html.md) .

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


