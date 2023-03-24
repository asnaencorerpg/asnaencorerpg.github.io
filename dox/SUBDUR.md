---
title: SUBDUR

Id: SUBDUR
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

**SUBDUR** either subtracts the duration specified in **F2** from a date or time and places the resulting date, time or timestamp in the **Result** , or calculates a duration between two **date/time** values. 

```

 **SUBDUR** 
F1 (Date | Time | Timestamp)
 **F2**  (Date | Time | Timestamp | Numeric Duration)
F2Fmt (*<u>NONE</u> | *DAYS, *MONTHS, *YEARS, *MSECONDS, *SECONDS, *MINUTES, *HOURS)
 **Result**  (Date | Time | Timestamp |Numeric Duration)
ResultFmt (*<u>NONE</u> | *DAYS, *MONTHS, *YEARS, *MSECONDS, *SECONDS, *MINUTES, *HOURS)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8
    | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
Err (Indicator Variable | *Extended)

```

### Parts

**F1** 

Optional. May contain a date, time or timestamp field, array, array element, literal or constant. 

- If **F1** contains a field name, array or array element, then its data type must be the same type as the field specified in the **Result** .


**F2** 

Required. A numeric field, array or constant with zero decimal positions. If the field is negative then the duration is added to the field.


**F2Fmt** 

Optional. Must be a valid [duration code](Duration_Codes.html) indicating the type of duration. The duration code must be consistent with the **Result** data type. For example, you can subtract a year, month or day duration but not a minute duration from a date field.


**Result** 

Required. The name of a zero decimal numeric field, array or array element in which the result of the operation will be placed.


**ResultFmt** 

Optional. Must be a date, time or timestamp data type field, array or array element.

- If **F1** is blank, the duration is subtracted from the value in the **Result** .
- If the **Result** is an array, the value in F2 is subtracted from each element in the array.
- If the **Result** is a time field, the result will always be a valid Time. For example, subtracting 59 minutes from 00:58:59 would give -00:00:01. Since this time is not valid, the run-time adjusts it to 23:59:59.


**Type** 

Optional. Can be any of the **Types** listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**Err** 

Optional. Determines what the run-time will do if an error occurs while executing this command. The following rules apply:


- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
**SUBDUR** allows two time/date data types to be subtracted with a resulting duration, or it allows a duration to be subtracted from a time/date data type with a resulting time/date. **SUBDUR** does not allow two time/date data types to be subtracted with a resulting time/date data type. 

<u> **Subtracting a Duration:** </u> 

Use **SUBDUR** to subtract a duration specified in **F2** from a field or constant specified in **F1** and place the resulting date, time or timestamp in the field specified in **Result** . 

When subtracting a duration in months from a date, the general rule is that the month portion is decreased by the number of months in the duration, and the day portion is unchanged. The exception to this is when the resulting day portion would exceed the actual number of days in the resulting month. In this case, the resulting day portion is adjusted to the actual month end date. See [Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html) for more information. 

The system places a 18 digit limit on durations. Subtracting a Duration with more than 18 significant digits will cause errors or truncation. These problems can be avoided by limiting the first factor in **F2** to 18 digits or less. 

** *Possible Error Situations* :** 

- If **F1**  is blank and the value of the **Result** 
                before the operation is invalid or if the result of the operation is invalid.
- If the value of the Date, Time or Timestamp field in **F1**  is
                invalid.

<u> **Calculating a Duration:** </u> 

The **SUBDUR** operation can also be used to calculate a duration between: 

- Two times
- A time and a timestamp
- Two dates
- A date and a timestamp
- Two timestamps

The data types in **F1** and **F2** must be compatible types as specified above. 

** *Possible Error Situations* :** 

- If **F1**  is blank and the value of the **Result** 
                before the operation is invalid or if the result of the operation is invalid.
- If the value of the Date, Time or Timestamp field in **F1**  is
                invalid.

### Example

```

"97/07/21" SUBDUR2: ***MONTH**  results in "97/ **05** /21"
"97/07/21" SUBDUR1: ***YEAR**  results in " **96** /07/21"
"97/07/21" SUBDUR5: ***DAY**  results in "97/07/ **16** "

 **SUBDUR F1** (isodate2) **F2** (isodate) **Result** (duration) **ResultFmt** (*Days)
```

### See Also
[ADDDUR](ADDDUR.html)
[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)
[EXTRACT](EXTRACT.html) 
