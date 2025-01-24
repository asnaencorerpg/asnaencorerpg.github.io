---
title: MOVE

Id: MOVE
TocParent: aerLrfOpCodesMain
TocOrder: 1210


---

Transfers characters from **Source** to the **Target** , right-adjusted with optional blanks padded on the left side of the **Target** . 

```
MOVE 
Source (Character Expression)
Target  (Character Expression)
Fill (<u>*NOPAD</u> | *PAD)
Pos (Indicator Variable) 
Neg (Indicator Variable)
Boz (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | 
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
TimFmt (<u>*NONE</u> | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD)      
```

### Parameters

**Source** 

Required. If the **Source** parameter is longer than the **Target** , the excess leftmost characters of **Source** are not moved. If the **Target** is longer than **Source** , the excess leftmost characters are left untouched, unless padding is specified.


**Target** 

Required. Resulting indicators cannot be specified if the **Target** is an array. They can be specified if the **Target** is a non-array field or array element.


**Fill** 

Optional. Specifies if you want to fill, or pad the **Target** (Target) with blanks. The default is *NOPAD. 

- *NOPAD indicates that the **Target** will not be padded with blanks.
- *PAD indicates that the **Target** will be padded with blanks.


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

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Type *CHAR, *PACKED, and *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**TimFmt** 

Optional. **TimFmt**  specifies the format for [time](Time_Formats.html),
                [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html)
                variables. If the TimFmt parameter is not specified, the format specified by the program is assumed.


### Remarks
**Moving Text from a Control to a Field** 

When moving text from a control into a field, be aware that the contents is a null-terminated string and does not assume the field length. **MOVE** and **MOVEL** operations will move only the number of characters in the string into the field, which may result in extraneous data remaining in the field. Be sure to use Fill(*Pad) in the operation to prevent this. 

**Moving Date, Time or Timestamp fields** 

**TimFmt** must be blank unless either the source or the target is a character or numeric field. Otherwise, **TimFmt** contains the date or time format compatible with the character or numeric field that is the source or target of the operation. 

If Source is *DATE and the result is a Date field, **TimFmt** is not required. If **TimFmt** contains a date format it must be compatible with the format of *DATE. See [Moving Date-Time Data](Moving_Data_Time_Data.html) for more information. 

**Moving a Character Field to a Date-Time Field** 
<table>
            <tr><th>Factor 1</th><th>Factor 2</th><th colspan="2">Results Field</th></tr>
            <tr><td>Entry</td><td>(Character)</td><td>Value</td><td>DTZ Type</td></tr>
            <tr><td>*MDY</td><td>11/19/75</td><td>75/323</td><td>D(*JUL)</td></tr>
            <tr><td>*JUL</td><td>92/114</td><td>23/04/92</td><td>D(*DMY)</td></tr>
            <tr><td>*YMD</td><td>14/1/28</td><td>01/28/2014</td><td>D(*USA)</td></tr>
            <tr><td>*USA</td><td>12/31/9999</td><td>31.12.9999</td><td>D(*EUR)</td></tr>
            <tr><td>*ISO</td><td>2036-05-21</td><td>21/05/36</td><td>D(*DMY)</td></tr>
            <tr><td>*JUL</td><td>45/333</td><td>11/29/1945</td><td>D(*USA)</td></tr>
            <tr><td>*USA</td><td>1:00 PM</td><td>13.00.00</td><td>T(*EUR)</td></tr>
            <tr><td>*EUR</td><td>1.10.07</td><td>11:10:07</td><td>T(*JIS)</td></tr>
            <tr><td>*JIS</td><td>14:16:18</td><td>14.16.18</td><td>T(*HMS)</td></tr>
            <tr><td>*ISO</td><td>24.00.00</td><td>12:00 AM</td><td>T(*USA)</td></tr>
            <tr><td>Blank</td><td>1991-09-14-13.12.56.123456</td><td>1991-09-14-13.12.56.123456</td><td>Z(*ISO)</td></tr>
            <tr><td>*ISO</td><td>1991-09-14-13.12.56.123456</td><td>1991-09-14-13.12.56.123456</td><td>Z(*ISO)</td>	</tr>
