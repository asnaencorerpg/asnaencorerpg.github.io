---
title: "*LOVAL"

Id: STARLOVAL
TocParent: aerLrfFigConstantsMain
TocOrder: 8


---

***LOVAL** moves the lowest collating value for the field type. 
<br />

<table class="dtTable" width="65%" style="WIDTH: 100%; border-spacing: 0px" cellspacing="0" x-use-null-cells="x-use-null-cells">
                <colgroup span="1">
                    <col span="1" width="15%" style="FONT-WEIGHT: bold" />
                    <col span="1" width="45%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1" style="height: 23px">
                        Field Types
                    </th>
                    <th colspan="1" rowspan="1" style="height: 23px">
                        Descriptions
                    </th>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1">

For Character Fields: 
</td>
                    <td colspan="1" rowspan="1">

* **LOVAL** moves the lowest collating character for the system (hexadecimal zeros). 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Graphic Fields:
</td>
                    <td colspan="1" rowspan="1">

* **LOVAL** moves the lowest collating character for the system (hexadecimal zeros). 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Numeric Fields:
</td>
                    <td colspan="1" rowspan="1">

* **LOVAL** moves all 9's with a negative sign.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Float Fields:
</td>
                    <td colspan="1" rowspan="1">

* **LOVAL** for 4-byte float = -3.402 823 5E38 (H"7F7FFFFF") 

* **LOVAL** for 8-byte float = -1.797 693 134 862 315 E308 (H"7FEFFFFFFFFFFFFF") 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Date Fields:
</td>
                    <td colspan="1" rowspan="1">

See [Default Values for all Date Formats](Default_Values_for_all_Date_Formats.html) for * **LOVAL** values. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Time Fields: 
</td>
                    <td colspan="1" rowspan="1">

See [Default Values for all Time Formats](default_values_for_all_time_formats.html) for * **LOVAL** values. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For TimeStamp Fields: 
</td>
                    <td colspan="1" rowspan="1">

***LOVAL** moves 0001-01-01-00.00.00.000000. 
</td>
                </tr>
</table>

<br />

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)
[Default Values for all Date Formats](Default_Values_for_all_Date_Formats.html)
[Default Values for all Time Formats](default_values_for_all_time_formats.html)
[*HIVAL](STARHIVAL.html)
[Figurative Constants Rules](Fig_Constants_Rules.html) 
