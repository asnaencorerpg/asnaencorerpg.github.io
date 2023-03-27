---
title: SETRANGE

Id: SETRANGE
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

**SETRANGE** positions the file to the desired range of records constrained by the **FirstKey** and the **LastKey** parameters. The range is determined by the combination of the parameters of the command. 

```

 **SETRANGE
File**  (file name | Format Name)
 **FirstKey**  (Key List Name | Variable Operand)
LastKey (<u>*FIRSTKEY</u> | Key List Name | Variable Operand)
StartAt (<u>*FIRST</u> | *LAST)
IncludeFirstKey (*<u>YES</u> |*NO)
IncludeLastKey (*<u>YES</u> | *NO)
Err (*EXTENDED | Indicator Variable)
```

### Parts

**File** 

Required. Must be the name of a file or a format name. The range operation works on this file or format name.


**FirstKey** 

Required. If the file is accessed by key, this parameter can be a field name, a named constant, a figurative constant, or a literal that is used as the search argument for the top of the range in positioning a file. If you want to ignore the top first record of the specified range to be deleted, use **IncludeFirstKey (*NO).**


**LastKey** 

Optional. Defaults to * **FirstKey** (meaning **LastKey** is the same as the **FirstKey** ). This parameter can be a field name, a named constant, a figurative constant, or a literal that is used as the search argument for the bottom of the range in positioning a file. If you want to ignore the bottom last record of the specified range to be read, use **IncludeLastKey (*NO)** .


**StartAt** 

Optional. Specifies the direction the records are read after the Set (either starting with the first record or the last record in the range). *First is the default. 

- *FIRST– (Default) The records read will start at the first record found in the range, using the first key, and continue reading until the last record in the range is read.
- *LAST - The records read will start at the last record found in the range, using the last key, and continue reading until the first record in the range is read.


**IncludeFirstKey** 

Optional. Specifies whether to include the very first record found within the range. The default is *YES. 

- *YES – (Default) If the operation finds a record whose key matches the **FirstKey** , then the file is positioned at that record. If the record that matches the key is not found, then the file is positioned at the first record whose key is greater than the **FirstKey** .
- *NO – The file is positioned on the first record whose key is greater than the **FirstKey** .


**IncludeLastKey** 

Optional. Specifies whether to mark the last record found that matches the **LastKey** as the bottom of the range. The default is *Yes. 

- *YES –(Default) If the operation finds a record whose key matches the **LastKey** , then the bottom of the range is marked at that record. If the record that matches the key is not found, then the last record whose key is less than the **LastKey** is marked as the bottom of the range.
- *NO – The last record whose key is less than the **LastKey** is marked as the bottom of the range.


**Err** 

Optional. Will be set if any error condition is found with the file. The following rules apply:

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime excepton will be thrown.


### Remarks
Use **SETRANGE** , in conjunction with the **READRANGE** and **DELETERANGE** op codes to optimize SQL Server processing and to enhance client/server performance with all supported database engines (System i, Acceler8DB and SQL Server) with dynamic Network Blocking. 

Use a SETRANGE – Read(P) loop instead of a SETLT/SETGT – Read(P)E loop. 

### Example
<img height="447" alt="..\Images\setrange1_wmf.gif" src="../Images/setrange1_wmf.gif" width="454" border="0" /> 

<span style="FONT-WEIGHT: bold"> If IncludeFirstKey (*No) </span> 

<img height="424" alt="..\Images\setrange2_wmf.gif" src="../Images/setrange2_wmf.gif" width="521" border="0" /> 

<span style="FONT-WEIGHT: bold"> If IncludeLastKey (*No) </span> 

<img height="432" alt="..\Images\setrange3_wmf.gif" src="../Images/setrange3_wmf.gif" width="521" border="0" /> 

### See Also
[DELETERANGE](DELETERANGE.html)

[DCLDISKFILE](DCLDISKFILE.html)

[READRANGE](READRANGE.html) 
