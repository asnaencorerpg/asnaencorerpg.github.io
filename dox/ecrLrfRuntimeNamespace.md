---
title: ASNA.VisualRPG.Runtime Namespace

Id: aerLrfRuntimeNamespace
TocParent: aerLrfClassLibraryMain
TocOrder: 0


---

The **ASNA.VisualRPG.Runtime** namespace contains classes that support compilation and code generation using the Encore RPG for Visual Studio language. Most of the classes are reserved for the Encore RPG system. Some classes and their members (which are documented here) may be employed by the Encore RPG programmer. 

[Namespace hierarchy](ecrLrfAsnaVisualRPGRuntimeHierarchy.html) 

### Classes
<table class="dtTABLE" id="Table2" cellspacing="0">
                <tr valign="top">
                    <th colspan="1" rowspan="1" style="width: 22%">
                        Class
                    </th>
                    <th colspan="1" rowspan="1" width="50%">
                        Description
                    </th>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [Database](ecrLrfDatabaseClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Defines a target for database operations. That is, a database source comprises
                        a connection to a database engine. The database object models this notion of a
                        database source.  See [DCLDB](DCLDB.html) for additional
                        information.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [DataGateException](ecrLrfDataGateExceptionClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Provides granular reporting for exceptions thrown by the DataGate
                        client for certain Database, DBFile and Printfile operations.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [DBFile](ecrLrfDBFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Defines a reference to a system-level database file object and its members. It
                        supports I/O operations to a database file.  See [DCLDISKFILE](DCLDISKFILE.html) for additional information.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [IDS](ecrLrfIDSClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        An Interface implemented by a data structure.  See [DCLDS](DCLDS.html) for additional information.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [IMODS](ecrLrfIMODSClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        An Interface implemented by a multiple occurance data
                        structure.  See [DCLDS](DCLDS.html) for additional information.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [LengthNotDeterminableException](ecrLrfLengthNotDeterminableExceptionClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Provides reporting for exceptions thrown when the length of a data
                        structure cannot be determined.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [MemoryFile](ecrLrfMemoryFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Maintains an ADO.NET Dataset as though it were a collection of "flat
                        files". See [DCLMEMORYFILE](DCLMEMORYFILE.html) for additional
                        information.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [MessageFileReader](ecrLrfMessageFileReaderClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Provides a method for reading message text from an ASNA .amf
                        Message file.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 22%">
                        [PrintFile](ecrLrfPrintFileClass.html)
                    </td>
                    <td colspan="1" rowspan="1" width="50%">
                        Defines a reference to an externally described, multiple-format
                        DataGate printer file. Supports output operations to the printer file. 
                        See [DCLPRINTFILE](DCLPRINTFILE.html) for additional information.
                    </td>
                </tr>
</table>

### See Also
[Database Class](ecrLrfDatabaseClass.html)

[DBFile Class](ecrLrfDBFileClass.html)

[DCLDB](DCLDB.html)

[DCLDISKFILE](DCLDISKFILE.html)

[DCLMEMORYFILE](DCLMEMORYFILE.html)

[DCLPRINTFILE](DCLPRINTFILE.html)

[MemoryFile Class](ecrLrfMemoryFileClass.html)

[Namespace hierarchy](ecrLrfAsnaVisualRPGRuntimeHierarchy.html)

[PrintFile Class](ecrLrfPrintFileClass.html)

[Encore RPG Class Library](ecrLrfClassLibraryMain.html) 
