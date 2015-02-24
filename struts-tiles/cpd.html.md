<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Tiles

-   [Welcome](index.html.md)
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
    -   [Checkstyle](checkstyle.html.md)
    -   **CPD Report**
    -   [DTDDoc](dtddoc/index.html.md)
    -   [JavaDocs](apidocs/index.html.md)
    -   [PMD Report](pmd.html.md)
    -   [Source Xref](xref/index.html.md)
    -   [Surefire Report](surefire-report.html.md)
    -   [Taglibdoc documentation](tlddoc/index.html.md)
    -   [Tag library validation](taglibvalidation.html.md)
    -   [Tag reference](tagreference.html.md)
    -   [Test JavaDocs](testapidocs/index.html.md)
    -   [Test Source Xref](xref-test/index.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

CPD Results
-----------

The following document contains the results of PMD's [CPD](http://pmd.sourceforge.net/cpd.html.md) 4.2.2.

Duplications
------------

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------

File
Line
org\\apache\\struts\\tiles\\taglib\\PutTag.java
[393](./xref/org/apache/struts/tiles/taglib/PutTag.html.md#393)
org\\apache\\struts\\tiles\\taglib\\util\\TagUtils.java
[212](./xref/org/apache/struts/tiles/taglib/util/TagUtils.html.md#212)
            } catch (NoSuchMethodException ex) {
                throw new JspException(
                    "Error - component.PutAttributeTag : Error while retrieving value from bean '"
                        + beanName
                        + "' with property '"
                        + beanProperty
                        + "' in scope '"
                        + beanScope
                        + "'. (exception : "
                        + ex.getMessage(), ex);

            } catch (InvocationTargetException ex) {
                throw new JspException(
                    "Error - component.PutAttributeTag : Error while retrieving value from bean '"
                        + beanName
                        + "' with property '"
                        + beanProperty
                        + "' in scope '"
                        + beanScope
                        + "'. (exception : "
                        + ex.getMessage(), ex);

            } catch (IllegalAccessException ex) {
                throw new JspException(
                    "Error - component.PutAttributeTag : Error while retrieving value from bean '"
                        + beanName
                        + "' with property '"
                        + beanProperty
                        + "' in scope '"
                        + beanScope
                        + "'. (exception : "
                        + ex.getMessage(), ex);
            }
        }

        /**
         * Store bean in requested context.
         * If scope is <code>null</code>, save it in REQUEST_SCOPE context.
         *
         * @param pageContext Current pageContext.
         * @param name Name of the bean.
         * @param scope Scope under which bean is saved (page, request, session, application)
         *  or <code>null</code> to store in <code>request()</code> instead.
         * @param value Bean value to store.
         *
         * @exception JspException Scope name is not recognized as a valid scope
         */
        public static void setAttribute(


