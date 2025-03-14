---
title: Overflow Indicators

Id: aerCycle_OverflowIndicators
TocParent: aerCycle_Overview
TocOrder: 20


---

To support the RPG cycle in Monarch migrated applications, the Encore RPG compiler has predefined the following print file overflow indicators that are used with the ```OverflowInd``` parameter of [DCLPRINTFILE](DetailCalcMethod.html). For example, these overflow indicators will be migrated as such, and do not need to be explicitly declared. 

- ```*INOA, *INOB, *INOC```, ... through ```*INOG```
- ```*INOV```

### Remarks
<dl class="normal">

Since you do not need to declare your overflow indicator, Monarch will migrate
                the code as follows:

**Previously** 

        
```
   DclFld IndicatorOF Type(* Ind ) 
   DclPrintFile QPRINT DB(MyJob.MyPrinterDB) File("A\CYCL_PRT_3") ImpOpen(*No) OverflowInd(IndicatorOF) 
```

 **Now:** 
        
```
  DclPrintFile QPRINT DB(MyJob.MyPrinterDB) File("A\CYCL_PRT_3") ImpOpen(*No) OverflowInd(*INOF) 
```

#### See Also
[Cycle Overview](Overview.html)

[DCLPRINTFILE](/dox/DCLPRINTFILE.html)

[Level Break Indicators](LevelBreakIndicators.html)

[Matching Record Indicators](MatchingRecordIndicators.html) 
