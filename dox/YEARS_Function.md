---
title: "%YEARS Function"

Id: YEARS_Function
TocParent: Functions_overview
TocOrder: 53


---

**%YEARS** [built-in function](Functions_overview.html) converts a number into a duration that can be added to a date or timestamp value. 

```

 **%YEARS (Number)** 
        
```

### Parts

**Number** 

Required. The number to be converted to duration and added to or subtracted from a date or timestamp value.


### Remarks
**%YEARS** can only be the right-hand value in an addition or subtraction operation. The left-hand value must be a date or timestamp. The result is a date or timestamp value with the appropriate number of years added or subtracted. For a date, the resulting value is *ISO format. 

In most cases, when adding or subtracting a duration in years, the general rule is that the year portion is increased or decreased by the number of years in the duration and the day portion is unchanged. There are exceptions resulting when the day portion will exceed the actual number of days in the resulting month/year. In this case, the resulting day portion is adjusted to the actual month end date. See [Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html) for more information. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[%DAYS](DAYS_Function.html)

[%DIFF](DIFF_Function.html)

[%HOURS](HOURS_Function.html)

[%MINUTES](MINUTES_Function.html)

[%MONTHS](MONTHS_Function.html)

[%MSECONDS](MSECONDS_Function.html)

[%SECONDS](SECONDS_Function.html) 
