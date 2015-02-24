<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](../images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](../2.x/) | [Struts 1](../1.x/)

------------------------------------------------------------------------

##### Struts 1

-   [Welcome](../index.html.md)
-   [Learning](../learning.html.md)
-   [Roadmap](../roadmap.html.md)
-   [Releases](../downloads.html.md)

##### Documentation

-   [User Guide](../userGuide/index.html.md)
-   [FAQs and HOWTOs](../faqs/index.html.md)
-   [Release Notes](../userGuide/release-notes.html.md)
-   [Javadoc](../apidocs/index.html.md)
-   [DTDDoc](../dtddoc/index.html.md)

##### Support

-   [User Mailing List](../mail.html.md)
-   [Issue Tracker (JIRA)](http://issues.apache.org/struts/)
-   [Wiki Pages](http://wiki.apache.org/struts/)

##### Components

-   [Struts Apps](../struts-apps/index.html.md)
-   [Struts EL](../struts-el/index.html.md)
-   [Struts Extras](../struts-extras/index.html.md)
-   [Struts Faces](../struts-faces/index.html.md)
-   [Struts Scripting](../struts-scripting/index.html.md)
-   [Struts Taglib](../struts-taglib/index.html.md)
-   [Struts Tiles](../struts-tiles/index.html.md)

##### Project Documentation

-   [Project Information](../project-info.html.md)
-   [Project Reports](../project-reports.html.md)

[![Built by Maven](../images/logos/maven-feather.png)](http://maven.apache.org/ "Built by Maven")

<span id="a6.1_Release_Notes_-_Version_1.2.7"></span>6.1 Release Notes - Version 1.2.7
--------------------------------------------------------------------------------------

### <span id="Introduction"></span>Introduction

This section contains release notes for changes that have taken place since [Version 1.2.4](release-notes-1_2_4.html.md) . To keep up-to-date on all changes to Struts, subscribe to the dev@ list.

**Notes on upgrading** are maintained in the [Wiki Upgrade pages](http://wiki.apache.org/struts/StrutsUpgrade) . The wiki is a community maintained resource - please feel free to add your input so that everyone can benefit from the collective experience.

For the version requirements of each library, see the [Installation chapter](installation.html.md) .

### <span id="Highlights_of_Changes"></span>Highlights of Changes

The purpose of this section is to highlight the new features since the Version 1.2.4 release. For detailed information concerning changes see the [Detailed Changes](#Detail) section.

### Dependencies

Struts has changed its dependencies on the following software components:

-   Commons BeanUtils dependency changed to Version 1.7.0
-   Commons Digester dependency changed to Version 1.6
-   Commons Validator dependency changed to Version 1.1.4
-   Dependency on Commons Collections has been removed
-   Dependency on Commons Lang has been removed

### Core Struts

#### Saving Messages in the Session

A new method to store *errors* in the Session [ `saveErrors(HttpSession, ActionMessages)` ] has been added to *Action* along with the automatic removal of these errors once they have been accessed. This is equivalent to the facility for *messages* that was included in the Version 1.2.4 release.

#### Re-directing ActionForward

*ActionRedirect* is a subclass of ActionForward which is designed for use in redirecting requests, with support for adding parameters at runtime. See the *javadoc* for more details.

#### Download Action

*DownloadAction* is an abstract action that provides the nuts and bolts for downloading files. See the *javadocs* and [Wiki](http://wiki.apache.org/struts/StrutsFileDownload) for further information.

#### Dispatch Helper

*ActionDispatcher* is a helper class for providing *DispatchAction* type behaviour without having to inherit from *DispatchAction* . See the *javadoc* for more details.

#### *Lazy* Validator Form

A *DynaBean* flavour ActionForm which doesn't need its properties to be defined and provides *Lazy List* and *Lazy Map* behaviours.

#### Config Files in jars

Config files (i.e. Struts config, Validator config and Tiles config files) can now be stored in jars. Struts checks the servlet context, as before but if not found Struts now tries the classloader to try and get them.

### Tag Library Changes

#### Highlighting Errors

Struts can now automatically highlight error fields using the new *errorKey* , *errorStyle* , *errorStyleClass* and *errorStyleId* attributes on the HTML Input Tags. See the [User Guide](struts.html.md.html) for details of these attributes.

#### Readonly / Disabled Forms

It is now possible to either *disable* or make *read only* all fields for a form using the new *readonly* and *disabled* attributes on the \.html.md:form\> tag. **N.B.** The *readonly* attribute only affects \<html:text\>, \<html:textarea\> and \<html:password\> as per the HTML 4 specification. See the [User Guide](struts-html.html#form) for details of these attributes.

#### HTML Tag Refactoring

Many of the *HTML* tags have been refactored to make them easier to extend.

-   A **prepareOtherAttributes()** method was added - called just before the closing tag element, it provides a place to render additional attributes.
-   The *name* attribute rendering is now in a **prepareName()** method to make it easier to provide custom behaviour.
-   The *value* attribute rendering is now in a **prepareValue()** method to make it easier to provide custom behaviour.
-   When rendering an attribute, these tags now use the *getter* for the property rather than the actual property - that means that if you wanted, for example to override the TextTag's *styleClass* then one option is to override the getStyleClass() method.
-   Rendering of attributes now uses a simple **prepareAttribute()** method to generate the *name="attribute"* format, making most attribute rendering a one line statement.

#### Bundle Attribute

The *bundle* attribute has been added to the following *HTML* tags: ButtonTag, CancelTag, CheckboxTag, FileTag, FrameTag, HiddenTag, LinkTag, MultiboxTag, PasswordTag, RadioTag, ResetTag, SelectTag, SubmitTag, TextTag, TextareaTag. See the [User Guide](struts.html.md.html) for details of the bundle attribute for these tags.

#### ErrorTag

Now has **header** , **footer** , **prefix** , **suffix** attributes. See the [User Guide](struts.html.md.html#errors) for details of these attributes.

### Validator

#### Resource Bundle Support

The *bundle* attribute for the \<msg\> and \<arg\> elements in the Validator configuration file (e.g. *validation.xml* ) are now supported along with the *resource* attribute on the \<msg\> element.

New pages have been added to the *struts-examples* webapp showing the new *Resource Bundle Support* and a page for *validwhen* examples.

### Subversion

Struts has migrated it's source repository from CVS to Subversion, following which the repository has been refactored into subprojects. The subproject re-factoring does not however affect the 1.2.x series which is released from the [STRUTS\_1\_2](http://svn.apache.org/viewcvs.cgi/struts/core/branches/STRUTS_1_2_BRANCH/) branch.

### People

On the [people](../volunteers.html.md) front, in addition to *Martin Cooper* being appointed the [new PMC chair](../announce.html#a20050331) , one new committer, *Hubert Rabago* , accepted an invitation to join us, and we welcome back *David Geary* from emeritus to active status.

### <span id="Detailed_Changes"></span>Detailed Changes

This section contains the details of changes since version 1.2.4 with links to bugzilla tickets and Subversion Revision details. It is split into the following sub-sections.

-   [Version 1.2.7 Changes](#STRUTS_1_2_7)
-   [Version 1.2.6 Changes](#STRUTS_1_2_6)
-   [Version 1.2.5 Changes](#STRUTS_1_2_5)

### Version 1.2.7

After [Version 1.2.6 was tagged](http://svn.apache.org/viewcvs.cgi/struts/core/tags/STRUTS_1_2_6/) the [1.2 Branch](http://svn.apache.org/viewcvs.cgi/struts/core/branches/STRUTS_1_2_BRANCH/) was created and work started on the next version ( *1.3.x series* ). Work has continued on both versions and *Revision* numbers shown in brackets are where a change has been ported from the current development version into the *1.2 Branch* .

| Modification | Revision                                                                                                                                                                                                                                                                | Bugzilla                                                                                                                          | Description                                                                                                                                                                                                                                               |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 2005-05-05   | [168223](http://svn.apache.org/viewcvs?rev=168223&view=rev)                                                                                                                                                                                                             | *n/a*                                                                                                                             | Fix 1.2.x Build - remove duplicate "el" directory from "contrib".                                                                                                                                                                                         |
| 2005-05-05   | [168218](http://svn.apache.org/viewcvs?rev=168218&view=rev)                                                                                                                                                                                                             | *n/a*                                                                                                                             | Fix 1.2.x build to include struts-chain in the "contrib" directory (from sandbox STRUTS\_1\_2\_BRANCH).                                                                                                                                                   |
| 2005-05-03   | [168011](http://svn.apache.org/viewcvs?rev=168011&view=rev) ( [168012](http://svn.apache.org/viewcvs.cgi?rev=168012&view=rev) )                                                                                                                                         | *n/a*                                                                                                                             | Prevent NullPointerException when toString() is called before dynaClass is initialized.                                                                                                                                                                   |
| 2005-04-29   | [165304](http://svn.apache.org/viewcvs?rev=165304&view=rev) ( [165305](http://svn.apache.org/viewcvs.cgi?rev=165305&view=rev) )                                                                                                                                         | *n/a*                                                                                                                             | Retrieve FormTag stored in Request scope, rather than the TagSupport's findAncestorWithClass() .                                                                                                                                                          |
| 2005-04-29   | [165186](http://svn.apache.org/viewcvs?rev=165186&view=rev) ( [165208](http://svn.apache.org/viewcvs.cgi?rev=165208&view=rev) )                                                                                                                                         | *n/a*                                                                                                                             | Fixing value escape so that both backslashes and quotes are escaped correctly.                                                                                                                                                                            |
| 2005-04-28   | [165158](http://svn.apache.org/viewcvs?rev=165158&view=rev) ( [165160](http://svn.apache.org/viewcvs.cgi?rev=165160&view=rev) )                                                                                                                                         | [20034](http://issues.apache.org/bugzilla/show_bug.cgi?id=20034)                                                                  | Additional fix to "Invalid cache in InsertTag" for a problem on Orion.                                                                                                                                                                                    |
| 2005-04-28   | [165097](http://svn.apache.org/viewcvs?rev=165097&view=rev)                                                                                                                                                                                                             | [33989](http://issues.apache.org/bugzilla/show_bug.cgi?id=33989)                                                                  | Fix cactus tests to work with Cactus 1.7.                                                                                                                                                                                                                 |
| 2005-04-27   | [164922](http://svn.apache.org/viewcvs?rev=164922&view=rev) ( [164927](http://svn.apache.org/viewcvs.cgi?rev=164927&view=rev) )                                                                                                                                         | [23127](http://issues.apache.org/bugzilla/show_bug.cgi?id=23127)                                                                  | Page attribute of img and image tags doesn't use pagePattern setting.                                                                                                                                                                                     |
| 2005-04-26   | [164814](http://svn.apache.org/viewcvs?rev=164814&view=rev) ( [164831](http://svn.apache.org/viewcvs.cgi?rev=164831&view=rev) )                                                                                                                                         | [34624](http://issues.apache.org/bugzilla/show_bug.cgi?id=34624)                                                                  | BeanValidatorForm's getValidationKey method should call mapping.getAttribute().                                                                                                                                                                           |
| 2005-04-26   | [164745](http://svn.apache.org/viewcvs?rev=164745&view=rev) ( [164746](http://svn.apache.org/viewcvs.cgi?rev=164746&view=rev) )                                                                                                                                         | [31270](http://issues.apache.org/bugzilla/show_bug.cgi?id=31270)                                                                  | Add ActionDispatcher to provide dispatch behavior to classes that do not extend DispatchAction.                                                                                                                                                           |
| 2005-04-26   | [164729](http://svn.apache.org/viewcvs?rev=164729&view=rev) ( [164862](http://svn.apache.org/viewcvs.cgi?rev=164862&view=rev) )                                                                                                                                         | [19901](http://issues.apache.org/bugzilla/show_bug.cgi?id=19901)                                                                  | Add a check for null page value and throwing more informative exception.                                                                                                                                                                                  |
| 2005-04-26   | [164723](http://svn.apache.org/viewcvs?rev=164723&view=rev) ( [164860](http://svn.apache.org/viewcvs.cgi?rev=164860&view=rev) )                                                                                                                                         | [16653](http://issues.apache.org/bugzilla/show_bug.cgi?id=16653)                                                                  | Add a check for missing Validator Resources and throw a more useful error message.                                                                                                                                                                        |
| 2005-04-26   | [164718](http://svn.apache.org/viewcvs?rev=164718&view=rev) ( [164858](http://svn.apache.org/viewcvs.cgi?rev=164858&view=rev) )                                                                                                                                         | [31658](http://issues.apache.org/bugzilla/show_bug.cgi?id=31658)                                                                  | LogonAction does not check errors in appropriate place.                                                                                                                                                                                                   |
| 2005-04-25   | [164734](http://svn.apache.org/viewcvs?rev=164734&view=rev) ( [164703](http://svn.apache.org/viewcvs.cgi?rev=164703&view=rev) )                                                                                                                                         | [34314](http://issues.apache.org/bugzilla/show_bug.cgi?id=34314)                                                                  | Add TilesRequestProcessor handling for NoSuchDefinitionException.                                                                                                                                                                                         |
| 2005-04-25   | ( [164684](http://svn.apache.org/viewcvs.cgi?rev=164684&view=rev) )                                                                                                                                                                                                     | [33132](http://issues.apache.org/bugzilla/show_bug.cgi?id=33132)                                                                  | Implement Servlet 2.3/2.4 methods using reflection in MultipartRequestWrapper.                                                                                                                                                                            |
| 2005-04-25   | [164591](http://svn.apache.org/viewcvs.cgi?rev=164591&view=rev) ( [164590](http://svn.apache.org/viewcvs.cgi?rev=164590&view=rev) )                                                                                                                                     | *n/a*                                                                                                                             | Synchronize the *Nested* tag attributes for changes made in [Bug \#17708](http://issues.apache.org/bugzilla/show_bug.cgi?id=17708) and [Bug \#21603](http://issues.apache.org/bugzilla/show_bug.cgi?id=21603) .                                           |
| 2005-04-23   | [164343](http://svn.apache.org/viewcvs.cgi?rev=164343&view=rev) ( [164340](http://svn.apache.org/viewcvs.cgi?rev=164340&view=rev) )                                                                                                                                     | [33122](http://issues.apache.org/bugzilla/show_bug.cgi?id=33122)                                                                  | Resolve \.html.md:link\> ClassCastException when a non String paramId value already exists in the params map.                                                                                                                                                |
| 2005-04-21   | [162109](http://svn.apache.org/viewcvs.cgi?rev=162109&view=rev) ( [164337](http://svn.apache.org/viewcvs.cgi?rev=164337&view=rev) )                                                                                                                                     | [33918](http://issues.apache.org/bugzilla/show_bug.cgi?id=33918)                                                                  | Allow saving errors to the session in the same way that messages are.                                                                                                                                                                                     |
| 2005-04-21   | [162094](http://svn.apache.org/viewcvs.cgi?rev=162094&view=rev) ( [164334](http://svn.apache.org/viewcvs.cgi?rev=164334&view=rev) )                                                                                                                                     | [33238](http://issues.apache.org/bugzilla/show_bug.cgi?id=33238)                                                                  | Change JavascriptValidatorTag to escape double quotes in variable values.                                                                                                                                                                                 |
| 2005-04-12   | [161093](http://svn.apache.org/viewcvs.cgi?rev=161093&view=rev) ( [164336](http://svn.apache.org/viewcvs.cgi?rev=164336&view=rev) )                                                                                                                                     | *n/a*                                                                                                                             | Change DigestingPlugIn to give an explicit message when configSource/configPath yields a null URL.                                                                                                                                                        |
| 2005-04-06   | [160261](http://svn.apache.org/viewcvs.cgi?rev=160261&view=rev) ( [160262](http://svn.apache.org/viewcvs.cgi?rev=160262&view=rev) )                                                                                                                                     | [21603](http://issues.apache.org/bugzilla/show_bug.cgi?id=21603)                                                                  | Automatic readonly/disabled settings using new \.html.md:form\> tag attributes.                                                                                                                                                                              |
| 2005-04-06   | [160255](http://svn.apache.org/viewcvs.cgi?rev=160255&view=rev) ( [160256](http://svn.apache.org/viewcvs.cgi?rev=160256&view=rev) )                                                                                                                                     | [32778](http://issues.apache.org/bugzilla/show_bug.cgi?id=32778)                                                                  | Resolve HTML Link Tag not working with JSTL Loop Tag.                                                                                                                                                                                                     |
| 2005-03-31   | [159608](http://svn.apache.org/viewcvs.cgi?rev=159608&view=rev) ( [159609](http://svn.apache.org/viewcvs.cgi?rev=159609&view=rev) )                                                                                                                                     | *n/a*                                                                                                                             | Improve ValidWhen Exception Handling - exceptions are now logged and validation fails returning an error message with details of the error.                                                                                                               |
| 2005-03-31   | [159583](http://svn.apache.org/viewcvs.cgi?rev=159583&view=rev) ( [159606](http://svn.apache.org/viewcvs.cgi?rev=159606&view=rev) )                                                                                                                                     | *n/a*                                                                                                                             | A validwhen examples page and validation resource/bundles example pages (Server Side and JavaScript) have been added to the struts-examples webapp.                                                                                                       |
| 2005-03-29   | [159342](http://svn.apache.org/viewcvs.cgi?rev=159342&view=rev)                                                                                                                                                                                                         | *n/a*                                                                                                                             | Commons Validator dependency changed to version 1.1.4.                                                                                                                                                                                                    |
| 2005-03-28   | [159292](http://svn.apache.org/viewcvs.cgi?rev=159292&view=rev)                                                                                                                                                                                                         | *n/a*                                                                                                                             | Add "bundle" attribute to El version of JavascriptValidatorTag.                                                                                                                                                                                           |
| 2005-03-28   | [159269](http://svn.apache.org/viewcvs.cgi?rev=159269&view=rev) & [159268](http://svn.apache.org/viewcvs.cgi?rev=159268&view=rev) ( [159291](http://svn.apache.org/viewcvs.cgi?rev=159291&view=rev) )                                                                   | [21760](http://issues.apache.org/bugzilla/show_bug.cgi?id=21760) [18169](http://issues.apache.org/bugzilla/show_bug.cgi?id=18169) | Resolve \#21760 Support for non-default resource bundles in validation. Resolve \#18169 Resource attribute of msg tag in the validation.xml doesn't work.                                                                                                 |
| 2005-03-22   | [158622](http://svn.apache.org/viewcvs.cgi?rev=158622&view=rev) ( [158617](http://svn.apache.org/viewcvs.cgi?rev=158617&view=rev) )                                                                                                                                     | [34120](http://issues.apache.org/bugzilla/show_bug.cgi?id=34120)                                                                  | Fix invalid XML in the struts-doc-config.xml file in the Tiles Documentation webapp.                                                                                                                                                                      |
| 2005-03-20   | [158267](http://svn.apache.org/viewcvs.cgi?rev=158267&view=rev) ( [158730](http://svn.apache.org/viewcvs.cgi?rev=158730&view=rev) )                                                                                                                                     | [27089](http://issues.apache.org/bugzilla/show_bug.cgi?id=27089)                                                                  | Add doubleRange validator to the validator-rules.xml                                                                                                                                                                                                      |
| 2005-03-19   | [158216](http://svn.apache.org/viewcvs.cgi?rev=158216&view=rev) ( [158727](http://svn.apache.org/viewcvs.cgi?rev=158727&view=rev) )                                                                                                                                     | [34027](http://issues.apache.org/bugzilla/show_bug.cgi?id=34027)                                                                  | Name attribute is no longer rendered in the \.html.md:form\> tag if the rendering mode is XHTML.                                                                                                                                                             |
| 2005-03-14   | [157398](http://svn.apache.org/viewcvs.cgi?rev=157398&view=rev) ( [157399](http://svn.apache.org/viewcvs.cgi?rev=157399&view=rev) )                                                                                                                                     | [33876](http://issues.apache.org/bugzilla/show_bug.cgi?id=33876)                                                                  | JavaDoc corrections.                                                                                                                                                                                                                                      |
| 2005-03-14   | [157395](http://svn.apache.org/viewcvs.cgi?rev=157395&view=rev) ( [157397](http://svn.apache.org/viewcvs.cgi?rev=157397&view=rev) )                                                                                                                                     | [33998](http://issues.apache.org/bugzilla/show_bug.cgi?id=33998)                                                                  | Fix @link() tags                                                                                                                                                                                                                                          |
| 2005-02-15   | [153901](http://svn.apache.org/viewcvs.cgi?rev=153901&view=rev) ( [164747](http://svn.apache.org/viewcvs.cgi?rev=164747&view=rev) )                                                                                                                                     | [866](http://issues.apache.org/bugzilla/show_bug.cgi?id=866)                                                                      | Add ActionRedirect class to allow adding request parameters to redirecting forwards.                                                                                                                                                                      |
| 2005-02-09   | [153065](http://svn.apache.org/viewcvs.cgi?rev=153065&view=rev) ( [158605](http://svn.apache.org/viewcvs.cgi?rev=158605&view=rev) )                                                                                                                                     | [14042](http://issues.apache.org/bugzilla/show_bug.cgi?id=14042)                                                                  | Resolve memory leaks with JBoss 3.x +(Tomcat/Jetty).                                                                                                                                                                                                      |
| 2005-01-06   | [124417](http://svn.apache.org/viewcvs.cgi?rev=124417&view=rev) ( [124418](http://svn.apache.org/viewcvs.cgi?rev=124418&view=rev) )                                                                                                                                     | *n/a*                                                                                                                             | Change DownloadAction to use supplied buffer size.                                                                                                                                                                                                        |
| 2004-12-28   | [123473](http://svn.apache.org/viewcvs.cgi?rev=123473&view=rev)                                                                                                                                                                                                         | [32490](http://issues.apache.org/bugzilla/show_bug.cgi?id=32490)                                                                  | Sync up the EL tags with their non-EL counterparts. This adds the 'bundle' attribute to many tags, and also the 'error\*' attributes, and 'header', 'footer', 'prefix' and 'suffix' for the Errors tag.                                                   |
| 2004-12-27   | [123447](http://svn.apache.org/viewcvs.cgi?rev=123447&view=rev) , [123444](http://svn.apache.org/viewcvs.cgi?rev=123444&view=rev) & [123442](http://svn.apache.org/viewcvs.cgi?rev=123442&view=rev) ( [123587](http://svn.apache.org/viewcvs.cgi?rev=123587&view=rev) ) | [32504](http://issues.apache.org/bugzilla/show_bug.cgi?id=32504) [32016](http://issues.apache.org/bugzilla/show_bug.cgi?id=32016) | Change ModuleException to ensure all constructors invoke super. Resolve \#32504 - document the means used to format values in the \<bean:write\> tag. Resolve \#32016 - wrap the hidden token field in a \<div\> element for HTML 4.01 Strict compliance. |
| 2004-12-12   | [111630](http://svn.apache.org/viewcvs.cgi?rev=111630&view=rev) ( [159674](http://svn.apache.org/viewcvs.cgi?rev=159674&view=rev) )                                                                                                                                     | *n/a*                                                                                                                             | Remove use of "enum" as its a keyword in Java 5.                                                                                                                                                                                                          |
| 2004-11-20   | [106043](http://svn.apache.org/viewcvs.cgi?rev=106043&view=rev)                                                                                                                                                                                                         | *n/a*                                                                                                                             | **[1.2.x Branch](http://svn.apache.org/viewcvs.cgi/struts/core/branches/STRUTS_1_2_BRANCH/) created**                                                                                                                                                     |

### Version 1.2.6

Modification
Revision
Bugzilla
Description
2004-11-20
[106041](http://svn.apache.org/viewcvs.cgi?rev=106041&view=rev)
*n/a*
[Version 1.2.6](http://svn.apache.org/viewcvs.cgi/struts/core/tags/STRUTS_1_2_6/) tagged
2004-11-20
[105966](http://svn.apache.org/viewcvs.cgi?rev=105966&view=rev)
[31642](http://issues.apache.org/bugzilla/show_bug.cgi?id=31642)
Resolve \<bean:include\> always include Session id (if any) even for external Urls (href attribute)
2004-11-20
[105965](http://svn.apache.org/viewcvs.cgi?rev=105965&view=rev)
[32283](http://issues.apache.org/bugzilla/show_bug.cgi?id=32283)
Two slashes created by TagUtils.getActionMappingURL for webapps in root context
2004-11-20
[105963](http://svn.apache.org/viewcvs.cgi?rev=105963&view=rev)
[32265](http://issues.apache.org/bugzilla/show_bug.cgi?id=32265)
Add a warning to reset FormFile
2004-11-20
[105907](http://svn.apache.org/viewcvs.cgi?rev=105907&view=rev)
[32323](http://issues.apache.org/bugzilla/show_bug.cgi?id=32323)
Shale mailreader example should define the servlet version as 2.4
2004-11-19
[105888](http://svn.apache.org/viewcvs.cgi?rev=105888&view=rev)
*n/a*
Changes to update maven build after SVN layout re-org.
2004-11-19
[105881](http://svn.apache.org/viewcvs.cgi?rev=105881&view=rev)
*n/a*
Remove redundant definitions of maven.repo.central and maven.repo.central.directory
2004-11-19
[105785](http://svn.apache.org/viewcvs.cgi?rev=105785&view=rev)
*n/a*
Added ability to load struts, validator, and tiles config files from classloader if not found in the servlet context.
2004-11-19
[105787](http://svn.apache.org/viewcvs.cgi?rev=105787&view=rev)
*n/a*
Better handling of servlet initialization errors to mark the servlet as unavailable and notify the developer of the probable cause.
2004-11-18
[76271](http://svn.apache.org/viewcvs.cgi?rev=76271&view=rev)
*n/a*
Add missing base class for Shale test cases.
2004-11-17
[76098](http://svn.apache.org/viewcvs.cgi?rev=76098&view=rev)
[32134](http://issues.apache.org/bugzilla/show_bug.cgi?id=32134)
Must use contextRelative to forward to Actions in Default module.
2004-11-13
[57587](http://svn.apache.org/viewcvs.cgi?rev=57587&view=rev) - [65927](http://svn.apache.org/viewcvs.cgi?rev=65927&view=rev)
 (not consecutive)
Subversion repository rearranged into separate core, el, faces and sandbox subprojects.
2004-11-09
[57108](http://svn.apache.org/viewcvs.cgi?rev=57108&view=rev)
[31983](http://issues.apache.org/bugzilla/show_bug.cgi?id=31983)
Validator validwhen documentation typo.
2004-11-09
[57099](http://svn.apache.org/viewcvs.cgi?rev=57099&view=rev)
[32123](http://issues.apache.org/bugzilla/show_bug.cgi?id=32123)
DigestingPlugIn can't load a digester rule file.
2004-11-06
[56770](http://svn.apache.org/viewcvs.cgi?rev=56770&view=rev)
[32047](http://issues.apache.org/bugzilla/show_bug.cgi?id=32047)
"Created" boolean in FacesRequestProcessor.doForward() not being set
2004-11-05
[56678](http://svn.apache.org/viewcvs.cgi?rev=56678&view=rev)
[23924](http://issues.apache.org/bugzilla/show_bug.cgi?id=23924)
Improve TagUtils.filter() performance.
2004-11-03
[56532](http://svn.apache.org/viewcvs.cgi?rev=56532&view=rev)
*n/a*
Add LazyValidatorForm
2004-10-30
[56018](http://svn.apache.org/viewcvs.cgi?rev=56018&view=rev) , [56513](http://svn.apache.org/viewcvs.cgi?rev=56513&view=rev) , [56520](http://svn.apache.org/viewcvs.cgi?rev=56520&view=rev)
*n/a*
Change BeanUtils dependency to 1.7.0, Digester dependency to 1.6 and remove Collections Dependency
2004-10-30
[56011](http://svn.apache.org/viewcvs.cgi?rev=56011&view=rev)
*n/a*
Add "actions/DownloadAction.java", an abstract action that provides the nuts and bolts for downloading files.
2004-10-29
[55980](http://svn.apache.org/viewcvs.cgi?rev=55980&view=rev)
*n/a*
Document that if a link to a forward is used to switch modules, the path must point to an action.
2004-10-26
[55577](http://svn.apache.org/viewcvs.cgi?rev=55577&view=rev)
[31399](http://issues.apache.org/bugzilla/show_bug.cgi?id=31399)
Message resources file in Struts Blank is misplaced. [ [55584](http://svn.apache.org/viewcvs.cgi?rev=55584&view=rev) ] Update README with new layout.
2004-10-26
[55576](http://svn.apache.org/viewcvs.cgi?rev=55576&view=rev)
[31348](http://issues.apache.org/bugzilla/show_bug.cgi?id=31348)
Using a tiles definition as errorPage causes infinite looping
2004-10-24
[55416](http://svn.apache.org/viewcvs.cgi?rev=55416&view=rev)
[31761](http://issues.apache.org/bugzilla/show_bug.cgi?id=31761)
NullPointerException in ActionServlet
2004-10-22
[55318](http://svn.apache.org/viewcvs.cgi?rev=55318&view=rev)
[31850](http://issues.apache.org/bugzilla/show_bug.cgi?id=31850)
Implement Serializable on ActionServletWrapper
2004-10-20
[55110](http://svn.apache.org/viewcvs.cgi?rev=55110&view=rev)
*n/a*
Add documentation to base chain-config.xml to help Tiles users.
2004-10-18
[55025](http://svn.apache.org/viewcvs.cgi?rev=55025&view=rev)
[31755](http://issues.apache.org/bugzilla/show_bug.cgi?id=31755)
Document the default value for "scope" on an \<action\> element in the DTD for a struts-config.xml file (along with all the other documentation).
### Version 1.2.5

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Modification</th>
<th align="left">Revision</th>
<th align="left">Bugzilla</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">2004-10-17</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=54947&amp;view=rev">54947</a></td>
<td align="left"><em>n/a</em></td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi/struts/core/tags/STRUTS_1_2_5/">Version 1.2.5</a> tagged</td>
</tr>
<tr class="even">
<td align="left">2004-10-16</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=54936&amp;view=rev">54936</a></td>
<td align="left"><em>n/a</em></td>
<td align="left">Update several Javadoc parameter names to resolve Javadoc generation warnings</td>
</tr>
<tr class="odd">
<td align="left">2004-10-16</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=54892&amp;view=rev">54892</a></td>
<td align="left"><em>n/a</em></td>
<td align="left">Remove dependency on commons-lang.</td>
</tr>
<tr class="even">
<td align="left">2004-10-16</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=54889&amp;view=rev">54889</a></td>
<td align="left"><em>n/a</em></td>
<td align="left">Update roadmap for 1.2.4 / 1.2.5 releases.</td>
</tr>
<tr class="odd">
<td align="left">2004-10-09</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=54187&amp;view=rev">54187</a></td>
<td align="left"><em>n/a</em></td>
<td align="left">Move Struts-Faces from &quot;contrib&quot; to the trunk.</td>
</tr>
<tr class="even">
<td align="left">2004-10-03</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=51829&amp;view=rev">51829</a></td>
<td align="left"><em>n/a</em></td>
<td align="left">Add header,footer,prefix,suffix attributes to ErrorsTag.</td>
</tr>
<tr class="odd">
<td align="left">2004-10-03</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=51825&amp;view=rev">51825</a></td>
<td align="left"><a href="http://issues.apache.org/bugzilla/show_bug.cgi?id=31481">31481</a></td>
<td align="left">Have Tiles ControllerSupport execute() call perform() for backward compatibility. To be removed after version 1.2.</td>
</tr>
<tr class="even">
<td align="left">2004-10-03</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=51824&amp;view=rev">51824</a></td>
<td align="left"><em>n/a</em></td>
<td align="left">Add validwhen test to compare two Strings containing numbers.</td>
</tr>
<tr class="odd">
<td align="left">2004-10-03</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=51823&amp;view=rev">51823</a></td>
<td align="left"><a href="http://issues.apache.org/bugzilla/show_bug.cgi?id=31514">31514</a></td>
<td align="left">validwhen validator should do numeric compare when both items convertable to Integer.</td>
</tr>
<tr class="even">
<td align="left">2004-10-01</td>
<td align="left"><a href="http://svn.apache.org/viewcvs.cgi?rev=51759&amp;view=rev">51759</a></td>
<td align="left"><em>n/a</em></td>
<td align="left"><strong>Move repository to Subversion.</strong></td>
</tr>
<tr class="odd">
<td align="left">2004-09-23</td>
<td align="left"><em>cvs</em></td>
<td align="left"><a href="http://issues.apache.org/bugzilla/show_bug.cgi?id=17708">17708</a></td>
<td align="left">Better i18n and alternate bundle support for.html.md tags. Add missing &quot;bundle&quot; attribute to tld for html tags. Tags affected are ButtonTag, CancelTag, CheckboxTag, FileTag, FrameTag, HiddenTag, LinkTag, MultiboxTag, PasswordTag, RadioTag, ResetTag, SelectTag, SubmitTag,TextTag, TextareaTag. Also added a test for the bundle attribute for each of the above tags.</td>
</tr>
<tr class="even">
<td align="left">2004-09-23</td>
<td align="left"><em>cvs</em></td>
<td align="left"><a href="http://issues.apache.org/bugzilla/show_bug.cgi?id=31212">31212</a> <a href="http://issues.apache.org/bugzilla/show_bug.cgi?id=20417">20417</a></td>
<td align="left">Add missing nested tag attributes. Resolve #31212 &quot;nested:link module attribute not specified in tld&quot;. Resolve #20417 &quot;Attribute idName not declared for NestedRadioTag&quot;.</td>
</tr>
<tr class="odd">
<td align="left">2004-09-23</td>
<td align="left"><em>cvs</em></td>
<td align="left"><a href="http://issues.apache.org/bugzilla/show_bug.cgi?id=31374">31374</a></td>
<td align="left">Forward path in Validator struts-config.xml in struts-examples incorrect</td>
</tr>
<tr class="even">
<td align="left">2004-09-23</td>
<td align="left"><em>cvs</em></td>
<td align="left"><em>n/a</em></td>
<td align="left">Refactor some of the HTML tags make extending them easier.
<ul>
<li>added prepareOtherAttributes() method</li>
<li>added prepareName() method</li>
<li>use getters rather than instance variables</li>
<li>refactored SubmitTag - ButtonTag, CancelTag and ResetTag now inherit from SubmitTag.</li>
</ul></td>
</tr>
</tbody>
</table>

Next: [Installation](installation.html.md)

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


