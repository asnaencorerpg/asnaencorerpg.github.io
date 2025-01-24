---
title: DCLPLIST

Id: DCLPLIST
TocParent: aerLrfOpCodesMain
TocOrder: 550



---

Begins the declaration of a list of parameters to be passed to a program, or be received from a caller if the name given is * **ENTRY** . 

```
DCLPLIST
Name   (ParmListName)
```

### Parameters

**Name** 

Required. **Name** must contain the name of the parameter list. 

A parameter list is ended when an operation other than **DCLPARM** is encountered.


### See Also
[DCLPARM](DCLPARM.html) 
