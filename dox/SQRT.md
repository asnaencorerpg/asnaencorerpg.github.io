---
title: SQRT

Id: SQRT
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

Specifies the square root of **F2** and places it in **Result** .

```
SQRT 
F2  (Numeric Expression | Character Expression)
Result  (Numeric Variable | Character Variable)
Adj (<u>*TRUNC</u> | *RNDUP)  
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer]
```

### Parameters

**F2** 

Required. Must be any valid numeric operand. It must be numeric, and can contain one of: an array, array element, field, figurative constant, literal, named constant, subfield, or table name.


**Result** 

Required. Must be numeric, and can contain one of: an array, array element, subfield, or table element. An entire array can be used in a **SQRT** operation if **F2** and **Result** contain array names. The number of decimal positions in **Result** can be either less than or greater than the number of decimal positions in **F2** . However, **Result** should not have fewer than half the number of decimal positions in **F2** . 

If the value of the **F2** field is zero, the **Result** value is also zero. However, if the value of **F2** is negative, this is invalid, and a run-time error will occur.


**Adj** 

Optional. Specifies if the field will be adjusted by truncation (*TRUNC) or by rounding up the value (*RNDUP). *TRUNC is the default.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
The **SQRT** operation derives the square root of **F2** and places it in **Result** . This operation is done in floating point mathematics, so some truncation/roundup may occur. 

### Example

```
// When NumberDresses equals 144, the result, PerBoxCount, will be 12.
DclFld NumberDresses *ZONED len(5,0)
DclFld PerBoxCount *ZONED len(3,0)
Sqrt NumberDresses PerBoxCount

/* When an array is used, all elements are computed at once and placed in the resulting array. In this case, each 
   element in array MinGroup would be 12. Each element will be rounded to the nearest decimal value. */

DclFld I *ZONED Len(3,0)
DCLARRAY Name(MajGroup) DIM(20) Len(9,0)
DCLARRAY Name(MinGroup) DIM(20) Len(9,0)
Do 1 20 I
	MajGroup[I] = 144  
	MinGroup[I] = 0
Enddo
Sqrt MajGroup MinGroup *RndUp       
```

### See Also
[%SQRT](SQRT_Function.html) 
