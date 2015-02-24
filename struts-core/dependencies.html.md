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
    -   [About](index.html.md)
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

| GroupId            | ArtifactId                                                      | Version | Type | Optional |
|--------------------|-----------------------------------------------------------------|---------|------|----------|
| antlr              | antlr                                                           | 2.7.2   | jar  | No       |
| commons-beanutils  | [commons-beanutils](http://commons.apache.org/beanutils/)       | 1.8.0   | jar  | No       |
| commons-chain      | [commons-chain](http://commons.apache.org/chain/)               | 1.2     | jar  | No       |
| commons-digester   | [commons-digester](http://jakarta.apache.org/commons/digester/) | 1.8     | jar  | No       |
| commons-logging    | [commons-logging](http://jakarta.apache.org/commons/logging/)   | 1.0.4   | jar  | No       |
| commons-validator  | commons-validator                                               | 1.3.1   | jar  | No       |
| oro                | oro                                                             | 2.0.8   | jar  | No       |
| commons-fileupload | commons-fileupload                                              | 1.1.1   | jar  | Yes      |
| junit              | [junit](http://junit.org)                                       | 3.8.1   | jar  | Yes      |

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

| GroupId    | ArtifactId                                          | Version | Type |
|------------|-----------------------------------------------------|---------|------|
| commons-io | [commons-io](http://jakarta.apache.org/commons/io/) | 1.1     | jar  |

Project Dependency Graph
------------------------

### Dependency Tree

-   org.apache.struts:struts-core:jar:1.3.10 ![Information](./images/icon_info_sml.gif)
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

    -   commons-fileupload:commons-fileupload:jar:1.1.1 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">FileUpload</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> The FileUpload component provides a simple yet flexible means of adding support for multipart file upload functionality to servlets and web applications.</p>
        <p><strong>URL:</strong> http://jakarta.apache.org/commons/${pom.artifactId.substring(8)}/</p>
        <p><strong>Project License:</strong> <a href="/LICENSE.txt">The Apache Software License, Version 2.0</a></p></td>
        </tr>
        </tbody>
        </table>

        -   commons-io:commons-io:jar:1.1 (compile) ![Information](./images/icon_info_sml.gif)
            <table>
            <colgroup>
            <col width="100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th align="left">IO</th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td align="left"><p><strong>Description:</strong> Commons-IO contains utility classes, stream implementations, file filters, and endian classes.</p>
            <p><strong>URL:</strong> <a href="http://jakarta.apache.org/commons/io/" class="uri">http://jakarta.apache.org/commons/io/</a></p>
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

    -   junit:junit:jar:3.8.1 (compile) ![Information](./images/icon_info_sml.gif)
        <table>
        <colgroup>
        <col width="100%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">JUnit</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><strong>Description:</strong> JUnit is a regression testing framework written by Erich Gamma and Kent Beck. It is used by the developer who implements unit tests in Java.</p>
        <p><strong>URL:</strong> <a href="http://junit.org" class="uri">http://junit.org</a></p>
        <p><strong>Project License:</strong> <a href="http://www.opensource.org/licenses/cpl1.0.txt">Common Public License Version 1.0</a></p></td>
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

Licenses
--------

**Unknown:** Unnamed - antlr:antlr:jar:2.7.2, Unnamed - javax.servlet:servlet-api:jar:2.3, Unnamed - oro:oro:jar:2.0.8

**Common Public License Version 1.0:** JUnit

**The Apache Software License, Version 2.0:** Commons BeanUtils, Commons Chain, Digester, FileUpload, IO, Logging, Struts Core, Validator

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
commons-io-1.1.jar
60.12 kB
52
41
4
1.1
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
servlet-api-2.3.jar
76.15 kB
83
63
4
1.1
debug
oro-2.0.8.jar
63.73 kB
74
62
6
1.2
release
commons-fileupload-1.1.1.jar
31.16 kB
33
22
4
1.3
debug
junit-3.8.1.jar
118.23 kB
119
100
6
1.1
debug
Total
Size
Entries
Classes
Packages
JDK Rev
Debug
11
1.30 MB
1,028
843
57
1.3
10
compile: 10
compile: 1.22 MB
compile: 945
compile: 780
compile: 53
-
compile: 9
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
<http://people.apache.org/repo/m2-snapshot-repository>
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
commons-io:commons-io:jar:1.1
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-io/commons-io/1.1/commons-io-1.1.jar)
commons-logging:commons-logging:jar:1.0.4
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-logging/commons-logging/1.0.4/commons-logging-1.0.4.jar)
commons-validator:commons-validator:jar:1.3.1
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-validator/commons-validator/1.3.1/commons-validator-1.3.1.jar)
javax.servlet:servlet-api:jar:2.3
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/javax/servlet/servlet-api/2.3/servlet-api-2.3.jar)
oro:oro:jar:2.0.8
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/oro/oro/2.0.8/oro-2.0.8.jar)
commons-fileupload:commons-fileupload:jar:1.1.1
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/commons-fileupload/commons-fileupload/1.1.1/commons-fileupload-1.1.1.jar)
junit:junit:jar:3.8.1
-
[![Found at http://repo1.maven.org/maven2](images/icon_success_sml.gif)](http://repo1.maven.org/maven2/junit/junit/3.8.1/junit-3.8.1.jar)
Total
apache.snapshots
central
11 (compile: 10, provided: 1)
0
11

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


