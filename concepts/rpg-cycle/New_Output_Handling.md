---
title: Handling Cycle Output

Id: aerCycle_New_Output_Handling
TocParent: aerCycle_Overview
TocOrder: 20


---

A file may be program described or externally described; in either case, the program may be performing output operations on the file using O-Specs. These O-specs may be Except type (E) or Cycle type (D, H, T). 

ECR supports program described database files via the ```InputHandler``` and ```OutputHandler``` keywords of the DclDiskFile command. Print and Workstation files are only supported when they are externally described. 

For Cycle output, ECR provides specialized constructs. 

#### <a name="Design_Spec">Design Specification for Cycle Output</a>

1. Add a Cycle Output block:
```
BegCycleOutput
   ...
EndCycleOutput
```

2. Between these commands, one or more of the following commands can be entered:

- ```DetailPrintSpec```
- ```HeadingPrintSpec```
- ```TotalPrintSpec```
- ```DetailDiskSpec```
- ```TotalDiskSpec```

#### <a name="Example">Example</a>

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

Developers can also mix print and disk file specs:

```
BegCycleOutput    
   DetailDiskSpec     MyDBFile cond(*in02)     
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
   DetailDiskSpec     DBFile2  cond(*in02) Op(*Delete)    
   DetailDiskSpec     DBFile3  cond(*in02) Op(*Update)    
   DetailDiskSpec     MYFMT    Op(*Update) Flds(Fld1, Fld2)    
   TotalDiskSpec      MasteF   cond(*inL1 *and LastInd) Op(*Add) 
EndCycleOutput
```

