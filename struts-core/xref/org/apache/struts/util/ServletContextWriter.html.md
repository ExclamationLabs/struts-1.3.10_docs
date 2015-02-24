[View Javadoc](../../../../../apidocs/org/apache/struts/util/ServletContextWriter.html.md)


    1   /*
    2    * $Id: ServletContextWriter.java 471754 2006-11-06 14:55:09Z husted $
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
    21  package org.apache.struts.util;
    22  
    23  import javax.servlet.ServletContext;
    24  
    25  import java.io.PrintWriter;
    26  import java.io.StringWriter;
    27  
    28  /**
    29   * A PrintWriter implementation that uses the logging facilities of a
    30   * <code>javax.servlet.ServletContext</code> to output its results.  Output
    31   * will be buffered until a newline character is output, <code>flush()</code>
    32   * is called, or until one of the <code>println()</code> methods is called.
    33   * Along the way, carriage return characters are skipped.
    34   *
    35   * @version $Rev: 471754 $ $Date: 2005-05-07 12:11:38 -0400 (Sat, 07 May 2005)
    36   *          $
    37   */
    38  public class ServletContextWriter extends PrintWriter {
    39      // ------------------------------------------------------------- Properties
    40  
    41      /**
    42       * The buffer into which we accumulate lines to be logged.
    43       */
    44      protected StringBuffer buffer = new StringBuffer();
    45  
    46      /**
    47       * The servlet context with which we are associated.
    48       */
    49      protected ServletContext context = null;
    50  
    51      /**
    52       * The error state for this stream.
    53       */
    54      protected boolean error = false;
    55  
    56      // ----------------------------------------------------------- Constructors
    57  
    58      /**
    59       * Construct a ServletContextWriter associated with the specified
    60       * ServletContext instance.
    61       *
    62       * @param context The associated servlet context
    63       */
    64      public ServletContextWriter(ServletContext context) {
    65          super(new StringWriter());
    66          this.context = context;
    67      }
    68  
    69      // --------------------------------------------------------- Public Methods
    70  
    71      /**
    72       * Flush the stream and check for its error state.  <strong>IMPLEMENTATION
    73       * NOTE</strong> - our associated servlet context gives no indication of
    74       * problems with logging, so the only way this method will return
    75       * <code>true</code> is if <code>setError()</code> is called.
    76       */
    77      public boolean checkError() {
    78          flush();
    79  
    80          return (error);
    81      }
    82  
    83      /**
    84       * Close the stream.
    85       */
    86      public void close() {
    87          flush();
    88      }
    89  
    90      /**
    91       * Flush the stream.
    92       */
    93      public void flush() {
    94          if (buffer.length() > 0) {
    95              context.log(buffer.toString());
    96              buffer.setLength(0);
    97          }
    98      }
    99  
    100     /**
    101      * Print a boolean value.
    102      *
    103      * @param b The value to be printed
    104      */
    105     public void print(boolean b) {
    106         write(String.valueOf(b));
    107     }
    108 
    109     /**
    110      * Print a character value.
    111      *
    112      * @param c The value to be printed
    113      */
    114     public void print(char c) {
    115         write(c);
    116     }
    117 
    118     /**
    119      * Print a character array.
    120      *
    121      * @param c The character array to be printed
    122      */
    123     public void print(char[] c) {
    124         for (int i = 0; i < c.length; i++) {
    125             write(c[i]);
    126         }
    127     }
    128 
    129     /**
    130      * Print a double value.
    131      *
    132      * @param d The value to be printed
    133      */
    134     public void print(double d) {
    135         write(String.valueOf(d));
    136     }
    137 
    138     /**
    139      * Print a float value.
    140      *
    141      * @param f The value to be printed
    142      */
    143     public void print(float f) {
    144         write(String.valueOf(f));
    145     }
    146 
    147     /**
    148      * Print an integer value.
    149      *
    150      * @param i The value to be printed
    151      */
    152     public void print(int i) {
    153         write(String.valueOf(i));
    154     }
    155 
    156     /**
    157      * Print a long value.
    158      *
    159      * @param l The value to be printed
    160      */
    161     public void print(long l) {
    162         write(String.valueOf(l));
    163     }
    164 
    165     /**
    166      * Print an object.
    167      *
    168      * @param o The value to be printed
    169      */
    170     public void print(Object o) {
    171         write(o.toString());
    172     }
    173 
    174     /**
    175      * Print a String value.
    176      *
    177      * @param s The value to be printed
    178      */
    179     public void print(String s) {
    180         int len = s.length();
    181 
    182         for (int i = 0; i < len; i++) {
    183             write(s.charAt(i));
    184         }
    185     }
    186 
    187     /**
    188      * Terminate the current line and flush the buffer.
    189      */
    190     public void println() {
    191         flush();
    192     }
    193 
    194     /**
    195      * Print a boolean value and terminate the line.
    196      *
    197      * @param b The value to be printed
    198      */
    199     public void println(boolean b) {
    200         println(String.valueOf(b));
    201     }
    202 
    203     /**
    204      * Print a character value and terminate the line.
    205      *
    206      * @param c The value to be printed
    207      */
    208     public void println(char c) {
    209         write(c);
    210         println();
    211     }
    212 
    213     /**
    214      * Print a character array and terminate the line.
    215      *
    216      * @param c The character array to be printed
    217      */
    218     public void println(char[] c) {
    219         for (int i = 0; i < c.length; i++) {
    220             print(c[i]);
    221         }
    222 
    223         println();
    224     }
    225 
    226     /**
    227      * Print a double value and terminate the line.
    228      *
    229      * @param d The value to be printed
    230      */
    231     public void println(double d) {
    232         println(String.valueOf(d));
    233     }
    234 
    235     /**
    236      * Print a float value and terminate the line.
    237      *
    238      * @param f The value to be printed
    239      */
    240     public void println(float f) {
    241         println(String.valueOf(f));
    242     }
    243 
    244     /**
    245      * Print an integer value and terminate the line.
    246      *
    247      * @param i The value to be printed
    248      */
    249     public void println(int i) {
    250         println(String.valueOf(i));
    251     }
    252 
    253     /**
    254      * Print a long value and terminate the line.
    255      *
    256      * @param l The value to be printed
    257      */
    258     public void println(long l) {
    259         println(String.valueOf(l));
    260     }
    261 
    262     /**
    263      * Print an object and terminate the line.
    264      *
    265      * @param o The value to be printed
    266      */
    267     public void println(Object o) {
    268         println(o.toString());
    269     }
    270 
    271     /**
    272      * Print a String value and terminate the line.
    273      *
    274      * @param s The value to be printed
    275      */
    276     public void println(String s) {
    277         int len = s.length();
    278 
    279         for (int i = 0; i < len; i++) {
    280             print(s.charAt(i));
    281         }
    282 
    283         println();
    284     }
    285 
    286     /**
    287      * Set the error state for this stream.
    288      */
    289     public void setError() {
    290         this.error = true;
    291     }
    292 
    293     /**
    294      * Write a single character to this stream.
    295      *
    296      * @param c The character to be written
    297      */
    298     public void write(char c) {
    299         if (c == '\n') {
    300             flush();
    301         } else if (c != '\r') {
    302             buffer.append(c);
    303         }
    304     }
    305 
    306     /**
    307      * Write a single character to this stream.
    308      *
    309      * @param c The character to be written
    310      */
    311     public void write(int c) {
    312         write((char) c);
    313     }
    314 
    315     /**
    316      * Write an array of charaters to this stream.
    317      *
    318      * @param buf The character array to be written
    319      */
    320     public void write(char[] buf) {
    321         for (int i = 0; i < buf.length; i++) {
    322             write(buf[i]);
    323         }
    324     }
    325 
    326     /**
    327      * Write the specified subset of an array of characters to this stream.
    328      *
    329      * @param buf The character array from which to write
    330      * @param off The zero-relative starting offset to write
    331      * @param len The number of characters to write
    332      */
    333     public void write(char[] buf, int off, int len) {
    334         for (int i = off; i < len; i++) {
    335             write(buf[i]);
    336         }
    337     }
    338 
    339     /**
    340      * Write a String to this stream.
    341      *
    342      * @param s The string to be written
    343      */
    344     public void write(String s) {
    345         int len = s.length();
    346 
    347         for (int i = 0; i < len; i++) {
    348             write(s.charAt(i));
    349         }
    350     }
    351 
    352     /**
    353      * Write the specified portion of a String to this stream.
    354      *
    355      * @param s   The String from which to write
    356      * @param off The zero-relative starting offset to write
    357      * @param len The number of characters to write
    358      */
    359     public void write(String s, int off, int len) {
    360         for (int i = off; i < len; i++) {
    361             write(s.charAt(i));
    362         }
    363     }
    364 }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
