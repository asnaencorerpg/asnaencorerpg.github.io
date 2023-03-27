---
title: WHEN

Id: WHEN
TocParent: aerLrfOpCodesMain
TocOrder: 1760


---

Determines where control passes after the [SELECT](SELECT.html) operation is processed. 

```

 **WHEN** 
 **Cond**  (Conditional Expression)
```

### Parts

**Cond** 

Required. Determines where control passes after the **SELECT** operation is processed.


### Remarks
If the expression is the first one true on the list of **WHEN** commands after the select, the group of statements after the **WHEN** will be executed. 

If no expressions or **WHEN** commands evaluate to true, the group of commands after the [OTHER](OTHER.html) command will be executed (if specified). 

### Example

```
// The following example shows nested SELECT groups. The employee type can be one of Casual, Retired, Regular, and Student.
Depending on the employee type (EmpType), the number of days off per year (Days) will vary. 

*/When the employee type is Regular, the days off depend also on the number of years of employment. The base number of days is 14. For 
  less than 2 years, no extra days are added. Between 2 and 5 years, 5 extra days are added. Between 6 and 10 years, 10 extra days are 
  added, and over 10 years, 20 extra days are added. */

Select
   When EmpType = Casual *or EmpType = Retired
     DaysWorked = *Zeros
   When EmpType = Regular
     DaysWorked = 14

  //Nested select group.

  Select
    When Yearsworked < 2
    When YearsWorked <= 5
      DaysWorked = DaysWorked + 5  
	When YearsWorked <= 10
	  DaysWorked = DaysWorked + 10
	Other 
	  DaysWorked = DaysWorked + 20
   Endsl

   //End of nested select group.      

   When	EmpType = Student
     DaysWorked = 5
Endsl
```

### See Also
[ENDSL](ENDSL.html)

[SELECT](SELECT.html) 
