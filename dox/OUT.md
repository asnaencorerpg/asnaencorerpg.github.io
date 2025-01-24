---
title: OUT

Id: OUT
TocParent: aerLrfOpCodesMain
TocOrder: 1310


---

**OUT** updates a **previously locked** data area. 

```
OUT
Name  (name | *DTAARA)
Lock ( <u>*NO</u> | *YES)
ERR (Indicator Variable | *EXTENDED)
```

### Parameters

**Name** 

Required. Specifies the name of a field, data structure or DS field that declares the **DATAAREA** keyword. Name can also be * **DTAARA** in which case all fields, DS, and DS fields that are data areas will be written. All of the data areas **must be locked** or a runtime error will occur.


**Lock** 

Optional. Specifies if the data area object will be locked, and no other program can access it. The default value is *NO.


- *NO - The data area will be unlocked after the **OUT** operation is complete.
- *YES - The data area object will remain locked.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- Err (Indicator Variable) - The specified Indicator is set if an error occurred.
- Err (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the Err keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Use **OUT** to update a data area that was previously locked with an [IN](IN.html) command. 

### See Also
[DCLFLD](DCLFLD.html)
        <br />
        [DCLDS](DCLDS.html)
        <br />
        [IN](IN.html)
        <br />
        [UNLOCK](UNLOCK.html)

