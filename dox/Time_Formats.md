---
title: Time Formats

Id: Time_Formats
TocParent: aerLrfDateandTimeMain
TocOrder: 10


---

The following is a list of the Time formats and separators for [*Time data type](Time_Data_Type.html). 

<table id="Table2" style="WIDTH: 100%; border-spacing: 0px" cellspacing="0" width="100%" x-use-null-cells="x-use-null-cells"> <tr valign="top" style="x-cell-content-align: top"> <td colspan="1" rowspan="1" width="48" bgcolor="#e0e0e0" style="height: 91px"> <p align="center"> **RPG name** 
</td>
        <td colspan="1" rowspan="1" width="150" bgcolor="#e0e0e0" style="height: 91px">

**Description** 
</td>
        <td colspan="1" rowspan="1" width="90" bgcolor="#e0e0e0" style="height: 91px">

<font> **Format <br /> (Default <br /> Separator)** 
</td>
        <td colspan="1" rowspan="1" width="54" bgcolor="#e0e0e0" style="height: 91px">

**Valid<br /> Sepa-<br /> rators** 
</td>
        <td colspan="1" rowspan="1" width="60" bgcolor="#e0e0e0" style="height: 91px">

**Length** 
</td>
        <td colspan="1" rowspan="1" width="66" bgcolor="#e0e0e0" style="height: 91px">

**Example** 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="48">

*ISO 
</td>
            <td colspan="1" rowspan="1" width="150">

International Standards Organization 
</td>
            <td colspan="1" rowspan="1" width="90">

hh.mm.ss 
</td>
            <td colspan="1" rowspan="1" width="54">

. 0 
</td>
            <td colspan="1" rowspan="1" width="60">

8 
</td>
            <td colspan="1" rowspan="1" width="66">

13.05.21 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="48">

*HMS 
</td>
            <td colspan="1" rowspan="1" width="150">

Hours:Minutes:Seconds 
</td>
            <td colspan="1" rowspan="1" width="90">

hh:mm:ss 
</td>
            <td colspan="1" rowspan="1" width="54">

: . , & 0 
</td>
            <td colspan="1" rowspan="1" width="60">

8 
</td>
            <td colspan="1" rowspan="1" width="66">

13:05:21 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="48">

*USA 
</td>
            <td colspan="1" rowspan="1" width="150">

IBM USA Standard. AM and PM can be any mix of upper and lower case. 
</td>
            <td colspan="1" rowspan="1" width="90">

hh:mm AM or hh:mm PM 
</td>
            <td colspan="1" rowspan="1" width="54">

: 0 
</td>
            <td colspan="1" rowspan="1" width="60">

8 
</td>
            <td colspan="1" rowspan="1" width="66">

1:05 PM 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="48">

*EUR 
</td>
            <td colspan="1" rowspan="1" width="150">

IBM European Standard 
</td>
            <td colspan="1" rowspan="1" width="90">

hh.mm.ss 
</td>
            <td colspan="1" rowspan="1" width="54">

. 0 
</td>
            <td colspan="1" rowspan="1" width="60">

8 
</td>
            <td colspan="1" rowspan="1" width="66">

13.05.21 
</td>
        </tr>
        <tr valign="top" style="x-cell-content-align: top">
            <td colspan="1" rowspan="1" width="48">

*JIS 
</td>
            <td colspan="1" rowspan="1" width="150">

Japanese Industrial Standard Christian Era 
</td>
            <td colspan="1" rowspan="1" width="90">

hh:mm:ss 
</td>
            <td colspan="1" rowspan="1" width="54">

: 0 
</td>
            <td colspan="1" rowspan="1" width="60">

8 
</td>
            <td colspan="1" rowspan="1" width="66">

13:05:21 
</td>
        </tr>
</table>
        </p>

The ampersand (&) separator is replaced with a blank character. E.g., * **HMS&** results in the example time formated as **01 05 PM** . 

The zero (0) separator is replaced with no character. E.g., * **EURO** results in the example time formated as **130521** . 

####  **See Also** 
[Date and Time](ecrLrfDateandTimeMain.html)

[*HIVAL](STARHIVAL.html)

[*LOVAL](STARLOVAL.html)

[Date Formats](Date_Formats.html)

[Default Values for all Time Formats](default_values_for_all_time_formats.html) 
