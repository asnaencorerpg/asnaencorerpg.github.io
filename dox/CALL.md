---
title: CALL

Id: CALL
TocParent: aerLrfOpCodesMain
TocOrder: 190


---

Transfers program control to a remote program.

```
 **CALL
Pgm** (Character Expression | Form variable)
ParmList (<u>*NONE</u>| Parameter List Name)
 **Db**  (Database Object)
Err (Indicator Variable | *EXTENDED)
Lr (Indicator Variable)    
```

### Parts

**Pgm** 

**Required** . **Pgm** specifies the name of the remote program to call.


**ParmList** 

Optional. **ParmList** specifies the parameter list name. *NONE is the default and indicates that there are no parameters to pass.


**Db** 

**Required** . **Db** specifies the database name where the program being Called is located. Database names are defined with the [DCLDB](DCLDB.html) command.


**Err** 

Optional. **Err** determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Lr** 

Optional. The **Lr** parameter will be set when the last record is read.


### Remarks
Use CALL to call an AS/400 program. To call a local program, use [CALLB](CALLB.html).

**Note** *Currently, a CALL with no DB parameter is converted (by the Compiler) to a CALLB. Programmers are encouraged to use CALLB for local calls in the future.* 

**Calling an AS/400 Program:** 

When calling an AS/400 program, PGM should include the library name or *LIBL, i.e. CALL PGM("Library/Program") or CALL PGM(*LIBL/Program'). The Call will use the library list associated with the user ID associated with the database name. The library list can be changed by calling the appropriate OS/400 command. 

The **maximum number** of parameters that can be passed in an AS/400 call is **36** . The parameters can be of any simple types (packed, char, date, zoned etc…) or data structures or multiple occurrence data structures. 

The AS/400 provides for three parameter data types for Commands (e.g., QCMDEXC) and Programs (CL, RPG, etc): Character, Boolean and Numeric. Typically, numeric parameters are always Packed. You must explicitly declare numeric parameters as Type(*packed) in your Encore RPG code. It may not be presumed that the Encore RPG compiler generates packed numerics. 

You can also call AS/400 APIs which can require a data structure as a Parm. This is supported and all required data types are permitted. When redefining data structure subfields, only the first definition is processed and converted between ASCII and EBCDIC. 

For Example:

```
dclDS Name(MYparmDS)
dcldsfld FieldA *char 10 // This value is passed and converted
dcldsfld FieldB *packed len(7,2) // Ignored dcldsfld FieldC *zoned len(9,2) // Ignored  
```

### Example

```
 dclDB Name ( ProdDB ) DBName ( "DG Net iSeries" )
 DclPlist Listout
 Dclparm TimeOfDay Type (*char) Len (10)
 Dclparm DayOfWeek Type (*packed) Len (1,0)
 Dclparm MonthOfYear Type (*packed) Len (2,0)

 // Call to a program with a PList. Call Pgm ( "LIBL/MyProgram" ) DB (ProdDB) ParmList (Listout)

 // Call to a program with parms. Call Pgm ( "LIBL/MyProgram" ) DB (ProdDB) ParmList (Listout)
 Dclparm TimeOfDay Type (*char) Len (10)
 Dclparm DayOfWeek Type (*packed) Len (1,0)
 Dclparm MonthOfYear Type (*packed) Len (2,0)			
```

### See Also
[CALLB](CALLB.html)

[CONNECT](CONNECT.html)

[DCLDB](DCLDB.html)

[DCLPARM](DCLPARM.html)

[DCLPLIST](DCLPLIST.html)

[HIDE](HIDE.html)

[UNLOAD](UNLOAD.html) 
