---
title: DCLKLIST

Id: DCLKLIST
TocParent: aerLrfOpCodesMain
TocOrder: 500



---

Gives a name to a list of DCLKFLDS. This list can be used to retrieve records from files that have a composite key. 

```
DCLKLIST 
Name  (KeyField name)
```

### Parameters

**Name** 

Required. Name must contain a unique name. 

A **DCLKLIST** must be followed immediately by at least one **DCLKFLD** . A **DCLKLIST** and its associated **DCLKFLD** fields must appear in the global declaration part of a class. 

A **DCLKLIST** name can be specified as a search argument only for externally described files. 

You must specify a **DCLKLIST** with multiple **DCLKFLDS** if a search argument contains more than one field. 

A **DCLKLIST** can appear as a factor of the [CHAIN](CHAIN.html), [DELETE](DELETE.html), [READE](READE.html), [READPE](READPE.html), [SETGT](SETGT.html), or [SETLL](SETLL.html) operations. 

### See Also
[CHAIN](CHAIN.html)

[DCLKFLD](DCLKFLD.html)

[DELETE](DELETE.html)

[READE](READE.html)

[READPE](READPE.html)

[SETGT](SETGT.html)

[SETLL](SETLL.html)


