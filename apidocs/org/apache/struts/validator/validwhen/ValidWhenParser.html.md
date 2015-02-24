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
<td align="left"><a href="class-use/ValidWhenParser.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhenLexer.html.md" title="class in org.apache.struts.validator.validwhen"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html" title="interface in org.apache.struts.validator.validwhen"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/validator/validwhen/ValidWhenParser.html"><strong>FRAMES</strong></a>    <a href="ValidWhenParser.html"><strong>NO FRAMES</strong></a>    
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
 Class ValidWhenParser
-------------------------------------

    java.lang.Object
      antlr.Parser
          antlr.LLkParser
              org.apache.struts.validator.validwhen.ValidWhenParser

**All Implemented Interfaces:**  
[ValidWhenParserTokenTypes](../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md "interface in org.apache.struts.validator.validwhen")

------------------------------------------------------------------------

    public class ValidWhenParser

extends antlr.LLkParser

implements [ValidWhenParserTokenTypes](../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md "interface in org.apache.struts.validator.validwhen")

------------------------------------------------------------------------

<span id="field_summary"></span>

**Field Summary**

`static String[]`

` _tokenNames`
            

`static antlr.collections.impl.BitSet`

` _tokenSet_0`
            

`static antlr.collections.impl.BitSet`

` _tokenSet_1`
            

 <span id="fields_inherited_from_class_antlr.Parser"></span>

| **Fields inherited from class antlr.Parser**                                        |
|-------------------------------------------------------------------------------------|
| `astFactory, inputState, returnAST, tokenNames, tokenTypeToASTClassMap, traceDepth` |

 <span id="fields_inherited_from_class_org.apache.struts.validator.validwhen.ValidWhenParserTokenTypes"></span>

| **Fields inherited from interface org.apache.struts.validator.validwhen.[ValidWhenParserTokenTypes](../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html.md "interface in org.apache.struts.validator.validwhen")**                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ` ANDSIGN,  DECIMAL_LITERAL,  EOF,  EQUALSIGN,  GREATEREQUALSIGN,  GREATERTHANSIGN,  HEX_LITERAL,  IDENTIFIER,  LBRACKET,  LESSEQUALSIGN,  LESSTHANSIGN,  LITERAL_null,  LPAREN,  NOTEQUALSIGN,  NULL_TREE_LOOKAHEAD,  OCTAL_LITERAL,  ORSIGN,  RBRACKET,  RPAREN,  STRING_LITERAL,  THIS,  WS` |

  <span id="constructor_summary"></span>

**Constructor Summary**

` `

` ValidWhenParser(antlr.ParserSharedInputState state)`
            

` `

` ValidWhenParser(antlr.TokenBuffer tokenBuf)`
            

`protected`

` ValidWhenParser(antlr.TokenBuffer tokenBuf, int k)`
            

` `

` ValidWhenParser(antlr.TokenStream lexer)`
            

`protected`

` ValidWhenParser(antlr.TokenStream lexer, int k)`
            

  <span id="method_summary"></span>

**Method Summary**

` void`

` comparison()`
            

` void`

` comparisonExpression()`
            

` void`

` expr()`
            

` void`

` expression()`
            

` void`

` field()`
            

` boolean`

` getResult()`
            

` void`

` identifier()`
            

` void`

` integer()`
            

` void`

` join()`
            

` void`

` joinedExpression()`
            

` void`

` literal()`
            

` void`

` setForm(Object f)`
            

` void`

` setIndex(int i)`
            

` void`

` setValue(String v)`
            

` void`

` string()`
            

` void`

` value()`
            

 <span id="methods_inherited_from_class_antlr.LLkParser"></span>

| **Methods inherited from class antlr.LLkParser** |
|--------------------------------------------------|
| `consume, LA, LT, traceIn, traceOut`             |

 <span id="methods_inherited_from_class_antlr.Parser"></span>

