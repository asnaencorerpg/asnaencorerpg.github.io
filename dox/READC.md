---
title: READC

Id: READC
TocParent: aerLrfOpCodesMain
TocOrder: 1330


---

Reads the next record that has been changed in a Subfile.

```
READC
From  (SubfileControl Name)
Err (*EXTENDED | Indicator Variable)
Eof (Indicator Variable)
IntoDS (Data structure)
```

### Parameters

**From** 

Required. Must contain the name of the SubfileControl.


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
**READC** retains the current cursor position as the starting point when looking for the next changed record. In order for a record format to be used in a **READC** operation, it has to be listed in the *Subfile* keyword of its corresponding file. See [DCLMEMORYFILE](DATE_Function.html) and [DCLWORKSTNFILE](DCLWORKSTNFILE.html). 

### See Also
[CHAIN](CHAIN.html)

[DCLMEMORYFILE](DATE_Function.html)

[DCLWORKSTNFILE](DCLWORKSTNFILE.html)

[READ](READ.html)

[READE](READE.html)

[READP](READP.html)

[READPE](READPE.html)

[%EOF](EOF_Function.html)

[%ERROR](ERROR_Function.html)

[IsEof Property](IsEofPropertyDbFileClass.html)

[IsError Property](IsErrorPropertyDbFileClass.html) 
