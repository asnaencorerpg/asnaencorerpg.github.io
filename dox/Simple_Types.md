---
title: Simple Types

Id: Simple_Types
TocParent: aerLrfLangElementsMain
TocOrder: 9


---

The following are the **simple** **types** allowed in the Encore RPG Language. 

**Character Types:** 
<table id="Table2" style="LEFT: 0px; WIDTH: 100%; TOP: 73px; border-spacing: 0px" cellspacing="0" width="100%" x-use-null-cells="x-use-null-cells">
            <colgroup span="1" />
</table>
<table>
            <col span="1" />
            <col span="1" style="WIDTH: 358px" />
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="105">

[<font>*CHAR](Character_Data_Type.html) 
</td>
                <td colspan="1" rowspan="1" style="width: 424px">

Character string. The maximum character string is 65,523. 
</td>
            </tr>
</table>
 **<br />Numeric
            Types:** 
<table id="Table3" style="LEFT: 0px; WIDTH: 100%; TOP: 150px; border-spacing: 0px" cellspacing="0" width="100%" x-use-null-cells="x-use-null-cells">
            <colgroup span="1">
                <col span="1" style="WIDTH: 149px" />
                <col span="1" style="WIDTH: 510px" />
            </colgroup>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="149" style="height: 81px">

[*BINARY](Binary_Data_Type.html) 
</td>
                <td colspan="1" rowspan="1" width="510" style="height: 81px">

Decimal binary number (2's complement). The maximum size for a 2-byte binary is four digits, and the maximum size for a 4-digit binary is 9 digits. 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="149">

[*PACKED](Packed_Data_Type.html) 
</td>
                <td colspan="1" rowspan="1" width="510">

Decimal packed number (X "7" as the rightmost nibble is negative, X"3" as the rightmost nibble is positive). The maximum number of digits can be 31 and the maximum number of decimal positions is 9. 
</td>
            </tr>
            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="149">

[*ZONED](Zoned_Data_Type.html) 
</td>
                <td colspan="1" rowspan="1" width="510">

Decimal zoned number (H"3" as the rightmost zone is positive, H"7" as the rightmost zone is negative). The maximum number of digits can be 31 and the maximum number of decimal positions is 9. 
</td>
            </tr>
</table>

**Special Type:** 
<table id="Table4" style="LEFT: 0px; WIDTH: 100%; TOP: 384px; border-spacing: 0px" cellspacing="0" width="100%" x-use-null-cells="x-use-null-cells">
            <colgroup span="1" />
</table>
<table>
            <col span="1" />
            <col span="1" style="WIDTH: 354px" />

            <tr valign="top" style="x-cell-content-align: top">
                <td colspan="1" rowspan="1" width="102">

[*IND](Ind_Data_Type.html) 
</td>
                <td colspan="1" rowspan="1" style="width: 431px">

Indicator (can only have the special values *ON and *OFF). 
</td>
            </tr>
</table>

### Related Sections
[Commands](Commands.html) 

[Expressions](Expressions.html) 

[Type Conversions](Type_Conversions.html) 

### See Also
[Language Elements](ecrLrfLangElementsMain.html)

[Encore RPG Language Reference](ecrLrfLangRefMain.html)

[Syntactical Elements](ecrLrfSyntacticalElementsMain.html) 
