---
title: DCLDISKFILE

Id: DCLDISKFILE
TocParent: aerLrfOpCodesMain
TocOrder: 410



---

Declares an externally described disk file, or RPG Cycle Program for processing in a program. 

```
DCLDISKFILE 
Name  (file name)
Type  (*INPUT | *OUTPUT | *UPDATE) 
Org (*ARRIVAL | *INDEXED) 
Db  (Database Object) 
File (*NAME  | String Literal) 
Mbr (*FIRST | *FILE | String Literal) 
Addrec (*NO | *YES) 
ImpOpen (*YES | *NO) 
InputHandler (*NONE | String Literal)
Rnmfmt (*NONE | Old Format name, New Format, ...) 
NetBlockFactor (*CALC | *NONE   | Number of Records to Block) 
CacheWrites (*NO | *YES | Indicator Expression) 
ShareType (*FILE | *EXCLUSIVE | *EXCLUSIVEREAD | *SHAREUPDATE | *SHARENOUPDATE | *SHAREREAD |
           Character Expression)
ChkFmtId (*SAME | *IGNORE | *MAP | *YES | *NO | Indicator Expression) 
Prefix (prefix name, [Length]) 
Commit (*NO | *YES | Boolean/Indicator Expression)
OutputHandler (*NONE | String Literal)
QrySelect (*NONE | String Literal) 
QryKeyFlds (*FILE   | *NONE | String Literal) 
QryFileName (*NAME | String Literal) 
WaitRec (*FILE | *IMMEDIATE | *NOMAX) 
Random (*YES | *NO) 
Access (*PRIVATE | *PUBLIC | *PROTECTED | *INTERNAL) 
Shared (*NO | *YES)
Ignore (Format name, ...)
Include (Format name, ...)
ServerCursor (*DFT | *STATIC | *FASTFORWARDONLY)
Designation (*Full Procedural| *Primary | *Secondary | *PrimaryDesc) 
UseKeyBuffer(*NO | *YES)
InfSR (Subroutine Name)
OnInput (Method name)
OnOutput (Method name)
```

### Parameters

**Name** 

Required. Name can contain either:

- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:
- a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

- A name of the form Library.Object, where Library is the name of one of the libraries selected in the new up and coming object libraries dialog, and Object is valid object name within that library.

**Note** : Using the DclDiskFile ** *name* ** , you can then get to its **fields** and **properties** . Please note that methods are reserved for use by the ASNA.Encore RPG compiler, so use the corresponding Encore RPG command if applicable. See [DBFile Class Members](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/database-file.html) for a listing of available members.


**Type** 

Required. Type determines the accesses that will be permitted on the file. *Note that the **Type** parameter determines the **NetBlockFactor** default.* Input and Output files can employ network blocking as long the appropriate keyword is also specified. See **NetBlockFactor** parameter for more information. 

Unless NetBlockFactor is *NONE, network blocking is employed for input and output files as described below. 

- *INPUT - will allow only read operations (i.e. [READ](READ.html), [READP](READP.html), [CHAIN](CHAIN.html)) to be performed on a file). The default for NetBlockFactor is *CALC - The system will calculate an efficient number of records to block.
- *OUTPUT - only allows WRITE operations to the file. The default for NetBlockFactor is *NONE - No blocking will occur on the file.
- *UPDATE - allows read, update and delete operations to a file. The default for NetBlockFactor is *NONE - No blocking will occur on the file.


**Org** 

Optional. Specifies if the file is a Sequential (*ARRIVAL) or Indexed (*INDEXED) file. The default is *ARRIVAL. 

- *ARRIVAL (default) - the file is a sequential file.
- *INDEXED - the file is an indexed file.


**Db** 

Required. Db specifies the Database Object declaration whose DBName specifies where the compiler will acquire the file description. Db specifies the Database Connection to use when opening the file at run-time. Database Objects are defined with the [DCLDB](DCLDB.html) command.


**File** 

Optional. File specifies the Library and File to use when opening the file at run-time. 

If the File parameter is not given, the same file that was used to retrieve the description will be opened at run-time. 

