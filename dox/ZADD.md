---
title: ZADD

Id: ZADD
TocParent: aerLrfOpCodesMain
TocOrder: 1810


---

The field specified in **F2** is added to a field of zeros and the sum is placed in **Result** . 

```
ZADD
F2 (Numeric Expression) Result (Numeric Variable)
Adj (*RNDUP | <u>*TRUNC</u>)
Pos (Indicator Variable)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**F2** 

Required. Must be numeric and can contain one of the following: an array, array element, field, figurative constant, literal, named constant, subfield, or table name.


**Result** 

Required. Can contain one of the following: an array, array element, field, subfield, or table name.


**Adj** 

Optional. Indicates half-adjust. Use **Adj** (*RNDUP) if you wish to round up the value, or use **Adj** (*TRUNC) if you wish to truncate the value of **Result** . *TRUNC is the default.


**Pos** 

Optional. Turned on if the value of **Result** is a positive number.


**Neg** 

Optional. Turned on if the value of **Result** is a negative number.


**Zero** 

Optional. Turned on if the value of **Result** is zero.


**Type** 

Optional. Can be any of the types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. The **Len** parameter defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
**F2** is added to a field of zeros. The sum is placed in **Result** . Half-adjust can be specified. 

### See Also
[ZSUB](Z_SUB.html) 
