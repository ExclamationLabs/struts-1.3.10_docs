<span id="bannerLeft">[![](http://www.apache.org/images/asf-logo.gif)](http://www.apache.org/)</span> <span id="bannerRight">[![](images/struts.gif)]()</span>

------------------------------------------------------------------------

Last Published: 2008-11-29

[Apache](http://www.apache.org/) | [Struts 2](2.x/) | [Struts 1](1.x/) | [Struts 1](1.x/) | [Struts 2](2.x/)

------------------------------------------------------------------------

##### Struts Taglib

-   [Welcome](index.html.md)

##### FAQs and HOWTOs

-   **Taglib FAQ**
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

<span id="top"></span>Taglib FAQ
--------------------------------

1.  [What about JSTL?](#jstl)
2.  [What about JSF?](#jsf)
3.  [Is Struts Taglib XHTML compliant?](#.html.md)
4.  [Will the Struts tags support other markup languages such as WML?](#wml)
5.  [Can I use multiple HTML form elements with the same name?](#multiple)
6.  [Can I have multiple submit buttons on the same form](#multipleSubmits)
7.  [Why doesn't the focus feature on the \.html.md:form\> tag work in every circumstance?](#focus)
8.  [Why are my checkboxes not being set from ON to OFF?](#checkbox)
9.  [Can I use JavaScript to submit a form?](#javascript.submit)
10. [How do I use JavaScript to ...](#javascript)
11. [Do I need to implement reset and set all my form properties to their initial values?](#reset)
12. [Can't I just create some of my JavaBeans in the JSP using a scriptlet?](#scriptlets)
13. [Why does the \.html.md:link\> tag URL-encode javascript and mailto links?](#link)
14. [How can I scroll through list of pages like the search results in Google?](#pager)
15. [Why does the option tag render selected=selected instead of just selected?](#minimization)
16. [Why does Struts Taglib provide for so little formatting?](#tags)
17. [Why doesn't Struts Taglib offer more layout options?](#layout)
18. [If you would like to contribute, here is a list of popular but undocumented questions](#undocumented)

<span id="jstl"></span>What about JSTL?  
There is overlap between Struts Taglib and the [JavaServer Standard Tag Library (JSTL).](http://java.sun.com/products/jsp/jstl/) To make the best use of JSTL, use the [Struts EL component](../struts-el/index.html.md) instead.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="jsf"></span>What about JSF?  
Struts 1 is **not** the best choice if you'd like to use JavaServer Faces components in your application. The Struts Faces component provides some interoperability with JSF, but Faces is really only intended as a stop gap for teams experimenting with JSF.

For better JavaServer Faces support, consider using Struts 2 or [Apache Shale.](http://shale.apache.org/)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id=".html.md"></span>Is Struts Taglib XHTML compliant?  
If you use an \.html.md:html xhtml="true\> or \<html:xhtml/\> element on your page, the tags will render as XHTML (since version 1.1).

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="wml"></span>Will the Struts tags support other markup languages such as WML?  
The framework itself is markup neutral. The original Struts taglibs are only one example of how presentation layer components can access the framework. The framework objects are exposed through the standard application, session, and request contexts, where any Java component in the application can make use of them.

Markup extensions that use the framework are available for [Velocity](http://jakarta.apache.org/velocity) and [XLST,](http://www.openroad.ca/opencode/) among others. A new Struts tag library for [Java Server Faces](#jsf) is also in development.

For more about using WAP/WML with Struts see the article [WAP up your EAserver.](http://www.sys-con.com/pbdj/archives2/0904/hamboeck/)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="multiple"></span>Can I use multiple HTML form elements with the same name?  
Yes. Define the element as an array and the framework will autopopulate it like any other.

                        
                            private String[] id= {};
                            public String[] getId() { return this.id; }
                            public void setItem(String id[]) {this.id = id;}
                       
                   

And so forth

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="multipleSubmits"></span>Can I have multiple submit buttons on the same form  
**Yes** . The issue is that only one action class can be associated with a single form. So the real issue is how do I decode multiple submit types to a single `Action` class. There is more than one way to achieve this functionality.

One popular approach is to use a [`LookupDispatchAction.`](../api/org/apache/struts/actions/LookupDispatchAction.html.md) Basically, `LookupDispatchAction` is using the keys from `ApplicationProperties.resources` as keys to a map of actions available to your `Action` class. It uses [reflection](http://java.sun.com/j2se/1.3/docs/guide/reflection/) to decode the request and invoke the proper action. It also takes advantage of the [`<html:submit>`](../userGuide/struts-html.html#submit) tags and is straight forward to implement.

You can roll your own with JavaScript events and `javascript:void (document.forms["myform"].submit)` on any.html.md element. This gives you control of how you want your page to look. Again you will have to decode the expected action in the `execute` method of your action form if you choose this route.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="focus"></span>Why doesn't the focus feature on the \.html.md:form\> tag work in every circumstance?  
Unfortunately, there is some disagreement between the various browsers, and different versions of the same browser, as to how the focus can be set. The \.html.md:form\> tag provides a quick and easy JavaScript that will set the focus on a form for most versions of most browsers. If this feature doesn't work for you, then you should set the focus using your own JavaScript. The focus feature is a convenient "value-add" -- not a core requirement of the tag. If you do come up with a JavaScript that provides the final solution to this project, please post your patch to this [JIRA ticket.](http://issues.apache.org/struts/browse/STR-899)

Another approach is to use a separate JavaScript that automatically focusses the first enabled field on the first form on a page. See the article [Set Focus to First Input on Web Page](http://www.codeproject.com/jscript/FocusFirstInput.asp) for a working example that you can use in your own applications.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="checkbox"></span>Why are my checkboxes not being set from ON to OFF?  
A problem with a checkbox is that the browser will only include it in the request when it is checked. If it is not checked, the HTML specification suggests that it not be sent (i.e. omitted from the request). If the value of the checkbox is being persisted, either in a session bean or in the model, a checked box can never unchecked by a HTML form -- because the form can never send a signal to uncheck the box. The application must somehow ascertain that since the element was not sent that the corresponding value is unchecked.

The recommended approach for framework applications is to use the reset method in the ActionForm to set all properties represented by checkboxes to null or false. The checked boxes submitted by the form will then set those properties to true. The omitted properties will remain false. Another solution is to use radio buttons instead, which always submit a value.

It is important to note that the HTML specification recommends this same behavior whenever a control is not "successful". Any blank element in a HTML form is not guaranteed to submitted. It is therefor very important to set the default values for an ActionForm correctly, and to implement the reset method when the ActionForm might kept in session scope.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="javascript.submit"></span>Can I use JavaScript to submit a form?  
You can submit a form with a link as below. BTW, the examples below assume you are in an \.html.md:form\> block and 'myForm' is picked up from the struts-config.xml name field of the action.

                        <a
                        href='javascript:void(document.forms["myForm"].submit()>My
                        Link</a>
                   

Now the trick in the action is to decode what action you intend to perform. Since you are using JavaScript, you could set a field value and look for it in the request or in the form.

....html.md/javascript part ...

                        <input type='hidden' value='myAction' />
                        <input type='button' value='Save Meeeee'
                        onclick='document.forms["myForm"].myAction.value="save";
                        document.forms["myForm"].submit();' />
                        <input type='button' value='Delete Meeeee'
                        onclick='document.forms["myForm"].myAction.value="delete";
                        document.forms["myForm"].submit();' />
                   

... the java part ...

                        class MyAction extends ActionForm implements Serializable
                        {

                        public ActionForward execute (ActionMapping map,
                        ActionForm form,
                        HttpServletRequest req, HttpServletResponse) {

                        String myAction = req.getParameter("myAction");

                        if (myAction.equals("save") {
                        // ... save action ...
                        } else if (myAction.equals("delete") {
                        // ... delete action ...
                        }
                        }
                        }
                        }
                   

This is just one of many ways to achieve submitting a form and decoding the intended action. Once you get used to the framework you will find other ways that make more sense for your coding style and requirements. Just remember this example is completely non-functional without JavaScript.

Here is a link which utilizes the LookupDispatch action to submit forms with multiple actions without javascript: <http://husted.com/struts/tips/003.html.md>

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="javascript"></span>How do I use JavaScript to ...  
The framework is mainly a server-side technology. We bundled in some JSP tags to expose the framework components to your presentation page, but past that, the usual development process applies.

Interactive pages require the use of JavaScript. (That's why it was invented.) If you want things popping up or doing this when they click that, you are outside the scope of the framework and back into the web development mainstream.

You use JavaScript with the framework the same way you use with any presentation page. Since JavaScript is a client-side technology, you can use simple relative references to your scripts. If you need to fire a JavaScript from a HTML control, the Struts HTML tags have properties for the JavaScript events.

A very good JavaScript resource is Matt Kruse's site at <http://www.mattkruse.com/javascript/>

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="reset"></span>Do I need to implement reset and set all my form properties to their initial values?  
No. You need to set checkbox properties to false if the ActionForm is being retained in session scope. This is because an unchecked box does not submit an attribute. Only checked boxes submit attributes. If the form is in session scope, and the checkbox was checked, there is no way to turn it back off without the reset method. Resetting the properties for other controls, or for a request scope form, is pointless. If the form is in request scope, everything already just started at the initial value.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="scriptlets"></span>Can't I just create some of my JavaBeans in the JSP using a scriptlet?  
The framework is designed to encourage a [Model 2/MVC architecture](http://www.javaworld.com/javaworld/jw-12-1999/jw-12-ssj-jspmvc.html.md) . But there is nothing that prevents you from using Model 1 techniques in your JavaServer Pages, so the answer to the question is "Yes, you can".

Though, using Model 1 techniques in a framework application does go against the grain. The approach recommended by most developers is to create and populate whatever objects the view may need in the Action, and then forward these through the request. Some objects may also be created and stored in the session or context, depending on how they are used.

Likewise, there is nothing to prevent you from using scriptlets along with JSP tags in your pages. Though, many developers report writing very complex scriplet-free applications and recommend the JSP tag approach to others.

For help with Model 1 techniques and scriptlets, you might consider joining the [Javasoft JSP-interest mailing list,](http://archives.java.sun.com/jsp-interest.html.md) where there are more people still using these approaches.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="link"></span>Why does the \.html.md:link\> tag URL-encode javascript and mailto links?  
The \.html.md:link\> tag is not intended for use with client-side references like those used to launch Javascripts or email clients. The purpose of link tag is to interject the context (or module) path into the URI so that your server-side links are not dependent on your context (or module) name. It also encodes the link, as needed, to maintain the client's session on the server. Neither feature applies to client-side links, so there is no reason to use the \<html:link\> tag. Simply markup the client-side links using the standard tag.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="pager"></span>How can I scroll through list of pages like the search results in Google?  
Many Struts developers use the Pager from the JSPTags site.

<http://jsptags.com/tags/navigation/pager/>

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="minimization"></span>Why does the option tag render selected=selected instead of just selected?  
Attribute minimization (that is, specifying an attribute with no value) is a place where HTML violates standard XML syntax rules. This matters a lot for people writing to browsers that support XHTML, where doing so makes the page invalid.It's much better for Struts to use the expanded syntax, which works the same on existing browsers interpreting HTML, and newer browsers that expect XHTML-compliant syntax. Struts is following the behavior recommended by the [XHTML specification](http://www.w3.org/TR/.html.md1/#h-4.5)

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="tags"></span>Why does Struts Taglib provide for so little formatting?  
*The Struts tags seem to provide only the most rudimentary functionality. Why is there not better support for date formatting and advanced string handling?*

Three historical reasons:

First, work started on the JSTL and we didn't want to duplicate the effort.

Second, work started on Java Server Faces, and we didn't want to duplicate that effort either.

Third, in a Model 2 application, most of the formatting can be handled in the ActionForms (or in the business tier), so all the tag has to do is spit out a string. This leads to better reuse since the same "how to format" code does not need to be repeated in every instance. You can "say it once" in a JavaBean and be done with it.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="layout"></span>Why doesn't Struts Taglib offer more layout options?  
For more flexible placement of error messages, try the [\.html.md2\>](http://www.rabago.net/struts/html2/) Tag Library for Struts.

Since the Struts tags are open source, you can extend them to provide whatever additional formatting you may need. If you are interested in a pre-written taglib that offers more layout options, see the [struts-layout taglib](http://struts.application-servers.com) .

In the same arena, there is a well regarded contributor taglib that can help you create [Menus for your Struts applications.](http://sourceforge.net/projects/struts-menu/)

Another very popular tag library is [DisplayTag.](http://displaytag.sourceforge.net) . DisplayTag is an excellent choice when you have tabular data to present.

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

<span id="undocumented"></span>If you would like to contribute, here is a list of popular but undocumented questions  
-   Why do my option lists disappear when validation fails?
-   Why can't I disable URL-encoding in the Struts taglibs?

|---------------|
| [[top]](#top) |

------------------------------------------------------------------------

© 2000-2008 Apache Software Foundation

------------------------------------------------------------------------


