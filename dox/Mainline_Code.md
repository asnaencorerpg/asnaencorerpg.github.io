---
title: Mainline Code

Id: Mainline_Code
TocParent: aerLrfLangElementsMain
TocOrder: 0


---

The `Main` procedure, or `mainline code` is the "starting point" for your application, or the first procedure that is accessed when you run your code. `Main` is where you would put the code that needs to be accessed first, and are not part of any subroutine, such as [Declarations](Declarations.html). 

In `Main`, you can determine:

- Which form is loaded first when the program is started
- Find out if a copy of your application is already running on the system
- Establish a set of variables for your application
- Open a database that the application requires

`Main` <u> **must be** </u> either a [BEGSR](BEGSR.html) or a [BEGFUNC](BEGFUNC.html) with `*Integer4` type, such as: 

```
BegFunc Main Type( *Integer4 ) Access( *Public ) Shared( *Yes ) 
``` 

> If `Type` is not `*Integer4` you will receive a compiler error stating "Main not found". 

It may have one [DCLSRPARM](DCLSRPARM.html), and the type of the parm <u> **must be** </u> a `*String Rank(1)` Array .

```
DclSrParm Args Type( *string ) Rank( 1 )
```

### See Also

[BEGFUNC](BEGFUNC.html)

[BEGSR](BEGSR.html)

[DCLSRPARM](DCLSRPARM.html)

[Declarations](Declarations.html)

[General Subroutines](General_Subroutines.html) 
