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
    -   [CPD Report](cpd.html.md)
    -   [DTDDoc](dtddoc/index.html.md)
    -   [JavaDocs](apidocs/index.html.md)
    -   **PMD Report**
    -   [Source Xref](xref/index.html.md)
    -   [Surefire Report](surefire-report.html.md)
    -   [Test JavaDocs](testapidocs/index.html.md)
    -   [Test Source Xref](xref-test/index.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

PMD Results
-----------

The following document contains the results of [PMD](http://pmd.sourceforge.net/) 4.2.2.

Files
-----

### org/apache/struts/action/ActionForm.java

| Violation                                         | Line                                                       |
|---------------------------------------------------|------------------------------------------------------------|
| An empty statement (semicolon) not part of a loop | [154](./xref/org/apache/struts/action/ActionForm.html.md#154) |

### org/apache/struts/action/ActionMapping.java

| Violation                                    | Line                                                                                                                      |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| These nested if statements could be combined | [76](./xref/org/apache/struts/action/ActionMapping.html.md#76) - [78](./xref/org/apache/struts/action/ActionMapping.html#78) |

### org/apache/struts/action/ActionServlet.java

| Violation                                              | Line                                                                                                                              |
|--------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| Avoid unused imports such as 'org.xml.sax.InputSource' | [57](./xref/org/apache/struts/action/ActionServlet.html.md#57)                                                                       |
| Avoid unused imports such as 'java.net.URLConnection'  | [75](./xref/org/apache/struts/action/ActionServlet.html.md#75)                                                                       |
| An empty statement (semicolon) not part of a loop      | [317](./xref/org/apache/struts/action/ActionServlet.html.md#317)                                                                     |
| An empty statement (semicolon) not part of a loop      | [854](./xref/org/apache/struts/action/ActionServlet.html.md#854)                                                                     |
| These nested if statements could be combined           | [1000](./xref/org/apache/struts/action/ActionServlet.html.md#1000) - [1026](./xref/org/apache/struts/action/ActionServlet.html#1026) |
| These nested if statements could be combined           | [1148](./xref/org/apache/struts/action/ActionServlet.html.md#1148) - [1174](./xref/org/apache/struts/action/ActionServlet.html#1174) |
| These nested if statements could be combined           | [1295](./xref/org/apache/struts/action/ActionServlet.html.md#1295) - [1321](./xref/org/apache/struts/action/ActionServlet.html#1321) |
| These nested if statements could be combined           | [1456](./xref/org/apache/struts/action/ActionServlet.html.md#1456) - [1490](./xref/org/apache/struts/action/ActionServlet.html#1490) |

### org/apache/struts/action/RequestProcessor.java

| Violation                                    | Line                                                                                                                                |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| These nested if statements could be combined | [455](./xref/org/apache/struts/action/RequestProcessor.html.md#455) - [457](./xref/org/apache/struts/action/RequestProcessor.html#457) |
| These nested if statements could be combined | [464](./xref/org/apache/struts/action/RequestProcessor.html.md#464) - [466](./xref/org/apache/struts/action/RequestProcessor.html#466) |

### org/apache/struts/chain/commands/servlet/ExceptionHandler.java

| Violation                                  | Line                                                                           |
|--------------------------------------------|--------------------------------------------------------------------------------|
| Avoid unused private fields such as 'log'. | [47](./xref/org/apache/struts/chain/commands/servlet/ExceptionHandler.html.md#47) |

### org/apache/struts/chain/commands/servlet/PopulateActionForm.java

| Violation                                  | Line                                                                             |
|--------------------------------------------|----------------------------------------------------------------------------------|
| Avoid unused private fields such as 'log'. | [42](./xref/org/apache/struts/chain/commands/servlet/PopulateActionForm.html.md#42) |

### org/apache/struts/chain/commands/servlet/SelectLocale.java

| Violation                                  | Line                                                                       |
|--------------------------------------------|----------------------------------------------------------------------------|
| Avoid unused private fields such as 'log'. | [41](./xref/org/apache/struts/chain/commands/servlet/SelectLocale.html.md#41) |

### org/apache/struts/chain/commands/servlet/ValidateActionForm.java

| Violation                                    | Line                                                                                                                                                                |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| These nested if statements could be combined | [64](./xref/org/apache/struts/chain/commands/servlet/ValidateActionForm.html.md#64) - [70](./xref/org/apache/struts/chain/commands/servlet/ValidateActionForm.html#70) |

### org/apache/struts/chain/contexts/WebActionContext.java

| Violation                            | Line                                                                                                                                            |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Overriding method merely calls super | [53](./xref/org/apache/struts/chain/contexts/WebActionContext.html.md#53) - [55](./xref/org/apache/struts/chain/contexts/WebActionContext.html#55) |

### org/apache/struts/config/impl/ModuleConfigImpl.java

| Violation                                    | Line                                                                                                                                          |
|----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| These nested if statements could be combined | [297](./xref/org/apache/struts/config/impl/ModuleConfigImpl.html.md#297) - [307](./xref/org/apache/struts/config/impl/ModuleConfigImpl.html#307) |

### org/apache/struts/mock/MockActionServlet.java

| Violation                                         | Line                                                                                                                              |
|---------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| An empty statement (semicolon) not part of a loop | [62](./xref/org/apache/struts/mock/MockActionServlet.html.md#62)                                                                     |
| Overriding method merely calls super              | [105](./xref/org/apache/struts/mock/MockActionServlet.html.md#105) - [108](./xref/org/apache/struts/mock/MockActionServlet.html#108) |

### org/apache/struts/mock/MockFormBean.java

| Violation                                                     | Line                                                     |
|---------------------------------------------------------------|----------------------------------------------------------|
| Do not use if statements that are always true or always false | [94](./xref/org/apache/struts/mock/MockFormBean.html.md#94) |

### org/apache/struts/upload/CommonsMultipartRequestHandler.java

| Violation                | Line                                                                                                                                                            |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Avoid empty catch blocks | [413](./xref/org/apache/struts/upload/CommonsMultipartRequestHandler.html.md#413) - [415](./xref/org/apache/struts/upload/CommonsMultipartRequestHandler.html#415) |

### org/apache/struts/util/ImageButtonBean.java

| Violation                                         | Line                                                        |
|---------------------------------------------------|-------------------------------------------------------------|
| An empty statement (semicolon) not part of a loop | [55](./xref/org/apache/struts/util/ImageButtonBean.html.md#55) |

### org/apache/struts/util/PropertyMessageResources.java

| Violation                                          | Line                                                                                                                                            |
|----------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Avoid empty if statements                          | [244](./xref/org/apache/struts/util/PropertyMessageResources.html.md#244) - [250](./xref/org/apache/struts/util/PropertyMessageResources.html#250) |
| Avoid unused local variables such as 'messageKey'. | [397](./xref/org/apache/struts/util/PropertyMessageResources.html.md#397)                                                                          |
| These nested if statements could be combined       | [448](./xref/org/apache/struts/util/PropertyMessageResources.html.md#448) - [450](./xref/org/apache/struts/util/PropertyMessageResources.html#450) |

### org/apache/struts/util/RequestUtils.java

| Violation                                         | Line                                                       |
|---------------------------------------------------|------------------------------------------------------------|
| An empty statement (semicolon) not part of a loop | [887](./xref/org/apache/struts/util/RequestUtils.html.md#887) |

### org/apache/struts/util/TokenProcessor.java

| Violation                                                           | Line                                                         |
|---------------------------------------------------------------------|--------------------------------------------------------------|
| Avoid unnecessary temporaries when converting primitives to Strings | [204](./xref/org/apache/struts/util/TokenProcessor.html.md#204) |

### org/apache/struts/validator/Resources.java

| Violation                                         | Line                                                         |
|---------------------------------------------------|--------------------------------------------------------------|
| Avoid unused local variables such as 'msgBundle'. | [296](./xref/org/apache/struts/validator/Resources.html.md#296) |

### org/apache/struts/validator/ValidatorPlugIn.java

| Violation                                     | Line                                                             |
|-----------------------------------------------|------------------------------------------------------------------|
| Avoid unused private fields such as 'config'. | [79](./xref/org/apache/struts/validator/ValidatorPlugIn.html.md#79) |

### org/apache/struts/validator/validwhen/ValidWhenLexer.java

| Violation                                                                       | Line                                                                        |
|---------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| Avoid unused imports such as 'java.util.Stack'                                  | [26](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#26)   |
| Avoid unused imports such as 'org.apache.commons.validator.util.ValidatorUtils' | [27](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#27)   |
| Avoid unused imports such as 'antlr.ANTLRException'                             | [36](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#36)   |
| Avoid unused imports such as 'antlr.CharScanner'                                | [39](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#39)   |
| Avoid unused imports such as 'antlr.CommonToken'                                | [44](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#44)   |
| Avoid unused imports such as 'antlr.MismatchedCharException'                    | [47](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#47)   |
| Avoid unused imports such as 'antlr.SemanticException'                          | [52](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#52)   |
| Avoid unused local variables such as 'theRetToken'.                             | [76](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#76)   |
| Avoid unused local variables such as '\_token'.                                 | [79](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#79)   |
| Avoid unused local variables such as '\_saveIndex'.                             | [213](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#213) |
| Avoid unused local variables such as '\_saveIndex'.                             | [259](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#259) |
| Avoid unused local variables such as '\_saveIndex'.                             | [305](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#305) |
| Avoid unused local variables such as '\_saveIndex'.                             | [345](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#345) |
| Avoid unused local variables such as '\_saveIndex'.                             | [370](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#370) |
| Avoid unused local variables such as '\_saveIndex'.                             | [432](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#432) |
| Avoid unused local variables such as '\_saveIndex'.                             | [445](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#445) |
| Avoid unused local variables such as '\_saveIndex'.                             | [458](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#458) |
| Avoid unused local variables such as '\_saveIndex'.                             | [471](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#471) |
| Avoid unused local variables such as '\_saveIndex'.                             | [484](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#484) |
| Avoid unused local variables such as '\_saveIndex'.                             | [497](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#497) |
| Avoid unused local variables such as '\_saveIndex'.                             | [579](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#579) |
| Avoid unused local variables such as '\_saveIndex'.                             | [593](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#593) |
| Avoid unused local variables such as '\_saveIndex'.                             | [607](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#607) |
| Avoid unused local variables such as '\_saveIndex'.                             | [620](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#620) |
| Avoid unused local variables such as '\_saveIndex'.                             | [633](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#633) |
| Avoid unused local variables such as '\_saveIndex'.                             | [647](./xref/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md#647) |

### org/apache/struts/validator/validwhen/ValidWhenParser.java

| Violation                                                                                                       | Line                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Avoid unused imports such as 'antlr.TokenStreamIOException'                                                     | [32](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#32)                                                                              |
| Avoid unused imports such as 'antlr.ANTLRException'                                                             | [33](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#33)                                                                              |
| Avoid unused imports such as 'antlr.LLkParser'                                                                  | [34](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#34)                                                                              |
| Avoid unused imports such as 'antlr.MismatchedTokenException'                                                   | [39](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#39)                                                                              |
| Avoid unused imports such as 'antlr.SemanticException'                                                          | [40](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#40)                                                                              |
| These nested if statements could be combined                                                                    | [72](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#72) - [74](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html#74) |
| These nested if statements could be combined                                                                    | [77](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#77) - [79](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html#79) |
| Avoid empty catch blocks                                                                                        | [133](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#133)                                                                            |
| An empty statement (semicolon) not part of a loop                                                               | [133](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#133)                                                                            |
| Avoid instantiating Boolean objects; reference Boolean.TRUE or Boolean.FALSE or call Boolean.valueOf() instead. | [406](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#406)                                                                            |
| Avoid instantiating Boolean objects; reference Boolean.TRUE or Boolean.FALSE or call Boolean.valueOf() instead. | [421](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#421)                                                                            |
| Avoid instantiating Boolean objects; reference Boolean.TRUE or Boolean.FALSE or call Boolean.valueOf() instead. | [423](./xref/org/apache/struts/validator/validwhen/ValidWhenParser.html.md#423)                                                                            |

### org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.java

| Violation                                                                       | Line                                                                                 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| Avoid unused imports such as 'java.util.Stack'                                  | [26](./xref/org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md#26) |
| Avoid unused imports such as 'org.apache.commons.validator.util.ValidatorUtils' | [27](./xref/org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md#27) |

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


