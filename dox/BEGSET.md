---
title: BEGSET

Id: BEGSET
TocParent: aerLrfOpCodesMain
TocOrder: 130


---

Declares a **SET** property procedure used to assign a value to a property. 

```
BEGSET   
NewValName (Name)
```

### Parameters

**NewValName** 

Optional. A user-given name for the property value being passed. If **NewValName** is not given, the received value is in a parameter with the special name *PROPVAL.


### Remarks
**BEGSET**  allows you to Set the value of the property. To **Get** the value of a property, use [BEGGET](BEGGET.html).  A **BEGSET**  routine must always end with an [ENDSET](ENDSET.html).

### Example

```
dclfld _FirstName *string INZ("")
dclfld _LastName  *string INZ("")       

BegProp Firstname *string Access( *public)
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
[BEGGET](BEGGET.html)

[BEGPROP](BEGPROP.html)

[ENDGET](ENDGET.html)

[ENDSET](ENDSET.html) 
