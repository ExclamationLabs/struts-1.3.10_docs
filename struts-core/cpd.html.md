<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/)

------------------------------------------------------------------------

##### Struts 1

-   [Welcome](index.html.md)
-   [Learning](learning.html.md)
-   [Roadmap](roadmap.html.md)
-   [Releases](downloads.html.md)

##### Documentation

-   [User Guide](userGuide/index.html.md)
-   [FAQs and HOWTOs](faqs/index.html.md)
-   [Release Notes](userGuide/release-notes.html.md)
-   [Javadoc](apidocs/index.html.md)
-   [DTDDoc](dtddoc/index.html.md)

##### Support

-   [User Mailing List](mail.html.md)
-   [Issue Tracker (JIRA)](http://issues.apache.org/struts/)
-   [Wiki Pages](http://wiki.apache.org/struts/)

##### Components

-   [Struts Apps](struts-apps/index.html.md)
-   [Struts EL](struts-el/index.html.md)
-   [Struts Extras](struts-extras/index.html.md)
-   [Struts Faces](struts-faces/index.html.md)
-   [Struts Scripting](struts-scripting/index.html.md)
-   [Struts Taglib](struts-taglib/index.html.md)
-   [Struts Tiles](struts-tiles/index.html.md)

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
org\\apache\\struts\\mock\\MockPageContext.java
[266](./xref/org/apache/struts/mock/MockPageContext.html.md#266)
org\\apache\\struts\\mock\\MockPageContext.java
[411](./xref/org/apache/struts/mock/MockPageContext.html.md#411)
                        public void print(String s)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(Object obj)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println()
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(boolean x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(char x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(int x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(long x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(float x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(double x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(char[] x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(String x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void println(Object x)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void clear()
                            throws IOException {
                            checkAndThrow();
                        }

                        public void clearBuffer()
                            throws IOException {
                            checkAndThrow();
                        }

                        public void close()

File
Line
org\\apache\\struts\\mock\\MockPageContext.java
[226](./xref/org/apache/struts/mock/MockPageContext.html.md#226)
org\\apache\\struts\\mock\\MockPageContext.java
[366](./xref/org/apache/struts/mock/MockPageContext.html.md#366)
                        public void writeOut(Writer out)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void newLine()
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(boolean b)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(char c)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(int i)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(long l)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(float f)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(double d)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(char[] s)
                            throws IOException {
                            checkAndThrow();
                        }

                        public void print(String s)

File
Line
org\\apache\\struts\\action\\ActionMessages.java
[206](./xref/org/apache/struts/action/ActionMessages.html.md#206)
org\\apache\\struts\\action\\ActionMessages.java
[274](./xref/org/apache/struts/action/ActionMessages.html.md#274)
            if (messages.isEmpty()) {
                return Collections.EMPTY_LIST.iterator();
            }

            ArrayList results = new ArrayList();
            ArrayList actionItems = new ArrayList();

            for (Iterator i = messages.values().iterator(); i.hasNext();) {
                actionItems.add(i.next());
            }

            // Sort ActionMessageItems based on the initial order the
            // property/key was added to ActionMessages.
            Collections.sort(actionItems, ACTION_ITEM_COMPARATOR);

            for (Iterator i = actionItems.iterator(); i.hasNext();) {
                ActionMessageItem ami = (ActionMessageItem) i.next();


