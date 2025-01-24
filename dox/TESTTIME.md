---
title: TESTTIME

Id: TESTTIME
TocParent: aerLrfOpCodesMain
TocOrder: 1530


---

Allows users to test the validity of [time](Time_Formats.html), [date](Date_Formats.html), or [timestamp](Timestamp_Literals.html) fields prior to using them. 

```
TESTTIME TimFmt (<u>*NONE</u> | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD)
 Result  (Char | Numeric | Date | Time | Timestamp)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
 Err  (Indicator Variable | *EXTENDED)
ResultType(<u>*NONE</u> | *DATE | *TIME | *TIMESTAMP)     
```

### Parameters

**TimFmt** 

**TimFmt**  specifies the format for [time](Time_Formats.html),
                [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html)
                variables. If the TimFmt parameter is not specified, the format specified by
                the program is assumed.


**Result** 

Required. Contains the field to be tested.


**Type** 

Optional. Can be any of the **Types** listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**Err** 

Required. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**ResultType** 

Optional. Unless the **Result** contains fields declared as character or numeric, then a **ResultType** must be specified, as indicated below. *NONE is the default. 

- If the **ResultType** is *DATE, **TimFmt** is optional and may contain any of the valid **Date** formats.
- If the **ResultType** is *TIMESTAMP, **TimFmt** is optional and may contain *ISO.
- If the **ResultType** is *TIME, **TimFmt** is optional and may contain any of the valid **Time** formats.

The ***USA** time format is not allowed with the **ResultType** * **TIME** and **Result** is numeric. The *USA time format has an AM/PM restriction that cannot be converted to numeric when a numeric **Result** is used.


### Remarks
Numeric fields are tested for valid digit portions of a Date, Time or Timestamp value. Character fields are tested for both valid digits and separators. 

### See Also
[ADDDUR](ADDDUR.html)

[EXTRACT](EXTRACT.html)

[SUBDUR](SUBDUR.html)

[Time Formats](Time_Formats.html) 
