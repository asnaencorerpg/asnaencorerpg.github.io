
title: ADD

Id: ADD
TocParent: aerLrfOpCodesMain
TocOrder: 0


---

Adds **F1** to **F2** and places the sum in **Result** .

```
ADD
F1 (Numeric Expression | Character Expression | <u>*NONE</u>) F2  (Numeric Expression | Character Expression) Result  (Numeric Variable | Character Variable)
Adj (<u>*TRUNC</u> | *RNDUP)
Pos (Indicator Variable)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer]
```

### Parts

**F1** 

Optional. If **F1** is not specified, **F2** is added to **Result** and the sum is placed in **Result** . 

If **F1** and **F2** are character type (*CHAR), they will be concatenated, and the result placed in the **Result** . In this case, the adjust (ADJ) parameter will be ignored. 

**F1** and **F2** may not be the Value property of an IOField control. Implicitly numeric control properties are allowed.


** **F2** ** 

Required. If **F1** and **F2** are character type (*CHAR), they will be concatenated, and the result placed in the **Result** . In this case, the adjust ( **ADJ** ) parameter will be ignored. 

**F1** and **F2** may not be the Value property of an IOField control. Implicitly numeric control properties are allowed.


**Result** 

Optional. Contains a numeric or character variable to contain the result of the addition.


**Adj** 

Optional. Db specifies the Database Name to use when opening the file at run-time. The actual file/member that is accessed at run-time is determined by the Mbr and File parameters. If the DB parameter is not given, the same database that was accessed to get the file description will be accessed to open the file.


**Pos** 

Optional. Pos will be turned on if the **Result** is a positive number.


**Neg** 

Optional. Neg will be turned on if the **Result** is a negative number.


**Zero** 

Optional. Zero will be turned on if the **Result** is zero.


**Type** 

Optional. **Type** can be any of the types listed. *NONE is the default.


**Len** 

Optional. **Len** defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *CHAR, *PACKED, *ZONED will require a **Len** . a compiler message will display if the **Len** parameter is needed.


**Example** 

```
// The value 1 is added to RecordNbr.

RecordNbr = RecordNbr + 1

// The contents of HoursWrk are added to CurrHours.

CurrHours = HoursWrk + CurrHours

// The contents of OTimePay and RegPay are added together and placed in TotalPay.

TotalPay = OTimePay + RegPayxamples 
```

### See Also
[+ Operator](Plus_Operator.html)

[CONCAT](CONCAT.html)

[Expressions](Expressions.html) 
