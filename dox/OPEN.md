---
title: OPEN

Id: OPEN
TocParent: aerLrfOpCodesMain
TocOrder: 1280


---

Opens the file named in **File** for processing.

```
OPEN 
File (Name of file)
FilePath (<u>*FILENAME</u> | Character Variable)
Mbr (<u>*FIRST</u> | *FILE | Character Variable)
Db (Database Object)
Err (*EXTENDED | Indicator Variable)
```

### Parts

**File** 

Required. Cannot be designated as a primary, secondary, or table file.


**FilePath** 

Optional. Contains the path to the **File** .


**Mbr** 

Optional. Specifies the file member to use when opening the file at runtime. The **Mbr** parameter allows you to specify the name of the member you want to access or *FIRST. *FIRST is the default. 

The following rules apply:

- *FIRST (default) - will access the member with the oldest creation date.
- *FILE - accesses the member name with the same name as the file name.


**Db** 

Optional. Specifies the Database Connection to use when opening the file at run-time.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Open the file specified in **File** for the first time in a program with an explicit OPEN operation. If a file is opened and later closed by the [CLOSE](CLOSE.html) operation in the program, you can reopen the file with the **OPEN** operation. Multiple **open** operations in a program to the same file are valid as long as the **File** is closed when the **OPEN** operation is issued. 

### Example

```
DCLDISKFILE ItemDetail *INPUT ORG(*INDEXED) ADDREC(*NO) Impopen(*NO)
DCLDISKFILE ItemOut *OutPut       

// The explicit **OPEN**  operation opens the ItemDetail file for processing if indicator 97 is on and 
   indicator 98 is off. Note that the ItemDetail file on the file description 
   specifications has the Impopen keyword specified. Indicator 99 will be set on if the **OPEN**  operation fails.

     If *In97 = *On *And *In98 = *Off
     Open ItemDetail Err (*In99)
       If *In99 = *On
       Write ErrorRecord
       Endif
     Endif
      
```

### See Also
[CLOSE](CLOSE.html)

[DCLDB](DCLDB.html)

[DCLDISKFILE](DCLDISKFILE.html)

[DCLMEMORYFILE](DATE_Function.html)

[DCLPRINTFILE](DCLPRINTFILE.html) 
