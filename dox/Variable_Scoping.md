---
title: Global Scope

Id: Variable_Scoping
TocParent: aerLrfVariablesMain
TocOrder: 5


---

**Variables** can be global to the program or local to a subroutine. 

#### Global Variables
Any field defined with a [DCLFLD](DCLFLD.html), [DCLDS](DCLDS.html), [DCLDSFLD](DCLDSFLD.html) and [DCLARRAY](DCLARRAY.html) in the "mainline code" (not contained between [BEGSR](BEGSR.html) and [ENDSR](ENDSR.html)) is globally defined for the entire Program. 

Any field defined implicitly in code anywhere in the program is globally defined for the entire program. 

Global variables can be of most any type. For example, you can have and access a global array data structure, file, or scalar (packed, char, or zoned field) all from a second program. 

Any name used without a previous definition gets implicitly declared with a global scope. 

#### Local Variables
Any field defined with a **DCLFLD** , **DCLDS** , **DCLDSFLD** and **DCLARRAY** within a subroutine (i.e., between **BEGSR** and **ENDSR** ) is defined locally to that subroutine only. 

Such definition strategies can make pre-written subroutines completely insular from the remaining code in a program. This allows subroutines written in this manner to be copied into a program without affecting declarations anywhere else in the program. If the subroutine uses indicators, it is only a simple matter to save the status of the indicators in locally defined fields upon entry to the subroutine, then restoring them to their original status upon exiting. 

A local variable hides the global one. A local variable exists from the point of its definition to the end of the subroutine. To define a local variable, any of the following commands can be used: **DCLARRAY** , **DCLDS** , **DCLFLD** . 

### Remarks
A local variable can not be defined in the equivalent of an old "C" spec. 

### See Also
[Variables](ecrLrfVariablesMain.html)

[DCLARRAY](DCLARRAY.html)

[DCLDS](DCLDS.html)

[DCLDSFLD](DCLDSFLD.html)

[DCLFLD](DCLFLD.html)

[BEGSR](BEGSR.html)

[ENDSR](ENDSR.html) 
