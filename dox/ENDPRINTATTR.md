---
title: ENDPRINTATTR

Id: ENDPRINTATTR
TocParent: aerLrfOpCodesMain
TocOrder: 880


---

Defines the **end** of a **cycle's** print attributes. 

```

 **```ENDPRINTATTR```** 
        
```

### Remarks
``` **ENDPRINTATTR** ``` must be the **last** statement in a [BEGPRINTATTR](BEGPRINTATTR.html). The ``` **BEGPRINTATTR** ``` section of migrated code controls printing. Each ```HeadingSpec```, ```DetailSpec``` and ```TotalSpec``` command contain the conditions in which each is printed. 

### Example

```
BEGPRINTATTR
   headingspec   CpyHdr   cond(*in1p *or *inOF)    headingspec   OrdHdr   cond(*in77) fetchOverflow(*yes)
   headingspec   DetdHdr  cond(*in77) fetchOverflow(*yes)
   detailspec    PDetail  cond(*in42) fetchOverflow(*yes)
   totalspec     DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)
   totalspec     BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)
   detailspec    PBo      cond(*in43) fetchOverflow(*yes)
   totalspec     BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes)
   totalspec     BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)
   totalspec     OrdTot   cond(*inL2) fetchOverflow(*yes)
ENDPRINTATTR
```

### See Also
[BEGPRINTATTR](BEGPRINTATTR.html)
[DCLFMTCYCLEATTR](DCLDISKFILE.html)
[HEADINGSPEC](HEADINGSPEC.html)
[DETAILSPEC](DETAILSPEC.html)
[TOTALSPEC](TOTALSPEC.html) 