If a file name is given on the **File** parameter, that file will be accessed and must have the same description as the file accessed in the **Name** parameter unless **ChkFmtID** parameter is other than *SAME. The File parameter accepts literal as a parameter. To override the file at run-time, set the FilePath property for the file object in the Name parameter prior to opening the file.


**Mbr** 

Optional. Mbr specifies the file member to use when opening the file at runtime. The **Mbr** parameter allows you to specify the name of the member you want to access or *FIRST. *FIRST is the default. 

- *FIRST (default) - will access the member with the oldest creation date.
- *FILE - accesses the member name with the same name as the file name.

If a member name is given on the **Mbr** parameter, that member will be accessed when the file is opened. The **Mbr** parameter accepts literal as a parameter. To override the Member at run-time, set the Membername property for the file object in the **Name** parameter prior to opening the file.


**Addrec** 

Optional. Addrec specifies whether you want to add a record to the file. The default is *DFT. You must use the Addrec (*YES) option if you wish to add a record to a *INPUT or *UPDATE file. *OUTPUT files automatically allow you to add records, and thus the Addrec parameter is not necessary. 

To utilize **network blocking** , ( **NetBlockFactor** ) which significantly reduces the network burden of transferring records between server and client machines, use Addrec (*NO) with *INPUT files. When an input file is "blocked", the buffered data resides on the client PC. This allows successive READ and READE statements to execute quickly. Be aware that should records be updated in other definitions of the file, those changed are not correspondingly updated in the buffer. For Netblockfactor, either use *CALC (the system will calculate the number of records to block), or enter the maximum number of records to include in the block. 

- *DFT (default) - will look at the file type and add a record to a *INPUT or *UPDATE file.
- *NO - with *INPUT file will enable network blocking, which significantly reduces the network burden of transferring records between server and client machines
- *YES - will add a record to a *INPUT or *UPDATE file.


**ImpOpen** 

Optional. ImpOpen specifies if the file will be implicitly opened. The default is *YES. 

- *YES (default) - specifies that the file will automatically be opened when the program is first run. If the implicit open is unsuccessful, a run-time error will occur.
- *NO - specifies that the file will not automatically be opened when the program is first run. The RPG IV USROPN keyword is supported in Encore RPG by using **ImpOpen** (*NO).


**Rnmfmt** 

Optional. Rnmfmt renames the external formats to new, internal formats to avoid clashes with duplicate format names. *NONE is the default. 

- For **multi** -format files, you enter the external and internal format names in pairs. All names are separated by commas.
- For **single** format files, you can either specify the internal format name as the only format name, or enter both the external and internal format names separated by a comma. 

Rnmfmt ( RCMMaster, CustInfo) // single format 

Rnmfmt ( CustInfo) // single format 

Rnmfmt (RSubCust, CustSub, RSubSales, SalesSub) // multi-format


**NetBlockFactor** 

Optional. NetBlockFactor determines if and optionally how many database records will be blocked across the Network for better performance when reading or writing groups of records. Network blocking significantly reduces the network burden of transferring records between server and client machines, and this is demonstrated by the substantial increase of data throughput. 

Network blocking is turned on by default for files declared with **Type** (*INPUT) and off by default for files declared with **Type** (*OUTPUT) and **Type** (*UPDATE). Blocking behaviors for INPUT and OUTPUT files are described below. Network blocking is not allowed on files open for UPDATE. 

**INPUT** - The file is declared with **Type** (*INPUT) and **AddRec** (*NO). When an input file is "blocked", the buffered data resides on the client PC. This allows successive **READ** and **READE** statements to execute quickly. Be aware that should records be updated in other definitions of the file, those changed are not correspondingly updated in the buffer. 

**OUTPUT** - The disk file is declared with **Type** (*OUTPUT). When an output file is "blocked", the buffered data resides on the client PC until the block has been filled or the file is closed. Then the block is sent to the server in a single transaction. Be aware that I/O errors at the server are returned only during processing of the block. In other words, if the 33rd record in a block of 100 records had a duplicate key, your application would not be aware of it until **after** writing the 100th record. Therefore, the use of network blocking for output files should be employed only when your application can be restarted. 