</table>

**Moving a Numeric Field to a Date-Time Field** 
<table>
            <tr><th>Factor 1</th><th>Factor 2</th><th colspan="2">Results Field</th></tr>
            <tr><td>Entry</td><td>(Character)</td><td>Value</td><td>DTZ Type</td></tr>
            <tr><td>*MDY</td><td>111975</td><td>75/323</td><td>D(*JUL)</td></tr>
            <tr><td>*JUL</td><td>92114</td><td>23/04/92</td><td>D(*DMY)</td></tr>
            <tr><td>*YMD</td><td>140128</td><td>01/28/2014</td><td>D(*USA)</td></tr>
            <tr><td>*USA</td><td>12319999</td><td>31.12.9999</td><td>D(*EUR)</td></tr>
            <tr><td>*ISO</td><td>20360521</td><td>21/05/36</td><td>D(*DMY)</td></tr>
            <tr><td>*JUL</td><td>45333</td><td>11/29/1945</td><td>D(*USA)</td></tr>
            <tr><td>*MDY</td><td>030533</td><td>03.05.33</td><td>D(*MDY)</td></tr>
            <tr><td>*USA</td><td>*DATE (092195)</td><td>1995-09-21</td><td>D(*JIS)</td></tr>
            <tr><td>Blank</td><td>*DATE (092195)</td><td>1995-09-21</td><td>D(*JIS)</td></tr>
            <tr><td>*MDY</td><td>UDATE (092195)</td><td>21.09.1995</td><td>D(*EUR)</td></tr>
            <tr><td>*HMS</td><td>231256</td><td>23.12.56</td><td>T(*ISO)</td></tr>
            <tr><td>*EUR</td><td>111007</td><td>11.10.07</td><td>T(*JIS)</td></tr>
            <tr><td>*JIS</td><td>141618</td><td>14.16.18</td><td>T(*HMS)</td></tr>
            <tr><td>*ISO</td><td>240000</td><td>12:00 AM</td><td>T(*USA)</td></tr>
            <tr><td>Blank</td><td>19910914131256123456</td><td>1991-09-14-13.12.56.123456</td><td>Z(*ISO)</td></tr>
</table>

**Moving a Date-Time Field to a Character Field.** 
<table>
            <tr><th>Factor 1</th><th>Factor 2</th><th colspan="2">Results Field</th></tr>
            <tr><td>Entry</td><td>(Character)</td><td>DTZ Type</td><td>(Character)</td></tr>
            <tr><td>*JUL</td><td>11/19/75</td><td>D(*MDY)</td><td>75/323</td></tr>
            <tr><td>*USA</td><td>15.01.28</td><td>D(*YMD)</td><td>01/28/2014</td></tr>
            <tr><td>*EUR</td><td>12/31/9999</td><td>D(*USA)</td><td>31.12.9999</td></tr>
            <tr><td>*USA</td><td>45/333</td><td>D(*JUL)</td><td>11/29/1945</td></tr>
            <tr><td>*ISO</td><td>24.12.56</td><td>T(*HMS)</td><td>24.12.56</td></tr>
            <tr><td>*EUR</td><td>11:00 AM</td><td>T(*USA)</td><td>11:00:00</td></tr>
            <tr><td>*JIS</td><td>11:10:07</td><td>T(*EUR)</td><td>11:10:07</td></tr>
            <tr><td>*USA</td><td>24:00:00</td><td>T(*ISO)</td><td>12:00 AM</td></tr>
            <tr><td>Blank</td><td>2045-10-27-23:34.59.123456</td><td>T(*ISO)</td><td>12:00 AM</td></tr>
</table>

