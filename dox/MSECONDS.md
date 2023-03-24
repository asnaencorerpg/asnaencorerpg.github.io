---
title: "%MSECONDS Function"

Id: MSECONDS
TocParent: Functions_overview
TocOrder: 31


---

<span style="FONT-WEIGHT: bold">%MSECONDS</span> [built-in function](Functions_overview.html) converts a number into a duration that can be added to a time or timestamp value. 

```

 **%MSECONDS (Number)** 
        
```

### Parts

**Number** 

Required. The number to be converted to duration and added to or subtracted from a time or timestamp value.


### Remarks
**%MSECONDS** can only be the right-hand value in an addition or subtraction operation. The left-hand value must be a time or timestamp. The result is a time or timestamp value with the appropriate number of microseconds added or subtracted. For a time, the resulting value is *ISO format. 

### See Also
[Built-in Function Overview](Functions_overview.html)
[%DAYS](DAYS_Function.html)
[%DIFF](DIFF_Function.html)
[%HOURS](HOURS_Function.html)
[%MINUTES](MINUTES_Function.html)
[%MONTHS](MONTHS_Function.html)
[%SECONDS](SECONDS_Function.html)
[%YEARS](YEARS_Function.html) 
