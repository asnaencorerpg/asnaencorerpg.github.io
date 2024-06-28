---
title: HeadingPrintSpec

Id: HeadingPrintSpec
TocParent: aerLrfOpCodesMain
TocOrder: 1120


---

**HeadingPrintSpec** is migrated and defines the Heading specs of a print file. It is generated in place of an O-Specs specified with an "H", and placed after a [BegCycleOutput](BegCycleOutput.html); one for each heading. 

```
HeadingPrintSpec 
 Fmt (Format name) 
Cond (Conditional indicator)
FetchOverflow (<u>*No</u>  | *Yes)      
```

### Parts

**Fmt** 

Required. Contains the name of the record format containing the header.


**Cond** 

Optional. Contains the conditional indicators. More than 1 condition can be specified using * **And** , and/or * **Not** between.


**FetchOverflow** 

Optional. Indicates if the page is full and has reached overflow. Only the overflow lines for the file are checked for output. All total lines conditioned by the overflow indicator is written.


### Example

```
BegCycleOutput
   HeadingPrintSpec   CpyHdr   cond(*in1p *or *inOF)    
   HeadingPrintSpec   OrdHdr   cond(*in77) fetchOverflow(*yes)
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

[DetailPrintSpec](DetailPrintSpec.html) 

[EndCycleOutput](EndCycleOutput.html) 

[TotalPrintSpec](TotalPrintSpec.html) 