**Moving a Date-Time Field to a Numeric Field.** 
<table>
            <tr><th>Factor 1</th><th>Factor 2</th><th colspan="2">Results Field</th></tr>
            <tr><td>Entry</td><td>(Character)</td><td>DTZ Type</td><td>(Character)</td></tr>
            <tr><td>*JUL</td><td>11/19/75</td><td>D(*MDY)</td><td>75323</td></tr>
            <tr><td>*USA</td><td>15.01.28</td><td>D(*YMD)</td><td>01282014</td></tr>
            <tr><td>*EUR</td><td>12/31/9999</td><td>D(*USA)</td><td>31129999</td></tr>
            <tr><td>*USA</td><td>45/333</td><td>D(*JUL)</td><td>11291945</td></tr>
            <tr><td>*ISO</td><td>24.12.56</td><td>T(*HMS)</td><td>241256</td></tr>
            <tr><td>*EUR</td><td>11:00 AM</td><td>T(*USA)</td><td>110000</td></tr>
            <tr><td>*JIS</td><td>11.10.07</td><td>T(*EUR)</td><td>111007</td></tr>
            <tr><td>*USA</td><td>45/333</td><td>T(*JUL)</td><td>11291945</td></tr>
</table>

### Example
<u> ** Source is shorter than Result. ** </u> 

```
Character to Character  

  Value1 = "ASNA4ME" 
  Value2 = "123456784"
    Move Value1 Value2

  Value2 now = "12ASNA4ME". 

 **Character to Numeric** 

  Value1 = "ASNA4ME" 
  Value2 = 123456784
    Move Value1 Value2

  Value2 now contains invalid Data for a numeric field. 

 **Numeric to Numeric** 

  Value1 = 1278425 
  Value2 = 123456789
    Move Value1 Value2

  Value2 now = 121278425. 

 **Numeric to Character** 

  Value1 = 1278425 
  Value2 = "ACFGPH4SN"
    Move Value1 Value2

  Value2 now = "AC1278425"
```      <br />
 **<u>Source is longer than Result.</u>** 
 
```
Character to Character 

  Value1 = "ASNA4ME" 
  Value2 = "PH4SN"
    Move Value1 Value2

  Value2 now = "NA4ME". 

 **Character to Numeric** 

  Value1 = "ASNA4ME" 
  Value2 = 56784
    Move Value1 Value2 

  Value2 now contains invalid Data for a numeric field. 

 **Numeric to Numeric** 

  Value1 = 1278425 
  Value2 = 56748
    Move Value1 Value2

  Value2 now = 78425. 

 **Numeric to Character** 

  Value1 = 1278425 
  Value2 = "ASNA4"
    Move Value1 Value2

  Value2 now = "78425". 

```
<br /> **<u> Source is shorter than Result with *Pad extension. </u>** 

```
Character to Character 

  Value1 = "ASNA4ME" 
  Value2 = "123456784"
    Move Value1 Value2 Fill(*Pad)

  Value2 now = // ASNA4ME'. 

 **Character to Numeric** 

  Value1 = "ASNA4ME" 
  Value2 = 123456784
    Move Value1 Value2 Fill(*Pad) 

 Value2 now contains invalid Data for a numeric field. 

 **Numeric to Numeric** 

  Value1 = 1278425 
  Value2 = 123456789
    Move Value1 Value2 Fill(*Pad)

  Value2 is now = 1278425. 

 **Numeric to Character** 

  Value1 = 1278425 
  Value2 = "ACFGPH4SN"
    Move Value1 Value2 Fill(*Pad)

  Value2 now = // 1278425'. 

```
<u>Source and Result are the same length.</u> 

```
Character to Character 

  Value1 = "ASNA4ME" 
  Value2 = "1234567"
    Move Value1 Value2

  Value2 now = "ASNA4ME". 

 **Character to Numeric** 

  Value1 = "ASNA4ME" 
  Value2 = 1234567
  Move Value1 Value2 

  Value2 now contains invalid Data for a numeric field. 

 **Numeric to Numeric** 

  Value1 = 1278425 
  Value2 = 1234567
    Move Value1 Value2

  Value2 now = 1278425.

 **Numeric to Character** 

  Value1 = 1278425 
  Value2 = "ACFGPH4"
    Move Value1 Value2

  Value2 now = "1278425" 
```

### See Also
[MOVEL](MOVEL.html)

[Moving Date-Time Data](Moving_Data_Time_Data.html) 
