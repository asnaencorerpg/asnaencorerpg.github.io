---
title: READRAND

Id: READRAND
TocParent: aerLrfOpCodesMain
TocOrder: 1370


---

Retrieves a record from a full procedural file, and places the data into the input fields. 

```
READRAND
From  (File Name | Format Name)
Key (KeyList Name | (Character Expression)
Access (*<u>DFT</u> | *NOLOCK)     
NotFnd (Indicator Variable) 
Err (*EXTENDED | Indicator Variable)
IntoDS (Data structure)  
```

### Parameters

**From** 

Required. Specifies the file or record format name that is to be read. A record format name is valid with an externally described file. If **From** is a record format name and access is by key, **READRAND** retrieves the first record of the specified record type whose key matches the search argument. If no record is found, a No record Found condition exists, and the Not Found indicator is set On. 

If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you must use the format name.


**Key** 

Optional. Must contain the key or relative record number used to retrieve the record. If access is by key, **From** can be any valid character expression. In addition, a [DCLKLIST](DCLKLIST.html) Name can be specified in Key for an externally described file. If access is by relative record number, **Key** must contain an integer literal or a numeric field with zero decimal positions. 

If the **Access** parameter is not given, the default record locking behavior is taken. This means, if **File** is specified as INPUT, all records are read without locks and the extender must be blank. If **File** is specified as UPDATE, all records are locked if blank.


**Access** 

Optional. Determines if records are locked.

- *DFT – (Default) If the parameter is not given, the default record locking behavior is taken. This means, if File is specified as INPUT, all records are read without locks and the extender must be blank. If File is specified as UPDATE, all records are locked if blank.
- *NOLOCK – If this option is specified, then in no case will the record be locked when the **READPE** operation is successful. The file specified in **From** is positioned so a subsequent read operation retrieves the next sequential record following the retrieved record. If **Access** (*NOLOCK) is specified, then in no case will the record be locked when the **READRAND** operation is successful. The file specified in **Key** is positioned so a subsequent read operation retrieves the next sequential record following the retrieved record. If the **READRAND** is not completed successfully, the file specified in **From** must be repositioned before a subsequent read operation can be done to that file.

If **READRAND** operation for file is successful, the RRNFldName property is updated with current RRN. If it is not successful, a value of zero is assigned to RRNFLDName.


**NotFnd** 

Optional. Used to determine if the record was found while executing this command. 

Note that you can also use the [%FOUND](FOUND_Function.html) function. However, be aware that %FOUND and the NotFnd indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function or the Files' [IsError](IsErrorPropertyDbFileClass.html) property.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
[CHAIN](CHAIN.html) is exactly the same as **READRAND** , and can be used interchangeably. 

### Example

```
/* The ReadRand operation retrieves the first record from the file CustMaster, that has a key field with the
same value as the search argument CustNumber (Factor 1). Indicator 60 will come on (File record not found). */ 

ReadRand CustMaster CustNumber NotFnd(*In60)
  If *In60 = *ON
Subfile1AgentName = *Blanks
  Else
    Subfile1AgentName = CustName
  Endif 
```

### See Also
[CHAIN](CHAIN.html) <br /> <span> [DCLKLIST](DCLKLIST.html) <br /> </span> <span> [READ](READ.html)

[READP](READP.html) </span> 
