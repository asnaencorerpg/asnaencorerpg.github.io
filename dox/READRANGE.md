---
title: READRANGE

Id: READRANGE
TocParent: aerLrfOpCodesMain
TocOrder: 1380


---

**READRANGE** positions the file to the desired range of records constrained by the **FirstKey** and the **LastKey** parameters and reads the first record of the range. The range is determined by the combination of the parameters of the command. 

This operation is valid only for files opened for indexed access. Use the ORG (*Indexed) option on [DCLDISKFILE](DCLDISKFILE.html). 

```
READRANGE
File  (FileName | FormatName)
 FirstKey  (Key List Name | Variable Operand)
LastKey (<u>*FIRSTKEY</u> | Key List Name | Variable Operand)
StartAt (<u>*FIRST</u> | *LAST)
IncludeFirstKey (*<u>YES</u> |*NO)
IncludeLastKey (*<u>YES</u> | *NO)
Access (*<u>DFT</u> | *NOLOCK)
NotFnd (Indicator Variable)
Err (*EXTENDED | Indicator Variable)
Eof (Indicator Variable)
```

### Parameters

**File** 

Required. Must be the name of a file or a format name. The range operation works on this file or format name.


**FirstKey** 

Required. Can be any valid variable operand or a Key List name that is used as the search argument for the top of the range in positioning a file. If you want to exclude from the range the records whose key is equal to the first key, use **IncludeFirstKey (*No),** which positions the file to the first record whose key is greater than the **FirstKey.**


**LastKey** 

Optional. Defaults to * **FirstKey** (meaning **LastKey** is the same as the **FirstKey** ). This parameter can be any valid variable operand or a Key List name that is used to mark the bottom of the range. If you want to exclude from the range the records whose key is equal to the **LastKey** , use **IncludeLastKey (*No)** , which marks the last record whose key is less than **LastKey** parameter as the bottom of the range.


**StartAt** 

Optional. Specifies the direction the records are read after the Set (either starting with the first record or the last record in the range). *First is the default. 

- *First – The records read will start at the first record found in the range, using the first key, and continue reading until the last record in the range is read.
- *Last - The records read will start at the last record found in the range, using the last key, and continue reading until the first record in the range is read.


**IncludeFirstKey** 

Optional. Specifies whether to include the very first record found within the range when deleting records. The default is *Yes. 

- *YES – (Default) If the operation finds a record whose key matches the **FirstKey** , then the file is positioned at that record. If the record that matches the key is not found, then the file is positioned at the first record whose key is greater than the **FirstKey** .
- *NO – The file is positioned on the first record whose key is greater than the **FirstKey** .


**IncludeLastKey** 

Optional. Specifies whether to mark the last record found that matches the **LastKey** as the bottom of the range. The default is *Yes. 

- *YES – (Default) If the operation finds a record whose key matches the **LastKey** , then the bottom of the range is marked at that record. If the record that matches the key is not found, then the last record whose key is less than the **LastKey** is marked as the bottom of the range.
- *NO – The last record whose key is less than the **LastKey** is marked as the bottom of the range.


**Access** 

Optional. Specifies the record locking behavior. If the parameter is not specified (*DFT), the default record locking behavior is taken. See below for a description of the parameters. 

- *DFT – (Default) If the parameter is not given, the default record locking behavior is taken. This means, if the File is specified as INPUT, all records are read without locks. If File is specified as UPDATE, all records are locked if blank.
- *NOLOCK – If this option is specified, then in no case will the record be locked when the **READRANGE** operation is successful.


**NotFnd** 

Optional. Used to determine if the record was found while executing this command.


Note that you can also use the [%FOUND](FOUND_Function.html) function. However, be aware that %FOUND and the **NotFnd** indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. Will be set if any error condition is found with the file. The following rules apply:

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function or the Files' [IsError](IsErrorPropertyDbFileClass.html) property.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Eof** 

Optional. Use the **Eof** (End-of-File) indicator, the [%EOF](EOF_Function.html) function, or the Files' [IsEof](IsEofPropertyDbFileClass.html) property to determine if the End-Of-File was reached while executing the command.


If any other error occurs, the error indicator will be set. The End of File indicator is also set when no more records exist with the same search argument.


### Remarks
Use **READRANGE** , in conjunction with the **SETRANGE** and **DELETERANGE** op codes to optimize SQL Server processing and to enhance client/server performance with all supported database engines (System i, Acceler8DB and SQL Server) with dynamic Network Blocking. 

Use a **READRANGE – Read(P)** loop instead of **Chain – Read(P)E** loop. 

To use a **READRANGE** in existing code, replace the **CHAIN** op code that exists outside of the **CHAIN** / **READE** loop with a **READRANGE** . Then replace the **READE** op code inside the loop with a **READP** . The **READRANGE** establishes the range of records to be read and proceeds to read the first record within the range. Subsequent uses of the read op code will only retrieve records that fall within that range. Once the last record within the range has been read, a subsequent use of the read op code will set on Eof. 

### See Also
[DELETERANGE](DELETERANGE.html)

[DCLDISKFILE](DCLDISKFILE.html)

[SETRANGE](SETRANGE.html)

[%EOF](EOF_Function.html)

[%ERROR](ERROR_Function.html)

[IsEof Property](IsEofPropertyDbFileClass.html)

[IsError Property](IsErrorPropertyDbFileClass.html) 
