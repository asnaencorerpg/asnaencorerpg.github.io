---
title: BEGPRINTATTR

Id: BEGPRINTATTR
TocParent: aerLrfOpCodesMain
TocOrder: 100


---

Defines the beginning of a **cycle's** print attributes. 

```
 **BEGPRINTATTR**    
```

### Remarks
The **BEGPRINTATTR** section contains OSpecs, which are printed during the cycle output phases. **HEADINGSPEC** s and **DETAILSPEC** s are written in the order they are specified during detail output. **TOTALSPEC** s are similarly written during total output. **EXCEPTSPEC** s are used for exception records which are conditioned on the Overlfow indicator. 

The **BEGPRINTATTR** section must end with an [ENDPRINTATTR](BEGPRINTATTR.html). 

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
[DCLFMTCYCLEATTR](DCLFMTCYCLEATTR.html)
[ENDPRINTATTR](ENDPRINTATTR.html)
[HEADINGSPEC](HEADINGSPEC.html)
[DETAILSPEC](DETAILSPEC.html)
[TOTALSPEC](TOTALSPEC.html)
[EXCEPTSPEC](EXCEPTSPEC.html) 
