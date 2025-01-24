---
title: READP

Id: READP
TocParent: aerLrfOpCodesMain
TocOrder: 1350


---

Reads the prior record from a full procedural file.

```
READP
From  (File Name | Format Name)
Access (<u>*DFT</u> | *NOLOCK)    
Err (*EXTENDED | Indicator Variable)
Bof (Indicator Variable)
IntoDS (Data structure)
```

### Parameters

**From** 

Required. Must contain a file name, or a record format name.


**Access** 

Optional. Determines if records are locked.

- *DFT – (Default) if the parameter is not given, the default record locking behavior is taken. This means, if File is specified as INPUT, all records are read without locks. If File is specified as UPDATE, all records are locked if blank.
- *NOLOCK – if this option is specified, then in no case will the record be locked when the **READP** operation is successful. The file specified in F2 is positioned so a subsequent read operation retrieves the next sequential record following the retrieved record.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.

If the file is a multiformat file accessed by RRN, you cannot perform the operation using the file name, you must use the format name.


**Bof** 

Optional. The **Bof** parameter, or the [%EOF](EOF_Function.html) function or Eof Parameter, can be used to determine if the Beginning-Of-File was reached.


Indicator Variable - The specified indicator is set if the beginning of file is reached.


**IntoDs** 

Optional. The name of the data structure to read from. The data structure must be of the same type and size that the file is expecting, or a runtime error will occur.


### Remarks
If the **READP**  operation is successful, the file is positioned
        at the record prior to the one just read. 

### Example

```
/* The READP operation reads the prior record from CustMast. Indicator 71 is set on if Beginning-of-file is encountered. When indicator 71 is set on, the program executes the subroutine BeginFile specified in the indicator conditioned instructions. If there is an error on the READP, indicator 99 will be turned on. */

ReadP CustMast Bof( *In71 ) Err ( *In99 )
    If *In71 = *On
       Exsr BeginFile
    Endif
    If *In99
        Exsr ErrorOnRead
    Endif

/* The READP operation reads the next prior record of the type CustRecd from an externally described file (CustRecd is a record format name). Indicator 72 is set on if Beginning-of-file is encountered during processing of the READP operation. When indicator 72 is set on, the program executes the subroutine BeginFile specified in the indicator conditioned instructions. Access(*NoLock) indicates that the record is not locked. */
ReadP CustRecd Access( *NoLock ) Bof(* In72 ) Err ( *In99 )
    If *In72 = *On
       Exsr BeginFile
    Endif
    If *In99
       Exsr ErrorOnRead
    Endif
```

### See Also
[CHAIN](CHAIN.html)

[DCLDISKFILE](DCLDISKFILE.html)

[READ](READ.html)

[READE](READE.html)

[READPE](READPE.html)

[%EOF](EOF_Function.html) 
