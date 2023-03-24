---
title: "*HIVAL"

Id: STARHIVAL
TocParent: aerLrfFigConstantsMain
TocOrder: 7


---

***HIVAL** moves the highest collating value for the field type. 
<br />

<table class="dtTable" id="Table2" width="65%" style="WIDTH: 100%; border-spacing: 0px" cellspacing="0" x-use-null-cells="x-use-null-cells">
                <colgroup span="1">
                    <col span="1" width="15%" style="FONT-WEIGHT: bold" />
                    <col span="1" width="45%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Field Types
                    </th>
                    <th colspan="1" rowspan="1">
                        Descriptions
                    </th>
                </tr>
                <tr valign="top" style="x-cell-content-align: top">
                    <td colspan="1" rowspan="1">

For Character Fields: 
</td>
                    <td colspan="1" rowspan="1">

* **HIVAL** moves the highest collating character for the system (hexadecimal FFs). ). 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Graphic Fields:
</td>
                    <td colspan="1" rowspan="1">

* **HIVAL** moves the highest collating character for the system (hexadecimal FF's). 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Numeric Fields:
</td>
                    <td colspan="1" rowspan="1">

* **HIVAL** moves the maximum value allowed for the corresponding field (with a positive sign if applicable). 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Float Fields:
</td>
                    <td colspan="1" rowspan="1">

* **HIVAL** for 4-byte float = 3.402 823 5E38 (H"FF7FFFFF") 

* **HIVAL** for 8-byte float = 1.797 693 134 862 315 E308 (H"FFEFFFFFFFFFFFFF") 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Date Fields:
</td>
                    <td colspan="1" rowspan="1">

See [Default Values for all Date Formats](Default_Values_for_all_Date_Formats.html) for * **HIVAL** values. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For Time Fields: 
</td>
                    <td colspan="1" rowspan="1">

See [Default Values for all Time Formats](default_values_for_all_time_formats.html) for * **HIVAL** values. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

For TimeStamp Fields: 
</td>
                    <td colspan="1" rowspan="1">

***HIVAL** moves 9999-12-31-23.59.59.999999. 
</td>
                </tr>
</table>

<br />

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)
[Default Values for all Date Formats](Default_Values_for_all_Date_Formats.html)
[Default Values for all Time Formats](default_values_for_all_time_formats.html)
[*LOVAL](STARLOVAL.html)
[Figurative Constants Rules](Fig_Constants_Rules.html) 
