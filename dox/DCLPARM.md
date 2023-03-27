---
title: DCLPARM

Id: DCLPARM
TocParent: aerLrfOpCodesMain
TocOrder: 540



---

Defines the parameters that compose a parameter list ([DCLPLIST](DCLPLIST.html)) that will be passed to a subprogram when a [CALL](CALL.html) or [CALLB](CALLB.html) command is issued, or will be passed to a subroutine when an [EXSR](EXSR.html) command is issued. 

```
 **DCLPARM
Name**  (Variable name | *OMIT)
CpyFrom (<u>*NONE</u> | Variable | Literal)
CpyTo (<u>*NONE</u> |  Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER |
      *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
DbDirection (<u>*BOTH</u> | *INPUT | *OUTPUT)
```

### Parts

**Name** 

**Required** . **Name** contains the name of the parameter field to pass, or * **OMIT** .


Encore RPG allows you to name a control property as a parameter field, provided the property conforms to valid **DCLPARM** types. However, you must not assume the default property for the control. Instead, you must specifically code the desired property, as shown below.


DCLPARM Name ( ioField1.value )<br /> DCLPARM Name ( checkbox1.value )


**CpyFrom** 

Optional. **CpyFrom** contains the value of the parameter. *NONE is the default. See Remarks section for more information.


**CpyTo** 

Optional. **CpyTo** contains the Parm values are copied from **CpyFrom** . *NONE is the default.


**Type** 

Optional. **Type** can be any of the types listed (Character, Packed or Zoned). *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. **Len** defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default.


Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**DbDirection** 

Optional. **DbDirection** specifies whether the parameter to a remote program call is an input-only parameter (*Input), an output-only parameter (*Output) or an input and output parameter (*Both). When a large amount of data is passed in only one direction - either to the called program, or from the called program, **DbDirection** allows you to reduce the call time by eliminating the transmission of unused data. *Both is the default. 

The direction of the parameter is from the perspective of the program being called. That is, *Input means the called program is expecting data in the parameter, but doesn't need to return it to the caller. *Output means the called program will send data back in the parameter to the caller, but is not expecting data in the parameter as input to it. 

**DbDirection** has specific meaning depending upon the type of the Database to which the Call is being made. 

- **Calling AS/400 programs** - AS/400 programs do not specify whether the parameter is used by the program for input or output, so the real value of DbDirection is in time savings when the parameter is large. Specifying the proper direction when data is only used in one direction saves time because the data in the parameter is only sent to the AS/400 when the parameter is marked as *Input and only transmitted back to the client if the parameter is marked for *Output.
- **Calling SQL Server stored procedures -** SQL Server defines two kinds of parameters, regular parameters and ‘output’ parameters. SQL Server regular parameters are only received by the procedure and so must have a **DbDirection** of ***Input** . What SQL Server means by an "output" parameter is really a parameter that is optionally received but always sent back to the client. Therefore, a SQL Server "output" parameter may have a **DbDirection** of ***Output** if it is certain the procedure does not use the received value. However, if ***Output** is specified and the procedure does depend on a received value, unpredictable results will occur. It is never wrong to specify a **DbDirection** of ***Both** for a SQL Server "output" parameter even if the stored procedure does not use the received value.<br />

DBDirection Example: 

If an SQL Server Stored procedure looks like the following:

```
CREATE PROCEDURE CountNewOrders
	@WarehouseId as decimal(8,0) ,
	@OrderCount as numeric (5,0) output
	AS
	select @OrderCount = count(distinct(OrderID)) from [Orders] where WId=@ WarehouseId WarehouseId
	GO 
```

Then the Encore RPG Call should be:

```
 CALL PGM (‘CountNewOrders’) DB (‘SQL’)
 DCLPARM OrderNum  DbDirection (*Input)
 DCLPARM OrderCount DbDirection (*BOTH)          
```


**Remarks** 

The **DCLPARM** command comes after a CALL, CALLB, DCLPLIST, or EXSR command, and defines the parameters that will be passed to the subprogram/subroutine when it is called. One or more **DCLPARM** commands can come after a CALL, CALLB or DCLPLIST command. 

A **DCLPARM** command that does not come after a CALL, CALLB, DCLPLIST or another **DCLPARM** command will cause a compiler error. 

When a program is called, any parameters specified are assigned the value of the operand specified in **CpyFrom** . The parameter is then passed to the program by reference, meaning that the program may change the value of the Parm. Finally, the Parm values are copied to any **CpyTo** operands specified on the CpyTo keyword. 

The data type and length can be specified.

You can pass a data structure as a parameter to an AS/400 program when doing a remote call. There are, however, some restrictions as noted below, on the format of the data structure due to the fact that these fields need to be converted between PC and AS/400 formats (things like ASCII to EBCDIC, byte order, etc.). Note that the following restrictions don't apply for calling programs within the same project. 

- All of the space taken by the data structure should be described. If an area of the data structure is not occupied by a field, the AS/400 program will not get the contents of that area. If the AS/400 program were to modify that area, then the PC program will not get the modification.
- Data structure fields cannot be arrays.

### Example

```
// Call program GetDate passing it a named parameter list.

   CALL PGM("GetDate") PARMLIST(IoDateValues) 

// Declare the parameter list for the above call. The value of DayYear is copied to IoDayYear before the CALL is 
   processed, and the return value is then placed in field IoYearMonthDay. These fields are declared elsewhere. */

   DCLPLIST Name(IoDateValues)
   DCLPARM Name (IoMonth)
   DCLPARM Name (IoCompleteDate) CPYFrom(DayYear) CPYTO(IoYearMonthDay)

// The following call is identical in function to the above call, but passes the parameters directly, 
   rather than using a names parameter list. */

   CALL PGM("GetDate")
   DCLPARM Name (IoMonth)
   DCLPARM Name (IoCompleteDate) CPYFrom(DayYear) CPYTO(IoYearMonthDay)

// The following is an example of calling a subroutine and passing parameters.

   EXSR ComputeTax
   DCLPARM Name (TaxRateCode)
   DCLPARM Name (Value)      
```

### See Also
[CALL](CALL.html)

[CALLB](CALLB.html)

[DCLPLIST](DCLPLIST.html)

[DCLSRPARM](DCLSRPARM.html)

[EXSR](EXSR.html) 
