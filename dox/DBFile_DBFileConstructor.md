---
title: DBFile.DBFile (string, string, string, int, string, boolean, int, string, string, string)

Id: DBFile_DBFileConstructor
TocParent: aerLrfDBFileConstructors
TocOrder: 10

---

**DBFile** initializes a new instance of a [DBFile](aerLrfDBFileClass.html) object. 

```

 **DBFile ( dclDiskFileName, filePath, memberName, blockingFactor, shareType,
	    isFormatID, waitRec, qrySelect, qryKeyFlds, qryFileName )** 
        
```

### Parameters

***dclDiskFileName*** 

String. This parameter can contain either:

- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent: 
<ul>
                            <li>

a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

</li>
                    <li>

A name of the form **Library.Object** , where Library is the name of one of the libraries selected in the new object libraries dialog, and Object is valid object name within that library. 
</li>
                </ul>


***filePath*** 

String. Specifies the Library and File to use when opening the file at run-time. If ***FilePath*** is not set, the Library and File of the **File** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. In addition, the file path can be established by setting the [FilePath](FilePathFieldDBFileClass.html) field of the file object prior to opening the file.


***memberName*** 

String. ***memberName*** specifies the file member to use when opening the file at runtime. This parameter allows you to specify the name of the member you want to access, literals are accepted, or *FIRST. *FIRST is the default. 

- *FIRST (default) - will access the member with the oldest creation date.
- *FILE - accesses the member name with the same name as the file name.


***blockingFactor*** 

Integer. ***blockingFactor*** determines if and how many database records will be blocked across the Network for better performance when reading groups of records. Blocking significantly reduces the network burden of transferring records between server and client machines, and this is demonstrated by the substantial increase of data throughput due to the reduced number of TCP/IP packet requests. 

The database file must be declared in the **DCLDISKFILE** command as **Type** ( *Input ) and **AddRec** ( *NO ) before network blocking can used. 

The blocking factor is expressed as the maximum number of records to blocked. Valid values are: 

-1 .......... The blocking factor will be computed automatically (6K/record length). 

0 or 1 ..... One record at a time will be transported across the network. 

nnn ........ nnn records at a time will be blocked.


***shareType*** 

String. Defines values on how a file will be shared. The default is *FILE.

- *File (default) - maintains the same share type specified when the file was created.
- *Exclusive - open for update, exclusive lock.
- *ExclusiveRead - open for update, other jobs may read.
- *ShareUpdate - open for update, other jobs may read or update.
- *ShareNoUpdate - open for read, other jobs may read.
- *ShareRead - open for read, other jobs may read or update.


***isFormatID*** 

Boolean. Set **True** if the format ID of the file at run-time is to be compared to the format ID of the file at compile-time.


***waitRec*** 

Integer. ***waitRec*** specifies the waiting period for a record. If ** *waitRec* ** is not set, the value of the **WaitRec** parameter specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. You can also establish the [WaitRec](WaitRecFieldDBFileClass.html) field of the file object prior to opening the file. 

- *FILE - indicates that the properties of the file are used to determine how long it waits for the record.
- *IMMEDIATE - it won't wait for a record.
- *NOMAX - it will wait indefinitely.


***qrySelect*** 

String. The selection expression used to determine which records are to be made available for processing when the open query file is created. The select expression syntax is the same as for a **Select/Omit** expression in DataGate. Use ***qrySelect*** in conjunction with ***qryKeyFlds*** to specify the selection criteria indicating which records to select from a file. 

When using ***qrySelect*** , please Note

- *NONE (default) - there is no selection.
- The parameter must be a string literal.
- If there are any errors in the expression, they will not be caught until the file is opened at run-time.


***qryKeyFlds*** 

String. The list of key fields to be used to arrange the query records when the open query file is created at run-time. Specify: 

- *FILE - is the default, which specifies that the value of the **QryKeyFlds** 
                        parameter specified in the **DCLDISKFILE** 
                        command is used. (See Remarks also).
- *NONE - specifies that the file has no keys.
- A string containing keyfieldname(s) and corresponding sort attributes. The
                        syntax for this string is:<br /><br />
                        ( KeyFieldName **1**  Attributes  KeyFieldName **2** 
                        Attributes … KeyFieldName **n**  Attributes )

KeyFieldName must be a valid field name in the file. Attributes consist of the following: *ASCEND, *DESCEND, or *ABSVAL. You can have as many attributes as you want after a field name as long as they conform to the rules below. 

1. Each KeyFieldName and attribute must be separated by at least one blank.
2. *ASCEND and *DESCEND cannot be applied to the same field.
3. *ABSVAL only applies to numeric fields.


***qryFileName*** 

String. The name of the temporary query file created in QTEMP for the ** *qrySelect* ** and ** *qryKeyFlds* ** parameters. If *Name is specified, which is the default, the **QryFileName** given on the **DCLDISKFILE** command is used. You can use the special name "*UNIQUE" (don't forget the quotes) to guarantee that there will be no conflicts with other files residing in QTEMP. You will receive errors if there are duplicate file names. 

If the database access with this file is an AS/400 database, then the ***qryFileName*** is used both on the OVRDBF and the OPNQRYF commands used when opening the file.


### Remarks
When a file is blocked, the block is delivered when the database engine receives the first read request. This means the client will wait to receive the block before competing the processing of the request. The subsequent read requests will retrieve the records from the cached block help by the client. When the cache is empty, the next block is retrieved when the database engine receives the next read request. To establish the blocking factor at runtime, set the BlockingFactor field for the file object prior to opening the file. 

The Encore RPG compiler stores the format ID of each file in the assembly when a program is compiled. At run-time, ***isFormatID*** **True** specifies ECR is to compare the stored format ID with the format ID of the currently-opened file. The comparing of format IDs can be especially useful when checking if new fields have been added to a file used by a program that has been compiled months ago. To establish this parameter at runtime, set the [IsFormatID](IsFormatIDFieldDBFileClass.html) field for the file object prior to opening the file. 

Use ***qryFileName*** to specify the name of the temporary query file created. It is recommended the use of ***qryFileName*** ("*UNIQUE") when working with Web Applications. Web Applications run under one user, the user that is specified in DataGate Work with Database Names dialogue. Web Applications usually store Runtime Errors and MsgBoxes in $$Encore RPGErr.TXT. To establish the query file name at runtime, set the [QryFileName](QryFileNameFieldDBFileClass.html) field for the file object prior to opening the file. 

Selection expressions for ***qryKeyFlds*** are evaluated during file open time. Therefore, a runtime error will be generated during the opening of the file when a selection expression error is encountered. To establish the query key fields at runtime, set the [QryKeyFlds](QryKeyFldsFieldDBFileClass.html) fields for the file object prior to opening the file. 

In addition, the member name, file path, and share type parameters can also be established at runtime by setting the [MemberName](MemberNameFieldDBFileClass.html), [FilePath](FilePathFieldDBFileClass.html), and [ShareType](ShareTypeFieldDBFileClass.html) fields respectively, prior to opening the file. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Window Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DBFile Class](aerLrfDBFileClass.html)
[DBFile Members](aerLrfDBFileMembers.html)
[DBFile Fields](aerLrfDbFileFieldsMain.html)
[DCLDISKFILE](DCLDISKFILE.html) 
