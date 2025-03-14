---
title: DCLFMTCYCLEATTR

Id: DCLFMTCYCLEATTR
TocParent: aerLrfOpCodesMain
TocOrder: 480


---

**DclFmtCycleAttr** is used to declare every format participating in the RPG Cycle. It specifies which indicator will be turned on when the cycle reads a record of that particular format, and which fields participate in level breaks (also known as control breaks) or matching records. 

```
DclFmtCycleAttr 
Fmt (Format name)
 Ind (Indicator)  
 L1 (...)
 ...
 L9 (...)
 M1 (...)
 ...
 M9 (...) 
```

### Parameters

**Fmt** 

Required. Contains the name of the record format of the records to read in the RPG cycle; and whose fields contain level breaks or matching records.


**Ind** 

Optional. Contains the indicator to turn on when a record of this kind is read.


**L1 through L9** 

Optional. Indicate which fields will cause a level break of that number. More than one field can be listed in each. These are defined in **L1 .... L9** . When the field is different, a level break occurs, and the defined level indicators are set; thus the calculations totals and output is printed. When a level indicator gets turned on, then all level indicators underneath that level will turn on also.


**M1 through M9** 

Optional. Matching record fields indicate which fields participate in matching records. These are defined in **M1 .... M9** . Only one field can be listed in each.


A field name cannot appear in more than one **L** and in more than one **M** parameter.


### Remarks
Every format in a file participating on the cycle must have a corresponding **DclFmtCycleAttr** command. It specifies which indicator will be turned on when the cycle reads a record of that particular format, and which fields participate in level breaks (also known as control breaks) or matching records. 

The level break fields listed in **L1** through **L9** indicate which fields will cause a level break of that number. More than one field can be listed in each. 

The matching record fields indicate which fields participate in matching records. Only one field can be listed in each. A field name cannot appear in more than one **L** and in more than one **M** parameter. 

### Example

```
DclFmtCycleAttr RMaster   *in77 M1(RMOrder#) L2(RMOrder#)
	DclFmtCycleAttr RDetail   *in42 M1(RDOrder#)
        DclFmtCycleAttr RBoOrders *in43 M1(RBOrder#) L1(RBOrder#, RBItem#)
```

### See Also
[BegCycleOutput](BegCycleOutput.html)

[Cycle Overview](/concepts/rpg-cycle/Overview.html) 

[DclFmtCycleAttr](DCLFMTCYCLEATTR.html)

[Level Break Indicators](/concepts/rpg-cycle/LevelBreakIndicators.html) 

[Matching Record Indicators](/concepts/rpg-cycle/MatchingRecordIndicators.html) 
