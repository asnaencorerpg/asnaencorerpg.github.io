---
title: MOVEREM

Id: MOVEREM
TocParent: aerLrfOpCodesMain
TocOrder: 1240


---

Moves the remainder from a previous [DIV](DIV.html) operation to a separate field named in the Result Field. 

```
 MOVEREM
Target  (Numeric Variable)
Pos (Indicator Variable) 
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | 
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parameters

**Target** 

Required. The maximum number of whole number positions in the remainder is equal to the whole number of positions in **F2** of the previous **DIV** operation.


**Pos** 

Optional. Turned on if the value of **Target** is a positive number.


**Neg** 

Optional. Turned on if the value of **Target** is a negative number.


**Zero** 

Optional. Turned on if the value of **Target** is zero.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
The **MOVEREM** operation must immediately follow the **DIV** operation (if the **REM** keyword was not used with the **DIV** operation) or undesirable results may occur. Note that you must use the **DIV** op code, and cannot use the divide sign "/" in it's place. 

Note that you can also use the **REM** parameter in the previous **DIV** operation instead of the **MOVEREM** op code. 

### See Also
[DIV](DIV.html) 
