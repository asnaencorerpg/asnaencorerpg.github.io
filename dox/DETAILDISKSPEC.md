---
title: DetailDiskSpec

Id: DetailDiskSpec
TocParent: aerLrfOpCodesMain
TocOrder: 655


---

**DetailDiskSpec** represents an OSpec that is written by the cycle during detail output time. 

```
DetailDiskSpec 
 Fmt (Format name) 
 Cond (Conditional indicator)
 FetchOverflow (<u>*No</u>  | *Yes)
```

### Parameters

**Fmt** 

Required. Contains the name of the record format containing the detail lines.


**Cond** 

Optional. Contains the conditional indicators. More than 1 condition can be specified using * **And** , and/or * **Not** between.


**FetchOverflow** 

Optional. Indicates whether the *FetchOverflow routine is called before printing this OSpec.


### Example

```
BegCycleOutput
   HeadingPrintSpec CpyHdr	cond(*in1p *or *inOF)  
   HeadingPrintSpec OrdHdr   cond(*in77) fetchOverflow(*yes)
   HeadingPrintSpec DetdHdr  cond(*in77) fetchOverflow(*yes)
   DetailDiskSpec  PDetail  cond(*in42) fetchOverflow(*yes)
   TotalPrintSpec   DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)
   TotalPrintSpec   BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)
   DetailDiskSpec  PBo      cond(*in43) fetchOverflow(*yes)
   TotalPrintSpec   BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes) 
   TotalPrintSpec   BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)
   TotalPrintSpec   OrdTot   cond(*inL2) fetchOverflow(*yes)
EndCycleOutput
```

<div>

### See Also
[BegCycleOutput](BegCycleOutput.html)

[DCLFMTCYCLEATTR](DCLFMTCYCLEATTR.html)

[EndCycleOutput](EndCycleOutput.html)

[HeadingPrintSpec](HeadingPrintSpec.html)

[TotalPrintSpec](TotalPrintSpec.html) 

