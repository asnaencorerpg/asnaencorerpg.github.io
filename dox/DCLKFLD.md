---
title: DCLKFLD

Id: DCLKFLD
TocParent: aerLrfOpCodesMain
TocOrder: 490


---

Indicates that a field is part of a search argument identified by a [DCLKLIST](DCLKLIST.html) name. 

```
DCLKFLD 
Name  (KeyField name)
```

### Parts

**Name** 

Required. Name **must** contain the field name that is to be part of the search argument, and cannot contain an array or table name.


Each **DCLKFLD** must correspond in length, data type, and decimal position with the corresponding field in the composite key of the record or file. 

The **DCLKFLD** order specified in the **DCLKLIST** determines which **DCLKFLD** is associated with a field in the composite key. For example, the first **DCLKFLD** following a **DCLKLIST** is associated with the left-most (or high-order) field of the composite key.


### See Also
[DCLKLIST](DCLKLIST.html) 
