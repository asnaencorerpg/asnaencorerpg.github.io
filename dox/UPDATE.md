---
title: UPDATE

Id: UPDATE
TocParent: aerLrfOpCodesMain
TocOrder: 1730


---

Modifies the last record retrieved for processing from an update disk file. 

```

 **UPDATE
File**  (file name | Format Name)
FromDS (Data structure)
Err (Indicator Variable | *EXTENDED)
Flds (field1, field2, ... , fieldn)
```

### Parts

**File** 

Required. Must contain the file or record format to be updated. For subfiles, the file name is the SubfileControl name. The relative record number to write the record must be greater than zero and contained in the numeric variable contained in the [RRNName](SF_RRNName_Property.html) property.


**FromDs** 

Optional. The name of the data structure to update. The data structure must be of the same type and size that the file is expecting, or a runtime error will occur.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply:


- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Flds** 

Optional. List of field names (1 - 32,767) of the file/format that are updated.


**Note** Please note that in prior versions the parameter was called **Fields** , and has been deprecated. From now on, you must use **Flds** .


### Remarks
If the file is a multiformat file, you cannot perform the operation using the file name, you must use the format name. 

### See Also
[DCLDISKFILE](DCLDISKFILE.html)
[READ](READ.html)
[UNLOCK](UNLOCK.html) 
