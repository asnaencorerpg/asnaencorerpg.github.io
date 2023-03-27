---
title: Printing

Id: Printing
TocParent: aerLrfLangElementsMain
TocOrder: 7


---

Local and network printing is accomplished in Encore RPG by writing to a print file contained in the Acceler8DB database. Because a user may select from a number of printer devices with different capabilities, some properties require special considerations. 

**Note &#8211;** Not all of the possible settings for the following properties may be valid as each printer device can have a limited set of capabilities. It is up to the programmer to select the setting appropriate to the actual printer device used. 

See the individual properties for more information on each of these property. 
<br />

<table class="dtTABLE" id="Table2" cellspacing="0" width="60%">
                <colgroup span="1" valign="top">
                    <col span="1" width="10%" />
                    <col span="1" width="50%" />
                </colgroup>
                <tr>
                    <th colspan="1" rowspan="1">
                        Property
                    </th>
                    <th colspan="1" rowspan="1">
                        Description
                    </th>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[Collate](Collate_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

Indicates whether collation will be used when printing multiple copies. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[Duplex](Duplex_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

Indicates whether the printer file is to print duplex (prints on both sides of the paper). 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[FormName](FormName_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The name of the customized page size to use.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[Orientation](Orientation_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The printer’s paper orientation (Horizontal or Vertical).
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[PaperLength](PaperLength_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The physical length of the page.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[PaperSize](PaperSize_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The paper (size) to be used.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[PaperSource](PaperSource_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The printer tray that will be used.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[PaperWidth](PaperWidth_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The physical width of the page.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[PrintableLength](PrintableLength_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The length of the printable area on the paper based on the page orientation selected. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[PrintableWidth](PrintableWidth_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The width of the printable area on the page based on the page orientation selected. 
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[Quality](Quality_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The print quality.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[Scale](Scale_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

The percentage factor by which the printed document is to be scaled.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[TTOption](Ttoption_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

Indicates how true type fonts are to be printed.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[UseColor](UseColor_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

Indicates whether to use color when a color printer is specified.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

[YResolution](YResolution_Property.html) 
</td>
                    <td colspan="1" rowspan="1">

Indicates the Y-axis resolution (in dot per inch) when printing graphics. 
</td>
                </tr>
</table>

### See Also
[Language Elements](ecrLrfLangElementsMain.html)

[PrintFile Class](ecrLrfPrintFileClass.html)

[PrintFile Properties](ecrLrfPrintFileProperties.html) 
