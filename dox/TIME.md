---
title: TIME

Id: TIME
TocParent: aerLrfOpCodesMain
TocOrder: 1550


---

Accesses the system time of day at any time during program processing. The system time is based on the 24-hour clock. 

```
TIME
Target (Numeric | Date | Time | Timestamp)
Type (*ZONED | *PACKED | *BINARY | *DATE | *TIME | *TIMESTAMP)
Len (Length Integer [, Decimal Integer])
ResultTimFmt(<u>*ISO</u> | *DMY | *EUR | *JIS | *JUL | *MDY | *USA | *YMD) 
```

### Parts

**Target** 

Required. Specifies the field into which the time of day or the date and time of day are written.


**Type** 

Optional. Can be any of the Types listed. See [Type Parameter](Type_Parameter.html) for further information. If the field specified in **Target** is to be declared in this command then at least one of **Type** or **Len** must be given. If **Type** is not given the type will be *ZONED and **Len** must contain a list describing its digits and decimals.


**Len** 

Optional. Defines the length of the field. It is required if **Type** represents one of the fixed-decimal types.


**ResultTimFmt** 

Optional. Specifies the format of the result, if the result is a numeric field. The default is ***ISO** .


### Remarks
The result value will depend on the type of the **Target** field and on the time format specified in the **ResultTimFmt** parameter, according to the following table: 

<table id="Table2" style="WIDTH: 100%; border-spacing: 0px; x-cell-content-align: top" cellspacing="0" width="100%" x-use-null-cells="x-use-null-cells"> <colgroup span="1" /> </table> <table> <col span="1" style="WIDTH: 29.68%" /> <col span="1" style="WIDTH: 31.54%" /> <col span="1" style="WIDTH: 38.77%" /> <tr valign="top" style="x-cell-content-align: top"> <td colspan="1" rowspan="1" width="29.68%" bgcolor="#e8e8e8" height="34"> <p style="FONT-WEIGHT: bold; MARGIN-BOTTOM: 4pt"> <font> Target 
</td>
        <td colspan="1" rowspan="1" width="31.54%" bgcolor="#e8e8e8" height="34">

<font> Value Returned 
</td>
        <td colspan="1" rowspan="1" width="38.77%" bgcolor="#e8e8e8" height="34">

<font> Returned Format 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="29.68%">
                <font>6-digit </td>
            <td colspan="1" rowspan="1" width="31.54%">
                <font>Numeric </td>
            <td colspan="1" rowspan="1" width="38.77%">
                <font>Time hhmmss </td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="29.68%">
                <font>12-digit </td>
            <td colspan="1" rowspan="1" width="31.54%">
                <font>Numeric </td>
            <td colspan="1" rowspan="1" width="38.77%">
                <font>Time and Date, two-digit year </td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="29.68%">
                <font>14-digit </td>
            <td colspan="1" rowspan="1" width="31.54%">
                <font>Numeric </td>
            <td colspan="1" rowspan="1" width="38.77%">
                <font>Time and Date, four-digit year </td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="29.68%">
                <font>Time </td>
            <td colspan="1" rowspan="1" width="31.54%">
                <font>Time </td>
            <td colspan="1" rowspan="1" width="38.77%">
                <font>Format of Result </td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="29.68%">
                <font>Date </td>
            <td colspan="1" rowspan="1" width="31.54%">
                <font>Date </td>
            <td colspan="1" rowspan="1" width="38.77%">
                <font>Format of Result </td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="29.68%">
                <font>Timestamp </td>
            <td colspan="1" rowspan="1" width="31.54%">
                <font>Timestamp </td>
            <td colspan="1" rowspan="1" width="38.77%">
                <font>Format of Result </td>
        </tr>
</table>
        

If **Target** is a numeric field, to access the time of day only, specify **Target** as a 6-digit numeric field. 

To access both the time of day and the system date, specify **Target** as a 12 (2-digit year) or 14-digit (4-digit year) numeric field. The time of day is always placed in the first six positions of **Target** in the following format: 

hhmmss (hh=hours, mm=minutes, and ss=seconds)

- If **Target** is a numeric field, then if the system date is included, it is placed in **Target** following the time. The format for the date part depends on the value of **ResultTimFmt** , with *ISO (yyMMdd or yyyyMMdd) as the default. If *JUL is specified as the desired format then the date part will be the year (2- or 4-digits) followed by the 3-digit day, followed by a zero (yyddd0 or yyyyddd0).
- If **Target** is a Timestamp field, the last 3 digits in the microseconds-part are always 000.

