---
title: "%HOURS Function"

Id: HOURS_Function
TocParent: Functions_overview
TocOrder: 22


---

<span style="FONT-WEIGHT: bold">%HOURS</span> [built-in function](Functions_overview.html) converts a number into a duration that can be added to a time or timestamp value. 

```
%HOURS  (Number)
```

### Parameters

**Number** 

Optional. The number to be converted to duration and added to or subtracted from a time or timestamp value.


### Remarks
**%HOURS** can only be the right-hand value in an addition or subtraction operation. The left-hand value must be a date or timestamp. The result is a time or timestamp value with the appropriate number of hours added or subtracted. For a time, the resulting value is *ISO format. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[%DAYS](DAYS_Function.html)

[%DIFF](DIFF_Function.html)

[%MINUTES](MINUTES_Function.html)

[%MONTHS](MONTHS_Function.html)

[%MSECONDS](MSECONDS_Function.html)

[%SECONDS](SECONDS_Function.html)

[%YEARS](YEARS_Function.html) 
