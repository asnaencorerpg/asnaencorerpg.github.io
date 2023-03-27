---
title: "%OMITTED Function"

Id: OMITTED_Function
TocParent: Functions_overview
TocOrder: 25


---

**%OMITTED** [built-in function](Functions_overview.html) determines if an procedure parameter that contains the **Options (*OMIT)** keyword contains a valid value. 

```
 **%OMITTED (ParameterName)**   
```

### Parts

**ParameterName** 

Required. The name of the parameter containing an **Options (*OMIT)** keyword.


### Remarks
To support **Procedure** parameters, the **DclSrParm** command has an **OPTIONS** keyword. It is **only** valid in **BegProc** subroutines, and it may contain * **OMIT** and/or * **NOPASS** . Please see **DclSrParm** for further information. 

Use the % **ISOMITTED** function to know whether a *OMIT parameter contains a valid value. 

**Note** % **ISOMITTED** and [%PARMS](PARMS_Function.html) functions are only valid inside a **BEGPROC** procedure. Also, % **IsOmitted** is only valid on parameters that have the **Options (*OMIT)** keyword. 

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

   //Get the Zip Code

   If not %OMITTED(CustZip)

// we have a valid zip code

   EndIf

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

[%PARMS Function](PARMS_Function.html)

[BEGPROC](BEGPROC.html)

[DCLSRPARM](DCLSRPARM.html) 
