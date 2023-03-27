---
title: READE

Id: READE
TocParent: aerLrfOpCodesMain
TocOrder: 1340


---

Reads the next sequential record in a full procedural file that has the same search argument. 

```

 **READE** 
From (File Name | Format Name)
Key (*CURRENT | KeyList Name | Character Expression)
Access (*DFT | *NOLOCK)
Err (*EXTENDED | Indicator Variable)
Eof (Indicator Variable)
IntoDS (Data structure)
```

### Parts

**From** 

Required. Must contain a file name or a record format name. If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you must use the format name.


**Key** 

Optional. Determines the key in which to search the file by. Refer to [%KDS](KDS_Function.html) to use this built-in function to establish search arguments (Key) for Data Structures.


**Access** 

Optional. Determines if records are locked.

- *DFT – (Default) if the parameter is not given, the default record locking behavior is taken. This means, if File is specified as INPUT, all records are read without locks; if File is specified as **UPDATE** , all records are locked if blank.
- *NOLOCK – if this option is specified then in no case will the record be locked when the **READE** operation is successful. The file specified in **F2** is positioned so a subsequent read operation retrieves the next sequential record following the retrieved record.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function or the Files' [IsError](IsErrorPropertyDbFileClass.html) property.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Eof** 

Optional. Use the **Eof** (End-of-File) indicator, the [%EOF](EOF_Function.html) function, or the Files' [IsEof](IsEofPropertyDbFileClass.html) property to determine if the End-Of-File was reached while executing the command. 

If any other error occurs, the error indicator will be set. The End of File indicator is also set when no more records exist with the same search argument.


**IntoDs** 

Optional. The name of the data structure to read from. The data structure must be of the same type and size that the file is expecting, or a runtime error will occur.


### Remarks
If the **READ** operation is successful, the file is positioned at the record prior to the one just read. 

### Example

```
/* With Key specified, the **ReadE**  operation retrieves
       the next record from the file CustMast and compares its key to the search argument, CustNumb. Indicator 55 is
       set on if CustNumb is not equal to the key of the record read or if End-Of-File is encountered. Indicator 99 is turned on
if any error occurred during **ReadE**  operation. */

 ReadE CustMast CustNumb Eof(*In55) Err(*In99)
If *In55 = *On
   Exsr EndOfJob
Endif
If *In99
   Exsr ErrorOnRead
Endif

/* With Key specified, the **ReadE**  operation retrieves the next record of the type CustRecd from
an externally described file and compares the key of the record read to the search argument, CustNumb
(CustRecd is a record format name). Indicator 61 is set on if CustNumb is not equal to the key of the
record read or if End-Of-File is encountered. Indicator 99 is turned on if any error occurred during
 **ReadE**  operation. The record is also unlocked after the read for an update described file. */

 ReadE CustRecd CustNumb Access(*noLock) Eof(*In61) Err(*In99)
If *In61 = *On
   Exsr EndOfJob
Endif
If *In99
   Exsr ErrorOnRead
Endif

/* With no Key specified, the **ReadE**  operation retrieves the next record in the access path from
the file CustMast if the key value is equal to the key value of the record at the current cursor
position. If the key values are not equal, indicator 55 is set on. Indicator 99 is turned on if any
error occurred during **ReadE**  operation. */

 ReadE CustMast Eof(*In55) Err(*In99)
If *In55 = *On
   Exsr EndOfJob
Endif
If *In99
   Exsr ErrorOnRead
Endif

/* With no Key specified, the **ReadE**  operation retrieves the next record in the access path from
the file CustMast if the key value equals the key value of the record at the current position.
CustRecd is a record format name. Indicator 61 is set on if the key values are unequal. Indicator 99
is turned on if any error occurred during **ReadE**  operation. The record is also unlocked after the read
for an update described file. */

 ReadE CustRecd Access(*noLock) Eof(*In61) Err(*In99)
If *In61 = *On
   Exsr EndOfJob
Endif
If *In99
   Exsr ErrorOnRead
Endif
```

### See Also
[CHAIN](CHAIN.html)

[READ](READ.html)

[READC](READC.html)

[READP](READP.html)

[READPE](READPE.html)

[%EOF](EOF_Function.html)

[%ERROR](ERROR_Function.html)

[%KDS](KDS_Function.html)

[IsEof Property](IsEofPropertyDbFileClass.html)

[IsError Property](IsErrorPropertyDbFileClass.html) 
