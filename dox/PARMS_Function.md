---
title: "%PARMS Function"

Id: PARMS_Function
TocParent: Functions_overview
TocOrder: 35


---

**%PARMS** [built-in function](Functions_overview.html) returns the number of procedure parameters that were received inside of a [BEGPROC](BEGPROC.html) procedure. 

```

 **%PARMS** 
        
```

### Remarks
To support **Procedure** parameters, the **DclSrParm** command has an **OPTIONS** keyword. It is **only** valid in **BegProc** subroutines, and it may contain * **OMIT** and/or * **NOPASS** . Please see **DclSrParm** for further information. 

Use the [%OMITTED](OMITTED_Function.html) function to know whether a parameter defined with **Options (*OMIT)** contains a valid value. 

**Note** % **PARMS** and % **IsOmitted** functions are only valid inside a **BEGPROC** procedure. Also, % **IsOmitted** is only valid on parameters that have the * **Omit** option. 

### Example

```
BegProc *ENTRY Access(*Public)

    DclSrParm CustName 
    DclSrParm CustAddress
    DclSrParm CustPhone Options(*NoPass)
    . . .

// Get the Phone Number

   If (%Parms = 3)

// if we are here, it means that CustPhone was passed

   EndIf
   . . .

EndProc

// Check the Location of a Customer

BegProc CheckLocation Access(*Public)
   DclSrParm CustZip Options(*Omit) 
   DclSrParm CustState Options(*Omit, *NoPass)
    . . .

// Get the Zip Code

   If not %OMITTED(CustZip)

// we have a valid zip code
// Get the State

   If(%Parms=2)

// if we are here, CustState was passed, but it may be omitted

      If not %OMITTED(CustState)

// we have a valid State

      EndIf  
   EndIf
  . . .      
EndProc  			
```

### See Also


[Built-in Function Overview](Functions_overview.html)
[%OMITTED Function](OMITTED_Function.html)
[BEGPROC](BEGPROC.html)
[DCLSRPARM](DCLSRPARM.html) 
