---
title: CHAIN

Id: CHAIN
TocParent: aerLrfOpCodesMain
TocOrder: 260


---

Retrieves a record from a full procedural file, and places the data into the input fields. 

Please note that if you want to process a " **Range** " of records, you could use the [READRANGE](READRANGE.html) op code. This op code is especially useful in increasing performance and speed when you are working with large files. Also, if you will be accessing SQL files, you will definitely want to use **READRANGE** . The **READRANGE** op code still only reads 1 record like chain, but remembers the last position. **READRANGE** replaces **CHAIN-** [READE](READE.html) loops. 

```
 CHAIN
From  (File Name | Format Name)
 Key  (KeyList Name | Character Expression)
Access (<u>*DFT</u>  |*NOLOCK | *CHECKONLY)
NotFnd (Indicator Variable) 
Err (Indicator Variable | *EXTENDED) 
```

### Parameters

**From** 

Required. **From** specifies the file or record format name that is to be read. A record format name is valid with an externally described file. If **From** is a record format name and access is by key, **CHAIN** retrieves the first record of the specified record type whose key matches the search argument. If no record is found, a No record Found condition exists, and the Not Found indicator is set On. 

If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you must use the format name.


**Key** 

Required. **Key** must contain the key or relative record number used to retrieve the record. If access is by key, **Key** can be any valid character expression. In addition, a [DCLKLIST](DCLKLIST.html) Name can be specified in **Key** for an externally described file. If access is by relative record number, **Key** must contain an integer literal or a numeric field with zero decimal positions. **** Refer to [%KDS](KDS_Function.html) to use this built-in function to establish search arguments (Key) for Data Structures.


**Access** 

Optional. **Access** determines if records are locked.

- *DFT – (Default) If the parameter is not given, the **default** record locking behavior is taken. This means, if File is specified as INPUT, all records are read without locks. If File is specified as UPDATE, all records are locked if blank.
- *NOLOCK – If this option is specified, then in **no** case will the record be locked when the **READRAND** operation is successful. The file specified in From is positioned so a subsequent read operation retrieves the next sequential record following the retrieved record. If the **CHAIN** is not completed successfully, the file specified in From must be repositioned before a subsequent read operation can be done to that file.
- *CHECKONLY - If this option is selected the Chain command will only set the **NotFound** indicator depending on whether the record exists, without copying the record values into the program fields. The **EOF** flag for the file is set to **false** . If there is an error in the operation the indicator specified in the **Err** keyword will be set.


**NotFnd** 

Optional. Used to determine if the record was found while executing this command.


Note that you can also use the [%FOUND](FOUND_Function.html) function. However, be aware that %FOUND and the NotFnd indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. **Err** determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Example
/* The **CHAIN** operation retrieves the first record from the file CustMaster, that has a key field with the same value as the search argument CustNumber. Indicator 60 will come on (File record not found). */ 

```
CHAIN  CustMaster CustNumber NotFnd(*In60)
If *In60 = *ON
    Subfile1AgentName = *Blanks
 Else
  Subfile1AgentName = CustName
Endif
```

### See Also
[READ](READ.html)

[READP](READP.html)

[READRAND](READRAND.html)

[READRANGE](READRANGE.html)

[%KDS](KDS_Function.html) 
