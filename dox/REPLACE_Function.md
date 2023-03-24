---
title: "%REPLACE Function"

Id: REPLACE_Function
TocParent: Functions_overview
TocOrder: 37


---

**%REPLACE** [built-in function](Functions_overview.html) returns the character string produced by inserting a replacement string into the source string, starting at the position specified and replacing the specified number of characters. 

```
 **&lt;stringVal&gt; = %REPLACE (ReplaceString, SourceString,**  {StartPos, {SourceLengthToReplace})
```

### Parts

**ReplaceString, SourceString** 

Required. Must be of type character, graphic, or UCS-2 and can be in either fixed or variable-length format. The second parameter must be the same type as the first.


**StartPos** 

Optional. Represents the starting position, measured in characters, to begin replacement. If it is not specified, the starting position is at the beginning of the source string. The value may range from one to the current length of the source string plus one.


**SourceLengthToReplace** 

Optional. Represents the number of characters in the source string to be replaced. If zero is specified, then the replacement string is inserted **before** the specified starting position. If the parameter is not specified, the number of characters replaced in **SourceString** is the length of the replacement string. The value must be greater than or equal to zero, and less than or equal to the current length of **SourceString** . 

The starting position and source length may be any numeric value or numeric expression with no decimal positions.


### Returns
**&lt;stringVal&gt;** contains the character string produced by inserting a replacement string into the source string, starting at the position specified and replacing the specified number of characters. **** The returned value is varying length if the source string or replacement string are varying length, or if the start position or source length to replace are variables. Otherwise, the result is fixed length. 

### Example

```
BEGSR Replace_Ex
   DclFld Name(B) Type(*CHAR) Len(20)
   DclFld Result *String
   B = "Encore RPG 3.5"
   Result = %Replace ("4.0", B,12,3 )
   IOField1.Text = Result=
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html) 