I/O operations that will reset the buffer are **SETLL** , **SETGT** , **SETRANGE** , **CHAIN** (READRAND) and **READRANGE** . Using *CALC, the system will calculate the number of records to block. The blocking factor is 6000 divided by the file's record length. If the record length is greater than 3000 (1/2 the block size), 

- *CALC (default) - will compute a record blocking Factor of 1 (one).
- *NONE - no blocking will occur on the file. This is the default when the Type is other than *INPUT.
- Record Count - the maximum number of records to include in the block. **Note** , the number of records in the block for **SETRANGE** with **READ** operations, and for **READRANGE** operations will be less than the record count if the set of records in the range is smaller than the maximum block size. Because of this dynamic blocking, the use of **SETRANGE** and **READRANGE** can realize even better performance than **SETLL** and **READE** , for example.

**Note** Record blocking requires **additional memory** to work. Blocking reserves memory for the complete block of each blocked file. For example, a record length of 2560 and a blocking factor of 100 will require an additional 256K of memory.


**CacheWrites** 

Optional. CacheWrites specifies whether data is written to disk immediately after an operation, or whether data is saved in a buffer, then written to disk when the Operating System has time. *NO is the default. 

- *NO (default) - indicates that data will be written to disk at the time the operation is performed. Note that this option is slower than saving the data to a buffer.
- *YES - indicates that data operations will be saved to a buffer, and written to disk when the Operating System has time. Note that this option is faster. However, if the system fails with data in the buffer that has not been written to disk, the information will be lost.


**ShareType** 

Optional. ShareType defines values on how a file will be shared. The default is *FILE. 

- *File (default) - maintains the same share type specified when the file was created.
- *Exclusive - open for update, exclusive lock.
- *ExclusiveRead - open for update, other jobs may read.
- *ShareUpdate - open for update, other jobs may read or update.
- *ShareNoUpdate - open for read, other jobs may read.
- *ShareRead - open for read, other jobs may read or update.


**ChkFmtId** 

Optional. ChkFmtId checks if the format ID of the file at run-time compares to the format ID of the file at compile-time. Encore RPG stores the format of file(s) when a program is first compiled. At run-time, Encore RPG compares the format ID that was stored during the compilation with the current format ID. The comparing of format ID's can be especially useful when checking if new fields have been added to a file used by a program that has been compiled months ago. 

- ***SAME** (default) -indicates that the run-time and compile-time format ID's **will be compared** to verify that they are the same. *(This is exactly the same as * **YES** in previous releases).*
- ***IGNORE -** ndicates that the run-time and compile-time format ID's **will not be compared** to verify that they are the same. Encore RPG will use the compile-time format ID. *(This is exactly the same as ***NO** in previous releases).*

**Note:** Please be extremely careful in using *IGNORE, as it has the risk of the corruption of data files and misbehavior of your application!! 

- ***MAP** - indicates that the run-time and compile-time format ID's will be compared, and Encore RPG will accommodate non-key fields added and changed **regardless** of where they are defined in the new record format. When the modified file is opened, Encore RPG will rebuild, or **map** its compiled record format at run-time to equal that of the new record format.
- ***YES** - See * **SAME** above.
- ***NO -** See * **IGNORE** above.

Any change in the count, order or type of Key fields is not allowed, except that a numeric key may be changed from packed to zoned and vice versa, as long as the precision remains unchanged.


**Prefix** 

Optional. Prefix allows the specification of a string which is to be prefixed to the field names of an externally described record format. The characters specified as (prefix name) are prefixed of all fields defined in all record formats of the file. 

You can also optionally specify a numeric value (length) to indicate the number of leading characters in the existing name to be replaced. If a length is not specified or is zero, the string is prepended to the name. 

- The total Length of a name after applying the prefix must not exceed the maximum length of an RPG field name.
- If a Length is specified, it must be a numeric constant containing a value between 0 and 13 with no decimal places. Specifying a value of zero is the same as not specifying a length at all.
- The Length parameter must not be greater than or equal to number of characters in the name to be prefixed. That is, the resulting name cannot be the same as the prefix string after the prefix is applied.


**Commit** 

Optional. Commit allows you to control if commitment control will be enabled for this file. You can also change at runtime by specifying a Boolean/Indicator expression. The default is *NO. 

