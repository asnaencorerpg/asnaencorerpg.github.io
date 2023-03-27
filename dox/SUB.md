---
title: SUB

Id: SUB
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

**F2** is subtracted from **F1** (if specified) and the difference is placed in **Result** . 

```

 **SUB** 
F1 (*NONE | Numeric Expression)
 **F2**  (Numeric Expression)
 **Result**  (Numeric Variable)
Adj (<u>*TRUNC</u> | *RNDUP)
Pos (<u>Indicator Variable</u>)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
     *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**F1** 

Optional.


**F2** 

Required. Contains a numeric value. The contents of **F2** is subtracted from the **Result** if **F1** is not specified.


**Result** 

Optional. Contains a numeric variable to contain the result of the subtraction.


**Adj** 

Optional. Indicates half-adjust. Use **ADJ** (*RNDUP) if you wish to round up the value, or use **ADJ** (*TRUNC) if you wish to truncate the value of the **Result** . *TRUNC is the default.


**Pos** 

Optional. Turned on if the value of the **Result** is a positive number.


**Neg** 

Optional. Turned on if the value of the **Result** is a negative number.


**Zero** 

Optional. Turned on if the value of the **Result** is zero.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
**F1, F2** and **Result** must be numeric. 

When **F1** is specified, **F2** is subtracted from **F1** with the difference placed in the **Result** . The contents of **F2** is subtracted from the **Result** if **F1** is not specified. 

### Example

```

B = 10.0; C = 32; D = -20; E = 6
DclFld W *PACKED Len(5,1)
E = 1 - E    // E = 5
W = C - B    // W = 22.0
W = C - D    // W = 52.0 
```

### See Also
[ADD](ADD.html)

[DIV](DIV.html)

[MULT](MULT.html) 
