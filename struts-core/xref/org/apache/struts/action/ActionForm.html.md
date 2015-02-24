[View Javadoc](../../../../../apidocs/org/apache/struts/action/ActionForm.html.md)


    1   /*
    2    * $Id: ActionForm.java 471754 2006-11-06 14:55:09Z husted $
    3    *
    4    * Licensed to the Apache Software Foundation (ASF) under one
    5    * or more contributor license agreements.  See the NOTICE file
    6    * distributed with this work for additional information
    7    * regarding copyright ownership.  The ASF licenses this file
    8    * to you under the Apache License, Version 2.0 (the
    9    * "License"); you may not use this file except in compliance
    10   * with the License.  You may obtain a copy of the License at
    11   *
    12   *  http://www.apache.org/licenses/LICENSE-2.0
    13   *
    14   * Unless required by applicable law or agreed to in writing,
    15   * software distributed under the License is distributed on an
    16   * "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    17   * KIND, either express or implied.  See the License for the
    18   * specific language governing permissions and limitations
    19   * under the License.
    20   */
    21  package org.apache.struts.action;
    22  
    23  import org.apache.struts.upload.MultipartRequestHandler;
    24  
    25  import javax.servlet.ServletRequest;
    26  import javax.servlet.http.HttpServletRequest;
    27  
    28  import java.io.Serializable;
    29  
    30  /**
    31   * <p>An <strong>ActionForm</strong> is a JavaBean optionally associated with
    32   * one or more <code>ActionMappings</code>. Such a bean will have had its
    33   * properties initialized from the corresponding request parameters before the
    34   * corresponding <code>Action.execute</code> method is called.</p>
    35   *
    36   * <p>When the properties of this bean have been populated, but before the
    37   * <code>execute</code> method of the <code>Action</code> is called, this
    38   * bean's <code>validate</code> method will be called, which gives the bean a
    39   * chance to verify that the properties submitted by the user are correct and
    40   * valid. If this method finds problems, it returns an error messages object
    41   * that encapsulates those problems, and the controller servlet will return
    42   * control to the corresponding input form. Otherwise, the
    43   * <code>validate</code> method returns <code>null</code>, indicating that
    44   * everything is acceptable and the corresponding <code>Action.execute</code>
    45   * method should be called.</p>
    46   *
    47   * <p>This class must be subclassed in order to be instantiated. Subclasses
    48   * should provide property getter and setter methods for all of the bean
    49   * properties they wish to expose, plus override any of the public or
    50   * protected methods for which they wish to provide modified functionality.
    51   * </p>
    52   *
    53   * <p>Because ActionForms are JavaBeans, subclasses should also implement
    54   * <code>Serializable</code>, as required by the JavaBean specification. Some
    55   * containers require that an object meet all JavaBean requirements in order
    56   * to use the introspection API upon which ActionForms rely.</p>
    57   *
    58   * @version $Rev: 471754 $ $Date: 2005-11-12 08:14:24 -0500 (Sat, 12 Nov 2005)
    59   *          $
    60   */
    61  public abstract class ActionForm implements Serializable {
    62      // ----------------------------------------------------- Instance Variables
    63  
    64      /**
    65       * <p>The servlet instance to which we are attached.</p>
    66       */
    67      protected transient ActionServlet servlet = null;
    68  
    69      /**
    70       * <p>The MultipartRequestHandler for this form, can be
    71       * <code>null</code>.</p>
    72       */
    73      protected transient MultipartRequestHandler multipartRequestHandler;
    74  
    75      // ------------------------------------------------------------- Properties
    76  
    77      /**
    78       * <p>Return the servlet instance to which we are attached.</p>
    79       *
    80       * @return The servlet instance to which we are attached.
    81       */
    82      protected ActionServlet getServlet() {
    83          return (this.servlet);
    84      }
    85  
    86      /**
    87       * <p>Return the controller servlet instance to which we are attached. as
    88       * an <code>ActionServletWrapper</code>.</p>
    89       *
    90       * @return An instance of {@link ActionServletWrapper}
    91       * @see ActionServletWrapper
    92       * @since Struts 1.0.1
    93       */
    94      public ActionServletWrapper getServletWrapper() {
    95          return new ActionServletWrapper(getServlet());
    96      }
    97  
    98      /**
    99       * <p>Return the <code>MultipartRequestHandler</code> for this form The
    100      * reasoning behind this is to give form bean developers control over the
    101      * lifecycle of their multipart requests through the use of the
    102      * <code>finish</code> and/or <code>rollback</code> methods of
    103      * <code>MultipartRequestHandler</code>.  This method will return
    104      * <code>null</code> if this form's enctype is not "multipart/form-data".
    105      * </p>
    106      *
    107      * @return The {@link org.apache.struts.upload.MultipartRequestHandler}
    108      *         for this form.
    109      * @see org.apache.struts.upload.MultipartRequestHandler
    110      */
    111     public MultipartRequestHandler getMultipartRequestHandler() {
    112         return multipartRequestHandler;
    113     }
    114 
    115     /**
    116      * <p>Set the servlet instance to which we are attached (if
    117      * <code>servlet</code> is non-null).</p>
    118      *
    119      * @param servlet The new controller servlet, if any
    120      */
    121     public void setServlet(ActionServlet servlet) {
    122         this.servlet = servlet;
    123 
    124         // :FIXME: Should this be releasing resources?
    125     }
    126 
    127     /**
    128      * <p>Set the Handler provided for use in dealing with file uploads.</p>
    129      *
    130      * @param multipartRequestHandler The Handler to use for fileuploads.
    131      */
    132     public void setMultipartRequestHandler(
    133         MultipartRequestHandler multipartRequestHandler) {
    134         this.multipartRequestHandler = multipartRequestHandler;
    135     }
    136 
    137     // --------------------------------------------------------- Public Methods
    138 
    139     /**
    140      * <p>>Can be used to reset all bean properties to their default state.
    141      * This method is called before the properties are repopulated by the
    142      * controller.</p>
    143      *
    144      * <p>The default implementation attempts to forward to the HTTP version
    145      * of this method.</p>
    146      *
    147      * @param mapping The mapping used to select this instance
    148      * @param request The servlet request we are processing
    149      */
    150     public void reset(ActionMapping mapping, ServletRequest request) {
    151         try {
    152             reset(mapping, (HttpServletRequest) request);
    153         } catch (ClassCastException e) {
    154             ; // FIXME: Why would this ever happen except a null
    155         }
    156     }
    157 
    158     /**
    159      * <p>Can be used to reset bean properties to their default state, as
    160      * needed.  This method is called before the properties are repopulated by
    161      * the controller.</p>
    162      *
    163      * <p>The default implementation does nothing. In practice, the only
    164      * properties that need to be reset are those which represent checkboxes
    165      * on a session-scoped form. Otherwise, properties can be given initial
    166      * values where the field is declared. </p>
    167      *
    168      * <p>If the form is stored in session-scope so that values can be
    169      * collected over multiple requests (a "wizard"), you must be very careful
    170      * of which properties, if any, are reset. As mentioned, session-scope
    171      * checkboxes must be reset to false for any page where this property is
    172      * set. This is because the client does not submit a checkbox value when
    173      * it is clear (false). If a session-scoped checkbox is not proactively
    174      * reset, it can never be set to false.</p>
    175      *
    176      * <p>This method is <strong>not</strong> the appropriate place to
    177      * initialize form value for an "update" type page (this should be done in
    178      * a setup Action). You mainly need to worry about setting checkbox values
    179      * to false; most of the time you can leave this method unimplemented.
    180      * </p>
    181      *
    182      * @param mapping The mapping used to select this instance
    183      * @param request The servlet request we are processing
    184      */
    185     public void reset(ActionMapping mapping, HttpServletRequest request) {
    186         // Default implementation does nothing
    187     }
    188 
    189     /**
    190      * <p>Can be used to validate the properties that have been set for this
    191      * non-HTTP request, and return an <code>ActionErrors</code> object that
    192      * encapsulates any validation errors that have been found. If no errors
    193      * are found, return <code>null</code> or an <code>ActionErrors</code>
    194      * object with no recorded error messages.</p>
    195      *
    196      * <p>The default implementation attempts to forward to the HTTP version
    197      * of this method.</p>
    198      *
    199      * @param mapping The mapping used to select this instance
    200      * @param request The servlet request we are processing
    201      * @return The set of validation errors, if validation failed; an empty
    202      *         set or <code>null</code> if validation succeeded.
    203      */
    204     public ActionErrors validate(ActionMapping mapping, ServletRequest request) {
    205         try {
    206             return (validate(mapping, (HttpServletRequest) request));
    207         } catch (ClassCastException e) {
    208             return (null);
    209         }
    210     }
    211 
    212     /**
    213      * <p>Can be used to validate the properties that have been set for this
    214      * HTTP request, and return an <code>ActionErrors</code> object that
    215      * encapsulates any validation errors that have been found. If no errors
    216      * are found, return <code>null</code> or an <code>ActionErrors</code>
    217      * object with no recorded error messages.</p>
    218      *
    219      * <p>The default implementation performs no validation and returns
    220      * <code>null</code>. Subclasses must override this method to provide any
    221      * validation they wish to perform.</p>
    222      *
    223      * @param mapping The mapping used to select this instance
    224      * @param request The servlet request we are processing
    225      * @return The set of validation errors, if validation failed; an empty
    226      *         set or <code>null</code> if validation succeeded.
    227      * @see DynaActionForm
    228      */
    229     public ActionErrors validate(ActionMapping mapping,
    230         HttpServletRequest request) {
    231         return (null);
    232     }
    233 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
