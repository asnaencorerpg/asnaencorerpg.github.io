---
title: Level Break Indicator (*INL1...*INL9)

Id: aerCycle_LevelBreakIndicators
TocParent: aerCycle_Overview
TocOrder: 0


---

To support the RPG cycle in Monarch migrated applications, the Encore RPG compiler has predefined the following print file level break indicators. For example, these level break indicators will be migrated as such, and do not need to be explicitly declared. 

- ```*INL1, *INL2```, ... through ```*INL9```

### Remarks
<dl class="normal">

Statements in a file are conditioned on the
                following:

1. The kind of record read.

2. The Level Break indicator.

3. The Matching Record indicator.

4. The Printer Overflow indicator.

Perform a level break any time you want "Total time"
                to occur.  When a level break occurs, the field from the currently
                selected record is compared with the previous field buffer.  If they are
                different, the current field is saved, and the level indicator is set. 
                At this time, the Totals will occur.

There are 4 routines that can cause a level break:

- Total time printing

- Detail time

- Calculation

- Printing

**Level Break Fields** 

You can specify up to 9 field(s) that are
                defined as the "control" field is read from the buffer.  You can specify
                up to 9 different fields, or levels using [DclFmtCycleAttr](/dox/DCLFMTCYCLEATTR.html).  
                These are defined as **L1 .... L9** .  When the
                field is different, a level break occurs, and the defined level indicators are
                set; thus the calculation totals and output are printed.

When a level indicator gets turned on, all level
                indicators underneath that level will turn on also.

To perform calculations, you want to know when you're moving from 1 line to another. As in the following example: 

- if ```Item#``` changes (```BOItem#```), then you want to print order and backorder changes. 

- if ```Order#``` changes, then you want to print the Invoice total for that ```Order#```. 

The following image shows the level break fields defined for L1 is defined by ```BOItem#``` and ```BOOrder#```; and L2 is ```OOrder#```. 


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
      BegCycleOutput 
            HeadingPrintSpec rptHeader cond (*in1p *or *inOF) 
            DetailPrintSpec rptDetail fetchOverflow ( *yes ) cond (*inL1)
            TotalPrintSpec rptTotal fetchOverflow ( *yes ) cond (*inl2) 
      EndCycleOutput

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

### See Also
[Matching Record Indicators](MatchingRecordIndicators.html)

[Cycle Overview](Overview.html)

[DclFmtCycleAttr](/dox/DCLFMTCYCLEATTR.html)<br /><br /> 
