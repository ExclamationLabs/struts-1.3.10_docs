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
-   **Indexed Properties**

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

<span id="Indexed_Properties_Mapped_Properties_and_Indexed_Tags"></span>Indexed Properties, Mapped Properties, and Indexed Tags
-------------------------------------------------------------------------------------------------------------------------------

### <span id="Introduction"></span>Introduction

The JSP specification discusses using "indexed properties" in reference to the \<jsp:setProperty\> tag. However, none of the support provided in the base JSP specification actually deals with the "indexing" part. In truth, it allows for setting "array properties", but it doesn't do much for setting or even getting the actual values in each entry of the array, except with explicit JSP expressions (\<%= %\>).

The framework provides much more powerful features related to indexed properties, but in truth most of the heavy lifting is not even in the framework, but in the Commons Beanutils package. This package is used by the framework to provide this functionality. You can see the javadoc documentation for the Beanutils package at <http://commons.apache.org/beanutils/api/index.html.md> . The information particularly related to indexed properties is in the package description for the org.apache.commons.beanutils package. This article mirrors that information, but focuses on how this functionality is mapped to JSP tags using the Struts tag library.

The support for indexed properties also includes "mapped properties", "nested properties" and "indexed tags", which are all related but slightly different. The latter is exclusive to the framework, but the first two are also provided by the Beanutils package. This article will cover all three of these topics.

### <span id="Indexed_Properties"></span>Indexed Properties

The simplest demonstration of using indexed properties can be shown with the following simple bean and JSP page:

                        package org.apache.struts.webapp.exercise;
                        import org.apache.struts.action.ActionForm;
                        public class StringBean extends ActionForm {
                        private String strAry[] = { "String 0", "String 1",
                        "String 2", "String 3", "String 4" };

                        public String getStringIndexed(int index) {
                        return strAry[index];
                        }

                        public void setStringIndexed(int index, String value) {
                        strAry[index] = value;
                        }
                        }

First note the two methods in the StringBean class, "getStringIndexed()" and "setStringIndexed()". Note that the "get" method takes an "int" and the "set" method takes an "int" and "String". The Beanutils package and the framework recognizes this arrangement of signatures as an "indexed property", in this case with the property name "stringIndexed".

                        <!-- indexedtest.jsp -->
                        <%@ taglib uri="/WEB-INF/struts-bean.tld" prefix="bean"
                        %>
                        <jsp:useBean id="bean"
                        class="org.apache.struts.webapp.exercise.StringBean"/>
                        <bean:write name="bean" property="stringIndexed[1]"/>

Note the property value of "stringIndexed[1]". This is intended to reference the indexed property "stringIndexed", and the 1st (zero-based) entry of whatever array or collection which the indexed property represents.

As you might be able to guess, when this page is executed, it will print just the string "String 1", which is the corresponding array entry at that index value.

This is a simple demonstration of what indexed properties can provide.

### <span id="List-Backed_Indexed_Properties"></span>List-Backed Indexed Properties

A variation on indexed properties are properties whose type is `java.util.List` or a subclass.

For instance, the first example using "StringBean.java" and "indexedtest.jsp" could use a modified "StringBean.java" class, like this:

                        package org.apache.struts.webapp.exercise;
                        import org.apache.struts.action.ActionForm;
                        public class StringBean2 extends ActionForm {
                        private String strAry[] = { "String 0", "String 1",
                        "String 2", "String 3", "String 4" };

                        public java.util.List getStringIndexed() {
                        return java.util.Arrays.asList(strAry);
                        }
                        }

Note the different implementation of the "getStringIndexed()" method, returning a List instead of a String. If this bean class is substituted with the original "indexedtest.jsp", the result will be identical.

### <span id="Mapped_Properties"></span>Mapped Properties

The idea of "mapped properties" as opposed to "indexed properties" is that the property represents a "map" type, as opposed to an array or collection type. The signature of the "get" and "set" methods for a mapped property are different from the same methods for an indexed property. In particular, instead of an "int" for the index, there is a "String" for the key.

The previous example for indexed properties can be changed to the following to demonstrate mapped properties:

                        package org.apache.struts.webapp.exercise;
                        import java.util.HashMap;
                        import org.apache.struts.action.ActionForm;
                        public class StringBean3 extends ActionForm {
                        private String strAry[] = { "String 0", "String 1",
                        "String 2", "String 3", "String 4" };

                        private HashMap map = new HashMap();

                        public StringBean() {
                        map.put("zero", strAry[0]);
                        map.put("one", strAry[1]);
                        map.put("two", strAry[2]);
                        map.put("three", strAry[3]);
                        map.put("four", strAry[4]);
                        }

                        public Object getStringMapped(String key) {
                        return map.get(key);
                        }

                        public void setStringMapped(String key, Object value) {
                        map.put(key, value);
                        }
                        }

