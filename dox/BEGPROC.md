---
title: BEGPROC

Id: BEGPROC
TocParent: aerLrfOpCodesMain
TocOrder: 110


---

**BEGPROC** is **only** available to support the Monarch migration of RPG ILE procedures and subprocedures from an System i. See **Remarks** for more information. 

```
BEGPROC 
 Name  (Procedure name | *Entry) 
Type (*BOOLEAN | *BINARY | *BYTE | *CHAR | *DATE | *IND | *PACKED | *TIME | *TIMESTAMP | *ZONED | 
      *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *STRING | name | String Literal | Library.Object) 
	  Len (Length Integer, [Decimal Positions Integer])
	  TimFmt (*<u>PGMDFT</u> | *MDY | *DMY | *YMD | *JUL| *ISO | *USA | *EUR | *JIS | *HMS)
	  Rank (IntegerLiteral)
	  Access (*Public | *Private)
Like (Procedure name | Field)
```


### Parameters

**Name** 

**Required** . The name of the procedure, or * **Entry** .


**Type** 

Required **only** if the procedure returns a value; otherwise Optional. **Type** can be any of the "*" Types (*CHAR, *BINARY, etc.) or it can be the name of a type or (class).


If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.


**Len** 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *BINARY, *CHAR, *PACKED, *ZONED, *DECIMAL, *FLOAT, and *INTEGER will require a **Len** . A compiler message will display if the **Len** parameter is needed.


Optional. **Len** defines the length of the field. E.g. if **Len** is (3,1) *ZONED is assigned as the default. If **Len** is (3), *CHAR is assigned as the default.


**Decimal** numeric types require **Len** to contain 2 values: (x, y) where *x* is the total number of digits and *y* is the number of decimal positions.


* **Char** types require to have one value (x) which is the length of the Character field.


* **Float** and * **Integer** types require **Len** to have one value (x), which is the length in bytes of the number.


**TimFmt** 

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the format specified by the program is assumed.


**Rank** 

Optional. Rank declares an n-dimensional array of indefinite elements. The value given for Rank defines the number of dimensions for the array.


**Access** 

Optional. The type of access to the member. * **Public** is the default. 

- *PUBLIC (default) - specified for a procedure or subprocedure. Access to the procedure is accessible from anywhere within the same project, and from other projects that reference the project.
- *PRIVATE - specified in a subprocedure; in addition to *Public. Access to the procedure is accessible only from within their declaration context, including from members of any nested types.



**Like** 

Optional. Like must be the name of a procedure or field already defined in the class.


### Remarks
** Migrated Procedures: ** 

**BEGPROC** is only available to support the Monarch migration of RPG ILE procedures and subprocedures from System i. The procedure, (which is the main entry point into a program), is migrated as a **BegProc *Entry Access (*Public)** routine, as shown below. A **BEGPROC** routine must always end with an [ENDPROC](ENDPROC.html). 

``` BegProc *Entry Access(*Public)``` 

``` . . .``` 

``` EndProc``` 

If the original program has a * **Entry** PList (RPG 400), or the RPG ILE main procedure contains parameters, they are migrated as [DclSrParm's](DCLSRPARM.html) in the BegProc **without a type** specification, as the fields in the PList refer to ** global ** fields in the System i source code. 

**Note &#8211;** A compilation error will occur if a parameter in a ***Entry BegProc** specifies an option of * **Omit** . 

** Migrated SubProcedures: ** 

Subprocedures are also migrated as a **BegProc** , but with slightly different options, as shown below: 

BegProc <Name> Access(*Public/*Private) 

**. . .** 

**EndProc** 

Parameters are also migrated as **DclSrParm's** , but with **full** type specification. <br /> 

** Procedure and SubProcedure Parameters ** 

The **DclSrParm** command was enhanced with the **OPTIONS** keyword to support certain options on procedure parameters. OPTIONS is only valid in BegProc parameters, and it may contain * **OMIT** and/or * **NOPASS.** Please see **DclSrParm** for further information. 

Refer to the built-in function [%PARMS](PARMS_Function.html) if you want to know how many parameters were received; or to the [%OMITTED](OMITTED_Function.html) function to know whether a *OMIT parameter contains a value. 

**Note &#8211;** The % **Parms** and % **IsOmitted** functions are only valid inside a **BEGPROC** procedure. Also, % **IsOmitted** is only valid on parameters that have the * **Omit** option. 

** Invoking a Procedure ** 

You can invoke, or call a Procedure by either using the [CALLB](CALLB.html) command, or a free-form expression, as shown briefly below. Please see **CALLB** for more information on both examples. 

CALLB Proc(<class or class.procedure or procedure>) ParmList(<parmlist name>)<br /><br /> - or - 

MyProc( CustName, *Omit ) 

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

BegProc  CheckLocation Access(*Public) 
    DclSrParm CustZip Options(*Omit) 
    DclSrParm CustState Options(*Omit, *NoPass) 
    . . . 
// Get the Zip Code 
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

DclFld myNumber Type( *Zoned ) Len( 8,2 ) 

// MyProc is of the same type as myNumber, i.e. *Zoned with a length of 8,2 

BegProc MyProc Like(myNumber) Access(*Public) 
    myNumber = 123456.78 
    Return myNumber 
EndProc 

// MyOtherProc is of the same type as MyProc 

BegProc MyOtherProc Like(MyProc) Access(*Public) 
    myNumber = 998877.66 
    Return myNumber 
EndProc  
```

### See Also
[%OMITTED Function](OMITTED_Function.html) [%PARMS Function](PARMS_Function.html) [BEGSR](BEGSR.html) [DCLSRPARM](DCLSRPARM.html) [ENDPROC](ENDPROC.html) 
