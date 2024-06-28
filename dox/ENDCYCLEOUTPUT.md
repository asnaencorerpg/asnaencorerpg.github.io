---
title: EndCycleOutput

Id: EndCycleOutput
TocParent: aerLrfOpCodesMain
TocOrder: 880


---

Defines the **end** of a **cycle's** print attributes. 

```

 **```EndCycleOutput```** 
        
```

### Remarks
```EndCycleOutput``` must be the **last** statement in a [BegCycleOutput](BegCycleOutput.html). The ```BegCycleOutput``` section of migrated code controls printing. Each ```HeadingPrintSpec```, ```DetailPrintSpec``` and ```TotalPrintSpec``` command contain the conditions in which each is printed. 

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
[BegCycleOutput](BegCycleOutput.html)

[DCLFMTCYCLEATTR](DCLDISKFILE.html)

[HeadingPrintSpec](HeadingPrintSpec.html)

[DetailPrintSpec](DetailPrintSpec.html)

[TotalPrintSpec](TotalPrintSpec.html) 
