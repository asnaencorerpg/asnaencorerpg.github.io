---
title: DETAILSPEC

Id: DETAILSPEC
TocParent: aerLrfOpCodesMain
TocOrder: 660


---

**DETAILSPEC** represents an OSpec that is written by the cycle during detail output time. 

```

 **DETAILSPEC** 
 **Fmt (Format name)** 
Cond (Conditional indicator)
FetchOverflow (<u>*No</u>  | *Yes)
```

### Parts

**Fmt** 

Required. Contains the name of the record format containing the detail lines.


**Cond** 

Optional. Contains the conditional indicators. More than 1 condition can be specified using * **And** , and/or * **Not** between.


**FetchOverflow** 

Optional. Indicates whether the *FetchOverflow routine is called before printing this OSpec.


### Example

```
BEGPRINTATTR
   headingspec CpyHdr	cond(*in1p *or *inOF)  
   headingspec OrdHdr   cond(*in77) fetchOverflow(*yes)
   headingspec DetdHdr  cond(*in77) fetchOverflow(*yes)
   detailspec  PDetail  cond(*in42) fetchOverflow(*yes)
   totalspec   DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)
   totalspec   BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)
   detailspec  PBo      cond(*in43) fetchOverflow(*yes)
   totalspec   BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes) 
   totalspec   BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)
   totalspec   OrdTot   cond(*inL2) fetchOverflow(*yes)
ENDPRINTATTR
```

<div>

### See Also
[BEGPRINTATTR](BEGPRINTATTR.html)

[DCLFMTCYCLEATTR](DCLFMTCYCLEATTR.html)

[ENDPRINTATTR](ENDPRINTATTR.html)

[HEADINGSPEC](HEADINGSPEC.html)

[TOTALSPEC](TOTALSPEC.html) 

[EXCEPTSPEC](EXCEPTSPEC.html) 
