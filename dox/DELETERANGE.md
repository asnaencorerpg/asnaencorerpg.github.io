---
title: DELETERANGE

Id: DELETERANGE
TocParent: aerLrfOpCodesMain
TocOrder: 650


---

Positions the file to the desired range of records constrained by the **FirstKey** and the **LastKey** parameters and deletes those records. The range is determined by the combination of the parameters of the command. For a detailed explanation of properly marking a range, please refer to the example provided within [SETRANGE](SETRANGE.html). 

This operation is valid only for files opened for indexed access (Use **ORG (*Indexed)** option on **DCLDISKFILE** ). 

```
 **DELETERANGE** 
 **File**  (FileName | FormatName) 
 **FirstKey**  (Key List Name | Variable Operand) 
LastKey (*<u>FIRSTKEY</u>  | Key List Name | Variable Operand) 
IncludeFirstKey (<u>*YES</u>  |*NO) 
IncludeLastKey (<u>*YES</u>  | *NO) 
NotFnd (Indicator Variable) 
Err (Indicator Variable | *EXTENDED)
NotAll (Indicator Variable)
```

### Parts

**File** 

Required. The name of a file or a format name. The range operation works on this file or format name.


**FirstKey** 

Required. Can be any valid variable operand or a Key List name that is used as the search argument for the top of the range in positioning a file. If you want to exclude from the range the records whose key is equal to the first key, use **IncludeFirstKey (*No),** which positions the file to the first record whose key is greater than the **FirstKey** .


**LastKey** 

Optional. Defaults to *FirstKey (meaning **LastKey** is the same as the **FirstKey** ). This parameter can be any valid variable operand or a Key List name that is used to mark the bottom of the range. If you want to exclude, from the range, the records whose key is equal to the **LastKey** , use **IncludeLastKey (*No),** which marks the last record whose key is less than the **LastKey** parameter as the bottom of the range.


**IncludeFirstKey** 

Optional. Specifies whether to include the very first record found within the range when deleting records. The default is *Yes. 

- <p> *YES (Default) If the operation finds a record whose key matches the FirstKey, then the file is positioned at that record. If the record that matches the key is not found, then the file is positioned at the first record whose key is greater than the **FirstKey** .
- *NO The file is positioned on the first record whose key is **greater than** the **FirstKey** .


**IncludeLastKey** 

Optional. Specifies whether to mark the last record found that matches the **LastKey** as the bottom of the range. The default is *Yes. 

- <p style="MARGIN-BOTTOM: 6pt; MARGIN-LEFT: 0px; TEXT-INDENT: 2px"> * **YES** (Default) If the operation finds a record whose key matches the **LastKey** , then the bottom of the range is marked at that record. If the record that matches the key is not found, then the last record whose key is less than the **LastKey** is marked as the bottom of the range.
- *NO The last record whose key is less than the **LastKey** is marked as the bottom of the range.


**NotFnd** 

Optional. Used to determine if the record was found while executing this command.


Note that you can also use the [%FOUND](FOUND_Function.html) function. However, be aware that %FOUND and the NotFnd indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. Will be set if any error condition is found with the file. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**NotAll** 

Optional. Is set on when all of the records specified in the range to be deleted were not deleted.


### Remarks
Use **DELETERANGE** , in conjunction with the **SETRANGE** and **READRANGE** op codes to optimize SQL Server processing and to enhance client/server performance with all supported database engines (System i, Acceler8DB and SQL Server) with dynamic Network Blocking. 

DELETERANGE replaces a **Read(PE) - Delete** loop.

### See Also
[DCLDISKFILE](DCLDISKFILE.html)
[READRANGE](READRANGE.html)
[SETRANGE](SETRANGE.html) 
