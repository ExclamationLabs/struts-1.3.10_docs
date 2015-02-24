[View Javadoc](../../../../../../../apidocs/org/apache/struts/webapp/example/memory/MemoryDatabasePlugIn.html.md)


    1   /*
    2    * $Id: MemoryDatabasePlugIn.java 471754 2006-11-06 14:55:09Z husted $
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
    21  
    22  
    23  package org.apache.struts.webapp.example.memory;
    24  
    25  
    26  import java.io.BufferedInputStream;
    27  import java.io.BufferedOutputStream;
    28  import java.io.File;
    29  import java.io.FileOutputStream;
    30  import java.io.InputStream;
    31  import java.util.ArrayList;
    32  import javax.servlet.ServletException;
    33  import org.apache.commons.logging.Log;
    34  import org.apache.commons.logging.LogFactory;
    35  import org.apache.struts.action.ActionServlet;
    36  import org.apache.struts.action.PlugIn;
    37  import org.apache.struts.config.ModuleConfig;
    38  import org.apache.struts.util.LabelValueBean;
    39  import org.apache.struts.webapp.example.Constants;
    40  
    41  /**
    42   * <p><strong>MemoryDatabasePlugIn</strong> initializes and finalizes the
    43   * persistent storage of User and Subscription information for the Struts
    44   * Demonstration Application, using an in-memory database backed by an
    45   * XML file.</p>
    46   *
    47   * <p><strong>IMPLEMENTATION WARNING</strong> - If this web application is run
    48   * from a WAR file, or in another environment where reading and writing of the
    49   * web application resource is impossible, the initial contents will be copied
    50   * to a file in the web application temporary directory provided by the
    51   * container.  This is for demonstration purposes only - you should
    52   * <strong>NOT</strong> assume that files written here will survive a restart
    53   * of your servlet container.</p>
    54   *
    55   * @author Craig R. McClanahan
    56   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    57   */
    58  
    59  public final class MemoryDatabasePlugIn implements PlugIn {
    60  
    61  
    62      // ----------------------------------------------------- Instance Variables
    63  
    64  
    65      /**
    66       * The {@link MemoryUserDatabase} object we construct and make available.
    67       */
    68      private MemoryUserDatabase database = null;
    69  
    70  
    71      /**
    72       * Logging output for this plug in instance.
    73       */
    74      private Log log = LogFactory.getLog(this.getClass());
    75  
    76  
    77      /**
    78       * The {@link ActionServlet} owning this application.
    79       */
    80      private ActionServlet servlet = null;
    81  
    82  
    83      // ------------------------------------------------------------- Properties
    84  
    85  
    86      /**
    87       * The web application resource path of our persistent database
    88       * storage file.
    89       */
    90      private String pathname = "/WEB-INF/database.xml";
    91  
    92      public String getPathname() {
    93          return (this.pathname);
    94      }
    95  
    96      public void setPathname(String pathname) {
    97          this.pathname = pathname;
    98      }
    99  
    100 
    101     // --------------------------------------------------------- PlugIn Methods
    102 
    103 
    104     /**
    105      * Gracefully shut down this database, releasing any resources
    106      * that were allocated at initialization.
    107      */
    108     public void destroy() {
    109 
    110         log.info("Finalizing memory database plug in");
    111 
    112         if (database != null) {
    113             try {
    114                 database.close();
    115             } catch (Exception e) {
    116                 log.error("Closing memory database", e);
    117             }
    118         }
    119 
    120     servlet.getServletContext().removeAttribute(Constants.DATABASE_KEY);
    121         database = null;
    122         servlet = null;
    123         database = null;
    124 
    125     }
    126 
    127 
    128     /**
    129      * Initialize and load our initial database from persistent storage.
    130      *
    131      * @param servlet The ActionServlet for this web application
    132      * @param config The ApplicationConfig for our owning module
    133      *
    134      * @exception ServletException if we cannot configure ourselves correctly
    135      */
    136     public void init(ActionServlet servlet, ModuleConfig config)
    137         throws ServletException {
    138 
    139         log.info("Initializing memory database plug in from '" +
    140                  pathname + "'");
    141 
    142         // Remember our associated configuration and servlet
    143         this.servlet = servlet;
    144 
    145         // Construct a new database and make it available
    146         database = new MemoryUserDatabase();
    147         try {
    148             String path = calculatePath();
    149             if (log.isDebugEnabled()) {
    150                 log.debug(" Loading database from '" + path + "'");
    151             }
    152             database.setPathname(path);
    153             database.open();
    154         } catch (Exception e) {
    155             log.error("Opening memory database", e);
    156             throw new ServletException("Cannot load database from '" +
    157                                        pathname + "'", e);
    158         }
    159 
    160         // Make the initialized database available
    161         servlet.getServletContext().setAttribute(Constants.DATABASE_KEY,
    162                                                  database);
    163 
    164         // Setup and cache other required data
    165         setupCache(servlet, config);
    166 
    167     }
    168 
    169 
    170     // --------------------------------------------------------- Public Methods
    171 
    172 
    173     // ------------------------------------------------------ Protected Methods
    174 
    175 
    176     /**
    177      * <p>Cache commonly required data as servlet context attributes.</p>
    178      *
    179      * @param servlet The <code>ActionServlet</code> instance running
    180      *  this webapp
    181      * @param config The <code>ModuleConfig</code> for this application module
    182      */
    183     protected void setupCache(ActionServlet servlet, ModuleConfig config) {
    184 
    185         // Set up list of server types under "serverTypes"
    186         ArrayList serverTypes = new ArrayList();
    187         serverTypes.add(new LabelValueBean("IMAP Protocol", "imap"));
    188         serverTypes.add(new LabelValueBean("POP3 Protocol", "pop3"));
    189         servlet.getServletContext().setAttribute("serverTypes", serverTypes);
    190 
    191     }
    192 
    193 
    194 
    195 
    196     // -------------------------------------------------------- Private Methods
    197 
    198 
    199     /**
    200      * Calculate and return an absolute pathname to the XML file to contain
    201      * our persistent storage information.
    202      *
    203      * @exception Exception if an input/output error occurs
    204      */
    205     private String calculatePath() throws Exception {
    206 
    207         // Can we access the database via file I/O?
    208         String path = servlet.getServletContext().getRealPath(pathname);
    209         if (path != null) {
    210             return (path);
    211         }
    212 
    213         // Does a copy of this file already exist in our temporary directory
    214         File dir = (File)
    215             servlet.getServletContext().getAttribute
    216             ("javax.servlet.context.tempdir");
    217         File file = new File(dir, "struts-example-database.xml");
    218         if (file.exists()) {
    219             return (file.getAbsolutePath());
    220         }
    221 
    222         // Copy the static resource to a temporary file and return its path
    223         InputStream is =
    224             servlet.getServletContext().getResourceAsStream(pathname);
    225         BufferedInputStream bis = new BufferedInputStream(is, 1024);
    226         FileOutputStream os =
    227             new FileOutputStream(file);
    228         BufferedOutputStream bos = new BufferedOutputStream(os, 1024);
    229         byte buffer[] = new byte[1024];
    230         while (true) {
    231             int n = bis.read(buffer);
    232             if (n <= 0) {
    233                 break;
    234             }
    235             bos.write(buffer, 0, n);
    236         }
    237         bos.close();
    238         bis.close();
    239         return (file.getAbsolutePath());
    240 
    241     }
    242 
    243 
    244 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
