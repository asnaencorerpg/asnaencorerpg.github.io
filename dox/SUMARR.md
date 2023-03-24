---
title: SUMARR

Id: SUMARR
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

Adds array elements of a single-dimensioned array together and places the sum into **Result** . 

```

 **SUMARR
Arr** (Array Name)
 **Result**  (Numeric Variable)
Adj (*RNDUP | <u>*TRUNC</u>)
Pos (Indicator Variable)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
     *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**Arr** 

Required. Specifies the name of the one-dimension array.


**Result** 

Required. The sum of the array elements.


**Adj** 

Optional. Indicates half-adjust. Use **Adj** (*RNDUP) if you wish to round up the value, or use **Adj** (*TRUNC) if you wish to truncate the value of **Result** . *TRUNC is the default.


**Pos** 

Optional. Turned on if the value of **Result** is a positive number.


**Neg** 

Optional. Turned on if the value of **Result** is a negative number.


**Zero** 

Optional. Turned on if the value of **Result** is zero.


**Type** 

Optional. Can be any of the **Types** listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
XFOOT is valid only with single-dimensioned numeric arrays.

If the array is half-adjusted, all elements will be added before rounding occurs. If **Result** is an element of the array in **ARR** , the value of the element preceding the **SUMARR** operation is used to calculate the array. 

[XFOOT](XFOOT.html) is exactly the same as **SUMARR** , and can be used interchangeably. 

### Example

```

// MyArray Values are 1.064, 1.703, -1.110.
DclArray MyArray 3 *PACKED Len(4,3)
DclFld MyArraySum *PACKED Len(5,2)
SumArr MyArray MyArraySum Adj(*RndUp)
// Result 1.66 
```

