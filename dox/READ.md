---
title: READ

Id: READ
TocParent: aerLrfOpCodesMain
TocOrder: 1320


---

Reads the currently pointed-to record from a full procedural file.

```
READ
From  (File Name | Format Name)
Access (<u>*DFT</u> | *NOLOCK)   
Err (*EXTENDED | Indicator Variable)
Eof (Indicator Variable)
IntoDS (Data structure)
```

### Parameters

**From** 

Required. Must contain a file name or a record format name. If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you **must** use the format name.


**Access** 

Optional. Determines if records are locked.

- *DFT – (Default) - if the parameter is not given, the default record locking behavior is taken. This means, if File is specified as INPUT, all records are read without locks. If File is specified as **UPDATE** , all records are locked if blank.
- *NOLOCK – if this option is specified, then in no case will the record be locked when the **READ** operation is successful. The file specified in From is positioned so a subsequent read operation retrieves the next sequential record following the retrieved record.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function or the Files' [IsError](IsErrorPropertyDbFileClass.html) property.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Eof** 

Optional. Use the **Eof** (End-of-File) indicator, the [%EOF](EOF_Function.html) function, or the Files' [IsEof](IsEofPropertyDbFileClass.html) property to determine if the End-Of-File was reached while executing the command. 

If any other error occurs, the error indicator will be set. The End of File indicator is also set when no more records exist with the same search argument.


**IntoDs** 

Optional. The name of the data structure to read from. The data structure must be of the same type and size that the file is expecting, or a runtime error will occur.


### Remarks
If the **READ**  operation is successful, the file is positioned at
        the next record that satisfies the read. 

### Example

```
/* Read retrieves the next record from the file CustMast, which must be a full procedural file. Indicator 61 is set on if
   End-Of-File occurs on Read, or if End-Of-File has occurred previously and the file has not been repositioned. When 
   indicator 61 is set on, the program will perform its End-of-Job routine. If there is an error on the Read, indicator 99 
   will be turned on. */

  Read CustMast Eof(*In61) Err(*In99)
  If *In61 = *On
   Exsr EndOfJob
  Endif  If *In99
   Exsr ErrorOnRead
  Endif

/* Read retrieves the next record of the type CustRecd from an externally described file (CustRecd is a record format name.)
   Indicator 61 is set on if End-Of-File occurs on Read, or if it has occurred previously and the file has not been 
   repositioned. When indicator 61 is set on, the program will perform its End-of-Job routine. Access(*NoLock) indicates
   that the record is not locked. */

  Read CustRecd Access(*noLock) Eof(*In61) Err(*In99)
  If *In61 = *On
   Exsr EndOfJob
  Endif  If *In99
   Exsr ErrorOnRead
  Endif

/* Read retrieves the next record from the file CustMast, which must be a full procedural file. Indicator 61 is set on if
   End-Of-File occurs on Read, or if End-Of-File has occurred previously and the file has not been repositioned. When 
   indicator 61 is set on, the program will perform its End-of-Job routine. If there is an error on the Read, indicator 99
   will be turned on. */

  Read CustMast Eof(*In61) Err(*In99)
  If *In61 = *On
   Exsr EndOfJob
  Endif  If *In99
   Exsr ErrorOnRead
  Endif

/* Read retrieves the next record of the type CustRecd from an externally described file (CustRecd is a record format name.)
   Indicator 61 is set on if End-Of-File occurs on Read, or if it has occurred previously and the file has not been 
   repositioned. When indicator 61 is set on, the program will perform its End-of-Job routine. Access(*NoLock) indicates
   that the record is not locked. */

  Read CustRecd Access(*noLock) Eof(*In61) Err(*In99)
  If *In61 = *On
   Exsr EndOfJob
  Endif  If *In99
   Exsr ErrorOnRead
  Endif
```

### See Also
[CHAIN](CHAIN.html)

[READE](READE.html)

[READP](READP.html)

[READPE](READPE.html)

[READC](READPE.html)

[%EOF](EOF_Function.html)

[%ERROR](ERROR_Function.html)

[IsEof Property](IsEofPropertyDbFileClass.html)

[IsError Property](IsErrorPropertyDbFileClass.html) 
