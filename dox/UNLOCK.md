---
title: UNLOCK

Id: UNLOCK
TocParent: aerLrfOpCodesMain
TocOrder: 1720


---

Releases record locks.

```

 **UNLOCK<br />Obj** (Oject Name | *DTAARA)<br />Err (Indicator Variable | *EXTENDED)
```

### Parts

**Obj** 

Required. Contains the name of the file, field, data structure or DS field name. You can also specify the special name * **DTAARA** , which will cause the unlocking of all previously locked data areas in the program.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
**UNLOCK** allows the most recently locked record to be unlocked for an update disk file. 

### See Also
[DCLDISKFILE](DCLDISKFILE.html)

[READ](READ.html)

[UPDATE](UPDATE.html) 
