<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts EL

-   [Welcome](index.html.md)

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
    -   [Continuous Integration](integration.html.md)
    -   **Dependencies**
    -   [Dependency Convergence](dependency-convergence.html.md)
    -   [Issue Tracking](issue-tracking.html.md)
    -   [Mailing Lists](mail-lists.html.md)
    -   [Plugin Management](plugin-management.html.md)
    -   [Project License](license.html.md)
    -   [Project Plugins](plugins.html.md)
    -   [Project Summary](project-summary.html.md)
    -   [Project Team](team-list.html.md)
    -   [Source Repository](source-repository.html.md)
-   [Project Reports](project-reports.html.md)

[![Built by Maven](./images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

Project Dependencies
--------------------

### compile

The following is a list of compile dependencies for this project. These dependencies are required to compile and run the application:

| GroupId           | ArtifactId                                | Version | Type | Optional |
|-------------------|-------------------------------------------|---------|------|----------|
| javax.servlet     | jstl                                      | 1.0.2   | jar  | No       |
| org.apache.struts | [struts-core](http://struts.apache.org)   | 1.3.10  | jar  | No       |
| org.apache.struts | [struts-taglib](http://struts.apache.org) | 1.3.10  | jar  | No       |
| taglibs           | standard                                  | 1.0.6   | jar  | No       |
| org.apache.struts | [struts-tiles](http://struts.apache.org)  | 1.3.10  | jar  | Yes      |

### provided

The following is a list of provided dependencies for this project. These dependencies are required to compile the application, but should be provided by default when using the library:

| GroupId       | ArtifactId  | Version | Type |
|---------------|-------------|---------|------|
| javax.servlet | servlet-api | 2.3     | jar  |

Project Transitive Dependencies
-------------------------------

The following is a list of transitive dependencies for this project. Transitive dependencies are the dependencies of the project dependencies.

### compile

The following is a list of compile dependencies for this project. These dependencies are required to compile and run the application:

| GroupId           | ArtifactId                                                      | Version | Type |
|-------------------|-----------------------------------------------------------------|---------|------|
| antlr             | antlr                                                           | 2.7.2   | jar  |
| commons-beanutils | [commons-beanutils](http://commons.apache.org/beanutils/)       | 1.8.0   | jar  |
| commons-chain     | [commons-chain](http://commons.apache.org/chain/)               | 1.2     | jar  |
| commons-digester  | [commons-digester](http://jakarta.apache.org/commons/digester/) | 1.8     | jar  |
| commons-logging   | [commons-logging](http://jakarta.apache.org/commons/logging/)   | 1.0.4   | jar  |
| commons-validator | commons-validator                                               | 1.3.1   | jar  |
| oro               | oro                                                             | 2.0.8   | jar  |

Project Dependency Graph
------------------------

### Dependency Tree

-   org.apache.struts:struts-el:jar:1.3.10 ![Information](./images/icon_info_sml.gif)
    <table>
    <colgroup>
    <col width="100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Struts EL</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>Description:</strong> Apache Struts</p>
    <p><strong>URL:</strong> <a href="http://struts.apache.org" class="uri">http://struts.apache.org</a></p>
    <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
    </tr>
    </tbody>
    </table>

    -   javax.servlet:jstl:jar:1.0.2 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">Unnamed - javax.servlet:jstl:jar:1.0.2</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> There is currently no description associated with this project.</p>
        <p><strong>Project License:</strong> No project license is defined for this project.</p></td>
        </tr>
        </tbody>
        </table>

    -   javax.servlet:servlet-api:jar:2.3 (provided) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">Unnamed - javax.servlet:servlet-api:jar:2.3</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> There is currently no description associated with this project.</p>
        <p><strong>Project License:</strong> No project license is defined for this project.</p></td>
        </tr>
        </tbody>
        </table>

    -   org.apache.struts:struts-core:jar:1.3.10 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">Struts Core</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> Apache Struts</p>
        <p><strong>URL:</strong> <a href="http://struts.apache.org" class="uri">http://struts.apache.org</a></p>
        <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
        </tr>
        </tbody>
        </table>

        -   antlr:antlr:jar:2.7.2 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Unnamed - antlr:antlr:jar:2.7.2</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> There is currently no description associated with this project.</p>
            <p><strong>Project License:</strong> No project license is defined for this project.</p></td>
            </tr>
            </tbody>
            </table>

        -   commons-beanutils:commons-beanutils:jar:1.8.0 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Commons BeanUtils</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> BeanUtils provides an easy-to-use but flexible wrapper around reflection and introspection.</p>
            <p><strong>URL:</strong> <a href="http://commons.apache.org/beanutils/" class="uri">http://commons.apache.org/beanutils/</a></p>
            <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>

        -   commons-chain:commons-chain:jar:1.2 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Commons Chain</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> An implementation of the GoF Chain of Responsibility pattern</p>
            <p><strong>URL:</strong> <a href="http://commons.apache.org/chain/" class="uri">http://commons.apache.org/chain/</a></p>
            <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>

        -   commons-digester:commons-digester:jar:1.8 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Digester</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> The Digester package lets you configure an XML-&gt;Java object mapping module which triggers certain actions called rules whenever a particular pattern of nested XML elements is recognized.</p>
            <p><strong>URL:</strong> <a href="http://jakarta.apache.org/commons/digester/" class="uri">http://jakarta.apache.org/commons/digester/</a></p>
            <p><strong>Project License:</strong> <a href="/LICENSE.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>

        -   commons-logging:commons-logging:jar:1.0.4 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Logging</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> Commons Logging is a thin adapter allowing configurable bridging to other, well known logging systems.</p>
            <p><strong>URL:</strong> <a href="http://jakarta.apache.org/commons/logging/" class="uri">http://jakarta.apache.org/commons/logging/</a></p>
            <p><strong>Project License:</strong> <a href="/LICENSE.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>

        -   commons-validator:commons-validator:jar:1.3.1 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Validator</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> Commons Validator provides the building blocks for both client side validation and server side data validation. It may be used standalone or with a framework like Struts.</p>
            <p><strong>URL:</strong> http://jakarta.apache.org/commons/${pom.artifactId.substring(8)}/</p>
            <p><strong>Project License:</strong> <a href="/LICENSE.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>

            -   commons-logging:commons-logging:jar:1.0.4 (compile) ![Information](./images/icon_info_sml.gif)
                <table>
                <colgroup>
                <col width="100%" />
                </colgroup>
                <thead>
                <tr class="header">
                <th align="left">Logging</th>
                </tr>
                </thead>
                <tbody>
                <tr class="odd">
                <td align="left"><p><strong>Description:</strong> Commons Logging is a thin adapter allowing configurable bridging to other, well known logging systems.</p>
                <p><strong>URL:</strong> <a href="http://jakarta.apache.org/commons/logging/" class="uri">http://jakarta.apache.org/commons/logging/</a></p>
                <p><strong>Project License:</strong> <a href="/LICENSE.txt">The Apache Software License, Version 2.0</a></p></td>
                </tr>
                </tbody>
                </table>
        -   oro:oro:jar:2.0.8 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Unnamed - oro:oro:jar:2.0.8</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> There is currently no description associated with this project.</p>
            <p><strong>Project License:</strong> No project license is defined for this project.</p></td>
            </tr>
            </tbody>
            </table>
    -   org.apache.struts:struts-taglib:jar:1.3.10 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">Struts Taglib</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> Apache Struts</p>
        <p><strong>URL:</strong> <a href="http://struts.apache.org" class="uri">http://struts.apache.org</a></p>
        <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
        </tr>
        </tbody>
        </table>

        -   org.apache.struts:struts-core:jar:1.3.10 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Struts Core</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> Apache Struts</p>
            <p><strong>URL:</strong> <a href="http://struts.apache.org" class="uri">http://struts.apache.org</a></p>
            <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>
    -   org.apache.struts:struts-tiles:jar:1.3.10 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">Struts Tiles</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> Apache Struts</p>
        <p><strong>URL:</strong> <a href="http://struts.apache.org" class="uri">http://struts.apache.org</a></p>
        <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
        </tr>
        </tbody>
        </table>

        -   org.apache.struts:struts-core:jar:1.3.10 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">Struts Core</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> Apache Struts</p>
            <p><strong>URL:</strong> <a href="http://struts.apache.org" class="uri">http://struts.apache.org</a></p>
            <p><strong>Project License:</strong> <a href="http://www.apache.org/licenses/LICENSE-2.0.txt">The Apache Software License, Version 2.0</a></p></td>
            </tr>
            </tbody>
            </table>
    -   taglibs:standard:jar:1.0.6 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">Unnamed - taglibs:standard:jar:1.0.6</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> There is currently no description associated with this project.</p>
        <p><strong>Project License:</strong> No project license is defined for this project.</p></td>
        </tr>
        </tbody>
        </table>

Licenses
--------

**Unknown:** Unnamed - antlr:antlr:jar:2.7.2, Unnamed - javax.servlet:jstl:jar:1.0.2, Unnamed - javax.servlet:servlet-api:jar:2.3, Unnamed - oro:oro:jar:2.0.8, Unnamed - taglibs:standard:jar:1.0.6

**The Apache Software License, Version 2.0:** Commons BeanUtils, Commons Chain, Digester, Logging, Struts Core, Struts EL, Struts Taglib, Struts Tiles, Validator

Dependency File Details
-----------------------

Filename
Size
Entries
Classes
Packages
JDK Rev
Debug
antlr-2.7.2.jar
349.88 kB
195
193
8
1.1
debug
commons-beanutils-1.8.0.jar
225.90 kB
155
137
6
1.3
debug
commons-chain-1.2.jar
89.55 kB
81
61
8
1.3
debug
commons-digester-1.8.jar
140.24 kB
114
100
6
1.2
debug
commons-logging-1.0.4.jar
37.12 kB
29
18
2
1.2
debug
commons-validator-1.3.1.jar
135.70 kB
93
46
3
1.3
debug
jstl-1.0.2.jar
20.47 kB
28
18
4
1.2
debug
servlet-api-2.3.jar
76.15 kB
83
63
4
1.1
debug
struts-core-1.3.10.jar
321.72 kB
192
150
15
1.4
debug
struts-taglib-1.3.10.jar
245.61 kB
158
125
8
1.4
debug
oro-2.0.8.jar
63.73 kB
74
62
6
1.2
release
standard-1.0.6.jar
496.73 kB
390
338
26
1.2
debug
struts-tiles-1.3.10.jar
116.84 kB
93
67
8
1.4
debug
Total
Size
Entries
Classes
Packages
JDK Rev
Debug
13
2.27 MB
1,685
1,378
104
1.4
12
compile: 12
compile: 2.19 MB
compile: 1,602
compile: 1,315
compile: 100
-
compile: 11
provided: 1
provided: 76.15 kB
provided: 83
provided: 63
provided: 4
-
provided: 1

Dependency Repository Locations
-------------------------------

Repo ID
URL
Release
Snapshot
apache.snapshots
<http://people.apache.org/maven-snapshot-repository>
-
Yes
central
<http://repo1.maven.org/maven2>
Yes
-
Repository locations for each of the Dependencies.

Artifact
apache.snapshots
central
antlr:antlr:jar:2.7.2
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/antlr/antlr/2.7.2/antlr-2.7.2.jar)
commons-beanutils:commons-beanutils:jar:1.8.0
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-beanutils/commons-beanutils/1.8.0/commons-beanutils-1.8.0.jar)
commons-chain:commons-chain:jar:1.2
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-chain/commons-chain/1.2/commons-chain-1.2.jar)
commons-digester:commons-digester:jar:1.8
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-digester/commons-digester/1.8/commons-digester-1.8.jar)
commons-logging:commons-logging:jar:1.0.4
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-logging/commons-logging/1.0.4/commons-logging-1.0.4.jar)
commons-validator:commons-validator:jar:1.3.1
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-validator/commons-validator/1.3.1/commons-validator-1.3.1.jar)
javax.servlet:jstl:jar:1.0.2
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/javax/servlet/jstl/1.0.2/jstl-1.0.2.jar)
javax.servlet:servlet-api:jar:2.3
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/javax/servlet/servlet-api/2.3/servlet-api-2.3.jar)
org.apache.struts:struts-core:jar:1.3.10
-
-
org.apache.struts:struts-taglib:jar:1.3.10
-
-
oro:oro:jar:2.0.8
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/oro/oro/2.0.8/oro-2.0.8.jar)
taglibs:standard:jar:1.0.6
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/taglibs/standard/1.0.6/standard-1.0.6.jar)
org.apache.struts:struts-tiles:jar:1.3.10
-
-
Total
apache.snapshots
central
13 (compile: 12, provided: 1)
0
10

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


