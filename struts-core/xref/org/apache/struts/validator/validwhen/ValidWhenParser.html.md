[View Javadoc](../../../../../../apidocs/org/apache/struts/validator/validwhen/ValidWhenParser.html.md)


    1   // $ANTLR 2.7.6 (2005-12-22): "ValidWhenParser.g" -> "ValidWhenParser.java"$
    2   
    3   /*
    4    * $Id: ValidWhenParser.java 569606 2007-08-25 03:54:59Z pbenedict $
    5    *
    6    * Licensed to the Apache Software Foundation (ASF) under one
    7    * or more contributor license agreements.  See the NOTICE file
    8    * distributed with this work for additional information
    9    * regarding copyright ownership.  The ASF licenses this file
    10   * to you under the Apache License, Version 2.0 (the
    11   * "License"); you may not use this file except in compliance
    12   * with the License.  You may obtain a copy of the License at
    13   *
    14   *  http://www.apache.org/licenses/LICENSE-2.0
    15   *
    16   * Unless required by applicable law or agreed to in writing,
    17   * software distributed under the License is distributed on an
    18   * "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    19   * KIND, either express or implied.  See the License for the
    20   * specific language governing permissions and limitations
    21   * under the License.
    22   */
    23  
    24  package org.apache.struts.validator.validwhen;
    25  
    26  import java.util.Stack;
    27  import org.apache.commons.validator.util.ValidatorUtils;
    28  
    29  
    30  import antlr.TokenBuffer;
    31  import antlr.TokenStreamException;
    32  import antlr.TokenStreamIOException;
    33  import antlr.ANTLRException;
    34  import antlr.LLkParser;
    35  import antlr.Token;
    36  import antlr.TokenStream;
    37  import antlr.RecognitionException;
    38  import antlr.NoViableAltException;
    39  import antlr.MismatchedTokenException;
    40  import antlr.SemanticException;
    41  import antlr.ParserSharedInputState;
    42  import antlr.collections.impl.BitSet;
    43  
    44  public class ValidWhenParser extends antlr.LLkParser       implements ValidWhenParserTokenTypes
    45   {
    46  Stack argStack = new Stack();
    47  Object form;
    48  int index;
    49  String value;
    50  
    51      public void setForm(Object f) { form = f; };
    52      public void setIndex (int i) { index = i; };
    53      public void setValue (String v) { value = v; };
    54  
    55      public boolean getResult() {
    56         return ((Boolean)argStack.peek()).booleanValue();
    57      }
    58  
    59      private final int LESS_EQUAL=0;
    60      private final int LESS_THAN=1;
    61      private final int EQUAL=2;
    62      private final int GREATER_THAN=3;
    63      private final int GREATER_EQUAL=4;
    64      private final int NOT_EQUAL=5;
    65      private final int AND=6;
    66      private final int OR=7;
    67  
    68      private  boolean evaluateComparison (Object v1, Object compare, Object v2) {
    69          boolean intCompare = true;
    70     if ((v1 == null) || (v2 == null)) {
    71             if (String.class.isInstance(v1)) {
    72                     if (((String) v1).trim().length() == 0) {
    73                             v1 = null;
    74                     }
    75             }
    76             if (String.class.isInstance(v2)) {
    77                     if (((String) v2).trim().length() == 0) {
    78                             v2 = null;
    79                     }
    80             }
    81             switch (((Integer)compare).intValue()) {
    82             case LESS_EQUAL:
    83             case GREATER_THAN:
    84             case LESS_THAN:
    85             case GREATER_EQUAL:
    86                     return false;
    87             case EQUAL:
    88                 return (v1 == v2);
    89             case NOT_EQUAL:
    90                 return (v1 != v2);
    91             }
    92     }
    93        if ((Integer.class.isInstance(v1) ||
    94             String.class.isInstance(v1)) &&
    95         (Integer.class.isInstance(v2) ||
    96             String.class.isInstance(v2))) {
    97         intCompare = true;
    98        } else {
    99         intCompare = false;
    100  }
    101  if (intCompare) {
    102      try {
    103          int v1i = 0, v2i = 0;
    104          if (Integer.class.isInstance(v1)) {
    105              v1i = ((Integer)v1).intValue();
    106          } else {
    107              v1i = Integer.parseInt((String) v1);
    108          }
    109          if (Integer.class.isInstance(v2)) {
    110              v2i = ((Integer)v2).intValue();
    111          } else {
    112              v2i = Integer.parseInt((String) v2);
    113          }
    114          switch (((Integer)compare).intValue()) {
    115          case LESS_EQUAL:
    116              return (v1i <= v2i);
    117 
    118          case LESS_THAN:
    119              return (v1i < v2i);
    120 
    121          case EQUAL:
    122              return (v1i == v2i);
    123 
    124          case GREATER_THAN:
    125              return (v1i > v2i);
    126 
    127          case GREATER_EQUAL:
    128              return (v1i >= v2i);
    129 
    130          case NOT_EQUAL:
    131              return (v1i != v2i);
    132          }
    133      } catch (NumberFormatException ex) {};
    134  }
    135  String v1s = "", v2s = "";
    136 
    137  if (Integer.class.isInstance(v1)) {
    138      v1s = ((Integer)v1).toString();
    139  } else {
    140      v1s = (String) v1;
    141  }
    142 
    143  if (Integer.class.isInstance(v2)) {
    144      v2s = ((Integer)v2).toString();
    145  } else {
    146      v2s = (String) v2;
    147  }
    148 
    149  int res = v1s.compareTo(v2s);
    150  switch (((Integer)compare).intValue()) {
    151  case LESS_EQUAL:
    152      return (res <= 0);
    153 
    154  case LESS_THAN:
    155      return (res < 0);
    156 
    157  case EQUAL:
    158      return (res == 0);
    159 
    160  case GREATER_THAN:
    161      return (res > 0);
    162 
    163  case GREATER_EQUAL:
    164      return (res >= 0);
    165 
    166  case NOT_EQUAL:
    167      return (res != 0);
    168  }
    169  return true;
    170     }
    171 
    172 
    173 protected ValidWhenParser(TokenBuffer tokenBuf, int k) {
    174   super(tokenBuf,k);
    175   tokenNames = _tokenNames;
    176 }
    177 
    178 public ValidWhenParser(TokenBuffer tokenBuf) {
    179   this(tokenBuf,6);
    180 }
    181 
    182 protected ValidWhenParser(TokenStream lexer, int k) {
    183   super(lexer,k);
    184   tokenNames = _tokenNames;
    185 }
    186 
    187 public ValidWhenParser(TokenStream lexer) {
    188   this(lexer,6);
    189 }
    190 
    191 public ValidWhenParser(ParserSharedInputState state) {
    192   super(state,6);
    193   tokenNames = _tokenNames;
    194 }
    195 
    196  public final void integer() throws RecognitionException, TokenStreamException {
    197          
    198          Token  d = null;
    199          Token  h = null;
    200          Token  o = null;
    201          
    202          switch ( LA(1)) {
    203          case DECIMAL_LITERAL:
    204          {
    205                  d = LT(1);
    206                  match(DECIMAL_LITERAL);
    207                  argStack.push(Integer.decode(d.getText()));
    208                  break;
    209          }
    210          case HEX_LITERAL:
    211          {
    212                  h = LT(1);
    213                  match(HEX_LITERAL);
    214                  argStack.push(Integer.decode(h.getText()));
    215                  break;
    216          }
    217          case OCTAL_LITERAL:
    218          {
    219                  o = LT(1);
    220                  match(OCTAL_LITERAL);
    221                  argStack.push(Integer.decode(o.getText()));
    222                  break;
    223          }
    224          default:
    225          {
    226                  throw new NoViableAltException(LT(1), getFilename());
    227          }
    228          }
    229  }
    230  
    231  public final void string() throws RecognitionException, TokenStreamException {
    232          
    233          Token  str = null;
    234          
    235          str = LT(1);
    236          match(STRING_LITERAL);
    237          argStack.push(str.getText().substring(1, str.getText().length()-1));
    238  }
    239  
    240  public final void identifier() throws RecognitionException, TokenStreamException {
    241          
    242          Token  str = null;
    243          
    244          str = LT(1);
    245          match(IDENTIFIER);
    246          argStack.push(str.getText());
    247  }
    248  
    249  public final void field() throws RecognitionException, TokenStreamException {
    250          
    251          
    252          if ((LA(1)==IDENTIFIER) && (LA(2)==LBRACKET) && (LA(3)==RBRACKET) && (LA(4)==IDENTIFIER)) {
    253                  identifier();
    254                  match(LBRACKET);
    255                  match(RBRACKET);
    256                  identifier();
    257                  
    258                  Object i2 = argStack.pop();
    259                  Object i1 = argStack.pop();
    260                  argStack.push(ValidatorUtils.getValueAsString(form, i1 + "[" + index + "]" + i2));
    261                  
    262          }
    263          else if ((LA(1)==IDENTIFIER) && (LA(2)==LBRACKET) && ((LA(3) >= DECIMAL_LITERAL && LA(3) <= OCTAL_LITERAL)) && (LA(4)==RBRACKET) && (LA(5)==IDENTIFIER)) {
    264                  identifier();
    265                  match(LBRACKET);
    266                  integer();
    267                  match(RBRACKET);
    268                  identifier();
    269                  
    270                  Object i5 = argStack.pop();
    271                  Object i4 = argStack.pop();
    272                  Object i3 = argStack.pop();
    273                  argStack.push(ValidatorUtils.getValueAsString(form, i3 + "[" + i4 + "]" + i5));
    274                  
    275          }
    276          else if ((LA(1)==IDENTIFIER) && (LA(2)==LBRACKET) && ((LA(3) >= DECIMAL_LITERAL && LA(3) <= OCTAL_LITERAL)) && (LA(4)==RBRACKET) && (_tokenSet_0.member(LA(5)))) {
    277                  identifier();
    278                  match(LBRACKET);
    279                  integer();
    280                  match(RBRACKET);
    281                  
    282                  Object i7 = argStack.pop();
    283                  Object i6 = argStack.pop();
    284                  argStack.push(ValidatorUtils.getValueAsString(form, i6 + "[" + i7 + "]"));
    285                  
    286          }
    287          else if ((LA(1)==IDENTIFIER) && (LA(2)==LBRACKET) && (LA(3)==RBRACKET) && (_tokenSet_0.member(LA(4)))) {
    288                  identifier();
    289                  match(LBRACKET);
    290                  match(RBRACKET);
    291                  
    292                  Object i8 = argStack.pop();
    293                  argStack.push(ValidatorUtils.getValueAsString(form, i8 + "[" + index + "]"));
    294                  
    295          }
    296          else if ((LA(1)==IDENTIFIER) && (_tokenSet_0.member(LA(2)))) {
    297                  identifier();
    298                  
    299                  Object i9 = argStack.pop();
    300                  argStack.push(ValidatorUtils.getValueAsString(form, (String)i9));
    301                  
    302          }
    303          else {
    304                  throw new NoViableAltException(LT(1), getFilename());
    305          }
    306          
    307  }
    308  
    309  public final void literal() throws RecognitionException, TokenStreamException {
    310          
    311          
    312          switch ( LA(1)) {
    313          case DECIMAL_LITERAL:
    314          case HEX_LITERAL:
    315          case OCTAL_LITERAL:
    316          {
    317                  integer();
    318                  break;
    319          }
    320          case STRING_LITERAL:
    321          {
    322                  string();
    323                  break;
    324          }
    325          case LITERAL_null:
    326          {
    327                  match(LITERAL_null);
    328                  argStack.push(null);
    329                  break;
    330          }
    331          case THIS:
    332          {
    333                  match(THIS);
    334                  argStack.push(value);
    335                  break;
    336          }
    337          default:
    338          {
    339                  throw new NoViableAltException(LT(1), getFilename());
    340          }
    341          }
    342  }
    343  
    344  public final void value() throws RecognitionException, TokenStreamException {
    345          
    346          
    347          switch ( LA(1)) {
    348          case IDENTIFIER:
    349          {
    350                  field();
    351                  break;
    352          }
    353          case DECIMAL_LITERAL:
    354          case HEX_LITERAL:
    355          case OCTAL_LITERAL:
    356          case STRING_LITERAL:
    357          case LITERAL_null:
    358          case THIS:
    359          {
    360                  literal();
    361                  break;
    362          }
    363          default:
    364          {
    365                  throw new NoViableAltException(LT(1), getFilename());
    366          }
    367          }
    368  }
    369  
    370  public final void expression() throws RecognitionException, TokenStreamException {
    371          
    372          
    373          expr();
    374          match(Token.EOF_TYPE);
    375  }
    376  
    377  public final void expr() throws RecognitionException, TokenStreamException {
    378          
    379          
    380          if ((LA(1)==LPAREN) && (_tokenSet_1.member(LA(2)))) {
    381                  match(LPAREN);
    382                  comparisonExpression();
    383                  match(RPAREN);
    384          }
    385          else if ((LA(1)==LPAREN) && (LA(2)==LPAREN)) {
    386                  match(LPAREN);
    387                  joinedExpression();
    388                  match(RPAREN);
    389          }
    390          else {
    391                  throw new NoViableAltException(LT(1), getFilename());
    392          }
    393          
    394  }
    395  
    396  public final void comparisonExpression() throws RecognitionException, TokenStreamException {
    397          
    398          
    399          value();
    400          comparison();
    401          value();
    402          
    403                      Object v2 = argStack.pop();
    404                      Object comp = argStack.pop();
    405          Object v1 = argStack.pop();
    406          argStack.push(new Boolean(evaluateComparison(v1, comp, v2)));
    407          
    408  }
    409  
    410  public final void joinedExpression() throws RecognitionException, TokenStreamException {
    411          
    412          
    413          expr();
    414          join();
    415          expr();
    416          
    417          Boolean v1 = (Boolean) argStack.pop();
    418          Integer join = (Integer) argStack.pop();
    419          Boolean v2 = (Boolean) argStack.pop();
    420          if (join.intValue() == AND) {
    421          argStack.push(new Boolean(v1.booleanValue() && v2.booleanValue()));
    422          } else {
    423          argStack.push(new Boolean(v1.booleanValue() || v2.booleanValue()));
    424          }
    425          
    426  }
    427  
    428  public final void join() throws RecognitionException, TokenStreamException {
    429          
    430          
    431          switch ( LA(1)) {
    432          case ANDSIGN:
    433          {
    434                  match(ANDSIGN);
    435                  argStack.push(new Integer(AND));
    436                  break;
    437          }
    438          case ORSIGN:
    439          {
    440                  match(ORSIGN);
    441                  argStack.push(new Integer(OR));
    442                  break;
    443          }
    444          default:
    445          {
    446                  throw new NoViableAltException(LT(1), getFilename());
    447          }
    448          }
    449  }
    450  
    451  public final void comparison() throws RecognitionException, TokenStreamException {
    452          
    453          
    454          switch ( LA(1)) {
    455          case EQUALSIGN:
    456          {
    457                  match(EQUALSIGN);
    458                  argStack.push(new Integer(EQUAL));
    459                  break;
    460          }
    461          case GREATERTHANSIGN:
    462          {
    463                  match(GREATERTHANSIGN);
    464                  argStack.push(new Integer(GREATER_THAN));
    465                  break;
    466          }
    467          case GREATEREQUALSIGN:
    468          {
    469                  match(GREATEREQUALSIGN);
    470                  argStack.push(new Integer(GREATER_EQUAL));
    471                  break;
    472          }
    473          case LESSTHANSIGN:
    474          {
    475                  match(LESSTHANSIGN);
    476                  argStack.push(new Integer(LESS_THAN));
    477                  break;
    478          }
    479          case LESSEQUALSIGN:
    480          {
    481                  match(LESSEQUALSIGN);
    482                  argStack.push(new Integer(LESS_EQUAL));
    483                  break;
    484          }
    485          case NOTEQUALSIGN:
    486          {
    487                  match(NOTEQUALSIGN);
    488                  argStack.push(new Integer(NOT_EQUAL));
    489                  break;
    490          }
    491          default:
    492          {
    493                  throw new NoViableAltException(LT(1), getFilename());
    494          }
    495          }
    496  }
    497  
    498  
    499  public static final String[] _tokenNames = {
    500          "<0>",
    501          "EOF",
    502          "<2>",
    503          "NULL_TREE_LOOKAHEAD",
    504          "DECIMAL_LITERAL",
    505          "HEX_LITERAL",
    506          "OCTAL_LITERAL",
    507          "STRING_LITERAL",
    508          "IDENTIFIER",
    509          "LBRACKET",
    510          "RBRACKET",
    511          "\"null\"",
    512          "THIS",
    513          "LPAREN",
    514          "RPAREN",
    515          "\"and\"",
    516          "\"or\"",
    517          "EQUALSIGN",
    518          "GREATERTHANSIGN",
    519          "GREATEREQUALSIGN",
    520          "LESSTHANSIGN",
    521          "LESSEQUALSIGN",
    522          "NOTEQUALSIGN",
    523          "WS"
    524  };
    525  
    526  private static final long[] mk_tokenSet_0() {
    527          long[] data = { 8273920L, 0L};
    528          return data;
    529  }
    530  public static final BitSet _tokenSet_0 = new BitSet(mk_tokenSet_0());
    531  private static final long[] mk_tokenSet_1() {
    532          long[] data = { 6640L, 0L};
    533          return data;
    534  }
    535  public static final BitSet _tokenSet_1 = new BitSet(mk_tokenSet_1());
    536  
    537  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
