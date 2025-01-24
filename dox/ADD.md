---
title: ADD

Id: ADD
TocParent: aerLrfOpCodesMain
TocOrder: 0

---

Adds **F1** to **F2** and places the sum in **Result** .

```c
ADD
F1 (Numeric Expression | Character Expression | <u>*NONE</u>)
F2 (Numeric Expression | Character Expression)
Result (Numeric Variable | Character Variable)
Adj (<u>*TRUNC</u> | *RNDUP)
Pos (Indicator Variable)
Neg (Indicator Variable)
Zero (Indicator Variable)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length [, Decimals])
```

### Parts

#### F1

Optional. If **F1** is not specified, **F2** is added to **Result** and the sum is placed in **Result**.

If **F1** and **F2** are character type (`*Char`), they will be concatenated, and the result placed in the **Result** . In this case, the adjust (**Adj**) parameter will be ignored.

#### F2

Required. If **F1** and **F2** are character type (`*Char`), they will be concatenated, and the result placed in the **Result** . In this case, the adjust (**Adj**) parameter will be ignored.

#### Result

Contains a numeric or character field to contain the result of the addition. Use **Type** and **Len** to declare the field if necessary.

#### Adj

Optional. Indicates how to perform half-adjust. Use `*RndUp` if you wish to round up the value, or use `*Trunc` if you wish to truncate the value of the **Result**. `*Trunc` is the default.

#### Pos

Optional. Indicator that will be turned on if the **Result** is a positive number.

#### Neg

Optional. Indicator that will be turned on if the **Result** is a negative number.

#### Zero

Optional. Indicator that will be turned on if the **Result** is zero.

#### Type

Optional. **Type** is used when impicitly declaring the **Result** field. It can be any of the types listed. `*None` is the default, except when **Len** is given, where **Type** will default to `*Zoned` for a **Len** with two arguments, or `*Char` for a **Len** with one argument.

#### Len

Optional. **Len** is used when impicitly declaring the **Result** field. When declaring a `*Zoned` or a `*Char` field, **Type** is optional.

Depending upon the **Type** specified, the **Len** parameter may be required. A compiler error message will display if the **Len** parameter is needed.

### Example

```c
// The value 1 is added to RecordNbr.

ADD F2(1) RESULT(RecordNbr)

// The contents of HoursWrk are added to CurrHours.

ADD F1(HoursWrk) F2(CurrHours) RESULT(CurrHours)

// The contents of OTimePay and RegPay are added together and placed in TotalPay.

ADD OTimePay RegPay TotalPay
```

### See Also

[+ Operator](Plus_Operator.html)

[CONCAT](CONCAT.html)

[Expressions](Expressions.html)
