---
title: PrintFile.PrintFile (string, string, string, boolean)

Id: PrintFile_PrintFileConstructor
TocParent: aerLrfPrintFileConstructors
TocOrder: 200

---

**PrintFile** initializes a new instance of a [PrintFile](aerLrfPrintFileClass.html) object. 

```

 **PrintFile ( dclPrintFileName, filePath, shareType, isFormatID )** 
        
```

### Parameters

***dclPrintFileName*** 

Required string. *dclPrintFileName* can contain either:

- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:
- A valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

- A name of the form **Library.Object** , where Library is the name of one of the libraries selected in the new object libraries dialog, and Object is valid object name within that library.


*filePath* 

String. Specifies the Library and File to use when opening the file at
                run-time. If *FilePath*  is not set, the Library and File of
                the *File*  parameter specified in the **DCLPRINTFILE**  command
                is used.


*shareType* 

String. Defines values on how a file will be shared. The default is *FILE.

- *File (default) - maintains the same share type specified when the file was created.
- *Exclusive - open for update, exclusive lock.
- *ExclusiveRead - open for update, other jobs may read.
- *ShareUpdate - open for update, other jobs may read or update.
- *ShareNoUpdate - Open for read, other jobs may read.
- *ShareRead - Open for read, other jobs may read or update.


*isFormatID* 

Boolean. Set **True**  if the format ID of the file at
                run-time is to be compared to the format ID of the file at compile-time.


### Remarks
The Encore RPG compiler stores the format ID of each file in the assembly when a program is compiled. At run-time, *isFormatID* **True** specifies ECR is to compare the stored format ID with the format ID of the currently-opened file. The comparing of format ID's can be especially useful when checking if new fields have been added to a file used by a program that has been compiled months ago. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[PrintFile Class](aerLrfPrintFileClass.html)
[PrintFile Members](aerLrfPrintFileMembers.html)
[DCLPRINTFILE](DCLPRINTFILE.html) 
