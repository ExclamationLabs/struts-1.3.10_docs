[View Javadoc](../../../../../../../apidocs/org/apache/struts/apps/scriptingmailreader/plugin/MemoryDatabasePlugIn.html.md)


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
    21  package org.apache.struts.apps.scriptingmailreader.plugin;
    22  
    23  
    24  import org.apache.commons.logging.Log;
    25  import org.apache.commons.logging.LogFactory;
    26  import org.apache.struts.action.ActionServlet;
    27  import org.apache.struts.action.PlugIn;
    28  import org.apache.struts.apps.scriptingmailreader.Constants;
    29  import org.apache.struts.apps.mailreader.dao.impl.memory.MemoryUserDatabase;
    30  import org.apache.struts.config.ModuleConfig;
    31  
    32  import javax.servlet.ServletException;
    33  import java.io.BufferedInputStream;
    34  import java.io.BufferedOutputStream;
    35  import java.io.File;
    36  import java.io.FileOutputStream;
    37  import java.io.InputStream;
    38  
    39  /**
    40   * <p><strong>MemoryDatabasePlugIn</strong> initializes and finalizes the
    41   * persistent storage of User and Subscription information for the Struts
    42   * Demonstration Application, using an in-memory database backed by an
    43   * XML file.</p>
    44   *
    45   * <p><strong>IMPLEMENTATION WARNING</strong> - If this web application is run
    46   * from a WAR file, or in another environment where reading and writing of the
    47   * web application resource is impossible, the initial contents will be copied
    48   * to a file in the web application temporary directory provided by the
    49   * container.  This is for demonstration purposes only - you should
    50   * <strong>NOT</strong> assume that files written here will survive a restart
    51   * of your servlet container.</p>
    52   *
    53   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    54   */
    55  
    56  public final class MemoryDatabasePlugIn implements PlugIn {
    57  
    58      // ---- Instance Variables ----
    59  
    60      /**
    61       * The {@link MemoryUserDatabase} object we construct and make available.
    62       */
    63      private MemoryUserDatabase database = null;
    64  
    65  
    66      /**
    67       * Logging output for this plug in instance.
    68       */
    69      private Log log = LogFactory.getLog(this.getClass());
    70  
    71  
    72      /**
    73       * The {@link ActionServlet} owning this application.
    74       */
    75      private ActionServlet servlet = null;
    76  
    77      // ---- Properties ----
    78  
    79      /**
    80       * The web application resource path of our persistent database
    81       * storage file.
    82       */
    83      private String pathname = "/WEB-INF/database.xml";
    84  
    85      public String getPathname() {
    86          return (this.pathname);
    87      }
    88  
    89      public void setPathname(String pathname) {
    90          this.pathname = pathname;
    91      }
    92  
    93      // ---- PlugIn Methods ----
    94  
    95  
    96      /**
    97       * Gracefully shut down this database, releasing any resources
    98       * that were allocated at initialization.
    99       */
    100     public void destroy() {
    101 
    102         log.info("Finalizing memory database plug in");
    103 
    104         if (database != null) {
    105             try {
    106                 database.close();
    107             } catch (Exception e) {
    108                 log.error("Closing memory database", e);
    109             }
    110         }
    111 
    112         servlet.getServletContext().removeAttribute(Constants.DATABASE_KEY);
    113         database = null;
    114         servlet = null;
    115         database = null;
    116     }
    117 
    118 
    119     /**
    120      * Initialize and load our initial database from persistent storage.
    121      *
    122      * @param servlet The ActionServlet for this web application
    123      * @param config  The ApplicationConfig for our owning module
    124      * @throws ServletException if we cannot configure ourselves correctly
    125      */
    126     public void init(ActionServlet servlet, ModuleConfig config)
    127             throws ServletException {
    128 
    129         log.info("Initializing memory database plug in from '" +
    130                 pathname + "'");
    131 
    132         // Remember our associated configuration and servlet
    133         this.servlet = servlet;
    134 
    135         // Construct a new database and make it available
    136         database = new MemoryUserDatabase();
    137         try {
    138             String path = calculatePath();
    139             if (log.isDebugEnabled()) {
    140                 log.debug(" Loading database from '" + path + "'");
    141             }
    142             database.setPathname(path);
    143             database.open();
    144         } catch (Exception e) {
    145             log.error("Opening memory database", e);
    146             throw new ServletException("Cannot load database from '" +
    147                     pathname + "'", e);
    148         }
    149 
    150         // Make the initialized database available
    151         servlet.getServletContext().setAttribute(Constants.DATABASE_KEY,
    152                 database);
    153 
    154     }
    155 
    156     // ---- Private Methods ----
    157 
    158     /**
    159      * Calculate and return an absolute pathname to the XML file to contain
    160      * our persistent storage information.
    161      *
    162      * @throws Exception if an input/output error occurs
    163      */
    164     private String calculatePath() throws Exception {
    165 
    166         // Can we access the database via file I/O?
    167         String path = servlet.getServletContext().getRealPath(pathname);
    168         if (path != null) {
    169             return (path);
    170         }
    171 
    172         // Does a copy of this file already exist in our temporary directory
    173         File dir = (File)
    174                 servlet.getServletContext().getAttribute
    175                         ("javax.servlet.context.tempdir");
    176         File file = new File(dir, "struts-example-database.xml");
    177         if (file.exists()) {
    178             return (file.getAbsolutePath());
    179         }
    180 
    181         // Copy the static resource to a temporary file and return its path
    182         InputStream is =
    183                 servlet.getServletContext().getResourceAsStream(pathname);
    184         BufferedInputStream bis = new BufferedInputStream(is, 1024);
    185         FileOutputStream os =
    186                 new FileOutputStream(file);
    187         BufferedOutputStream bos = new BufferedOutputStream(os, 1024);
    188         byte buffer[] = new byte[1024];
    189         while (true) {
    190             int n = bis.read(buffer);
    191             if (n <= 0) {
    192                 break;
    193             }
    194             bos.write(buffer, 0, n);
    195         }
    196         bos.close();
    197         bis.close();
    198         return (file.getAbsolutePath());
    199 
    200     }
    201 
    202 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