Note the "get" and "set" methods to represent the mapped property.

                        <!-- indexedtest3.jsp -->
                        <%@ taglib uri="/WEB-INF/struts-bean.tld" prefix="bean"
                        %>
                        <jsp:useBean id="bean"
                        class="org.apache.struts.webapp.exercise.StringBean"/>
                        <bean:write name="bean" property="stringMapped(two)"/>

Note the property value of "stringMapped(two)". This will reference the mapped property "stringMapped", using the key value of "two".

When this page is executed, it will print just the string "String 2", which is the string stored in the HashMap with the key "two".

### <span id="Nested_Properties"></span>Nested Properties

Nested properties allows you to combine normal properties, indexed properties, and mapped properties in a hierarchical fashion. A property value of a bean does not have to be a primitive like "int" or "String. The property value can be a bean with its own properties. The following example demonstrates this.

                        package org.apache.struts.webapp.exercise;
                        import org.apache.struts.util.LabelValueBean;
                        import org.apache.struts.action.ActionForm;
                        public class StringBean4 extends ActionForm {
                        private LabelValueBean[] lvbeans;

                        public StringBean() {
                        lvbeans = new LabelValueBean[5];
                        lvbeans[0] = new LabelValueBean("Zero", 0+"");
                        lvbeans[1] = new LabelValueBean("One", 1+"");
                        lvbeans[2] = new LabelValueBean("Two", 2+"");
                        lvbeans[3] = new LabelValueBean("Three", 3+"");
                        lvbeans[4] = new LabelValueBean("Four", 4+"");
                        }

                        public LabelValueBean getLabelValue(int index) {
                        return lvbeans[index];
                        }
                        }

First note the use of the class "LabelValueBean". This is a simple class provided in the framework which represents a pair of two Strings, a "label" and a "value". It itself is a bean, providing these two properties with standard getters and setter methods.

Then, see the "getLabelValue()" method, representing the indexed property "labelValue". This class doesn't show a "setter" method. If you only ever provide read-only access a property, then it is not necessary to provide a setter method.

                        <!-- indexedtest4.jsp -->
                        <%@ taglib uri="/WEB-INF/struts-bean.tld" prefix="bean"
                        %>
                        <jsp:useBean id="bean"
                        class="org.apache.struts.webapp.exercise.StringBean"/>
                        <bean:write name="bean" property="labelValue[1].label"/>

Note here the "nested" property reference. It is first using the indexed property "labelValue" and then the "normal" property of the LabelValueBean to get the final result. When this page is executed, it will print the string "One", representing the "label" property of the 1st entry of the array represented by the "labelValue" indexed property.

### <span id="Dynamic_Indexes_for_Indexed_Properties"></span>Dynamic Indexes for Indexed Properties

People often start using indexed properties with enthusiasm, but soon become frustrated by an inconvenient reality. The reality is that the "index" for indexed properties often needs to be a dynamic value, usually from the "indexId" counter in the "\<logic:iterate\>" tag.

For instance, the following example JSP page using the same "StringBean" bean class uses a dynamic value for the index:

                        <!-- indexedtest5.jsp -->
                        <%@ taglib uri="/WEB-INF/struts.html.md.tld" prefix="html"
                        %>
                        <%@ taglib uri="/WEB-INF/struts-logic.tld"
                        prefix="logic" %>
                        .html.md>
                        <body>
                        .html.md:form action="indexedtest5.do">
                        <logic:iterate name="stringbean" property="stringArray"
                        id="foo"
                        indexId="ctr">
                        .html.md:text name="stringbean"
                        property='<%= "labelValue[" + ctr + "].label" %>' />
                        </logic:iterate>
                        .html.md:submit property="submitValue">Submit Changes</html:submit>
                        <.html.md:form>
                        </body>
                        <.html.md>

The JSP expression syntax for the `property` attribute is somewhat messy and easy to get wrong so it's something we want to avoid. One way to make this a little cleaner is to use "indexed tags", but there's a wrinkle to this approach. We'll first cover the details of indexed tags, then we'll talk about the wrinkle, and then finally an alternative to indexed tags.

### <span id="Indexed_Tags"></span>Indexed Tags

