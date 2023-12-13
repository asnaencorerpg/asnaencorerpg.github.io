---
title: "%DIFF Function"

Id: DIFF_Function
TocParent: Functions_overview
TocOrder: 10


---

<span style="FONT-WEIGHT: bold">%DIFF</span> [built-in function](Functions_overview.html) produces the difference (duration) between two date or time values. The first and second parameters must be the same or compatible types. 

```
%DIFF (Op1, Op2, {*MSECONDS | *SECONDS | *MINUTES | *HOURS | *DAYS | *MONTHS | *YEARS}) 
        
```

### Parts

**Op1, Op2** 

Required. These two parameters must be the same or compatible types. The following combination are valid: 

- Date and Date
- Time and Time
- Timestamp and Timestamp
- Date and Timestamp
- Time and Timestamp


***MSECONDS, *SECONDS, *MINUTES, *HOURS, *DAYS, *MONTHS, *YEARS** 

Required. This specifies the duration. Valid codes depend upon the previous parameters as follows: 

- For Date and Date, you can specify *DAYS,
                        *MONTHS, or *YEARS.
- For Time and Time, you can specify *SECONDS, *MINUTES,
                        or *HOURS.
- For Timestamp and Timestamp, you can
                        specify *MSECONDS, *SECONDS, *MINUTES, *HOURS, *DAYS, *MONTHS,
                        or *YEARS.
- For Date and Timestamp, you can specify *DAYS, *MONTHS, or
                        *YEARS. **Note** 
                        Only the date portion of the Timestamp is considered.
- For Time and Timestamp,  you can specify *SECONDS, *MINUTES, or
                        *HOURS. **NOTE** : Only the time portion of the Timestamp is
                        considered.


### Remarks
The result will be rounded down with any remainder discarded. For example, 61 minutes is equal to 1 hour, and 59 minutes is equal to 0 hours. Visual RPG places an 18-digit limit on durations. A duration with more than 15 significant digits will cause errors or truncation. The value returned by this function is compatible with both type numeric and type duration. You can add or subtract the result to a number (type numeric) or a date, time, or timestamp (type duration). See [Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html) for more information. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Date and Time Topics](ecrLrfDateandTimeMain.html)

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[%DAYS](DAYS_Function.html)

[%HOURS](HOURS_Function.html)

[%MINUTES](MINUTES_Function.html)

[%MONTHS](MONTHS_Function.html)

[%MSECONDS](MSECONDS_Function.html)

[%SECONDS](SECONDS_Function.html)

[%YEARS](YEARS_Function.html)

[ADDDUR](ADDDUR.html)

[SUBDUR](SUBDUR.html) 
