---
title: MULT

Id: MULT
TocParent: aerLrfOpCodesMain
TocOrder: 1260



---

**F1** (if specified) is multiplied by **F2** and the product is placed in **Result** . 

```
MULT 
F1 (Numeric Expression | <u>*NONE</u>) F2  (Numeric Expression) Result (Numeric Variable) 
Adj (*<u>TRUNC</u>  | *RNDUP )
Pos (Indicator Variable) 
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | 
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**F1** 

Optional. If **F1** is not specified, **F2** is multiplied by the **Result** and the product is placed in **Result** .


**F2** 

Required. Contains a numeric expression to multiply.


**Result** 

Required. Must be large enough to hold the product of **F1** and **F2** . The length of **Result** equals the length of **F1** plus the length of **F2** .


**Adj** 

Optional. Indicates half-adjust. Use **Adj** (*RNDUP) if you wish to round up the value, or use **Adj** (*TRUNC) if you wish to truncate the value of the Result Field. *TRUNC is the default.


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


### Example

```
/* Multiply the value of ManualPremium by the value of DrugFreeCredit and place 
 Result in ExperienceModify.

 **Mult**  ManualPremium DrugFreeCredit ExperienceModify

/* Multiply the value of ManualPremium by the value of DrugFreeCredit and place 
 Result in ManualPremium with half adjust. */

 **Mult**  *NONE DrugFreeCredit ManualPremium *RNDUP

OR

 **Mult**  ManualPremium DrugFreeCredit ManualPremium *RNDUP
```

### See Also
[* Operator](Multiply_Operator.html) [<br /> Assignment](Assignment.html) 
