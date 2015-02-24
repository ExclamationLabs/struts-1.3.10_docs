<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts EL

-   **Welcome**

##### Reference

-   [Bean EL](tagreference.html.md#struts-bean-el.tld)
-   [HTML EL](tagreference.html.md#struts-html-el.tld)
-   [Logic EL](tagreference.html.md#struts-logic-el.tld)
-   [Tiles EL](tagreference.html.md#struts-tiles-el.tld)
-   [Javadoc](apidocs/index.html.md)

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

<span id="Welcome_to_Struts_EL"></span>Welcome to Struts EL
-----------------------------------------------------------

<span id="welcome"></span>
Struts EL is an extension of the Struts Taglib component that uses JSTL (the JavaServer Pages Standard Tag Library) as a foundation technology. Each JSP custom tag in this library is a JSTL-aware subclass of a corresponding tag in Struts Taglib. Since JSTL is a prerequisite, only those tags without a JSTL corrollary were ported to Struts EL.

Since this component utilizes JSTL, the JSTL expression language ("EL"), and Struts Taglib, an understanding of all three is a prerequisite.

<span id="Evaluating_Expressions"></span>Evaluating Expressions
---------------------------------------------------------------

Unlike the Struts Taglib component, Struts EL does not use runtime scriptlet expressions ("rtexprvalues"), EL uses the expression evaluation engine in the Jakarta Taglibs implementation of JSTL (version 1.0) to evaluate attribute values.

The base Struts Taglib contains tags which rely on the evaluation of "rtexprvalue"s to render dynamic attribute values. For instance, to print a message from a properties file based on a resource key, you would use the `bean:write` tag, perhaps like this:

                    <bean:message key='<%= stringvar %>'/>
                

This assumes that `stringvar` exists as a JSP scripting variable. If you're using the **Struts-EL** library, the reference looks very similar, but slightly different, like this:

                    <bean-el:message key="${stringvar}"/>
                

<span id="Tag_Mapping"></span>Tag Mapping
-----------------------------------------

In implementing the Struts-EL library, every Struts tag that provides a feature that is not covered by the JSTL (1.0) library is mapped into the Struts-EL library. This section reviews which Struts tags are NOT implemented in the Struts-EL library, and which JSTL tags provide that feature. (See the [reference](tagreference.html.md) for the tags that are implemented.)

Many of the non-porting decisions were based on the fact that the JSTL expression language itself provides the same functionality. In those cases, in addition to a possible JSTL tag name, the symbol "EL" will be listed.

### <span id="Bean_Tag_Library_Tags_NOT_Implemented_in_Struts-EL"></span>Bean Tag Library Tags NOT Implemented in Struts-EL

| Struts Tag | JSTL Tag  |
|------------|-----------|
| cookie     | c:set, EL |
| define     | c:set, EL |
| header     | c:set, EL |
| include    | c:import  |
| parameter  | c:set, EL |
| write      | c:out     |

### <span id="Logic_Tag_Library_Tags_NOT_Implemented_in_Struts-EL"></span>Logic Tag Library Tags NOT Implemented in Struts-EL

| Struts Tag   | JSTL Tag         |
|--------------|------------------|
| empty        | c:if, c:when, EL |
| equal        | c:if, c:when, EL |
| greaterEqual | c:if, c:when, EL |
| greaterThan  | c:if, c:when, EL |
| lessEqual    | c:if, c:when, EL |
| lessThan     | c:if, c:when, EL |
| notEmpty     | c:if, c:when, EL |
| notEqual     | c:if, c:when, EL |

(Note that the "iterate" tag was originally ported, even with the presence of the "c:forEach" tag, as the "indexed tag" functionality was not supported when using "c:forEach" instead of "logic:iterate". This has since been rectified, such that the "indexed tag" functionality checks for being contained in a "c:forEach" tag, in addition to the "logic:iterate" tag. However, the ported "iterate" tag has not been removed from Struts-EL, for backward compatibility.)

### <span id="Html_Tag_Library_Tags_NOT_Implemented_in_Struts-EL"></span>Html Tag Library Tags NOT Implemented in Struts-EL

None (all of them were ported).

<span id="Attribute_Mapping"></span>Attribute Mapping
-----------------------------------------------------

At this point of the implementation, there is only one change (to two similar tags) to the set of attributes between the Struts tags, and the Struts-EL tags. The "logic:match" and "logic:notMatch" tags have an additional attribute named "expr", which can take any value, and will be used as the value to compare against, in addition to the choices of "cookie", "header", "name"/"property", and "parameter".

<span id="Usage_Requirements"></span>Usage Requirements
-------------------------------------------------------

The Struts-EL tag library requires the use of the Struts tag library, and the Java Server Pages Standard Tag Library. It is not necessary for JSP pages using the Struts-EL tag library to also use the Struts tags or the JSTL tags, but the Struts and JSTL tag libraries need to be part of the application utilizing the Struts-EL tag library.

This is because the Struts-EL tag classes are all subclasses of Struts tag classes, and their implementation uses classes provided by the JSTL.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


