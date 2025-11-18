---
title: Properties and Property Procedures

Id: aerTourPropertiesandPropertyProcedures
TocParent: aerTourClassPropertiesFieldsandMethodsMain
TocOrder: 10


---

To store information in an object, you can use both properties and fields. Fields are simply public variables, properties use property procedures to control how values are set or returned. Property procedures are blocks of code declared within property definitions that allow you to execute code when a property value is set or retrieved. 

Encore RPG .NET has two commands for this: `BEGGET` command for retrieving a property value, and `BEGSET` command for assigning a value to a property. In short, property procedures allow an object to protect and validate its own data. 

The following code fragment shows using the `BEGGET` and `BEGSET` commands within a `BEGPROP`. 

```
DclFld hiddenField Type( *Integer ) Len( 4 ) Access( *Private )
BegProp BePositive Type( *Integer ) Len( 4 ) Access( *Public )
      BegGet
            LeaveSR hiddenField
      EndGet     
      BegSet 
            if (*PropVal > 0)
                  hiddenField = *PropVal
            else
                  hiddenField = -*PropVal
            endif

      EndSet
EndProp
```

### See Also
[Property Procedures vs. Fields](PropertyProceduresvsFields.html) 
