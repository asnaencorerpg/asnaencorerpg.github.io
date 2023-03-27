---
title: Database Members

Id: aerLrfDatabaseMembers
TocParent: aerLrfDatabaseClass
TocOrder: 0


---

[Database overview](ecrLrfDatabaseClass.html) 

### Public Constructor
<table class="dtTABLE" id="Table2" cellspacing="0">
                <colgroup span="1" valign="top">
                    <col span="1" width="20%" />
                    <col span="1" width="79.99%" />
                </colgroup>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="constructor" src="../Images/methods.bmp" border="0" /> Database
                    </td>
                    <td colspan="1" rowspan="1">
                        This can not be called directly in code, instantiate using [DCLDB](DCLDB.html).
                    </td>
                </tr>
</table>

### Public Methods
<table class="dtTABLE" id="Table3" cellspacing="0">
                <colgroup span="1" valign="top">
                    <col span="1" width="20%" />
                    <col span="1" width="79.99%" />
                </colgroup>
                <tr>
                    <td colspan="1" rowspan="1" style="height: 20px; width: 207px;">
                        <img alt="public method" src="../Images/public method.gif" />
                        [AddMember](AddMember_Method.html)
                    </td>
                    <td colspan="1" rowspan="1" style="height: 20px">
                        Adds the specified member to
                        a database file.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [ClearMember](ClearMember_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Clears the specified member in a
                        database file.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="height: 24px; width: 207px;">
                        <img alt="public method" src="../Images/public method.gif" />
                        [CopyFileToDb](CopyFileToDb_Method.html)
                    </td>
                    <td colspan="1" rowspan="1" style="height: 24px">Copies a physical file and its members from the current database to another database.			</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" border="0" />
                        [CopyLogicalFileToDb](CopyLogicalFileToDb_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Copies a logical file and its base physical files from the current
                        database to another database.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [CreateDirectory](CreateDirectory_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Creates a directory (library) with the specified name in the database.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" border="0" />
                        [CreateName](CreateName_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Takes all the current values of the database name, except for the name itself, and creates
                        a new "Database Name" in the Application
                        Datafolder with the name given in *NewName* .
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="height: 23px; width: 207px;">
                        <img alt="public method" src="../Images/public method.gif" />
                        [DeleteFile](DeleteFile_Method.html)
                    </td>
                    <td colspan="1" rowspan="1" style="height: 23px">
                        Deletes an existing file from the database.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" border="0" />
                        [DeleteName](DeleteName_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Deletes an existing database name from the
                        Application Datafolder.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="height: 44px; width: 207px;">
                        <img alt="public method" src="../Images/public method.gif" border="0" />
                        [GetNames](GetNames_Method.html)
                    </td>
                    <td colspan="1" rowspan="1" style="height: 44px">
                        Returns an array of strings with all of the names found in the Application Data special folders and the registry (for backward compatibility)
                        The boolean parameter indicates whether to get PublicDatabase (*True) or those private to the current user (*False).
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [InitializeMember](InitializeMember_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Initializes a file member with the specified number of deleted records.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [RemoveDirectory](RemoveDirectory_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Removes the specified directory from a
                        database.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [RemoveMember](RemoveMember_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Removes the specified member from a
                        database file.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [RenameFile](RenameFile_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Changes the name of the specified file.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" />
                        [RenameMember](RenameMember_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Changes the name of the specified member.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="width: 207px">
                        <img alt="public method" src="../Images/public method.gif" border="0" />
                        [UpdateName](UpdateName_Method.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        The current values of the database name object are written out as the new values of the database name in the Application Data
                        folder.
                    </td>
                </tr>
</table>

### Public Properties
<table class="dtTABLE" id="Table5" cellspacing="0">
                <colgroup span="1" valign="top">
                    <col span="1" width="20%" />
                    <col span="1" width="79.99%" />
                </colgroup>
                <tr>
                    <td colspan="1" rowspan="1" height="27">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [CurrentUserLibl](CurrentUserLiblProperty.html)
                    </td>
                    <td colspan="1" rowspan="1" height="27">Sets the current library list for the current connection.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [DBName](DBName_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        gets or sets the name of a database.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [InitialException](InitialExceptionProperty.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets the first exception thrown for this database. This property is of type ASNA.DataGate.Common.dgException.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [InitialLibl](InitialLiblProperty.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets or sets the current database’s initial library list.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [IsOpen](IsOpen_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets a boolean value indicating if the file is currently open for I/O operations.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [Label](Label_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets or sets a string containing the label of the database to connect to.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [Password](Password_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">The password to be used in conjunction with **User**  for connection authentication.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [PlatformAttribute](PlatformAttribute_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">Returns or sets a platform-specific attribute of the database engine</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [PoolingTimeOut](PoolingTimeOutProperty.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Gets or sets the amount of time (in minutes) in which
                        a connection will remain idle in the pool until it is closed and removed from the pool. 
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [Port](Port_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets or sets the TCP port number used by the database server for TCP/IP-based transport (default 5042).</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [Server](Server_Property.html)
                    </td>
                    <td colspan="1" rowspan="1">Gets or sets the database server host machine name or address.</td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [Text](TextProperty.html)
                    </td>
                    <td colspan="1" rowspan="1">
                        Gets or sets a description of the database name.
                    </td>
                </tr>
                <tr>
                    <td colspan="1" rowspan="1" style="height: 23px">
                        <img alt="public property" src="../Images/property.bmp" border="0" />
                        [User](User_Property.html)
                    </td>
                    <td colspan="1" rowspan="1" style="height: 23px">Gets or sets the authenticated user profile that is used to authorize the current database connection.</td>
                </tr>
</table>

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](ecrLrfDatabaseClass.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[DCLDB](DCLDB.html) 
