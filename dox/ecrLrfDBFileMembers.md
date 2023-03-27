---
title: DBFile Members

Id: aerLrfDBFileMembers
TocParent: aerLrfDBFileClass
TocOrder: 0


---

[DBFile overview](ecrLrfDBFileClass.html) 

### Public Constructor
<br />

<table class="dtTABLE" id="Table3" cellspacing="0">
                <tr>
                    <td colspan="1" rowspan="1" width="20%">
                        <img alt="overloaded method" src="../Images/Methods.bmp" border="0" /> DBFile
                    </td>
                    <td colspan="1" rowspan="1" width="79.99%">
                        This can not be called directly in code, instantiate using [DCLDISKFILE](DCLDB.html).
                    </td>
                </tr>
</table>

<br />

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
                        Returns **True**  when akeyed file **"Seek"**  operation results in
                        a record being found that matches the seek Key. 
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" /> [IsError](IsErrorPropertyDbFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">Returns **True**  when an I/O operation results in an error condition.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" height="30">
                        <img alt="public property" src="../Images/property.bmp" border="0" /> [IsFound](IsEqualPropertyDbFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1" height="30">
                        Returns **True**  when akeyed file record I/O operation results in
                        a record being found.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" /> [IsOpen](IsOpen_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets a boolean value indicating if the file is currently open for I/O operations.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" /> [LastException](LastException_Property_PrintFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Gets the last exception thrown for this file. This property is of type 	ASNA.VisualRPG.Runtime.AvrException.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" /> [Overrider](ecrLrfDBFileClassOverriderProperty.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Gets or sets the DB file overrider. This property is of type ASNA.VisualRPG.Runtime.IDBFileOverrider.
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

<br />

### Public Fields
<br />

<table class="dtTABLE" id="Table2" cellspacing="0">
                <colgroup span="1">
                    <col span="1" valign="top" width="20%" />
                    <col span="1" width="79.99%" />
                </colgroup>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [BlockingFactor](BlockingFactorFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the client/server record blocking size.
                    </td>
                </tr>
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
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [FilePath](FilePathFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the path of the file.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [IsDefaultRFN](ecrLrfIsDefaultRFNFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">Contains **True**  if the "default" renamed format is going to be used.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" height="23">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [IsFormatID](IsFormatIDFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1" height="23">Contains **True**  if the opened file"s format ID is equal to the described file"s format ID.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [IsKeyed](ecrLrfIsKeyedFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">Contains **True**  if the file has been opened for "keyed" access.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [MemberName](MemberNameFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the name of the file member to be opened when the file is opened.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [QryFileName](QryFileNameFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the name of the query file created for the **QrySelect** 
                        and **QryKeyFlds**  parameters.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [QryKeyFlds](QryKeyFldsFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the name of one or more key fields used to arrange the query records.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [QrySelect](QrySelectFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the selection expression used to determine which records are to be made available for processing.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [ShareType](ShareTypeFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains a string defining how a file will be shared.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public method" src="../Images/fields.gif" border="0" /> [WaitRec](WaitRecFieldDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Contains the waiting period for a record. 
                    </td>
                </tr>
</table>

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DCLDISKFILE](DCLDISKFILE.html) 