The parameter must be set prior to opening the file. If the file is opened explicitly using the OPEN operation in the calculation specifications, the parameter can be set prior to the OPEN operation. 

Use the [COMMIT](COMIT.html) and [ROLLBACK](ROLBACK.html) operation codes to group changes to this file and other files currently under commitment control, so that all changes happen together, or do not happen at all. 

- *NO (default) - indicates that commitment control is not enabled.
- *YES - indicates that commitment control has been enabled.
- Boolean/Indicator Expression - allows commitment control to be specified or changed at runtime.


**QrySelect** 

Optional. QrySelect specifies the selection expression used to determine which records are to be made available for processing. The select expression syntax is the same as for a **Select/Omit** expression in DataGate. 

**QryKeyFlds** can be used in conjunction with **QrySelect** parameters to specify ordering of the selected records. Use **QryFileName** to specify the name of the temporary query file created. 

When using QrySelect, please **note** : 

- *NONE (default) - there is no selection expression available for processing.
- The parameter must be string literal (use DBFile. **QrySelect** property to set as a character expression at runtime).
- If there are any errors in the character expression, they will not be caught until the file is opened at run-time.

Selection expressions are evaluated during file open time. Therefore, a runtime error will be generated during the opening of the file when a selection expression error is encountered.


**QryKeyFlds** 

Optional. The **QryKeyFlds** parameter is used to specify the name of one or more key fields used to arrange the query records. Each key field is composed of a field name followed by optional attributes that determine the sorting order (ascending descending, or absolute value for numeric fields). 

- *FILE (default) - specifies that the original keys in the file should be used.
- *NONE - specifies that the file has no keys.
- String Literal - contains a string containing key field name(s) and corresponding sort attributes. (Use DBFile. **QryKeyFlds** property to set as a character expression at runtime).

To establish the query key fields at runtime, set the QryKeyFlds property for the file object in the Name parameter prior to opening the file. 

When specifying QryKeyFlds with key fields that do not match the original file's key definition, you must also specify **Random** (*NO). See [DBFILE.QryKeyFlds](QryKeyFldsFieldDBFileClass.html) for more information.


In addition, in order to process the file in the sequence specified by the **QryKeyFlds** parameter, you must specify **Org** (* **INDEXED** ). 

Valid input operations for **Random** (*NO) files are limited to: **READ** , **READP** and **SETLL** when used with the new special values * **START** and * **END** . 

**Syntax** : The syntax for the QryKeyFlds parameter is: <br /> (KeyFieldName Attributes ) 

- Key Field Name must be a valid field name in the file.
- Attributes consist of the following: * **ASCEND** , * **DESCEND** , or * **ABSVAL** . You can have as many attributes as you want after a field name as long as they conform to the rules below.
- ... Indicates that you can repeat the sequence for as many key fields as you want.

**When using QryKeyFlds, please note** : 

- Each key field name and attribute must be separated by at least one blank.
- *ASCEND and *DESCEND cannot be applied to the same field.
- *ABSVAL only applies to numeric fields.
- The parameter can be a character literal.
- If there are any errors in the key fields' expression, they will not be caught until the file is opened at run-time.

To establish the query selection at runtime, set the QrySelect property for the file object in the Name parameter prior to opening the file. 

Use QrySelect in conjunction with QryKeyFlds to specify the selection criteria indicating which records to select from a file. Use QryFileName to specify the name of the temporary query file created. Selection expressions are evaluated during file open time. Therefore, a runtime error will be generated during the opening of the file when a selection expression error is encountered. Example: QryKeyFlds ("CustNo *ASCEND ORDERDATE *DESCEND LINENO TOTAL *ABSVAL *DESCEND") For more information on QryKeyFlds examples and using open query files in Encore RPG, refer to the following link: Using Open Query File in Encore RPG.


**QryFileName** 

Optional. QryFileName specifies the name of the query file created for the **QrySelect** and **QryKeyFlds** parameters. If *Name is specified, which is the default, the file name given on the DCLDISKFILE command is used. 

If the database access with this file is an AS/400 database, then the QryFileName is used both on the OVRDBF and the OPNQRYF commands used when opening the file. 

