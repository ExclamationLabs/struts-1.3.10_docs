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
-   [Project Reports](project-reports.html.md)
    -   [Checkstyle](checkstyle.html.md)
    -   **CPD Report**
    -   [JavaDocs](apidocs/index.html.md)
    -   [PMD Report](pmd.html.md)
    -   [Source Xref](xref/index.html.md)
    -   [Surefire Report](surefire-report.html.md)

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
examples\\bean\\ExampleBean.java
[80](./xref/examples/bean/ExampleBean.html.md#80)
examples\\TestBean.java
[65](./xref/examples/TestBean.html.md#65)
        public TestBean() {
            super();
        }

        // -------------------------------------------------------------- Properties

        /**
         * Returns the booleanValue.
         * @return boolean
         */
        public boolean isBooleanValue() {
            return booleanValue;
        }

        /**
         * Returns the doubleValue.
         * @return double
         */
        public double getDoubleValue() {
            return doubleValue;
        }

        /**
         * Returns the floatValue.
         * @return float
         */
        public float getFloatValue() {
            return floatValue;
        }

        /**
         * Returns the intValue.
         * @return int
         */
        public int getIntValue() {
            return intValue;
        }

        /**
         * Returns the longValue.
         * @return long
         */
        public long getLongValue() {
            return longValue;
        }

        /**
         * Returns the shortValue.
         * @return short
         */
        public short getShortValue() {
            return shortValue;
        }

        /**
         * Returns the stringValue.
         * @return String
         */
        public String getStringValue() {
            return stringValue;
        }

        /**
         * Sets the booleanValue.
         * @param booleanValue The booleanValue to set
         */
        public void setBooleanValue(boolean booleanValue) {
            this.booleanValue = booleanValue;
        }

        /**
         * Sets the doubleValue.
         * @param doubleValue The doubleValue to set
         */
        public void setDoubleValue(double doubleValue) {
            this.doubleValue = doubleValue;
        }

        /**
         * Sets the floatValue.
         * @param floatValue The floatValue to set
         */
        public void setFloatValue(float floatValue) {
            this.floatValue = floatValue;
        }

        /**
         * Sets the intValue.
         * @param intValue The intValue to set
         */
        public void setIntValue(int intValue) {
            this.intValue = intValue;
        }

        /**
         * Sets the longValue.
         * @param longValue The longValue to set
         */
        public void setLongValue(long longValue) {
            this.longValue = longValue;
        }

        /**
         * Sets the shortValue.
         * @param shortValue The shortValue to set
         */
        public void setShortValue(short shortValue) {
            this.shortValue = shortValue;
        }

        /**
         * Sets the stringValue.
         * @param stringValue The stringValue to set
         */
        public void setStringValue(String stringValue) {
            this.stringValue = stringValue;
        }

        /**
         * Returns the dateValue.
         * @return java.util.Date
         */
        public java.util.Date getDateValue() {

File
Line
examples\\logic\\PrepareLogicAction.java
[87](./xref/examples/logic/PrepareLogicAction.html.md#87)
examples\\options\\PrepareOptionsAction.java
[124](./xref/examples/options/PrepareOptionsAction.html.md#124)
            request.setAttribute("days", days);

            /* Collection of custom beans */
            ArrayList books = new ArrayList();
            books.add(new BookBean("0596003285", "Programming Jakarta Struts"));
            books.add(new BookBean("1930110502", "Struts in Action"));
            books.add(
                new BookBean("1861007817", "Professional Struts Applications"));
            books.add(new BookBean("0672324725", "Struts Kick Start"));
            books.add(new BookBean("0471213020", "Mastering Jakarta Struts"));
            books.add(new BookBean("1558608621", "The Struts Framework"));
            books.add(new BookBean("0971661901", "Struts Fast Track"));
            request.setAttribute("books", books);


