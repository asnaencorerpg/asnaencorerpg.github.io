---
title: Declaration Operation Codes

Id: aerConDeclarationOpCodes
TocParent: aerConOpCodes
TocOrder: 2


---

 Declaration operation codes are used to name and define subroutines, variables, arrays, and constants. When you declare a procedure, variable, or constant, you also define its **access** , depending upon where you place the declaration and what keywords you use to declare it. 

A declaration operation code reserves the memory needed to create a variable, but does not explicitly create it. You can explicitly create a variable and assign it a value at the same time by using the following syntax: 

```
// MyField is created and assigned the initial value 45.
```
        
```
DCLFLD Name( MyField ) Type (*Integer) Len( 2) Inz( 45 )  
```

If your variable is an object variable, you can explicitly create an instance of its class when you declare it by using the ```New``` keyword, as illustrated below: 

```
 DclFld TheOtherForm Type( Form2 ) New( *Dft )
```

**The following is a listing of declaration operation codes and those that allow you to specify an access type** . 

- [BEGCLASS](BEGCLASS.html)
- [BEGCONSTRUCTOR](BEGCONSTRUCTOR.html)
- [BEGENUM](BEGENUM.html)
- [BEGFUNC](BEGFUNC.html)
- [BEGINTERFACE](BEGINTERFACE.html)
- [BEGPROP](BEGPROP.html)
- [BEGSR](BEGSR.html)
- [DCLALIAS](DCLALIAS.html)
- [DCLARRAY](DCLARRAY.html)
- [DCLCONST](DCLCONST.html)
- [DCLDB](DCLDB.html)
- [DCLDISKFILE](DCLDISKFILE.html)
- [DCLDS](DCLDS.html)
- [DCLEVENT](DCLEVENT.html)
- [DCLFLD](DCLFLD.html)
- [DCLMEMORYFILE ](DCLMEMORYFILE.html)
- [DCLSUBFILE](DCLSUBFILE.html)
- [DCLSUBFILEFLD ](DCLSUBFILEFLD.html)
- [DCLWORKSTNFILE](DCLWORKSTNFILE.html)

### See Also
[Declaring Elements](ecrConDeclaredElements.html) 
