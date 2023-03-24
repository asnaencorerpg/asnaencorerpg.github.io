---
title: DSDUMP

Id: DSDUMP
TocParent: aerLrfOpCodesMain
TocOrder: 730


---

Dumps the contents of the fields of the **data structure** assembled into a string. 

```
 **DSDUMP** 
Name (Data structure name)
 **Target**  (Data structure contents)
```

### Parts

**Name** 

Optional. The name of the data structure to dump the contents from.


**Target** 

Required. The string in which you will store the contents of the data structure.


### Remarks
Make sure that all the numeric fields are positive and all characters are padded with the right amount of blanks. 

The **Target** field length may be longer or shorter than the sum of the fields in the data structure. If the Target length is greater than the data structure length, the remaining target data is cleared to blanks. If the Target length is less than the data structure length, DSDump will complete without error when the Target field is filled. 

### Example

```
DclDs myDs
DclDsFld myDSChar *Char Len(6)
DclDSFld myDSZoned  *Zoned len(5, 2)
DclDSFld myDSIndicator *Ind
   myDSChar = "Hello"
   myDSZoned = 987.65
   myDSIndicator = *Off
DSDump Name(myDS) target(myString)
```

### See Also
[DSLOAD](DSLOAD.html) 