| **Methods inherited from class antlr.Parser**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `addMessageListener, addParserListener, addParserMatchListener, addParserTokenListener, addSemanticPredicateListener, addSyntacticPredicateListener, addTraceListener, consumeUntil, consumeUntil, defaultDebuggingSetup, getAST, getASTFactory, getFilename, getInputState, getTokenName, getTokenNames, getTokenTypeToASTClassMap, isDebugMode, mark, match, match, matchNot, panic, removeMessageListener, removeParserListener, removeParserMatchListener, removeParserTokenListener, removeSemanticPredicateListener, removeSyntacticPredicateListener, removeTraceListener, reportError, reportError, reportWarning, rewind, setASTFactory, setASTNodeClass, setASTNodeType, setDebugMode, setFilename, setIgnoreInvalidDebugCalls, setInputState, setTokenBuffer, traceIndent` |

 <span id="methods_inherited_from_class_java.lang.Object"></span>

| **Methods inherited from class java.lang.[Object](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/Object.html.md?is-external=true "class or interface in java.lang")** |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait, wait, wait`                                                                          |

 

<span id="field_detail"></span>

**Field Detail**

### \_tokenNames

    public static final String[] _tokenNames

------------------------------------------------------------------------

### \_tokenSet\_0

    public static final antlr.collections.impl.BitSet _tokenSet_0

------------------------------------------------------------------------

### \_tokenSet\_1

    public static final antlr.collections.impl.BitSet _tokenSet_1

<span id="constructor_detail"></span>

**Constructor Detail**

### ValidWhenParser

    protected ValidWhenParser(antlr.TokenBuffer tokenBuf,
                              int k)

------------------------------------------------------------------------

### ValidWhenParser

    public ValidWhenParser(antlr.TokenBuffer tokenBuf)

------------------------------------------------------------------------

### ValidWhenParser

    protected ValidWhenParser(antlr.TokenStream lexer,
                              int k)

------------------------------------------------------------------------

### ValidWhenParser

    public ValidWhenParser(antlr.TokenStream lexer)

------------------------------------------------------------------------

### ValidWhenParser

    public ValidWhenParser(antlr.ParserSharedInputState state)

<span id="method_detail"></span>

**Method Detail**

### setForm

    public void setForm(Object f)

------------------------------------------------------------------------

### setIndex

    public void setIndex(int i)

------------------------------------------------------------------------

### setValue

    public void setValue(String v)

------------------------------------------------------------------------

### getResult

    public boolean getResult()

------------------------------------------------------------------------

### integer

    public final void integer()
                       throws antlr.RecognitionException,
                              antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### string

    public final void string()
                      throws antlr.RecognitionException,
                             antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### identifier

    public final void identifier()
                          throws antlr.RecognitionException,
                                 antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### field

    public final void field()
                     throws antlr.RecognitionException,
                            antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### literal

    public final void literal()
                       throws antlr.RecognitionException,
                              antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### value

    public final void value()
                     throws antlr.RecognitionException,
                            antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### expression

    public final void expression()
                          throws antlr.RecognitionException,
                                 antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### expr

    public final void expr()
                    throws antlr.RecognitionException,
                           antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### comparisonExpression

    public final void comparisonExpression()
                                    throws antlr.RecognitionException,
                                           antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### joinedExpression

    public final void joinedExpression()
                                throws antlr.RecognitionException,
                                       antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### join

    public final void join()
                    throws antlr.RecognitionException,
                           antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

`antlr.TokenStreamException`

------------------------------------------------------------------------

### comparison

    public final void comparison()
                          throws antlr.RecognitionException,
                                 antlr.TokenStreamException

**Throws:**  
`antlr.RecognitionException`

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
<td align="left"><a href="class-use/ValidWhenParser.html.md"><strong>Use</strong></a> </td>
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
<td align="left"> <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhenLexer.html.md" title="class in org.apache.struts.validator.validwhen"><strong>PREV CLASS</strong></a>   <a href="../../../../../org/apache/struts/validator/validwhen/ValidWhenParserTokenTypes.html" title="interface in org.apache.struts.validator.validwhen"><strong>NEXT CLASS</strong></a></td>
<td align="left"><a href="../../../../../index.html.md?org/apache/struts/validator/validwhen/ValidWhenParser.html"><strong>FRAMES</strong></a>    <a href="ValidWhenParser.html"><strong>NO FRAMES</strong></a>    
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
