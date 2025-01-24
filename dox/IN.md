---
title: IN

Id: IN
TocParent: aerLrfOpCodesMain
TocOrder: 1150


---

**IN** reads in a data area. 

```
 IN
Name  (name | *DTAARA)
Lock ( <u>*NO</u> | *YES)
DB (database objectt)
ERR (Indicator Variable | *EXTENDED)
```

### Parameters

**Name** 

Required. The name of a field, data structure or DS field that declares the **DATAAREA** keyword. Name can also be * **DTAARA** in which case all fields, data structures, and DS fields that are data areas will ALL be read in.


**Note** If you specify * **DTAARA** with the **DB** parameter, this will override the DB name for **all** the DataAreas you specified. For example, if a database defined by declaring the **dataAreaDB** parameter is different than the database specified using the **DB** parameter, then unexpected results may occur when ECR attempts to populate fields on databases other than the one specified. <br /><br /> *See example below, note that ECR will attempt to populate the **myField** and **myDS** fields, even though **myDS** does not exist in **myDatabase** .*


```
 DCLFLD myfield DataArea (... ) dataAreaDB (myDatabase)
 DCLDS myDS DataArea ( ... ) dataAreaDB (myDatabase1)

 IN *dtaara DB (myDatabase)
```


**Lock** 

Optional. Specifies if the data area object will be locked, and no other program can access it. The default value is *NO.


- *NO - The lock status of the data area will not change. For example, if it was locked before, it will be locked after; and if it was not locked before, it will not be locked after.
- *YES - The data area object will be locked and no other program can access it. If the name of the data area is specified with * **VAR** , the name of the data area must already be set in the indicated symbol. However, if there was a prior IN LOCK(*Yes), the symbol containing the name will not be consulted.


**DB** 

Optional. The default value is the value of the **DataAreaDB** parameter from the data area declaration ( **DclFld** , **DclDS** , **DclDSFld** ).\


(If DCLDS specifies another


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- Err (Indicator Variable) - The specified Indicator is set if an error occurred.
- Err (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the Err keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
Use **IN** to read a data area field, data structure, or DS field that was declared with the DATAAREA, or *DTAARA keyword. Use the **Lock** keyword to specify whether the data area object can be accessed by another program(s). 

### See Also
[DCLFLD](DCLFLD.html) 

[DCLDS](DCLDS.html) 

[DCLDSFLD](DCLDSFLD.html) 

[OUT](OUT.html) 

[UNLOCK](UNLOCK.html) 