The "indexed tags" feature is provided by several tags that have an optional boolean "indexed" attribute. This is only legal when inside a "\<logic:iterate\>" tag. When the "indexed" attribute is true, then the tag will incorporate the loop index into the resulting HTML component.

The several tags that support the "indexed" attribute can be broken into three groups, split by what they do to incorporate the loop index into the resulting HTML component.

| Group 1  | Group 2 | Group 3 |
|----------|---------|---------|
| checkbox | button  | link    |
| file     | image   |         |
| hidden   | submit  |         |
| password |         |         |
| radio    |         |         |
| select   |         |         |
| text     |         |         |
| textarea |         |         |

In Group 1, all of these tags will generate an HTML "name" attribute of "name[nn].property". The value of each tag will also be initialized by the getter method corresponding to that property specification.

In Group 2, these tags will generate an HTML "name" attribute of "property[nn]". These three tags don't have "name" attributes, so since it wouldn't make sense to use "[nn].property" (no name value), the array indexes are attached to the property instead.

The "link" tag in Group 3 isn't anything like any of the others. The base description of the "link" tag doesn't even mention how this works, but the description of the "indexed" tag describes how it works somewhat (although it doesn't specifically say that it uses the name "index" if "indexId" isn't set). In short, the "indexed" behavior of this tag is to add a URL query parameter, where the parameter name is "index" or the value of the "indexId" attribute, and the parameter value is the current index value. Outside of this, the "indexed" behavior of the "link" tag needs no more explanation, in contrast to the tags in the first two groups.

### <span id="The_Wrinkle_with_Indexed_Tags"></span>The Wrinkle with Indexed Tags

The problem with using the "indexed" attribute to automatically attach the loop index is that it gives you less control over how the loop index is used. For instance, in our earlier examples using the "\.html.md:text\>" tag, we attached the loop index to the end of the "property" attribute value, which was "labelValue" in our example. This results in a "name" attribute value in the HTML component of "labelValue[nn]". This maps to a "labelValue" indexed property on the "stringbean" bean instance.

However, if we instead add the "indexed" attribute, and remove the manual attachment of the loop index, then the resulting "name" attribute in the HTML component ends up as "stringbean[nn].labelValue". This will not work as is. It can be changed to work, however. From the previous example (indexedtest5.jsp), the "\.html.md:text\>" component would change the "name" attribute from "stringbean" to "labelValue", and the "property" attribute to "label". With the "indexed" attribute, that ends up with a "name" attribute value of "labelValue[nn].label".

So, it's very likely you could use indexed tags to support your needs for indexed properties, but you have to understand the resulting structure of your "name" attribute in order to understand what other attribute values you need.

### <span id="Using_Struts-EL_To_Avoid_Some_Of_The_Pain"></span>Using Struts-EL To Avoid Some Of The Pain

The "indexed tags" feature was created partially because of the awkward process for encoding the loop index into the property attribute, using a JSP expression. The creation of the [JSTL](http://java.sun.com/products/jsp/jstl/) eventually resulted in a solution that makes that process less painful.

The JSTL uses a string-based expression language to evaluate attribute values, instead of using a run-time JSP expression. The engine that performs these evaluations is often called just "EL" (expression language) for short. After the JSTL was created, a derivative of Struts Taglib called Struts-EL was created. In short, this component does everything that Struts Taglib does, but it uses the JSTL EL engine to evaluate attribute values.

If you use Struts-EL, you can get back some of the flexibility of encoding your loop indices manually, but the resulting expressions will be a little more readable, and thus maybe a little easier to maintain.

For instance, following this is a version of "indexedtest5.jsp" using Struts-EL:

                        <!-- indexedtest6.jsp -->
                        <%@ taglib uri="/WEB-INF/struts.html.md-el.tld"
                        prefix=.html.md-el" %>
                        <%@ taglib uri="/WEB-INF/struts-logic-el.tld"
                        prefix="logic-el" %>
                        .html.md>
                        <body>
                        .html.md-el:form action="indexedtest6.do">
                        <logic-el:iterate name="stringbean"
                        property="stringArray" id="foo"
                        indexId="ctr">
                        .html.md-el:text name="stringbean"
                        property="labelValue[${ctr}].label" />
                        </logic-el:iterate>
                        .html.md-el:submit property="submitValue">Submit
                        Changes<.html.md:submit>
                        <.html.md-el:form>
                        </body>
                        <.html.md>

If you are using JSTL in your application (and we recommend that you do!), then use Struts EL in place of Struts Taglib.

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


