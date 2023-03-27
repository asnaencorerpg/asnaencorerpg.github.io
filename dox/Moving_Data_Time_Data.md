---
title: Moving Date-Time Data

Id: Moving_Data_Time_Data
TocParent: aerLrfDateandTimeMain
TocOrder: 8


---

The following considerations are provided for the [MOVE](MOVE.html) and [MOVEL](MOVEL.html) operation codes when moving Date, Time, and Timestamp data type fields. 

The combinations below are allowed for the **MOVE** and **MOVEL** operation codes: 

- Date to Date
- Time to Time
- Timestamp to Timestamp
- Date to Timestamp
- Time to Timestamp (sets micro-seconds to 000000)
- Timestamp to Date
- Timestamp to Time
- Date to Character or Numeric
- Time to Character or Numeric
- Timestamp to Character or Numeric
- Character or Numeric to Date
- Character or Numeric to Time
- Character or Numeric to Timestamp

### Remarks
<span style="FONT-WEIGHT: bold">TimFmt</span> must be blank if: 

- The source or target of the move is a timestamp field.
- Both the source and the target of the move are date or time fields. Otherwise, **TimFmt** contains the date or time format compatible with the character or numeric field that is the source or target of the operation.
- Any valid format can be specified.<br />

Keep in mind the following when specifying **TimFmt** : 

- Time format *USA is not allowed for movement between Time and numeric classes.

- A two-digit year format (*MDY, *DMY and *JUL) can only represent dates in the range 1940 through 2039. An error occurs if converting to a two- or three-digit year format for dates outside this range.
- When moving a value to a date field, keep in mind that **TimFmt** determines the number of digits moved.

<span style="FONT-WEIGHT: bold">Source is required</span> and may contain a character or numeric, Date, Time, or Timestamp field; array; array element; a literal; or a named constant, to be converted. 

The following rules apply to Source: 

- In general, if the field specified in **Source** is character, it must have separator characters, for example 09/06/91.
- Separator characters must be valid for the specified format.
- If **Source** is not a valid representation of a date or time or its format does not match the format specified in TimFmt, an error occurs.

If Source contains * **DATE** , the **TimFmt** entry must be a date format with a 4-digit year. 

The <span style="FONT-WEIGHT: bold">Target</span> must be a Date, Time, or Timestamp field or a numeric or character class field, array or array element. The date or time is placed in **Target** according to its defined format or the format code specified in **TimFmt** . If **Target** is numeric, separator characters are removed prior to the operation. The length used is the length after removing the separator characters. 

When moving from a **Date to a Timestamp** field, the time and microsecond portion of the timestamp are unaffected. However, an error occurs if the entire timestamp is not valid. 

When moving from a **Time to a Timestamp** field, the microsecond's part of the timestamp is set to 000000. The date portion remains unaffected, but an error occurs if the entire timestamp is not valid. 

### See Also
[Date and Time](aerLrfDateandTimeMain.html)

[Date Data Type](Date_Data_Type.html)

[MOVE](MOVE.html)

[MOVEL](MOVEL.html)

[Time Data Type](Time_Data_Type.html)

[Timestamp Data Type](Timestamp_Data_Type.html) 
