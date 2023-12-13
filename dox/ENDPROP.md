---
title: ENDPROP

Id: ENDPROP
TocParent: aerLrfOpCodesMain
TocOrder: 900


---

**ENDPROP** identifies the ending of a property routine. 

```
ENDPROP 
        
```

### Remarks
**ENDPROP** must be the last statement within a property routine that is preceded with a [BEGPROP](BEGPROP.html). 

Note that if the **BEGPROP** is a (*GET) routine, then your subroutine must also contain a [LEAVESR](LEAVESR.html) before the **ENDPROP** , as shown in the example below. 

### Example

```
DclFld_Firstname   *string   INZ("")
DclFld_Lastname    *string   INZ(" ")

BegProp Firstname   *string   Access( *public )
   BegSet
      _FirstName = *Propval
   EndSet

   BegGet
      LeaveSr _FirstName
   EndGet
EndProp

BegProp Lastname   *string   Access( *public )
   BegSet NewValname( Lname )
      _LastName = Lname
   EndSet

   BegGet
      LeaveSr _LastName
   EndGet
EndProp

// Read only property
BegProp FullName Type( *string )  Access( *public )
   BegGet
      LeaveSR Value( FirstName + " " + LastName )
   EndGet
EndProp
```

### See Also
[BEGPROP](BEGPROP.html)

[LEAVESR](LEAVESR.html)

[ENDGET](ENDGET.html)

[ENDSET](ENDSET.html) 
