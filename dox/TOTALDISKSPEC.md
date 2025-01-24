---
title: TotalDiskSpec

Id: TotalDiskSpec
TocParent: aerLrfOpCodesMain
TocOrder: 1555


---

**TotalDiskSpec** is migrated and defines the Heading specs of a print file. It is generated in place of an O-Specs specified with an "H", and placed after a [BegCycleOutput](BegCycleOutput.html); one for each heading. 

```
TotalDiskSpec 
 Fmt (Format name) 
Cond (Conditional indicator)
FetchOverflow (<u>*No</u>  | *Yes)
```

### Parameters

**Fmt** 

Required. Contains the name of the record format containing the header.


**Cond** 

Optional. Contains the conditional indicators. More than 1 condition can be specified using * **And** , and/or * **Not** between.


**FetchOverflow** 

Optional. Indicates if the page is full and has reached overflow. Only the overflow lines for the file are checked for output. All total lines conditioned by the overflow indicator are rewritten.


### Example

```

BegCycleOutput
   HeadingPrintSpec   CpyHdr   cond(*in1p *or *inOF)    HeadingPrintSpec   OrdHdr   cond(*in77) fetchOverflow(*yes)
   HeadingPrintSpec   DetdHdr  cond(*in77) fetchOverflow(*yes)
   DetailPrintSpec    PDetail  cond(*in42) fetchOverflow(*yes)
   TotalDiskSpec     DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)
   TotalDiskSpec     BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)
   DetailPrintSpec    PBo      cond(*in43) fetchOverflow(*yes)
   TotalDiskSpec     BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes)
   TotalDiskSpec     BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)
   TotalDiskSpec     OrdTot   cond(*inL2) fetchOverflow(*yes)
EndCycleOutput  
```

### See Also
[BegCycleOutput](BegCycleOutput.html) 

[DCLFMTCYCLEATTR](DCLDISKFILE.html) 

[EndCycleOutput](EndCycleOutput.html) 

[HeadingPrintSpec](HeadingPrintSpec.html) 

[DetailPrintSpec](DetailPrintSpec.html) 
