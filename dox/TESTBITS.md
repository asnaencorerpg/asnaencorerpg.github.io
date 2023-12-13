---
title: TESTBITS

Id: TESTBITS
TocParent: aerLrfOpCodesMain
TocOrder: 1510


---

Compares the bits in **Mask** with the corresponding bits in the field named in **Fld** . 

```
TESTBITS
Mask  (Expression) Fld  (Character Expression)
Off (Indicator Variable)
On (Indicator Variable)
Eq (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**Mask** 

Required. Can contain:

- Bit numbers 0-7. Enclose the bit numbers in apostrophes. For example, to set bits 0, 3, 6 on, enter "036".
- A [Character Expression](Character_Expression.html).
- Hexadecimal literal (H"01") for example.
- Named constant up to 8 positions long containing the bit numbers to be set on.


**Fld** 

Required. Contains the result of the compare.


**Off** 

Optional. Reflects the status of the result field bits. Assuming a **Mask** of H"E4" (1100 0100), **Off** is true if all of the masked bits are **Off** in the field. In this case, for **Off** to be true, the field would contain H"3B" (0011 1011).


**On** 

Optional. Reflects the status of the result field bits. Assuming a **Mask** of H"E4" (1100 0100), **On** is true if some of the masked bits are **On** and some the masked bits are **Off** in the field. In this case, the field would contain anything but H"3B" or H"E4".


**Eq** 

Optional. Reflects the status of the result field bits. Assuming a **Mask** of H"E4" (1100 0100), **Eq** is true if all of the masked bits are **On** in the field. In this case, the field would contain H"E4" (1100 0100).


**Type** 

Optional. Can be any of the **Types** listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, **Type** 's of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
When using Bit operations to format a character, you should use both **BITON** and **BITOFF** . **BITON** specifies the bits to be set on (= 1). **BITOFF** to specify the bits to be set off (= 0). You may not get the character you want unless you explicitly set all the bits in a character **On** or **Off** . 

### See Also
[BITOFF](BITOFF.html)

[BITON](BITON.html) 
