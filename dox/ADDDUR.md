---
title: ADDDUR

Id: ADDDUR
TocParent: aerLrfOpCodesMain
TocOrder: 10

---

**ADDDUR** adds the duration specified in **F2** to the date or time specified in **F1**, and places the resulting date, time or timestamp in **Result**.

```c
ADDDUR
F1 (<u>*NONE</u>| Date | Time | Timestamp field | Subfield | Array | Array element | Literal | Constant)
F2 (Numeric field | Array element | Constant : Date | Time | Timestamp | Array | Array element)
F2Fmt (*DAYS, *MONTHS, *YEARS, *MSECONDS, *SECONDS, *MINUTES, *HOURS)
Result  (Date | Time | Timestamp field | Subfield | Array | Array element)
Err (*EXTENDED | Indicator Variable)
```

### Parameters

#### F1

Optional. May contain a date, time or timestamp field, subfield, array, array element, literal or constant. If **F1** is not specified, the duration is added to the field specified in the **Result**. If **F1** contains a field name, array or array element, then its data type must be the same data type as the field specified in **Result**.

#### F2

Required. May be a numeric field, array element or constant with zero decimal positions. If the duration is negative, then it is subtracted from the date.

#### F2Fmt

Required. **F2Fmt** must be a valid duration code indicating the type of duration. The duration code must be consistent with the **Result** data type. You can add a year, month or day duration to a date field, but you cannot add a minute.

#### Result

Required. **Result** must be a date, time or timestamp data type field, array or array element.

If **Result** is an array, the value in **F2** is added to each element of the array.

If **F1** is blank, the duration is added to the value in **Result**.

If **Result** is a time field, the result will always be a valid time. For example, adding 10 minutes to 23:59:59 would give 24:09:59. Since this time is not valid, the run-time adjusts it to 00:09:59.

When adding a duration to a date in months, only the month portion is increased by the number of months in the duration. The day portion remains unchanged. The exception to this is when the resulting day portion would exceed the actual number of days in the resulting month. In this case, the resulting day portion is adjusted to the actual month-end date. See [Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html) for more information.

#### Err

Optional. **Err** determines what the runtime will do if an error occurs while executing this command. The following rules apply:

**Err**(Indicator Variable) - The specified Indicator is set if an error occurred. The **Err** indicator will be turned on when one of the following occurs:

- The result of the operation is invalid.
- The value of the date, time or timestamp field in **F1** is invalid.
- The value of the date, time or timestamp field in **Result** is invalid when **F1** is not given.

**Err(`*Extended`)** - a program status flag is set whose status can be checked using the %ERROR built-in function.

If the **Err**  keyword is not given and an error occurs, a runtime exception will be thrown.

### Example

The following examples assume a *ISO format:

```c
"2023/07/28" ADDDUR 2:*MONTHS results in "2023/09/28"
"2023/07/28" ADDDUR -10:*YEARS results in "2013/07/28"
"2023/07/28" ADDDUR 5:*DAYS results in "2023/08/02"
```

### See Also

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[Duration Codes](Duration_Codes.html)

[EXTRACT](EXTRACT.html)

[SUBDUR](SUBDUR.html)
