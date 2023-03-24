---
title: Handling Cycle Output to Database Files

Id: aerCycle_New_Output_Handling
TocParent: aerCycle_Overview
TocOrder: 20


---

A file may be program described or externally described; in either case, the program may be performing output operations on the file using O-Specs. These O-specs may be Except type (E) or Cycle type (D, H, T). 

As of version 7.0, ECR (and therefore Monarch) support "program described" database files via the <code>InputHandler</code> and <code>OutputHandler</code> keywords of the DclDiskFile. Print and Workstation files are only supported when they are externally described. 

For (externally described) printer files, ECR provides specialized constructs to handle the cycle type output, but there is no support for database cycle driven output. 

#### <a name="Design_Spec">Design Specification for Cycle Output</a>

1. Add new Commands, similar to those used with printer output, as follows:
                    <ol>
                        <li>
                            <code>BegCycleOutPut</code> (replaces <code>BegPrintAttr</code>)
2. <code>EndCycleOutput</code> (replaces <code>EndPrintAttr</code>)

Between these commands, a group of the following (also new) commands can be entered:

- <code>DetailPrintSpec</code>
- <code>HeaderPrintSpec</code>
- <code>TotalPrintSpec</code>
- <code>DetailPrintSpec</code>
- <code>TotalDiskSpec</code>

</li>
                <li>
                    <code>BegPrintAttr</code>, <code>EndPrintAttr</code>, <code>DetailSpec</code>,
                    <code>HeadingSpec</code> and <code>TotalSpec</code> are all now obsolete.
                </li>
                <li>The keywords for the <code> *Xxx* PrintSpec</code> are identical to their corresponding <code> *Xxx* Spec</code>.</li>
                <li>
                    The keywords for the <code> *Xxx* DiskSpec</code> are:

3. File &#8211; The File parameter can be a DiskFile or a Record Format of a DiskFile.
4. Cond (<code><u>*NONE</u></code>, Boolean Expression)
5. <code>Op(*ADD, *DELETE, *UPDATE)</code>
|
6. <code>Flds(*ALL, {names}+ )</code>

</li>
            </ol>

#### <a name="Example">Example</a>
Instead of this:
<div>
<pre>
BEGPRINTATTR    
   headingspec   CpyHdr   cond(*in1p *or *inOF)        
   headingspec   OrdHdr   cond(*in77) fetchOverflow(*yes)    
   headingspec   DetdHdr  cond(*in77) fetchOverflow(*yes)    
   detailspec    PDetail  cond(*in42) fetchOverflow(*yes)    
   totalspec     DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)    
   totalspec     BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)    
   detailspec    PBo      cond(*in43) fetchOverflow(*yes)    
   totalspec     BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes)    
   totalspec     BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)    
   totalspec     OrdTot   cond(*inL2) fetchOverflow(*yes) 
ENDPRINTATTR  
</pre>

This can now be used:
<pre>
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
</pre>

Developers can also mix print and database specs: 
<pre>
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
EndCycleOutput</pre>

