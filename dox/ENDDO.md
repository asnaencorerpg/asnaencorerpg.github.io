---
title: ENDDO

Id: ENDDO
TocParent: aerLrfOpCodesMain
TocOrder: 810


---

Ends a [DO](DO.html), [DOUNTIL](DOUNTIL.html) or [DOWHILE](DOWHILE.html) group. 

```

 **ENDDO** 
Incr (Numeric Expression)
```

### Parts

**Incr** 

Optional. Only valid if ending a **DO** loop. The loop index will be incremented by the increment value each time the group of commands is executed. The **DO** group will never end if a value is negative.


### Remarks
Conditioning indicators are optional.

Resulting indicators are not allowed.

If you do increment the loop with a negative value, keep in mind that **INCR** of the **DO** operation does not work in the opposite way it does with a positive value. That is, you can't have a larger number in the first value (say 45), and 1 in the second, and expect the loop to stop. 

In a decrementing loop, the second value must be equal to or larger than the first. After the loop starts, the second value is no longer a "factor" in the loop, which is why you must check your index value and stop the loop manually when the index reaches the desired value. 

### Example

```
/* The Do group can be processed 10 times. The Do group stops running when the index value in field X is greater 
   than the limit value (20) in Factor 2. The starting value of 2 is specified 
   in the Do operation, and the incrementing value of 2 is specified in the **Enddo**  operation. */

Do 2 20 X
 Y = Y + 1
Enddo 2      

// In this example of DoUntil, one of several conditions are met with the **Enddo** .

DoUntil 
   *In99 = *On *and ManualPremium = TotalPremium +
   *Or EarnedPremium = 1500
   ManualPremium = ManualPremium + AvgDailyPremium
   EarnedPremium = EarnedPremium + ManualPremium
   Read CustMaster Eof(*In99)
 Enddo // In this example of DoWhile, one of several conditions are met with the **Enddo** .

DoWhile 
   *In99 = *Off *or EarnedPremium &lt; TotalPremium +
   *or EarnedPremium &lt; DrugFreePremium
   EarnedPremium = DailyAvgPremium + EarnedPremium
   DrugFreePremium = DailyAvgPremium + DrugFreePremium
   Read CustMaster Eof(*In99)
 Enddo 
```

### See Also
[DO](DO.html)
[DOUNTIL](DOUNTIL.html)
[DOWHILE](DOWHILE.html)
[END](END.html) 
