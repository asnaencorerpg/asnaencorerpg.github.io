---
title: CLOSE

Id: CLOSE
TocParent: aerLrfOpCodesMain
TocOrder: 300


---

Allows the user to close a file manually instead of when the program goes to end-of-job. 

```
CLOSE
File (*ALL| file name )
Err (Indicator Variable | *EXTENDED)
```

### Parameters

**File** 

Required. Will either contain the name of the file to be closed, or *ALL. **CLOSE** *ALL will only close those files that were implicitly and explicitly opened in that program as noted below. However, if all files were opened by the Startup program and a SHOWed form executed a **CLOSE** *ALL, no files would be closed. 

1. When the **CLOSE**  *ALL is issued from a shared member, only
                        shared files in the class are closed.
2. When the **CLOSE**  *ALL is issued from an instanced member, only
                        instanced files in the object are closed.
3. Only Disk and Printer files apply.  Memory files and subfiles are not
                        included.

You cannot specify an array or table file in **File** . You can specify a resulting indicator to be set on if the **CLOSE** operation is not completed successfully.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Once a file has been closed, you cannot perform any operations on it unless you reopen it with an [OPEN](OPEN.html) statement. 

The explicit **CLOSE** operation closes one or more files or devices and disconnects them from the program. The file cannot be used again in the program unless you specify an explicit OPEN for that file. 

An error will not occur if a **CLOSE** operation is performed to an already closed file. 

### Example

```
// The explicit **CLOSE**  operation closes ItemMaster.

 **Close**  ItemMaster

/* The **CLOSE** *ALL operation closes all files in the program. You must specify an explicit 
OPEN for any File that you wish to use again. If the **CLOSE** 
operation is not completed successfully, indicator 99 is set on and an error 
subroutine is performed. */

 **Close**  *All
       If *In99
       Exsr ErrorOnClose
       Endif
```

### See Also
[DCLDISKFILE](DCLDISKFILE.html)

[OPEN](OPEN.html) 
