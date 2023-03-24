---
title: WRITE

Id: WRITE
TocParent: aerLrfOpCodesMain
TocOrder: 1780


---

Writes a new record to a file.

```

 **WRITE
File**  (file name | Format Name)
At (integer) 
FromDS (Data structure)
Err (Indicator Variable | *EXTENDED)
Eof (Indicator Variable)
```

### Parts

**File** 

Required. Must contain a file name or record format name. The file must be declared to allow adding of records, otherwise a compile error will occur. For subfiles, the file name is the SubfileControl name. The relative record number to write the record must be greater than zero and contained in the numeric variable contained in the [RRNName](SF_RRNName_Property.html) property.


If the file is a multiformat file, you cannot perform the operation using the file name, you must use the format name.


**At** 

Optional.  An integer representing the position within the Memory file
                Subfile control where the new row/record is to be **inserted** . 
                Indexing is relative to 0.  For example:


```
Write FName  At( 1 )  // inserts record <u>between</u> 1st and 2nd records
Write FName  At( 0 )  // inserts record as first in file/table
```
                
```

 **Note**   If **At**  row is greater than row count, the row is added at [rowcount](SF_RowCount_Property.html) + 1.
```


**FromDs** 

Optional. The name of the data structure to write to the database. The data structure must be of the same type and size that the file is expecting, or a runtime error will occur.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- Err (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Eof** 

Optional for ASNA Monarch™
                Subfiles.  Not allowed for database files.  Use the
                EOF (End-of-File) indicator, the %EOF function, or the Subfile's
                IsEof property to determine if the End-Of-File was reached while executing the **Write**  command.


### Remarks
When writing records to a subfile where the *char data contains hex zeros (H"00"), these values will be displayed as a period. Hex 00 is a terminator character for a windows string. 

### See Also
[DCLDISKFILE](DCLDISKFILE.html)
[IsEof Property](IsEofPropertyDbFileClass.html)
[RRNName Property](SF_RRNName_Property.html)
[%ERROR](ERROR_Function.html)
[RowCount Property](SF_RowCount_Property.html) 
