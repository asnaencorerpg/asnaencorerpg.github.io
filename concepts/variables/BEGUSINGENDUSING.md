---
title: BegUsing/EndUsing Blocks

Id: /concepts/variables/BEGUSINGENDUSING
TocParent: aerConObjectVariableDeclaration
TocOrder: 120


---

The BegUsing/EndUsing block provides a convenient way to use `IDisposable` objects correctly. Its syntax is: 

```
   BegUsing Name(<variable name>)
   Type(<object type>) Value(<expression>) 
      .
      .
      . 
   EndUsing
```

The `Name` parameter is required. Name specifies the name of a property or field, visible in the scope and declared with the proper type. You can specify `Type` instead if this is a new name in the scope (keep in mind that this declaration is valid in the whole method body). 

The type must be a class or interface that implements `IDisposable`. If given, `Value` specifies the expression to be evaluated and assigned to `Name`; otherwise `Name` should already have a value. When execution reaches the end of the `BegUsing` block, the variable will be disposed and set to `*Nothing` to prevent its (invalid) usage outside the block. 

```
BegUsing 
	  myFld type(myDisposableClass) value(*new myDisposableClass()) 
       .
       .
       .  
	  EndUsing
```

Is equivalent to:
        
```        
    DclFld myFld type(myDisposableClass) 
    myFld = *new myDisposableClass() 
    
    Try 
       .
       .
       . 
    Finally 
       If myFld <> *nothing 
          myFld.Dispose() 
          myFld = *nothing 
       EndIf
    EndTry
```

> Warning:  `BegUsing/EndUsing` blocks are only to be used with `IDisposable` Objects. 


### See Also

[DCLPROP](/dox/DCLPROP.html)

[BEGSR](/dox/BEGSR.html)

[Custom Attributes](/concepts/assemblies/CustomAttributes.html)

[DCLSRPARM](/dox/DCLSRPARM.html)

[ENDPROP](/dox/ENDPROP.html)

[LEAVESR](/dox/LEAVESR.html) 
