---
title: DBFile Properties

Id: aerLrfDBFilePropertiesMain
TocParent: aerLrfDBFileClass
TocOrder: 1


---

### Public Properties
<br />

<table class="dtTABLE" id="Table4" cellspacing="0">
                    <colgroup span="1">
                        <col span="1" valign="top" width="20%" />
                        <col span="1" width="79.99%" />
                    </colgroup>
                    <tr>
                        <td colspan="1" rowspan="1" height="28">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [FormatName](FormatName_Property.html)
                        </td>
                        <td colspan="1" rowspan="1" height="28">Gets the name of the record format last read or written.</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [IsEOF](IsEofPropertyDbFileClass.html)
                        </td>
                        <td colspan="1" rowspan="1">
                            Returns **True**  when a
                            file input operation results in **End-of-File** 
                            being reached. 
                        </td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [IsEqual](IsEqualPropertyDbFileClass.html)
                        </td>
                        <td colspan="1" rowspan="1">
                            Returns **True**  when akeyed file **"Seek"**  operation 	results in
                            a record being found that matches the seek Key. 
                        </td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [IsError](IsErrorPropertyDbFileClass.html)
                        </td>
                        <td colspan="1" rowspan="1">Returns **True**  when an I/O operation results in an error 	condition.</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1" height="30">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [IsFound](IsEqualPropertyDbFileClass.html)
                        </td>
                        <td colspan="1" rowspan="1" height="30">
                            Returns **True**  when akeyed file record I/O 	operation results in
                            a record being found.
                        </td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [IsOpen](IsOpen_Property.html)
                        </td>
                        <td colspan="1" rowspan="1">Gets a boolean value indicating if the file is currently open for I/O 	operations.</td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [LastException](LastException_Property_PrintFileClass.html)
                        </td>
                        <td colspan="1" rowspan="1">
                            Gets the last exception thrown for this file. This property is of type 	    ASNA.VisualRPG.Runtime.AvrException.
                        </td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [Overrider](ecrLrfDBFileClassOverriderProperty.html)
                        </td>
                        <td colspan="1" rowspan="1">
                            Gets or sets the DB file overrider. This property is of type 	ASNA.VisualRPG.Runtime.IDBFileOverrider.
                        </td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [RecCount](RecCount_Property.html)
                        </td>
                        <td colspan="1" rowspan="1">
                            Gets the current number of non-deleted records in the file.
                        </td>
                    </tr>
                    <tr>
                        <td colspan="1" rowspan="1">
                            <img alt="public property" src="../Images/property.bmp" border="0" /> [RecNum](RecNum_Property.html)
                        </td>
                        <td colspan="1" rowspan="1">
                            Gets the current RRN for the last input operation to
                            a file.
                        </td>
                    </tr>
</table>

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DCLDISKFILE](DCLDISKFILE.html) 
