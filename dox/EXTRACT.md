---
title: EXTRACT

Id: EXTRACT
TocParent: aerLrfOpCodesMain
TocOrder: 1050


---

The **EXTRACT** operation code will return one of the following: 

- The hours, minutes or seconds part of a time or timestamp field.
- The year, month or day part of a date or timestamp field.
- The microseconds part of the timestamp field to the field specified in **Result** .


```
 **EXTRACT** 
 **F2**  (Date | Time | Timestamp | Array | Array element)
 **F2Fmt**  (*DAYS, *MONTHS, *YEARS, *MSECONDS, *SECONDS, *MINUTES, *HOURS)
 **Result**  (Numeric Variable)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | 
       *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
Err (Indicator Variable | *EXTENDED)
```

### Parts

**F2** 

Required. Contains the Date, Time or Timestamp from which the information is required, followed by the [Duration Code](Duration_Codes.html) ( **F2FMT** ).


**F2Fmt** 

Required. Can be a field, subfield, table element, or array element. The duration code must be consistent with the data type of **F2** .


**Result** 

Required. Can be any numeric or character field, subfield, array/table element. **Result** is cleared before the extracted data is assigned. For a character **Result** , the data is put left adjusted into **Result** .


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Please note that **EXTRACT** does not extract the century, so you would have to hardcode a value for the century. When using the **EXTRACT** operation with a Julian Date (format *JUL), specifying a duration code of ***D** will return the day of the month, specifying ***M** will return the month of the year. If you require the day and month to be in the 3-digit format, you can use a data structure to overlay the field, and extract the three digits. 

### Example

```

 **EXTRACT**  StartDate: *M StartMonth 2 0
 **EXTRACT**  StartDate: *D StartDay 2
```

### See Also
[ADDDUR](ADDDUR.html)

[Duration Codes](Duration_Codes.html) | [SUBDUR](SUBDUR.html) 
