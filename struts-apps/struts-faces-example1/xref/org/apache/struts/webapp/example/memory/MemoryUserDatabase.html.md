[View Javadoc](../../../../../../../apidocs/org/apache/struts/webapp/example/memory/MemoryUserDatabase.html.md)


    1   /*
    2    * $Id: MemoryUserDatabase.java 471754 2006-11-06 14:55:09Z husted $
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
    27  import java.io.File;
    28  import java.io.FileInputStream;
    29  import java.io.FileOutputStream;
    30  import java.io.IOException;
    31  import java.io.OutputStreamWriter;
    32  import java.io.PrintWriter;
    33  import java.util.HashMap;
    34  import org.apache.commons.digester.Digester;
    35  import org.apache.commons.digester.ObjectCreationFactory;
    36  import org.apache.commons.logging.Log;
    37  import org.apache.commons.logging.LogFactory;
    38  import org.apache.struts.webapp.example.Subscription;
    39  import org.apache.struts.webapp.example.User;
    40  import org.apache.struts.webapp.example.UserDatabase;
    41  import org.xml.sax.Attributes;
    42  
    43  
    44  /**
    45   * <p>Concrete implementation of {@link UserDatabase} for an in-memory
    46   * database backed by an XML data file.</p>
    47   *
    48   * @author Craig R. McClanahan
    49   * @version $Rev: 471754 $ $Date: 2006-11-06 08:55:09 -0600 (Mon, 06 Nov 2006) $
    50   * @since Struts 1.1
    51   */
    52  
    53  public final class MemoryUserDatabase implements UserDatabase {
    54  
    55  
    56      // ----------------------------------------------------------- Constructors
    57  
    58  
    59      // ----------------------------------------------------- Instance Variables
    60  
    61  
    62      /**
    63       * Logging output for this user database instance.
    64       */
    65      private Log log = LogFactory.getLog(this.getClass());
    66  
    67  
    68      /**
    69       * The {@link User}s associated with this UserDatabase, keyed by username.
    70       */
    71      private HashMap users = new HashMap();
    72  
    73  
    74      // ------------------------------------------------------------- Properties
    75  
    76  
    77      /**
    78       * Absolute pathname to the persistent file we use for loading and storing
    79       * persistent data.
    80       */
    81      private String pathname = null;
    82  
    83      private String pathnameOld = null;
    84  
    85      private String pathnameNew = null;
    86  
    87      public String getPathname() {
    88          return (this.pathname);
    89      }
    90  
    91      public void setPathname(String pathname) {
    92          this.pathname = pathname;
    93          pathnameOld = pathname + ".old";
    94          pathnameNew = pathname + ".new";
    95      }
    96  
    97  
    98      // --------------------------------------------------------- Public Methods
    99  
    100 
    101     /**
    102      * <p>Finalize access to the underlying persistence layer.</p>
    103      *
    104      * @exception Exception if a database access error occurs
    105      */
    106     public void close() throws Exception {
    107 
    108         save();
    109 
    110     }
    111 
    112 
    113     /**
    114      * <p>Create and return a new {@link User} defined in this user database.
    115      * </p>
    116      *
    117      * @param username Username of the new user
    118      *
    119      * @exception IllegalArgumentExceptionif the specified username
    120      *  is not unique
    121      */
    122     public User createUser(String username) {
    123 
    124         synchronized (users) {
    125             if (users.get(username) != null) {
    126                 throw new IllegalArgumentException("Duplicate user '" +
    127                                                    username + "'");
    128             }
    129             if (log.isTraceEnabled()) {
    130                 log.trace("Creating user '" + username + "'");
    131             }
    132             MemoryUser user = new MemoryUser(this, username);
    133             synchronized (users) {
    134                 users.put(username, user);
    135             }
    136             return (user);
    137         }
    138 
    139     }
    140 
    141 
    142     /**
    143      * <p>Return the existing {@link User} with the specified username,
    144      * if any; otherwise return <code>null</code>.</p>
    145      *
    146      * @param username Username of the user to retrieve
    147      */
    148     public User findUser(String username) {
    149 
    150         synchronized (users) {
    151             return ((User) users.get(username));
    152         }
    153 
    154     }
    155 
    156 
    157     /**
    158      * <p>Return the set of {@link User}s defined in this user database.</p>
    159      */
    160     public User[] findUsers() {
    161 
    162         synchronized (users) {
    163             User results[] = new User[users.size()];
    164             return ((User[]) users.values().toArray(results));
    165         }
    166 
    167     }
    168 
    169 
    170     /**
    171      * <p>Initiate access to the underlying persistence layer.</p>
    172      *
    173      * @exception Exception if a database access error occurs
    174      */
    175     public void open() throws Exception {
    176 
    177         FileInputStream fis = null;
    178         BufferedInputStream bis = null;
    179 
    180         try {
    181 
    182             // Acquire an input stream to our database file
    183             if (log.isDebugEnabled()) {
    184                 log.debug("Loading database from '" + pathname + "'");
    185             }
    186             fis = new FileInputStream(pathname);
    187             bis = new BufferedInputStream(fis);
    188 
    189             // Construct a digester to use for parsing
    190             Digester digester = new Digester();
    191             digester.push(this);
    192             digester.setValidating(false);
    193             digester.addFactoryCreate
    194                 ("database/user",
    195                  new MemoryUserCreationFactory(this));
    196             digester.addFactoryCreate
    197                 ("database/user/subscription",
    198                  new MemorySubscriptionCreationFactory(this));
    199 
    200             // Parse the input stream to initialize our database
    201             digester.parse(bis);
    202             bis.close();
    203             bis = null;
    204             fis = null;
    205 
    206         } catch (Exception e) {
    207 
    208             log.error("Loading database from '" + pathname + "':", e);
    209             throw e;
    210 
    211         } finally {
    212 
    213             if (bis != null) {
    214                 try {
    215                     bis.close();
    216                 } catch (Throwable t) {
    217                     ;
    218                 }
    219                 bis = null;
    220                 fis = null;
    221             }
    222 
    223         }
    224 
    225     }
    226 
    227 
    228     /**
    229      * Remove the specified {@link User} from this database.
    230      *
    231      * @param user User to be removed
    232      *
    233      * @exception IllegalArgumentException if the specified user is not
    234      *  associated with this database
    235      */
    236     public void removeUser(User user) {
    237 
    238         if (!(this == user.getDatabase())) {
    239             throw new IllegalArgumentException
    240                 ("User not associated with this database");
    241         }
    242         if (log.isTraceEnabled()) {
    243             log.trace("Removing user '" + user.getUsername() + "'");
    244         }
    245         synchronized (users) {
    246             users.remove(user.getUsername());
    247         }
    248 
    249     }
    250 
    251 
    252     /**
    253      * <p>Save any pending changes to the underlying persistence layer.</p>
    254      *
    255      * @exception Exception if a database access error occurs
    256      */
    257     public void save() throws Exception {
    258 
    259         if (log.isDebugEnabled()) {
    260             log.debug("Saving database to '" + pathname + "'");
    261         }
    262         File fileNew = new File(pathnameNew);
    263         PrintWriter writer = null;
    264 
    265         try {
    266 
    267             // Configure our PrintWriter
    268             FileOutputStream fos = new FileOutputStream(fileNew);
    269             OutputStreamWriter osw = new OutputStreamWriter(fos);
    270             writer = new PrintWriter(osw);
    271 
    272             // Print the file prolog
    273             writer.println("<?xml version='1.0'?>");
    274             writer.println("<database>");
    275 
    276             // Print entries for each defined user and associated subscriptions
    277             User users[] = findUsers();
    278             for (int i = 0; i < users.length; i++) {
    279                 writer.print("  ");
    280                 writer.println(users[i]);
    281                 Subscription subscriptions[] =
    282                     users[i].getSubscriptions();
    283                 for (int j = 0; j < subscriptions.length; j++) {
    284                     writer.print("    ");
    285                     writer.println(subscriptions[j]);
    286                     writer.print("    ");
    287                     writer.println("</subscription>");
    288                 }
    289                 writer.print("  ");
    290                 writer.println("</user>");
    291             }
    292 
    293             // Print the file epilog
    294             writer.println("</database>");
    295 
    296             // Check for errors that occurred while printing
    297             if (writer.checkError()) {
    298                 writer.close();
    299                 fileNew.delete();
    300                 throw new IOException
    301                     ("Saving database to '" + pathname + "'");
    302             }
    303             writer.close();
    304             writer = null;
    305 
    306         } catch (IOException e) {
    307 
    308             if (writer != null) {
    309                 writer.close();
    310             }
    311             fileNew.delete();
    312             throw e;
    313 
    314         }
    315 
    316 
    317         // Perform the required renames to permanently save this file
    318         File fileOrig = new File(pathname);
    319         File fileOld = new File(pathnameOld);
    320         if (fileOrig.exists()) {
    321             fileOld.delete();
    322             if (!fileOrig.renameTo(fileOld)) {
    323                 throw new IOException
    324                     ("Renaming '" + pathname + "' to '" + pathnameOld + "'");
    325             }
    326         }
    327         if (!fileNew.renameTo(fileOrig)) {
    328             if (fileOld.exists()) {
    329                 fileOld.renameTo(fileOrig);
    330             }
    331             throw new IOException
    332                 ("Renaming '" + pathnameNew + "' to '" + pathname + "'");
    333         }
    334         fileOld.delete();
    335 
    336     }
    337 
    338 
    339 }
    340 
    341 
    342 /**
    343  * Digester object creation factory for subscription instances.
    344  */
    345 class MemorySubscriptionCreationFactory implements ObjectCreationFactory {
    346 
    347     public MemorySubscriptionCreationFactory(MemoryUserDatabase database) {
    348     }
    349 
    350     private Digester digester = null;
    351 
    352     public Digester getDigester() {
    353         return (this.digester);
    354     }
    355 
    356     public void setDigester(Digester digester) {
    357         this.digester = digester;
    358     }
    359 
    360     public Object createObject(Attributes attributes) {
    361         String host = attributes.getValue("host");
    362         User user = (User) digester.peek();
    363         Subscription subscription = user.createSubscription(host);
    364         String autoConnect = attributes.getValue("autoConnect");
    365         if (autoConnect == null) {
    366             autoConnect = "false";
    367         }
    368         if ("true".equalsIgnoreCase(autoConnect) ||
    369             "yes".equalsIgnoreCase(autoConnect)) {
    370             subscription.setAutoConnect(true);
    371         } else {
    372             subscription.setAutoConnect(false);
    373         }
    374         subscription.setPassword(attributes.getValue("password"));
    375         subscription.setType(attributes.getValue("type"));
    376         subscription.setUsername(attributes.getValue("username"));
    377         return (subscription);
    378     }
    379 
    380 }
    381 
    382 
    383 /**
    384  * Digester object creation factory for user instances.
    385  */
    386 class MemoryUserCreationFactory implements ObjectCreationFactory {
    387 
    388     public MemoryUserCreationFactory(MemoryUserDatabase database) {
    389         this.database = database;
    390     }
    391 
    392     private MemoryUserDatabase database = null;
    393 
    394     private Digester digester = null;
    395 
    396     public Digester getDigester() {
    397         return (this.digester);
    398     }
    399 
    400     public void setDigester(Digester digester) {
    401         this.digester = digester;
    402     }
    403 
    404     public Object createObject(Attributes attributes) {
    405         String username = attributes.getValue("username");
    406         User user = database.createUser(username);
    407         user.setFromAddress(attributes.getValue("fromAddress"));
    408         user.setFullName(attributes.getValue("fullName"));
    409         user.setPassword(attributes.getValue("password"));
    410         user.setReplyToAddress(attributes.getValue("replyToAddress"));
    411         return (user);
    412     }
    413 
    414 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
