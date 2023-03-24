---
title: EXCEPTSPEC

Id: EXCEPTSPEC
TocParent: aerLrfOpCodesMain
TocOrder: 1000


---

**EXCEPTSPEC** marks an exception format that is conditioned on the printfile's overflow indicator. It will be written out during execution of [*FetchOverflow](aerCycle_FetchOverflowMethod.html) method if the file's overflow indicator is *ON. 

```

 **EXCEPTSPEC** 
 **Fmt (Format name)** 
        
```

### Parts

**Fmt** 

Required. Contains the name of the record format containing the detail lines.


### Remarks
Use an **EXCEPTSPEC** when an exception record is conditioned on the file's overflow indicator.

### Example

```
BEGPRINTATTR
   exceptspec TotLine ENDPRINTATTR
```

### See Also
[*FetchOverflow Method](aerCycle_FetchOverflowMethod.html)

[BEGPRINTATTR](BEGPRINTATTR.html)

[DCLFMTCYCLEATTR](DCLDISKFILE.html)

[ENDPRINTATTR](ENDPRINTATTR.html)

[HEADINGSPEC](HEADINGSPEC.html)

[DETAILSPEC](DETAILSPEC.html)

[TOTALSPEC](TOTALSPEC.html)
