---
title: DIV

Id: DIV
TocParent: aerLrfOpCodesMain
TocOrder: 680


---

Divides **F1** by **F2** if **F1** is specified. If not, it divides the **Result** by **F2** and places the quotient in **Result** . 

```
DIV 
F1 (<u>*NONE</u> | Numeric Expression)
F2  (Numeric Expression)
Result  (Numeric Expression)
Rem (<u>*NONE</u> | Numeric Variable)
Adj (<u>*TRUNC</u> | *RNDUP)
Pos (Indicator Variable)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 
     | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**F1** 

Optional. Must be numeric and be any valid expression. When **F1** is not specified, the dividend **(Result)** is divided by F2 (divisor), and the result (quotient) is placed in **Result** .


**F2** 

Required. Must be a numeric expression. If it is zero, an error occurs at run-time.


**Result** 

Required. Must be a numeric expression.


**Rem** 

Optional. The remainder is lost unless the **Rem** parameter is specified, or the [MOVEREM](MOVEREM.html) (Move Remainder) operation is specified as the next operation. If **Rem** is not used, and MOVEREM is not processed directly after the **DIV** operation, undesirable results will occur.


**Adj** 

Optional. Indicates half-adjust. Use **Adj** (*RNDUP) if you wish to round up the value, or use **Adj** (*TRUNC) if you wish to truncate the value of the Result Field. *TRUNC is the default.


**Pos** 

Optional. Will be turned on if the value of **Result** is a positive number.


**Neg** 

Optional. Will be turned on if the value of **Result** is a negative number.


**Zero** 

Optional. Will be turned on if the value of **Result** is zero.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Example
When using positional values, (i.e. **F1** is not used) the Keywords **F2** and **Result** must be used unless ***NONE** occupies the null position. 

In these examples the following are set values.

```
DclFld Name (A) Len(5,0) Inz (515)
DclFld Name (B) Len(5,0) Inz (280)
DclFld Name (C) Len(7,2) Inz(0)
DclFld Name (D) Len(9,3) Inz(0)
DclFld Name (E) Len(7,2) Inz(35)
```

Divide A by B giving C. If *RNDUP is specified, the **rem** value will be zero and should be set to *none. The value of C will be 1.84. 

```
 If B <> *Zeros
 Div A B C rem(*none) adj(*rndup)
 Endif
```

Divide A by B giving C. Adj(*RNDUP) is not specified, and the REM parameter will be used. The value of C will be 1.83 and the value of D will be 2.6. 

```
 If B <> *Zeros
 Div A B C rem(D)
 Endif
```

Divide E by B giving E. If *RNDUP is specified, the rem value will be zero and should be set to *none. The value of E will be 0.13 and there is no remainder. When all values (Factor 1, Factor 2 and result) are not used, the keywords **F2** and **Result** must be specified. 

```
 If B <> *Zeros
 Div F2(B) Result(E) rem(*none) adj(*rndup)
 Endif
```

Divide E by B giving E. Adj(*RNDUP) is not specified, and the REM parameter will be used. The value of E will be 0.12 and the remainder will be 1.4. When all values (Factor 1, Factor 2 and result) are not used, the keywords **F2** and **Result** must be specified. 

```
 If B <> *Zeros
 Div F2(B) Result(E) rem(D)
 Endif
```

