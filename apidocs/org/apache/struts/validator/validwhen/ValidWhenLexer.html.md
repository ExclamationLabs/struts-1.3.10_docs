------------------------------------------------------------------------

<span id="navbar_top"></span> [](#skip-navbar_top "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_top_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ValidWhenLexer.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhen.html.md" title="class in org.apache.struts.validator.validwhen"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhenParser.html" title="class in org.apache.struts.validator.validwhen"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/validator/validwhen/ValidWhenLexer.html"><strong>FRAMES</strong></a>    <a href="ValidWhenLexer.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_top"></span>

------------------------------------------------------------------------

org.apache.struts.validator.validwhen
 Class ValidWhenLexer
-------------------------------------

    java.lang.Object
      antlr.CharScanner
          org.apache.struts.validator.validwhen.ValidWhenLexer

**All Implemented Interfaces:**  
antlr.TokenStream, [ValidWhenParserTokenTypes](../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md "interface in org.apache.struts.validator.validwhen")

------------------------------------------------------------------------

    public class ValidWhenLexer

extends antlr.CharScanner

implements [ValidWhenParserTokenTypes](../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md "interface in org.apache.struts.validator.validwhen"), antlr.TokenStream

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static antlr.collections.impl.BitSet`

` _tokenSet_0`
            

`static antlr.collections.impl.BitSet`

` _tokenSet_1`
            

 <span id="fields_inherited_from_class_antlr.CharScanner"></span>

| **Fields inherited from class antlr.CharScanner**                                                                                                                              |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `_returnToken, caseSensitive, caseSensitiveLiterals, commitToPath, EOF_CHAR, hashString, inputState, literals, saveConsumedInput, tabsize, text, tokenObjectClass, traceDepth` |

 <span id="fields_inherited_from_class_org.apache.struts.validator.validwhen.ValidWhenParserTokenTypes"></span>

| **Fields inherited from interface org.apache.struts.validator.validwhen.[ValidWhenParserTokenTypes](../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md "interface in org.apache.struts.validator.validwhen")**                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ANDSIGN,  DECIMAL_LITERAL,  EOF,  EQUALSIGN,  GREATEREQUALSIGN,  GREATERTHANSIGN,  HEX_LITERAL,  IDENTIFIER,  LBRACKET,  LESSEQUALSIGN,  LESSTHANSIGN,  LITERAL_null,  LPAREN,  NOTEQUALSIGN,  NULL_TREE_LOOKAHEAD,  OCTAL_LITERAL,  ORSIGN,  RBRACKET,  RPAREN,  STRING_LITERAL,  THIS,  WS` |

  <span id="constructor_summary"></span>

| **Constructor Summary**                              |
|------------------------------------------------------|
| ` ValidWhenLexer(antlr.InputBuffer ib)`              
                                                       |
| ` ValidWhenLexer(InputStream in)`                    
                                                       |
| ` ValidWhenLexer(antlr.LexerSharedInputState state)` 
                                                       |
| ` ValidWhenLexer(Reader in)`                         
                                                       |

  <span id="method_summary"></span>

**Method Summary**

` void`

` mDECIMAL_LITERAL(boolean _createToken)`
            

` void`

` mEQUALSIGN(boolean _createToken)`
            

` void`

` mGREATEREQUALSIGN(boolean _createToken)`
            

` void`

` mGREATERTHANSIGN(boolean _createToken)`
            

` void`

` mHEX_LITERAL(boolean _createToken)`
            

` void`

` mIDENTIFIER(boolean _createToken)`
            

` void`

` mLBRACKET(boolean _createToken)`
            

` void`

` mLESSEQUALSIGN(boolean _createToken)`
            

` void`

` mLESSTHANSIGN(boolean _createToken)`
            

` void`

` mLPAREN(boolean _createToken)`
            

` void`

` mNOTEQUALSIGN(boolean _createToken)`
            

` void`

` mOCTAL_LITERAL(boolean _createToken)`
            

` void`

` mRBRACKET(boolean _createToken)`
            

` void`

` mRPAREN(boolean _createToken)`
            

` void`

` mSTRING_LITERAL(boolean _createToken)`
            

` void`

` mTHIS(boolean _createToken)`
            

` void`

` mWS(boolean _createToken)`
            

` antlr.Token`

` nextToken()`
            

 <span id="methods_inherited_from_class_antlr.CharScanner"></span>

| **Methods inherited from class antlr.CharScanner**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `append, append, commit, consume, consumeUntil, consumeUntil, getCaseSensitive, getCaseSensitiveLiterals, getColumn, getCommitToPath, getFilename, getInputBuffer, getInputState, getLine, getTabSize, getText, getTokenObject, LA, makeToken, mark, match, match, match, matchNot, matchRange, newline, panic, panic, reportError, reportError, reportWarning, resetText, rewind, setCaseSensitive, setColumn, setCommitToPath, setFilename, setInputState, setLine, setTabSize, setText, setTokenObjectClass, tab, testLiteralsTable, testLiteralsTable, toLower, traceIn, traceIndent, traceOut, uponEOF` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

### \_tokenSet\_0

    public static final antlr.collections.impl.BitSet _tokenSet_0

------------------------------------------------------------------------

### \_tokenSet\_1

    public static final antlr.collections.impl.BitSet _tokenSet_1

<span id="constructor_detail"></span>

**Constructor Detail**

### ValidWhenLexer

    public ValidWhenLexer(InputStream in)

------------------------------------------------------------------------

### ValidWhenLexer

    public ValidWhenLexer(Reader in)

------------------------------------------------------------------------

### ValidWhenLexer

    public ValidWhenLexer(antlr.InputBuffer ib)

------------------------------------------------------------------------

### ValidWhenLexer

    public ValidWhenLexer(antlr.LexerSharedInputState state)

<span id="method_detail"></span>

**Method Detail**

### nextToken

    public antlr.Token nextToken()
                          throws antlr.TokenStreamException

**Specified by:**  
`nextToken` in interface `antlr.TokenStream`

**Specified by:**  
`nextToken` in class `antlr.CharScanner`

<!-- -->

**Throws:**  
`antlr.TokenStreamException`

------------------------------------------------------------------------

### mWS

    public final void mWS(boolean _createToken)
                   throws antlr.RecognitionException,
                          antlr.CharStreamException,
                          antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mDECIMAL\_LITERAL

    public final void mDECIMAL_LITERAL(boolean _createToken)
                                throws antlr.RecognitionException,
                                       antlr.CharStreamException,
                                       antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mHEX\_LITERAL

    public final void mHEX_LITERAL(boolean _createToken)
                            throws antlr.RecognitionException,
                                   antlr.CharStreamException,
                                   antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mOCTAL\_LITERAL

    public final void mOCTAL_LITERAL(boolean _createToken)
                              throws antlr.RecognitionException,
                                     antlr.CharStreamException,
                                     antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mSTRING\_LITERAL

    public final void mSTRING_LITERAL(boolean _createToken)
                               throws antlr.RecognitionException,
                                      antlr.CharStreamException,
                                      antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mLBRACKET

    public final void mLBRACKET(boolean _createToken)
                         throws antlr.RecognitionException,
                                antlr.CharStreamException,
                                antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mRBRACKET

    public final void mRBRACKET(boolean _createToken)
                         throws antlr.RecognitionException,
                                antlr.CharStreamException,
                                antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mLPAREN

    public final void mLPAREN(boolean _createToken)
                       throws antlr.RecognitionException,
                              antlr.CharStreamException,
                              antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mRPAREN

    public final void mRPAREN(boolean _createToken)
                       throws antlr.RecognitionException,
                              antlr.CharStreamException,
                              antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mTHIS

    public final void mTHIS(boolean _createToken)
                     throws antlr.RecognitionException,
                            antlr.CharStreamException,
                            antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mIDENTIFIER

    public final void mIDENTIFIER(boolean _createToken)
                           throws antlr.RecognitionException,
                                  antlr.CharStreamException,
                                  antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mEQUALSIGN

    public final void mEQUALSIGN(boolean _createToken)
                          throws antlr.RecognitionException,
                                 antlr.CharStreamException,
                                 antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mNOTEQUALSIGN

    public final void mNOTEQUALSIGN(boolean _createToken)
                             throws antlr.RecognitionException,
                                    antlr.CharStreamException,
                                    antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mLESSTHANSIGN

    public final void mLESSTHANSIGN(boolean _createToken)
                             throws antlr.RecognitionException,
                                    antlr.CharStreamException,
                                    antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mGREATERTHANSIGN

    public final void mGREATERTHANSIGN(boolean _createToken)
                                throws antlr.RecognitionException,
                                       antlr.CharStreamException,
                                       antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mLESSEQUALSIGN

    public final void mLESSEQUALSIGN(boolean _createToken)
                              throws antlr.RecognitionException,
                                     antlr.CharStreamException,
                                     antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### mGREATEREQUALSIGN

    public final void mGREATEREQUALSIGN(boolean _createToken)
                                 throws antlr.RecognitionException,
                                        antlr.CharStreamException,
                                        antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.CharStreamException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

<span id="navbar_bottom"></span> [](#skip-navbar_bottom "Skip navigation links")

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><span id="navbar_bottom_firstrow"></span>
<table>
<tbody>
<tr class="odd">
<td align="left"><a href="../../../../../overview-summary.html.md"><strong>Overview</strong></a> </td>
<td align="left"><a href="package-summary.html.md"><strong>Package</strong></a> </td>
<td align="left"> <strong>Class</strong> </td>
<td align="left"><a href="class-use/ValidWhenLexer.html.md"><strong>Use</strong></a> </td>
<td align="left"><a href="package-tree.html.md"><strong>Tree</strong></a> </td>
<td align="left"><a href="../../../../../deprecated-list.html.md"><strong>Deprecated</strong></a> </td>
<td align="left"><a href="../../../../../index-all.html.md"><strong>Index</strong></a> </td>
<td align="left"><a href="../../../../../help-doc.html.md"><strong>Help</strong></a> </td>
</tr>
</tbody>
</table></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"> <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhen.html.md" title="class in org.apache.struts.validator.validwhen"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhenParser.html" title="class in org.apache.struts.validator.validwhen"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/validator/validwhen/ValidWhenLexer.html"><strong>FRAMES</strong></a>    <a href="ValidWhenLexer.html"><strong>NO FRAMES</strong></a>    
<a href="../../../../../allclasses-noframe.html.md"><strong>All Classes</strong></a></td>
</tr>
<tr class="odd">
<td align="left">SUMMARY: NESTED | <a href="#field_summary">FIELD</a> | <a href="#constructor_summary">CONSTR</a> | <a href="#method_summary">METHOD</a></td>
<td align="left">DETAIL: <a href="#field_detail">FIELD</a> | <a href="#constructor_detail">CONSTR</a> | <a href="#method_detail">METHOD</a></td>
</tr>
</tbody>
</table>

<span id="skip-navbar_bottom"></span>

------------------------------------------------------------------------

Copyright © 2000-2008 [Apache Software Foundation](http://www.apache.org/). All Rights Reserved.
