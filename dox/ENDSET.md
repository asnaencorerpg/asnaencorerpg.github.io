---
title: ENDSET

Id: ENDSET
TocParent: aerLrfOpCodesMain
TocOrder: 910


---

Terminates a [BEGSET](BEGSET.html) property procedure.

```

 **ENDSET** 
        
```

### Remarks
An **ENDSET** routine **must** begin with a **BEGSET** .

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
[BEGGET](BEGGET.html)

[BEGSET](BEGSET.html)

[ENDGET](ENDGET.html) 