For DataGate databases, a temporary logical file is created in QTemp with the QryFileName as its name. You can use the special name "*UNIQUE" (don't forget the quotes) to guarantee that there will be no conflicts with other files residing in QTemp. You will receive errors if there are duplicate file names in QTEMP. 

It is recommended the use of QryFileName("*UNIQUE") when working with Web Applications. Web Applications run under one user, the user that is specified in DataGate Work with Database Names dialogue. Web Applications usually store Runtime Errors and MsgBoxes in $$Encore RPGErr.TXT. 

- *Name (default) - the file name given on the DCLDISKFILE's **Name** parameter is used.

To establish the query file name at runtime, set the QryFileName property for the file object in the Name parameter prior to opening the file. 

For more information on QryKeyFlds and using open query files in Encore RPG, refer to the following link: Using Open Query File.


**WaitRec** 

Optional. WaitRec specifies the waiting period for a record. *FILE is the default. 

- *FILE (default) - indicates that the properties of the file are used to determine how long it waits for the record.
- *IMMEDIATE - it won't wait for a record.
- *NOMAX - it will wait indefinitely.


**Random** 

Optional. Random specifies whether random database processing using Keys and RRNs is allowed. *YES is the default, which determines the random database processing using keys and RRNs is allowed. 

- *YES (default) - specifies that random database processing using Keys and RRNs on op codes such as SETLL, CHAIN, etc., is allowed.
- *NO - specifies that random database processing using Keys and RRNs is not allowed. This option is commonly used when the Keys look different at runtime from the compile time. The common scenario is when using **QryKeyFlds** and under this scenario *NO option must be used to avoid a runtime exception.

**The only I/O operations allowed are:** 

- Input - READ, READP and SETLL with *START or *END as the Keys. Any other operations throw compiler error - "Random Access Operation Not Allowed For File". The results of READ and READP depend on the **Org** option and if *INDEXED read them sequentially based on the Key of the file and *ARRIVAL reads in arrival sequence in the file.
- Output - Write and Update.


**Access** 

Optional. The type of access to the member. *PRIVATE is the default. 

- *PRIVATE (default) - access to the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the member is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member is accessible from within the same project, but not from outside the project.


**Shared** 

Optional. Shared specifies whether or not this file is to be shared. *NO is the default.

- *NO (default) - this file will not be shared.
- *YES - this file will be shared.


**ServerCursor** 

Optional. (For SQL Server files only). ServerCursor allows you to gain access to a table or view that isn't supported by Dynamic cursors. *Dft is the default, which relates to Dynamic cursors. Please refer to your SQL Server documentation for information on Dynamic vs. Static cursors.


- *DFT (default) - Attempts to use a Dynamic server cursor. If the ```QryKeFlds``` parameter provides a key sequence, the server will be made static.
- *STATIC - defines the server cursor as Static.
- *FASTFORWARDONLY (previously *FORWARDONLY) - Specifies that the reading of records in this file will be done only via forward reads (READ and not READP); using this kind of cursor optimizes reading performance performance. It is only valid for files opened for *Input only.

Opening a file for Update or Output requires the server cursor to be ```Dynamic```.

For newly compiled files with this feature, running against an older version of SQL server, and for any files running against any other server (non-SQL) all values of ```ServerCursor``` are basically ignored.



**Ignore** 

Optional. The Ignore keyword allows a record format from an externally-described file to be ignored by the compiler. The external name of the record format to be ignored is specified as the parameter record format. One or more record formats can be specified, separated by commas (,) or colons (:).


Notes:


- When the program runs, the specified record format(s) will still exist in your application. All record formats contained in the file are included.
- When the Ignore keyword is specified for a file, the **Include** keyword cannot be specified.


**Include** 

Optional. The Include keyword specifies those record format names that are to be included by the compiler; all other record formats contained in the file will be ignored at compile time. For WORKSTN files, the record formats specified using the SFILE keyword are also included in the program, they need not be specified twice. Multiple record formats can be specified, separated by commas (,) or colons (:).


Notes:


- When the program runs, the record format(s) not specified will still exist in your application. All record formats contained in the file are included.
- When the Include keyword is specified for a file, the **Ignore** keyword cannot be specified.


**Designation** 

Optional. The type of file to be access in the RPG Cycle. * **Full Procedural** is the default, which indicates that initial file declared will be used.


- *Full Procedural - (Default) The default file declared when not using the RPG cycle will be used.
- *Primary - The file is designated as the Primary, or main file in the cycle.
- *Secondary - The file is designated as the Secondary file in the cycle.
- *Primary Desc - The description of the Primary file will be designated.


**InputHandler** 

Optional. A handler generated by Monarch in the event that a Program Described File cannot be simply migrated.


- *NONE - (Default) This Keyword is unused.
- String Literal - The name of the generated handler.


**OutputHandler** 

Optional. A handler generated by Monarch in the event that a Program Described File cannot be simply migrated.


- *NONE - (Default) This Keyword is unused.
- String Literal - The name of the generated handler.


**OnInput** 

Optional. This sets a method to be called during an input operation (Read, Chain, etc) after data is read but before the file buffer (the AdgDataSet) is copied into the program fields.


- *NONE - (Default) This Keyword is unused.
- Method - Method to be called.


**OnOutput** 

Optional. Sets a method to be called during an output operation (Write, Update, etc) right after the program fields have been copied to the file buffer but before the file buffer data is written into the file.


- *NONE - (Default) This Keyword is unused.
- Method - Method to be called.


[**UseKeyBuffer**](DCLDISKFILEUseKeyBuffer.html)

Optional. ```UseKeyBuffer``` specifies whether any keyed operation on the file (e.g. ```CHAIN```) will consider its key parameter to be a key buffer, i.e. it will be considered as containing pieces of the key up to its length. ```*NO``` is the default. 

- ```*NO``` (default) - indicates that the key parameter will not be considered a key buffer.
- ```*YES``` - indicates that any keyed operation on the file (e.g. ```CHAIN```) will consider its key parameter to be a key buffer. See the


**InfSR** 

Optional. A subroutine that is called when a file error occurs in a file operation that is NOT using an error indicator. 

- For more detail see the related Concepts page: [Using the InfSR Keyword](/concepts/print/InfSRKeyword.html)


### Remarks
Since **ASNA.DataGate.Client** is a managed object, you should never refer to a **dclDiskfile** object in **Finalize** . 

The use of the OnInput and OnOutput keywords allows the manipulation of data directly into the file buffer on its way between the file and the program fields. Use of these keywords should be limited to those cases in Monarch migrated code where the record format doesn’t match the program fields (e.g. fields that must be merged in the program and split on the way back to the DB). 
<br />

**Example** <br /> 

```

 dclDB Name ( DBLocal ) DBName ( "DG Net Local" )
 dclDB Name ( ProdDB  ) DBName ( "DG Net iSeries" )
 dclDB Name ( DBSQL   ) DBName ( "DG SQL Server" )
<br /> // Sequential file for output, but do not open it until an OPEN operation is used.
// File description is "*LIBL/SKUMAST" dclDiskFile Name (SKUMAST) Type (*output) Org (*arrival) DB (DBLocal) ImpOpen (*NO)
<br /> // Indexed file for input, and rename format to CUST1.
// File description is "*LIBL/CSMASTERL1" dclDiskFile Name (SalesMast) Type (*input) Org (*indexed) DB (DBSQL) +
 File ( "*LIBL/CSMASTERL1" ) RnmFmt (CUST1)<br /> // Indexed file for input and block 100 records. File description is "TestLib/CMASTNEWL1"
 dclDiskFile Name (CustFile) Type (*input) Org (*indexed) DB (DB400) +
 NetBlockFactor (100) Impopen (*NO) File ( "TestLib/CMASTNEWL1" )
```

### See Also
[CLOSE](CLOSE.html)

[COMMIT](COMIT.html)

[DCLDS](DCLDS.html)

[DCLDSFLD](DCLDSFLD.html)

[DCLFLD](DCLFLD.html)

[DCLPRINTFILE](DCLPRINTFILE.html)

[LOOKUP](LOOKUP.html)

[OPEN](OPEN.html)

[ROLLBACK](ROLBACK.html)

[DBFile Class Members](ecrLrfDBFileMembers.html)

[DBFile Class](ecrLrfDBFileClass.html) 
