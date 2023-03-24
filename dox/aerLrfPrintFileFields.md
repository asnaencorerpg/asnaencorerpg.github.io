---
title: PrintFile Fields

Id: aerLrfPrintFileFields
TocParent: aerLrfPrintFileClass
TocOrder: 2


---

[PrintFile overview](aerLrfPrintFileClass.html) 

### Public Fields
<br />

<table class="dtTABLE" id="Table2" cellspacing="0">
                <colgroup span="1" valign="top">
                    <col span="1" width="20%" />
                    <col span="1" width="79.99%" />
                </colgroup>
                <tr>
                    <td colspan="1" rowspan="1">

<img alt="public method" src="../Images/fields.gif" border="0" /> [DclFileName](DclFileNameFieldRPGFileClass.html) 
</td>
                    <td colspan="1" rowspan="1">

Contains the name of the file field. This field is readonly.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

<img alt="public field" src="../Images/field.bmp" border="0" /> [DclPrintFileName](DclPrintFileName_Field.html) 
</td>
                    <td colspan="1" rowspan="1">

Contains the name of the file field.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

<img alt="public field" src="../Images/field.bmp" border="0" /> [FilePath](FilePath_Field_PrintFileClass.html) 
</td>
                    <td colspan="1" rowspan="1">

Contains a string that specifies the path of the file.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

<img alt="public field" src="../Images/field.bmp" border="0" /> [IsFormatID](IsFormatID_Field_PrintFileClass.html) 
</td>
                    <td colspan="1" rowspan="1">

Contains **True** if the opened (run-time) file"s format ID is equal to the declared (compile-time) file"s format ID.
</td>
                </tr>
</table>

<br />

### Protected Fields
<br />

<table class="dtTABLE" id="Table3" cellspacing="0">
                <colgroup span="1" valign="top">
                    <col span="1" width="20%" />
                    <col span="1" width="79.99%" />
                </colgroup>
                <tr>
                    <td colspan="1" rowspan="1">

<img alt="public field" src="../Images/field.bmp" border="0" /> [isOpen](isOpen_Field_PrintFileClass.html) 
</td>
                    <td colspan="1" rowspan="1">

Contains the open state of the printer file. When the value is **True** , the file is open.
</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">

<img alt="public field" src="../Images/field.bmp" border="0" /> [lastException](lastException_Field_PrintFileClass.html) 
</td>
                    <td colspan="1" rowspan="1">

Contains the last exception thrown for this file. This is a protected public field of type **ASNA.VisualRPG.Runtime.AvrException** . 
</td>
                </tr>
</table>

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 
