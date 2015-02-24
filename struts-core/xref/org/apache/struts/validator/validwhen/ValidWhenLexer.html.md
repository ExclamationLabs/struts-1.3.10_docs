[View Javadoc](../../../../../../apidocs/org/apache/struts/validator/validwhen/ValidWhenLexer.html.md)


    1   // $ANTLR 2.7.6 (2005-12-22): "ValidWhenParser.g" -> "ValidWhenLexer.java"$
    2   
    3   /*
    4    * $Id: ValidWhenLexer.java 569606 2007-08-25 03:54:59Z pbenedict $
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
    30  import java.io.InputStream;
    31  import antlr.TokenStreamException;
    32  import antlr.TokenStreamIOException;
    33  import antlr.TokenStreamRecognitionException;
    34  import antlr.CharStreamException;
    35  import antlr.CharStreamIOException;
    36  import antlr.ANTLRException;
    37  import java.io.Reader;
    38  import java.util.Hashtable;
    39  import antlr.CharScanner;
    40  import antlr.InputBuffer;
    41  import antlr.ByteBuffer;
    42  import antlr.CharBuffer;
    43  import antlr.Token;
    44  import antlr.CommonToken;
    45  import antlr.RecognitionException;
    46  import antlr.NoViableAltForCharException;
    47  import antlr.MismatchedCharException;
    48  import antlr.TokenStream;
    49  import antlr.ANTLRHashString;
    50  import antlr.LexerSharedInputState;
    51  import antlr.collections.impl.BitSet;
    52  import antlr.SemanticException;
    53  
    54  public class ValidWhenLexer extends antlr.CharScanner implements ValidWhenParserTokenTypes, TokenStream
    55   {
    56  public ValidWhenLexer(InputStream in) {
    57     this(new ByteBuffer(in));
    58  }
    59  public ValidWhenLexer(Reader in) {
    60     this(new CharBuffer(in));
    61  }
    62  public ValidWhenLexer(InputBuffer ib) {
    63     this(new LexerSharedInputState(ib));
    64  }
    65  public ValidWhenLexer(LexerSharedInputState state) {
    66     super(state);
    67     caseSensitiveLiterals = true;
    68     setCaseSensitive(false);
    69     literals = new Hashtable();
    70     literals.put(new ANTLRHashString("null", this), new Integer(11));
    71     literals.put(new ANTLRHashString("or", this), new Integer(16));
    72     literals.put(new ANTLRHashString("and", this), new Integer(15));
    73  }
    74  
    75  public Token nextToken() throws TokenStreamException {
    76     Token theRetToken=null;
    77  tryAgain:
    78     for (;;) {
    79             Token _token = null;
    80             int _ttype = Token.INVALID_TYPE;
    81             resetText();
    82             try {   // for char stream error handling
    83                     try {   // for lexical error handling
    84                             switch ( LA(1)) {
    85                             case '\t':  case '\n':  case '\r':  case ' ':
    86                             {
    87                                     mWS(true);
    88                                     theRetToken=_returnToken;
    89                                     break;
    90                             }
    91                             case '-':  case '1':  case '2':  case '3':
    92                             case '4':  case '5':  case '6':  case '7':
    93                             case '8':  case '9':
    94                             {
    95                                     mDECIMAL_LITERAL(true);
    96                                     theRetToken=_returnToken;
    97                                     break;
    98                             }
    99                             case '"':  case '\'':
    100                          {
    101                                  mSTRING_LITERAL(true);
    102                                  theRetToken=_returnToken;
    103                                  break;
    104                          }
    105                          case '[':
    106                          {
    107                                  mLBRACKET(true);
    108                                  theRetToken=_returnToken;
    109                                  break;
    110                          }
    111                          case ']':
    112                          {
    113                                  mRBRACKET(true);
    114                                  theRetToken=_returnToken;
    115                                  break;
    116                          }
    117                          case '(':
    118                          {
    119                                  mLPAREN(true);
    120                                  theRetToken=_returnToken;
    121                                  break;
    122                          }
    123                          case ')':
    124                          {
    125                                  mRPAREN(true);
    126                                  theRetToken=_returnToken;
    127                                  break;
    128                          }
    129                          case '*':
    130                          {
    131                                  mTHIS(true);
    132                                  theRetToken=_returnToken;
    133                                  break;
    134                          }
    135                          case '.':  case '_':  case 'a':  case 'b':
    136                          case 'c':  case 'd':  case 'e':  case 'f':
    137                          case 'g':  case 'h':  case 'i':  case 'j':
    138                          case 'k':  case 'l':  case 'm':  case 'n':
    139                          case 'o':  case 'p':  case 'q':  case 'r':
    140                          case 's':  case 't':  case 'u':  case 'v':
    141                          case 'w':  case 'x':  case 'y':  case 'z':
    142                          {
    143                                  mIDENTIFIER(true);
    144                                  theRetToken=_returnToken;
    145                                  break;
    146                          }
    147                          case '=':
    148                          {
    149                                  mEQUALSIGN(true);
    150                                  theRetToken=_returnToken;
    151                                  break;
    152                          }
    153                          case '!':
    154                          {
    155                                  mNOTEQUALSIGN(true);
    156                                  theRetToken=_returnToken;
    157                                  break;
    158                          }
    159                          default:
    160                                  if ((LA(1)=='0') && (LA(2)=='x')) {
    161                                          mHEX_LITERAL(true);
    162                                          theRetToken=_returnToken;
    163                                  }
    164                                  else if ((LA(1)=='<') && (LA(2)=='=')) {
    165                                          mLESSEQUALSIGN(true);
    166                                          theRetToken=_returnToken;
    167                                  }
    168                                  else if ((LA(1)=='>') && (LA(2)=='=')) {
    169                                          mGREATEREQUALSIGN(true);
    170                                          theRetToken=_returnToken;
    171                                  }
    172                                  else if ((LA(1)=='0') && (true)) {
    173                                          mOCTAL_LITERAL(true);
    174                                          theRetToken=_returnToken;
    175                                  }
    176                                  else if ((LA(1)=='<') && (true)) {
    177                                          mLESSTHANSIGN(true);
    178                                          theRetToken=_returnToken;
    179                                  }
    180                                  else if ((LA(1)=='>') && (true)) {
    181                                          mGREATERTHANSIGN(true);
    182                                          theRetToken=_returnToken;
    183                                  }
    184                          else {
    185                                  if (LA(1)==EOF_CHAR) {uponEOF(); _returnToken = makeToken(Token.EOF_TYPE);}
    186                          else {throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());}
    187                          }
    188                          }
    189                          if ( _returnToken==null ) continue tryAgain; // found SKIP token
    190                          _ttype = _returnToken.getType();
    191                          _ttype = testLiteralsTable(_ttype);
    192                          _returnToken.setType(_ttype);
    193                          return _returnToken;
    194                  }
    195                  catch (RecognitionException e) {
    196                          throw new TokenStreamRecognitionException(e);
    197                  }
    198          }
    199          catch (CharStreamException cse) {
    200                  if ( cse instanceof CharStreamIOException ) {
    201                          throw new TokenStreamIOException(((CharStreamIOException)cse).io);
    202                  }
    203                  else {
    204                          throw new TokenStreamException(cse.getMessage());
    205                  }
    206          }
    207  }
    208 }
    209 
    210  public final void mWS(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    211          int _ttype; Token _token=null; int _begin=text.length();
    212          _ttype = WS;
    213          int _saveIndex;
    214          
    215          {
    216          int _cnt15=0;
    217          _loop15:
    218          do {
    219                  switch ( LA(1)) {
    220                  case ' ':
    221                  {
    222                          match(' ');
    223                          break;
    224                  }
    225                  case '\t':
    226                  {
    227                          match('\t');
    228                          break;
    229                  }
    230                  case '\n':
    231                  {
    232                          match('\n');
    233                          break;
    234                  }
    235                  case '\r':
    236                  {
    237                          match('\r');
    238                          break;
    239                  }
    240                  default:
    241                  {
    242                          if ( _cnt15>=1 ) { break _loop15; } else {throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());}
    243                  }
    244                  }
    245                  _cnt15++;
    246          } while (true);
    247          }
    248          _ttype = Token.SKIP;
    249          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    250                  _token = makeToken(_ttype);
    251                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    252          }
    253          _returnToken = _token;
    254  }
    255  
    256  public final void mDECIMAL_LITERAL(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    257          int _ttype; Token _token=null; int _begin=text.length();
    258          _ttype = DECIMAL_LITERAL;
    259          int _saveIndex;
    260          
    261          {
    262          switch ( LA(1)) {
    263          case '-':
    264          {
    265                  match('-');
    266                  break;
    267          }
    268          case '1':  case '2':  case '3':  case '4':
    269          case '5':  case '6':  case '7':  case '8':
    270          case '9':
    271          {
    272                  break;
    273          }
    274          default:
    275          {
    276                  throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());
    277          }
    278          }
    279          }
    280          {
    281          matchRange('1','9');
    282          }
    283          {
    284          _loop20:
    285          do {
    286                  if (((LA(1) >= '0' && LA(1) <= '9'))) {
    287                          matchRange('0','9');
    288                  }
    289                  else {
    290                          break _loop20;
    291                  }
    292                  
    293          } while (true);
    294          }
    295          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    296                  _token = makeToken(_ttype);
    297                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    298          }
    299          _returnToken = _token;
    300  }
    301  
    302  public final void mHEX_LITERAL(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    303          int _ttype; Token _token=null; int _begin=text.length();
    304          _ttype = HEX_LITERAL;
    305          int _saveIndex;
    306          
    307          match('0');
    308          match('x');
    309          {
    310          int _cnt23=0;
    311          _loop23:
    312          do {
    313                  switch ( LA(1)) {
    314                  case '0':  case '1':  case '2':  case '3':
    315                  case '4':  case '5':  case '6':  case '7':
    316                  case '8':  case '9':
    317                  {
    318                          matchRange('0','9');
    319                          break;
    320                  }
    321                  case 'a':  case 'b':  case 'c':  case 'd':
    322                  case 'e':  case 'f':
    323                  {
    324                          matchRange('a','f');
    325                          break;
    326                  }
    327                  default:
    328                  {
    329                          if ( _cnt23>=1 ) { break _loop23; } else {throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());}
    330                  }
    331                  }
    332                  _cnt23++;
    333          } while (true);
    334          }
    335          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    336                  _token = makeToken(_ttype);
    337                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    338          }
    339          _returnToken = _token;
    340  }
    341  
    342  public final void mOCTAL_LITERAL(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    343          int _ttype; Token _token=null; int _begin=text.length();
    344          _ttype = OCTAL_LITERAL;
    345          int _saveIndex;
    346          
    347          match('0');
    348          {
    349          _loop26:
    350          do {
    351                  if (((LA(1) >= '0' && LA(1) <= '7'))) {
    352                          matchRange('0','7');
    353                  }
    354                  else {
    355                          break _loop26;
    356                  }
    357                  
    358          } while (true);
    359          }
    360          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    361                  _token = makeToken(_ttype);
    362                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    363          }
    364          _returnToken = _token;
    365  }
    366  
    367  public final void mSTRING_LITERAL(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    368          int _ttype; Token _token=null; int _begin=text.length();
    369          _ttype = STRING_LITERAL;
    370          int _saveIndex;
    371          
    372          switch ( LA(1)) {
    373          case '\'':
    374          {
    375                  {
    376                  match('\'');
    377                  {
    378                  int _cnt30=0;
    379                  _loop30:
    380                  do {
    381                          if ((_tokenSet_0.member(LA(1)))) {
    382                                  matchNot('\'');
    383                          }
    384                          else {
    385                                  if ( _cnt30>=1 ) { break _loop30; } else {throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());}
    386                          }
    387                          
    388                          _cnt30++;
    389                  } while (true);
    390                  }
    391                  match('\'');
    392                  }
    393                  break;
    394          }
    395          case '"':
    396          {
    397                  {
    398                  match('\"');
    399                  {
    400                  int _cnt33=0;
    401                  _loop33:
    402                  do {
    403                          if ((_tokenSet_1.member(LA(1)))) {
    404                                  matchNot('\"');
    405                          }
    406                          else {
    407                                  if ( _cnt33>=1 ) { break _loop33; } else {throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());}
    408                          }
    409                          
    410                          _cnt33++;
    411                  } while (true);
    412                  }
    413                  match('\"');
    414                  }
    415                  break;
    416          }
    417          default:
    418          {
    419                  throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());
    420          }
    421          }
    422          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    423                  _token = makeToken(_ttype);
    424                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    425          }
    426          _returnToken = _token;
    427  }
    428  
    429  public final void mLBRACKET(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    430          int _ttype; Token _token=null; int _begin=text.length();
    431          _ttype = LBRACKET;
    432          int _saveIndex;
    433          
    434          match('[');
    435          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    436                  _token = makeToken(_ttype);
    437                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    438          }
    439          _returnToken = _token;
    440  }
    441  
    442  public final void mRBRACKET(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    443          int _ttype; Token _token=null; int _begin=text.length();
    444          _ttype = RBRACKET;
    445          int _saveIndex;
    446          
    447          match(']');
    448          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    449                  _token = makeToken(_ttype);
    450                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    451          }
    452          _returnToken = _token;
    453  }
    454  
    455  public final void mLPAREN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    456          int _ttype; Token _token=null; int _begin=text.length();
    457          _ttype = LPAREN;
    458          int _saveIndex;
    459          
    460          match('(');
    461          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    462                  _token = makeToken(_ttype);
    463                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    464          }
    465          _returnToken = _token;
    466  }
    467  
    468  public final void mRPAREN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    469          int _ttype; Token _token=null; int _begin=text.length();
    470          _ttype = RPAREN;
    471          int _saveIndex;
    472          
    473          match(')');
    474          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    475                  _token = makeToken(_ttype);
    476                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    477          }
    478          _returnToken = _token;
    479  }
    480  
    481  public final void mTHIS(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    482          int _ttype; Token _token=null; int _begin=text.length();
    483          _ttype = THIS;
    484          int _saveIndex;
    485          
    486          match("*this*");
    487          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    488                  _token = makeToken(_ttype);
    489                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    490          }
    491          _returnToken = _token;
    492  }
    493  
    494  public final void mIDENTIFIER(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    495          int _ttype; Token _token=null; int _begin=text.length();
    496          _ttype = IDENTIFIER;
    497          int _saveIndex;
    498          
    499          {
    500          switch ( LA(1)) {
    501          case 'a':  case 'b':  case 'c':  case 'd':
    502          case 'e':  case 'f':  case 'g':  case 'h':
    503          case 'i':  case 'j':  case 'k':  case 'l':
    504          case 'm':  case 'n':  case 'o':  case 'p':
    505          case 'q':  case 'r':  case 's':  case 't':
    506          case 'u':  case 'v':  case 'w':  case 'x':
    507          case 'y':  case 'z':
    508          {
    509                  matchRange('a','z');
    510                  break;
    511          }
    512          case '.':
    513          {
    514                  match('.');
    515                  break;
    516          }
    517          case '_':
    518          {
    519                  match('_');
    520                  break;
    521          }
    522          default:
    523          {
    524                  throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());
    525          }
    526          }
    527          }
    528          {
    529          int _cnt42=0;
    530          _loop42:
    531          do {
    532                  switch ( LA(1)) {
    533                  case 'a':  case 'b':  case 'c':  case 'd':
    534                  case 'e':  case 'f':  case 'g':  case 'h':
    535                  case 'i':  case 'j':  case 'k':  case 'l':
    536                  case 'm':  case 'n':  case 'o':  case 'p':
    537                  case 'q':  case 'r':  case 's':  case 't':
    538                  case 'u':  case 'v':  case 'w':  case 'x':
    539                  case 'y':  case 'z':
    540                  {
    541                          matchRange('a','z');
    542                          break;
    543                  }
    544                  case '0':  case '1':  case '2':  case '3':
    545                  case '4':  case '5':  case '6':  case '7':
    546                  case '8':  case '9':
    547                  {
    548                          matchRange('0','9');
    549                          break;
    550                  }
    551                  case '.':
    552                  {
    553                          match('.');
    554                          break;
    555                  }
    556                  case '_':
    557                  {
    558                          match('_');
    559                          break;
    560                  }
    561                  default:
    562                  {
    563                          if ( _cnt42>=1 ) { break _loop42; } else {throw new NoViableAltForCharException((char)LA(1), getFilename(), getLine(), getColumn());}
    564                  }
    565                  }
    566                  _cnt42++;
    567          } while (true);
    568          }
    569          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    570                  _token = makeToken(_ttype);
    571                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    572          }
    573          _returnToken = _token;
    574  }
    575  
    576  public final void mEQUALSIGN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    577          int _ttype; Token _token=null; int _begin=text.length();
    578          _ttype = EQUALSIGN;
    579          int _saveIndex;
    580          
    581          match('=');
    582          match('=');
    583          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    584                  _token = makeToken(_ttype);
    585                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    586          }
    587          _returnToken = _token;
    588  }
    589  
    590  public final void mNOTEQUALSIGN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    591          int _ttype; Token _token=null; int _begin=text.length();
    592          _ttype = NOTEQUALSIGN;
    593          int _saveIndex;
    594          
    595          match('!');
    596          match('=');
    597          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    598                  _token = makeToken(_ttype);
    599                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    600          }
    601          _returnToken = _token;
    602  }
    603  
    604  public final void mLESSTHANSIGN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    605          int _ttype; Token _token=null; int _begin=text.length();
    606          _ttype = LESSTHANSIGN;
    607          int _saveIndex;
    608          
    609          match('<');
    610          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    611                  _token = makeToken(_ttype);
    612                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    613          }
    614          _returnToken = _token;
    615  }
    616  
    617  public final void mGREATERTHANSIGN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    618          int _ttype; Token _token=null; int _begin=text.length();
    619          _ttype = GREATERTHANSIGN;
    620          int _saveIndex;
    621          
    622          match('>');
    623          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    624                  _token = makeToken(_ttype);
    625                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    626          }
    627          _returnToken = _token;
    628  }
    629  
    630  public final void mLESSEQUALSIGN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    631          int _ttype; Token _token=null; int _begin=text.length();
    632          _ttype = LESSEQUALSIGN;
    633          int _saveIndex;
    634          
    635          match('<');
    636          match('=');
    637          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    638                  _token = makeToken(_ttype);
    639                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    640          }
    641          _returnToken = _token;
    642  }
    643  
    644  public final void mGREATEREQUALSIGN(boolean _createToken) throws RecognitionException, CharStreamException, TokenStreamException {
    645          int _ttype; Token _token=null; int _begin=text.length();
    646          _ttype = GREATEREQUALSIGN;
    647          int _saveIndex;
    648          
    649          match('>');
    650          match('=');
    651          if ( _createToken && _token==null && _ttype!=Token.SKIP ) {
    652                  _token = makeToken(_ttype);
    653                  _token.setText(new String(text.getBuffer(), _begin, text.length()-_begin));
    654          }
    655          _returnToken = _token;
    656  }
    657  
    658  
    659  private static final long[] mk_tokenSet_0() {
    660          long[] data = { -554050771456L, 9223372036854775807L, 0L, 0L};
    661          return data;
    662  }
    663  public static final BitSet _tokenSet_0 = new BitSet(mk_tokenSet_0());
    664  private static final long[] mk_tokenSet_1() {
    665          long[] data = { -21474826752L, 9223372036854775807L, 0L, 0L};
    666          return data;
    667  }
    668  public static final BitSet _tokenSet_1 = new BitSet(mk_tokenSet_1());
    669  
    670  }

------------------------------------------------------------------------

This page was automatically generated by [Maven](http://maven.apache.org/)
