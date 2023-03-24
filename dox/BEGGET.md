---
title: BEGGET

Id: BEGGET
TocParent: aerLrfOpCodesMain
TocOrder: 80


---

Declares a **GET** property procedure used to assign a value to a property. 

```

 **BEGGET** 
        
```

### Remarks

 **BEGGET**  allows you to get the value of the property with
        the [BEGPROP](BEGPROP.html) routine.
        To set the value of a property, use [BEGSET](BEGSET.html). A **BEGGET** routine
        must always end with an [ENDGET](ENDGET.html),
        and **BEGSET**  must always end with an [ENDSET](ENDSET.html).



### Example

```
dclfld_Firstname    *string           INZ("")
dclfld_Lastname     *string           INZ("")        
 BegProp Firstname    *string           Access( *public )
         BegSet
               _FirstName = *Propval
         EndSet

         BegGet
               LeaveSR _FirstName
         EndGet
 EndProp 
 BegProp Lastname     *string           Access( *public )
         BegSet NewValname( Lname )
              _LastName = Lname
         EndSet

         BegGet
              LeaveSR _LastName
         EndGet
 EndProp
 // Read only property
 BegProp FullName Type( *string )       Access ( *public )
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
