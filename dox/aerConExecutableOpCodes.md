---
title: Executable Operation Codes

Id: aerConExecutableOpCodes
TocParent: aerConOpCodes
TocOrder: 3


---

An executable command initiates action by executing a method. It can loop or branch through blocks of code. Executable commands often contain mathematical or conditional operators. 

The following example uses an **If...Then...Else** command to execute different blocks of code based on the value of a variable. 

```
BegSr StartCounter
   DCLFLD counter Type (*Integer)
   If clockwise = *True
      Then .....
        .............
      Else
        ....................
        ..................
        ...........
   EndIf
EndSr
```

The **If...Else** command block always end with an **EndIf** .

### See Also
[Operation Codes Overview](aerConOpCodesOverview.html)

[Assignment Operation Codes](aerConAssignmentOpCodes.html)

[Declaration Operation Codes](aerConDeclarationOpCodes.html) 
