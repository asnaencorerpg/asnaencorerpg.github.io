---
title: Matching Record Indicator (*INMR)"

Id: aerCycle_MatchingRecordIndicators
TocParent: aerCycle_Overview
TocOrder: 10


---

To support the RPG cycle in Monarch migrated applications, the Encore RPG compiler has predefined the matching record indicator ```*INMR```. This matching record indicator will be migrated as such, and does not need to be explicitly declared. 

- ```*INMR```

### Remarks
<dl class="normal">

Statements in a file are conditioned on the
                following:

1. The kind of record read.

2. The Level Break indicator.

3. The Matching Record indicator.

4. The Printer Overflow indicator.

**Matching Record Fields** 

You can specify up to 9 field(s) that are defined as the "control"
                matching field is read from the buffer.  You can specify up to 9
                different fields, or levels using [DclFmtCycleAttr](DCLFMTCYCLEATTR.html).   These are defined
                as ```M1 .... M9```.  When the field is different, a level
                break occurs, and the defined level indicators are set; thus the calculations
                totals and output is printed.

When a level indicator gets turned on, then all level indicators
                underneath that level will turn on as well.


The following image shows the Matching Record field as ```M1``` is defined by ```Item#```; ```OOItem#``` and ```DOrder#``` and ```BOOrder#```. 


![](Images/Level_Break.jpg" border="0) 


#### Code Example

```
BegClass MyCycleProgram Access ( *Public )
      ...
      dclDiskFile Order Type ( *input ) Designation ( *primary ) ...    
      dclDiskFile Detail Type ( *input ) Designation ( *secondary ) ...        
      dclDiskFile BackOrder Type ( *input ) Designation ( *secondary ) ... 
      dclPrintFile OrderRpt OverflowInd (*INOF) ... 
      DclFmtCycleAttr ROrder      *in77 M1 (OOrder#)   L2 (OOrder#)
      DclFmtCycleAttr RDetail     *in42 M1 (DOrder#) 
      DclFmtCycleAttr RBackOrder *in43 M1 (BOOrder#)  L1 (BOOrder#,BOItem#) 
      BEGCYCLEOUTPUT
            headerprintspec rptHeader cond (*in1p *or *inOF) 
            detailprintspec rptDetail fetchOverflow ( *yes ) cond (*inL1)
            totalprintspec rptTotal fetchOverflow ( *yes ) cond (*inl2) 
      ENDCYCLEOUTPUT \aerLrfDatabaseMembers.htm 

      Begsr Main shared ( *yes ) access ( *public )  
            dclsrparm args type ( *string ) rank (1) 
            dclfld pgm Type (MyCycleProgram) new () 
            pgm.*StartCycle() 
            Close pgm.CustRpt 
            Console.ReadLine() 
      endsr 

      BegSr *DetailCalc 
            if *inMR  
                  ... 
            endif 
      EndSr 

      BegSr *TotalCalc 
            if *inL1
                  ... 
            endif 
      EndSr 
EndClass  

```

#### See Also
[Cycle Overview](aerCycle_Overview.html)
[DclFmtCycleAttr](DCLFMTCYCLEATTR.html)
[Level Break Indicators](aerCycle_LevelBreakIndicators.html) 
