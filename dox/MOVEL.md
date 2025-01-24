---
title: MOVEL

Id: MOVEL
TocParent: aerLrfOpCodesMain
TocOrder: 1230


---

Transfers characters from **Source** to the **Target** , left-adjusted with optional padding on the right. 

```
MOVEL 
Source  (Expression)
Target  (Character Expression)
Fill (*NOPAD | *PAD)
Pos (Indicator Variable)
Neg (Indicator Variable)
Boz (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | 
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (length integer, decimal integer)
TimFmt (*NONE | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD)
```

### Parameters

**Source** 

Required. If **Source** is longer than the **Target** , the excess rightmost characters of **Source** are not moved. If the **Target** is longer than **Source** , the rightmost excess characters of **Target** are left untouched, unless padding is specified (Fill (*PAD)). 

Resulting indicators cannot be specified if the **Target** is an array. They can be specified if the **Target** is a non-array field or array element. 

When Data is moved to a numeric field, if **Source** is as long or longer than the **Target** , the sign (+ or -) will not be retained.


**Target** 

Required. If **Source** is longer than the **Target** , the excess rightmost characters of **Source** are not moved. If the **Target** is longer than **Source** , the rightmost excess characters of **Target** are left untouched, unless padding is specified (Fill (*PAD)). 

Resulting indicators cannot be specified if the **Target** is an array. They can be specified if the **Target** is a non-array field or array element. 

When Data is moved to a numeric field, if **Source** is as long or longer than the **Target** , the sign (+ or -) will not be retained.


**Fill** 

Optional. Specifies if padding will be specified on the right of the **Target** . *NOPAD is the default. 

- *NOPAD indicates that the Target will not be padded with blanks.

- *PAD indicates that the Target will be padded from the right with blanks.


**Pos** 

Optional only if Target is numeric. Turned on if the value of **Target** is a positive number.


**Neg** 

Optional only if Target is numeric. Turned on if the value of **Target** is a negative number.


**Boz**  [Blank or Zero]

Optional. Turned on if the value of **Target** is blank or zero.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**TimFmt** 

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the format specified by the program is assumed.


### Remarks
**Moving Text from a Control to a Field** 

When moving text from a control into a field, be aware that the contents is a null-terminated string and does not assume the field length. **MOVE** and **MOVEL** operations will move only the number of characters in the string into the field, which may result in extraneous data remaining in the field. Be sure to use Fill(*Pad) in the operation to prevent this. 

**When moving Date, Time or Timestamp fields** 

**TimFmt** must be blank unless either the source or the target is a character or numeric field. Otherwise, **TimFmt** contains the date or time format compatible with the character or numeric field that is the source or target of the operation. 

If Source is *DATE and the result is a Date field, **TimFmt** is not required. If **TimFmt** contains a date format it must be compatible with the format of *DATE. See [Moving Date-Time Data](Moving_Data_Time_Data.html) for more information. 

### Example
** <u> Source and Result are the same length. </u> ** 

```
 **Numeric to Numeric** 

  Value1 = 78425
  Value2 = 56784
    Movel Value1 Value2

  Value2 now = 78425. 

 **Numeric to Character** 

  Value1 = 78425
  Value2 = "ASNA4"
    Movel Value1 Value2

  Value2 now = "78425".

 **Character to Numeric** 

  Value1 = "ASNA4"
  Value2 = 78425
    Movel Value1 Value2

  Value2 is no longer a valid field. 

 **Character to Character** 

  Value1 = "ASNA4"
  Value2 = "MENOW"
    Movel Value1 Value2

  Value2 now = "ASNA4" 
```
<br /> <u> **Source Longer than Result.** </u> 

```
 **Numeric to Numeric** 

  Value1 = 000258425
  Value2 = 56784
    Movel Value1 Value2

  Value2 now = 00025. 

 **Numeric to Character** 

  Value1 = 903178425
  Value2 = "ASNA4"
    Movel Value1 Value2

  Value2 now = 90317. 

 **Character to Numeric** 

  Value1 = "ASNA4MEEE"
  Value2 = '56784
    Movel Value1 Value2

  Value2 is no longer a valid field. 

 **Character to Character** 

  Value1 = "ASNA4MEE"E
  Value2 = "OK4EU"
    Movel Value1 Value2

  Value2 now = "ASNA4".
```
**<u> Source is shorter than Result. </u>** 

```
 **Numeric to Numeric** 

  Value1 = 78425
  Value2 = 130943210
    Movel Value1 Value2 

  Value2 now = 784253210. 

 **Character to Numeric** 

  Value1 = "ASNA4"
  Value2 = 130943210
    Movel Value1 Value2

  Value2 is no longer a valid field.

 **Numeric to Character** 

  Value1 = 78425
  Value2 = "ASNA4MEEE"
    Movel Value1 Value2

  Value2 now = "78425MEEE". 

 **Character to Character** 

  Value1 = "ASNA4"
  Value2 = "NOMORERPG"
    Movel Value1 Value2

  Value2 now = "ASNA4ERPG". 
```
**<u>Source is shorter than Result with Fill(*Pad).</u>** 

```

 **Numeric to Numeric** 

  Value1 = 78425
  Value2 = 130943210
    Movel Value1 Value2 Fill(*Pad)

  Value2 now = 784250000. 

 **Character to Numeric** 

  Value1 = "ASNA4"
  Value2 = 130943210
    Movel Value1 Value2 Fill(*Pad)

  Value2 is no longer a valid field. 

 **Numeric to Character** 

  Value1 = 78425
  Value2 = "ASNA4MEEE"
    Movel Value1 Value2 Fill(*Pad)

  Value2 now = "78425" 

 **Character to Character** 

  Value1 = "ASNA4"
  Value2 = "NOMORERPG"
    Movel Value1 Value2 Fill(*Pad)

  Value2 now = "ASNA4" 
```

### See Also
[MOVE](MOVE.html)

[Moving Date-Time Data](Moving_Data_Time_Data.html) 
