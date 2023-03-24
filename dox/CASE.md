---
title: CASE

Id: CASE
TocParent: aerLrfOpCodesMain
TocOrder: 220


---

Allows you to conditionally select a subroutine for processing.

```

 **CASE<br />Cond** (Expression)
 **Sr**  (Subroutine Name)<br /><br />ParmList (<u>*NONE</u> | Parameter List)
```

### Parts

**Cond** 

Required. **Cond** allows you to enter the expression of the condition.


**Sr** 

Required. **Sr** is the name of the subroutine to process when the condition is met.


**ParmList** 

Optional. The name of the parameter list. *NONE is the default.


### Remarks
The **CASE** operation allows you to use a comparison expression. 

### Example

```
/* The **Case**  operation compares OnHand with UnitSold. If OnHand is greater than or equal to UnitSold, 
ReturnNow is processed and the program continues with the operation after the Endcs operation. */

      Case Cond(OnHand &gt;= UnitSold) Sr(ReturnNow)

/* If OnHand is not greater than or equal to UnitSold, the program compares OnHand with OnOrder. 
If OnHand is equal to OnOrder, CutOrder is processed and the program continues with the operation 
after the Endcs operation. */

     Case Cond(OnHand = OnOrder) Sr(CutOrder)

/* If OnHand is not equal to OnOrder, the **Case**  operation causes ReviewOrder to be processed 
before the program continues with the operation after the Endcs operation. The **Case**  statement
 is used to provide a subroutine if none of the previous **Case**  operations have been met. */

     CaseDft Sr(ReviewOrder)

// The Endcs operation denotes the end of the **Case**  group. 

     Endcs
```

### See Also
[CASEDFT](CASEDFT.html)
[ENDCS](ENDCS.html)
[EXSR](EXSR.html) 
