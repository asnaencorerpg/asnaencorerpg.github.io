---
title: "%EDITC Function"

Id: EDITC_Function
TocParent: Functions_overview
TocOrder: 13


---

**%EDITC** [built-in function](Functions_overview.html) returns a character result representing the numeric value edited according to the **edit code.** 
<pre class="prettyprint">
 **%EDITC (NumericExpression, EditCode,**  {*ASTFill | *CURSYM | Currency-symbol} **)** <br /></pre>

### Parts

**NumericExpression, EditCode** 

Required. In general, the rules for the [Numeric Expression](Num_Expression.html) and [Edit Code](aerLrfEditCodeTable.html) parameters are identical to those for editing numeric values in output specifications. 

When using the % **EDITC** built-in-function, you can only enter the alpha representation for the desired edit code. You cannot enter the numeric representation.


***ASTFill,** 
 ***CURSYM, Currency-symbol** 

Optional. The third parameter is optional, and if specified, must be one of the following: 

- *ASTFill - Indicates that **asterisk protection** 
                        is to be used. T his means that leading zeros are %EDITC'd with asterisks in
                        the returned value. For example,<br />
                        <pre> **%EDITC** (-0012.5 , "K" , *ASTFill)returns "***12.5"</pre>
- *CURSYM - Indicates that a floating **currency symbol** 
                        is to be used.  The actual symbol will be the one specified on the control
                        specification in the *CURSYM keyword, or the default, "$".  When *CURSYM
                        is specified, the currency symbol is placed in the result just before the first
                        significant digit. For example,<br />
                        <pre> **%EDITC** (0012.5 , "K" , *CURSYM) returns // $12.5 //</pre>
- Currency-symbol - Indicates that floating **currency** 
                        is to be used with the provided currency **symbol** .  It must be a 1-byte
                        character constant (literal, named constant or expression that can be evaluated
                        at compile time). For example,<br />
                        <pre> **%EDITC** (0012.5 , "K" , £") returns // £12.5 "</pre>


### See Also
[Built-in Function Overview](Functions_overview.html)
[Numeric Expression](Num_Expression.html)
[Edit Code Usage](aerLrfEditCodeTable.html) 
