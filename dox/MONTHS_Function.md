---
title: "%MONTHS Function"

Id: MONTHS_Function
TocParent: Functions_overview
TocOrder: 30


---

<span style="FONT-WEIGHT: bold">%MONTHS</span> [built-in function](Functions_overview.html) converts a number into a duration that can be added to a date or timestamp value. 

```
%MONTHS (Number)        
```

### Parameters

**Number** 

Required. The number to be converted to duration and added to or subtracted from a date or timestamp value.


### Remarks
**%MONTHS** can only be the right-hand value in an addition or subtraction operation. The left-hand value must be a date or timestamp. The result is a date or timestamp value with the appropriate number of months added or subtracted. For a date, the resulting value is *ISO format. 

In most cases, when adding or subtracting a duration in months, the general rule is that the month portion is increased or decreased by the number of months in the duration and the day portion is unchanged. 

There are exceptions resulting when the day portion will exceed the actual number of days in the resulting month. In this case, the resulting day portion is adjusted to the actual month end date. For example, adding one month to "97/05/31" results in "97/06/30". The resulting month portion has been increased by 1 and the resulting day portion has been adjusted because June only has 30 days. See [Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html) for more information. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[%DAYS](DAYS_Function.html)

[%DIFF](DIFF_Function.html)

[%HOURS](HOURS_Function.html)

[%MINUTES](MINUTES_Function.html)

[%MSECONDS](MSECONDS_Function.html)

[%SECONDS](SECONDS_Function.html)

[%YEARS](YEARS_Function.html) 
