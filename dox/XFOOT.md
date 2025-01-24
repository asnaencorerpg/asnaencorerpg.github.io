---
title: XFOOT

Id: XFOOT
TocParent: aerLrfOpCodesMain
TocOrder: 1790


---

Adds array elements of a single-dimensioned array together and places the sum into **Result** . 

```
XFOOT
Arr (Array Name)
 Result (Numeric Variable)
Adj (<u>*TRUNC</u> | *RNDUP)
Pos (Indicator Variable)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED))
Len (Length Integer, [Decimal Integer])
```

### Parameters

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

Optional. Can be any of the types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
XFOOT is valid only with single-dimensioned numeric arrays. 

If half-adjust is specified, the rounding occurs after all elements are summed and before the results are moved into the result field. If **Result** is an element of the array specified in **Arr** , the value of the element before the **XFOOT** operation is used to calculate the total of the array. 

If the array is float, **XFOOT** will be performed as follows: When the array is in descending sequence, the elements will be added together in reverse order. Otherwise, the elements will be added together starting with the first elements of the array. 

[SUMARR](SUMARR.html) is exactly the same as **XFOOT** , and can be used interchangeably. 

### Example

```

// MyArray Values are 1.064, 1.703, -1.110.

   DclArray MyArray 3 *PACKED Len(4,3)
   DclFld MyArraySum *PACKED Len(5,2)
   XFoot MyArray MyArraySum Adj(*RndUp) 

// Result 1.66
```

### See Also
[SUMARR](SUMARR.html) 
