---
title: BegCycleOutput

Id: BegCycleOutput
TocParent: aerLrfOpCodesMain
TocOrder: 100


---

Defines the beginning of a **cycle's** print attributes. 

```
BegCycleOutput    
```

### Remarks
The **BegCycleOutput** section contains OSpecs, which are printed during the cycle output phases. **HeadingPrintSpec** s and **DetailPrintSpec** s are written in the order they are specified during detail output. **TotalPrintSpec** s are similarly written during total output.

The **BegCycleOutput** section must end with an [EndCycleOutput](EndCycleOutput.html). 

### Example

```
BegCycleOutput
   HeadingPrintSpec   CpyHdr   cond(*in1p *or *inOF)    HeadingPrintSpec   OrdHdr   cond(*in77) fetchOverflow(*yes)
   HeadingPrintSpec   DetdHdr  cond(*in77) fetchOverflow(*yes)
   DetailPrintSpec    PDetail  cond(*in42) fetchOverflow(*yes)
   TotalPrintSpec     DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)
   TotalPrintSpec     BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)
   DetailPrintSpec    PBo      cond(*in43) fetchOverflow(*yes)
   TotalPrintSpec     BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes)
   TotalPrintSpec     BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)
   TotalPrintSpec     OrdTot   cond(*inL2) fetchOverflow(*yes)
EndCycleOutput 
```

### See Also
[DCLFMTCYCLEATTR](DCLFMTCYCLEATTR.html)

[EndCycleOutput](EndCycleOutput.html)

[HeadingPrintSpec](HeadingPrintSpec.html)

[DetailPrintSpec](DetailPrintSpec.html)

[TotalPrintSpec](TotalPrintSpec.html)
