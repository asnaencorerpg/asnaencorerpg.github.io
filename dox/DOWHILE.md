---
title: DOWHILE

Id: DOWHILE
TocParent: aerLrfOpCodesMain
TocOrder: 720


---

Begins a group of operations you want to process while the relationship "xx" exists between the two operands. 

```

 **DOWHILE** 
 **Cond**  (Comparison Expression)   
```

### Parts

**Cond** 

Required. The comparison expression is evaluated at the end of the execution of the group of commands between the **DOWHILE** and the [ENDDO](ENDDO.html). If the expression is True, the group of commands is executed again.


### Remarks
**DOWHILE** first evaluates the complete condition. If the condition is True, the group of statements up to the ENDDO will be executed and control passes back to the **DOWHILE** command again. 

If the conditioning indicators on the **DOWHILE** command line are satisfied, the **DOWHILE** operation is processed. If the indicators are not satisfied, control passes to the next operation to be processed following the associated **ENDDO** command. 

### Example

```
/* The **DOWHILE** 	operation allows the operation within the DO group to be processed only if EarnedPremium is less than 
   TotalPremium. If EarnedPremium is not less than TotalPremium, the program branches to the operation immediately 
   following the ENDDO operation. If EarnedPremium is less than TotalPremium, the operation within the DO group is 
   processed. */

DoWhile EarnedPremium < TotalPremium

/* The ENDDO operation causes the program to branch to the first **DOWHILE** 	operation, where a test is made 
   to determine whether EarnedPremium is less than TotalPremium. This loop continues processing until EarnedPremium is 
   equal to or greater than TotalPremium; then the program branches to the operation immediately following the ENDDO operation. */

EarnedPremium = DailyAvgPremium + EarnedPremium
Read CustMaster Eof(*In99)
Enddo

/* In this example, multiple conditions are tested. The combined **DOWHILE** operation 
    allows the operation within the DO group to be processed only while *IN99 is off due to "Not End of file" or 
    EarnedPremium is less than TotalPremium or DrugFreePremium. If neither specified condition exists, the program 
    branches to the operation immediately following the ENDDO operation. If either of the specified conditions exists, 
   the operation after the ORLT operation is processed. */

Read CustMaster Eof(*In99)
DoWhile *In99 = *Off *or EarnedPremium < TotalPremium +
*or EarnedPremium < DrugFreePremium 

/* The ENDDO operation causes the program to branch to the second **DOWHILE**  operation where a test determines whether
   specified conditions exist. This loop continues until EarnedPremium is equal to or greater than TotalPremium and 
   DrugFreePremium; then the program branches to the operation immediately following the ENDDO operation. */

EarnedPremium = DailyAvgPremium + EarnedPremium
DrugFreePremium = DailyAvgPremium + DrugFreePremium
Read CustMaster Eof(*In99)
Enddo

/* The **DOWHILE**  operation allows the operation within the DO group to be processed only if EarnedPremium is less
   than TotalPremium. If EarnedPremium is not less than TotalPremium, the program branches to the operation immediately 
   following the ENDDO operation. If EarnedPremium is less than TotalPremium, the operation within the DO group is 
   processed. */

DoWhile	EarnedPremium < TotalPremium

/* The ENDDO operation causes the program to branch to the first **DOWHILE** 	operation, where a test is made to 
   determine whether EarnedPremium is less than TotalPremium. This loop continues processing until EarnedPremium is 
   equal to or greater than TotalPremium; then the program branches to the operation immediately following the ENDDO 
   operation. */

EarnedPremium = DailyAvgPremium + EarnedPremium
Read CustMaster Eof(*In99)
Enddo

/* In this example, multiple conditions are tested. The combined **DOWHILE** operation allows the operation within 
   the DO group to be processed only while *IN99 is off due to "Not End of file" or EarnedPremium is less than 
   TotalPremium or DrugFreePremium. If neither specified condition exists, the program branches to the operation 
   immediately following the ENDDO operation. If either of the specified conditions exists, the operation after the ORLT
   operation is processed. */

Read CustMaster Eof(*In99)
DoWhile *In99 = *Off *or EarnedPremium < TotalPremium +
*or EarnedPremium < DrugFreePremium 

/* The ENDDO operation causes the program to branch to the second **DOWHILE**  operation where a test determines whether 
   specified conditions exist. This loop continues until EarnedPremium is equal to or greater than TotalPremium and 
   DrugFreePremium; then the program branches to the operation immediately following the ENDDO operation. */

EarnedPremium = DailyAvgPremium + EarnedPremium
DrugFreePremium = DailyAvgPremium + DrugFreePremium
Read CustMaster Eof(*In99)
Enddo
```

### See Also
[DO](DO.html)
[DOUNTIL](DOUNTIL.html)
[ENDDO](ENDDO.html) 
