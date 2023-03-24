---
title: TESTNUM

Id: TESTNUM
TocParent: aerLrfOpCodesMain
TocOrder: 1520


---

Tests a field for the presence of zoned decimal digits and blanks.

```

 **TESTNUM
Fld**  (Character Expression) 
Num (Indicator Variable) 
BlankNum (Indicator Variable)
Blank (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
       *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED))
Len (Length Integer, [Decimal Integer])
```

### Parts

**Fld** 

Required. The **Fld** parameter is required and contains the character expression to test.


**Num** 

Optional. Turned on if **Fld** contains all numeric characters.


**BlankNum** 

Optional. Turned on if **Fld** contains both numeric characters and at least one leading blank. Fields with embedded blanks will be considered an invalid field.


**Blank** 

Optional. Turned on if **Fld** contains all blanks.


**Type** 

Optional. Can be any of the **Types** listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, TYPES of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
To be considered numeric, **each** character in the field, except the low-order character, **must** contain a hexadecimal 3 zone and a digit from 0 through 9. The number has a negative value when the low-order character contains a hexadecimal 7 zone, and a digit from 0 through 9 (alphabetic characters "p" through "y"). 

### See Also
[TESTBITS](TESTBITS.html)
[Character Expression](Character_Expression.html) 
