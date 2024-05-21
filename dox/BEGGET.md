---
title: BEGGET

Id: BEGGET
TocParent: aerLrfOpCodesMain
TocOrder: 80


---

Declares a **GET** property procedure used to retrieve the value of a property. 

```
BEGGET 
        
```

### Remarks

The **BEGGET** method within a [BEGPROP](BEGPROP.html) block allows you to get the value of the property. A **BEGGET** routine must always end with an [ENDGET](ENDGET.html).


### Example

```
dclfld _FirstName *string INZ("")
dclfld _LastName  *string INZ("")

BegProp Firstname *string Access( *public )
    BegSet
        _FirstName = *Propval
    EndSet
    BegGet
        LeaveSR _FirstName
    EndGet
EndProp 

BegProp Lastname *string Access( *public )
    BegSet NewValname( Lname )
        _LastName = Lname
    EndSet
    BegGet
        LeaveSR _LastName
    EndGet
EndProp

 // Read only property

BegProp FullName Type( *string ) Access( *public )
    BegGet
        LeaveSR Value( FirstName + " " + LastName )
    EndGet
EndProp

```

### See Also
[BEGPROP](BEGPROP.html)

[BEGSET](BEGSET.html)

[ENDGET](ENDGET.html)

[ENDSET](ENDSET.html)
