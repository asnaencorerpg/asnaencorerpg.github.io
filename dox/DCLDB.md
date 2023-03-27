---
title: DCLDB

Id: DCLDB
TocParent: aerLrfOpCodesMain
TocOrder: 390


---

Declares a database. The **Name** parameter can then be used on [DCLDISKFILE](DCLDISKFILE.html)'s **Db** parameter and [DCLMEMORYFILE](DCLMEMORYFILE.html)'s DbDesc parameter. 

```

 **DCLDB
Name** (Database name in code)
DbName (Actual Database name)
Access (<u>*PRIVATE</u> | *PUBLIC | *PROTECTED | *INTERNAL)
Shared (<u>*NO</u> | *YES)
VTerm (<u>*NONE</u> | *MONARCHWEB)
OpenAccessDspF (<u>*NONE</u> | *WINGS| *MOBILERPG)
```

### Parts

**Name** 

Required. A character expression containing the name to call your database in code.


For a listing of the **Database Class members** , [click here](aerLrfDatabaseMembers.html).


**DbName** 

Optional. A character expression containing the name of the actual database.


**Access** 

Optional. The type of access to the member. *PRIVATE is the default.

- *PRIVATE (default) - access to the database is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the database is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the database is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the database is accessible from within the same project, but not from outside the project.


**Shared** 

Optional. Shared specifies whether or not this database connection object is to be shared. *NO is the default, which is the recommended option. 

- *NO (default) - this database connection object will not be shared (recommended).
- *YES - this database connection object will be shared (not recommended). <br /> Since a shared database connection is not thread safe, defining the connections as a shared member implies that the program will have to ensure that only one thread utilizes the connection at a time. Since the connection is used any time there is file I/O activity on files opened with this connection, or when programs are called using this connection, maintaining ‘only one thread’ can become challenging for the program. The program can employ a Semaphore, AutoResetEvent or a Monitor (from System.Threading) to coordinate access to the object utilizing the shared database connection. Since ASP.NET operates on a multithreaded engine, using shared connections in a web application or web service is strongly discouraged.


**VTerm** 

Optional. VTerm specifies the kind of 5250 virtual terminal emulation this database connection will support. *NONE is the default. 

- *NONE (default) - this database connection object will not handle virtual terminals.
- *MONARCHWEB - this database connection object will support the Monarch Web 5250 emulation on a browser. The application must be running in a Monarch Web environment for this virtual terminal to work. The Monarch web environment is **only** supported in Monarch and Wings applications.


**OpenAccessDspF** 

Optional. OpenAccessDspF specifies the kind of Open Access RPG support for Display Files that the database connection will provide. *NONE is the default. 

- *NONE (default) - this database connection object will not handle Open Access RPG Display Files.
- *WINGS - this database connection object will service Open Access RPG Display File requests via the Wings service. This support is currently available only in Wings applications.
- *MOBILERPG - this database connection object will service Open Access RPG Display File requests via the MobileRPG service. This support is currently available only in MobileRPG applications.


### Remarks
You must specify the **Name** parameter, which is the name to call your database in code. 

The **DbName** parameter is optional and is the name of the actual database you are declaring. 

Use [CONNECT](CONNECT.html) to create a connection to a database, and [DISCONNECT](DISCONNECT.html) to close a database connection. 

To "load" the contents of the registry for a particular database name, set the **DbName** property of the database object declared with DCLDB. If a database name exists with the name, values such as server, label, and user, etc., become current and available through properties of the object. 

You can use the [CreateName](CreateName_Method.html) method to take all the current values of the database name, except for the name itself, and creates a new "Database Name" in the registry with the name given in <span class="SpellE">NewName</span>. 

You can use the [UpdateName](UpdateName_Method.html) method to write the current values of the database name object as the new values of the database name in the registry. 

There are **two methods** which are Shared. These methods don't affect the current values of the database object. 

- <div>
                    [GetNames Method](GetNames_Method.html) (*Boolean Public Databases)
                    - Returns an array of string with all the names found in the registry. The
                    boolean parameter indicates whether to get PublicDatabase ( **True** ) or
                    those private to the current user ( **False** ).
- <div>
                    [DeleteName Method](DeleteName_Method.html) (*String ExistingName) -
                    This method deletes from the registry an existing database Name.

Because ASNA.DataGate.Client is a managed object, you should never refer to a **dclDB** object in **Finalize** . 

Be careful when setting the Shared parameter to *Yes; thus sharing a single connection to the database. Since a shared database connection is not thread safe, defining the connections as a shared member implies that the program will have to ensure that only one thread utilizes the connection at a time. Since the connection is used any time there is file I/O activity on files opened with this connection, or when programs are called using this connection, maintaining ‘only one thread’ can become challenging for the program. The program can employ a Semaphore, AutoResetEvent or a Monitor (from System.Threading) to coordinate access to the object utilizing the shared database connection. Since ASP.NET operates on a multithreaded engine, using shared connections in a web application or web service is particularly challenging. 

### See Also
[CONNECT](CONNECT.html)

[CreateName Method](CreateName_Method.html)

[DbName Property](DBName_Property.html)

[DeleteName Method](DeleteName_Method.html)

[DISCONNECT](DISCONNECT.html)

[UpdateName Method](UpdateName_Method.html)

[GetNames Method](GetNames_Method.html)

[Database Class](aerLrfDatabaseClass.html)

[Database Class Members](aerLrfDatabaseMembers.html) 
