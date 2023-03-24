---
title: SORTARR

Id: SORTARR
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

Sorts an array.

```

 **SORTARR<br />Arr**  (Array Name)
```

### Parts

**Arr** 

Required. Contains the name of an array to be sorted. The array is sorted in ascending or descending order, depending on the sequence specified for the array in the extension specifications. The default is ascending order.


### Remarks
In a **SORTARR** operation, array *IN cannot be designated in **Arr** .

Sorting an array does not maintain the previous order. 

### Example

```
/* The **SORTARR**  operation sorts MyArray into descending sequence because the array is defined 
   as descending. If the unsorted MyArray contents were ASNARPGZ, the sorted MyArray contents would be ZSRPNGAA. */

DCLARRAY Name(MyArray) dim(8) Len(1) Seq(*Descend)
SORTARR MyArray
```

### See Also
[DCLARRAY](DCLARRAY.html) 
