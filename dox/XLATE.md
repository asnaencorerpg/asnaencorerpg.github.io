---
title: XLATE

Id: XLATE
TocParent: aerLrfOpCodesMain
TocOrder: 1800


---

Translates characters in the source string according to the **MapFrom** and **MapTo** string and puts them into **Target** . 

```
XLATE
MapFrom (Character Expression) MapTo  (Character Expression) BaseStr  (Character Expression)
StartPos Numeric Expression) | <u>1</u> ) Target  (Character Expression)
Fill (<u>*NOPAD</u> | *PAD)
Err (Indicator Variable | *EXTENDED) 
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *STRING | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**MapFrom** 

Required. Must contain the **from** string, along with the **MapTo** string. If a character in the from string is duplicated, the first occurrence is used.


**MapTo** 

Required. Must contain the **to** string.


**BaseStr** 

Required. Must contain either the source string or the source string followed by a colon and the start location ( **StartPos** ).


**StartPos** 

Optional. Start location.


**Target** 

Required. Contains the **Target** string.


**Fill** 

Optional. Specifies if you want to fill, or pad the **Target** with blanks. The default is *NoPad. 

- *NoPad indicates that **Target** will not be padded with blanks.
- *Pad indicates that **Target** will be padded with blanks.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
**XLATE** starts translating the source at the location specified in **BaseStr** and continues character by character, from left to right. If a character of the source string exists in the **MapFrom** string, the corresponding character in the **MapTo** string is placed in **Target** . Any characters in the source field before the starting position are placed unchanged in **Target** . 

### See Also
[%XLATE](XLATE_Function.html)

[%ERROR](ERROR_Function.html)

[Type Parameter](Type_Parameter.html) 
