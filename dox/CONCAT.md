---
title: CONCAT

Id: CONCAT
TocParent: aerLrfOpCodesMain
TocOrder: 330


---

Adds to the end of the character field specified by **Pre** (Prefix) the character field specified by **Suf** (Suffix). he concatenated field is placed in **Target** . Indicators are optional. 

```

 **CONCAT** 
Pre (*NONE | Character Expression) **Suf**   (String:Blanks) **Target** (Character Expression)
BLANK (Numeric Expression)
Fill (<u>*NOPAD</u> | *PAD)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**Pre** 

Optional. When used, must contain a valid [character expression](Character_Expression.html). 

If **Pre** is not specified, **Suf** is concatenated to the end of **Target** . **Pre** can contain a string, which can be one of: a field name, array element, named constant, data structure name, table name, or literal. 

If **Pre** is not specified, **Target** is used. The following references to **Pre** apply to **Target** if **Pre** is not specified.


**Suf** 

Required. Must contain a string that may contain the number of blanks to be inserted between the concatenated strings. Its format is the string, followed by a colon, followed by the number of blanks. 

If graphic strings are being concatenated, the blanks are double-byte blanks. 

The string portion can contain one of: a field name, array element, named constant, data structure name, table name, literal, or data structure subfield name. 

The number of blanks portion must be numeric with zero decimal positions, and can contain one of: a named constant, array element, literal, table name, or field name. If a colon is specified, the number of blanks must be specified. If no colon is specified, concatenation occurs with the trailing blanks, if any, in **Pre** , or **Target** if **Pre** is not specified. If the number of blanks, N, is specified, **Pre** is copied to **Target** left-justified. Use the **Blank** () parameter to specify the number of blanks. The number of blanks must be numeric with zero decimal places, and can be a literal, an array element, or field name. Leading blanks are never dropped.


**Target** 

Required. Must be a string and can contain one of: a field name, array element, data structure name, or table name. It is always left justified and its length is the length of **Pre** and **Suf** combined, plus any intervening blanks. If it is not, truncation occurs from the right.


**BLANK** 

Optional. Indicates that **Target** should be padded on the right with blanks after the concatenation occurs, if **Target** is longer than the result of the operation. Only the left-most part of the field is affected if padding is not specified. 

Resulting indicators are optional. If specified, they are set just as if a [COMPARE](COMPARE.html) operation had executed, whether or not the condition in the operation code was satisfied. Avoid using indicators in this way, however, as they detract from the structure and readability of the program. This capability is provided only for compatibility with the AS/400 and System/38.


**Fill** 

Optional. Specifies if you want to fill, or pad **Target** (Target) with blanks. The default is *NOPAD. 

- *NOPAD indicates that **Target** will not be padded with blanks.
- *PAD indicates that **Target** will be padded with blanks.


**Type** 

Optional. Can be any of the types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
The **CONCAT** operation concatenates the string specified in **Suf** to the end of the string specified in **Pre** and places it in **Target** . The source and target strings must all be of the same type, either all character or all graphic. 

### See Also
[+ Operator](Plus_Operator.html)

[COMPARE](COMPARE.html) 
