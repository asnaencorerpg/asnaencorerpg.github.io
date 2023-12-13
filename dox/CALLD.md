---
title: CALLD

Id: CALLD
TocParent: aerLrfOpCodesMain
TocOrder: 210


---

        Used to dynamically
        invoke a procedure. [Only used with Monarch ILE Procedures]. 
```
CALLD 
Pgm  (Character expression)
ParmList (<u>*NONE</u>| Parameter List Name)
Assembly (Character expression)
Prototype (Name)
Err (Indicator Variable | *EXTENDED)
Lr (Indicator Variable)    
```

### Parts

**Pgm** 

**Required** . Pgm is required and is a character expression that evaluates to the name of the program to call. It can be a string constant, a field, or an expression that returns a string value.


During compilation of **CALLD** , if the **Pgm** keyword is a constant, the compiler searches the available dynamic references to obtain the signature of the * **Entry** method of the class, and match it against the parameters of the **CALLD** . If they're not found, the parameters are assumed to be of the same type as the **DclParm** argument passed by reference, and with **Option(*nopass)** .


**ParmList** 

Optional. ParmList specifies the list of parameters. *NONE is the default and indicates that there is not a parameter list.


If a ParmList is not given, **CALLD** *may* be followed by a group of [DCLPARM](DCLPARM.html) commands specifying the parameters to be passed to the program. If a parameter is going to be omitted (the corresponding DclSrParm has the * **OMIT** option), use the special value * **OMIT** in the **DCLPARM's** name.


**Assembly** 

Optional. Assembly is a character expression that evaluates to the assembly name or complete assembly path where the Pgm is located.


**Prototype** 

Optional. Specifies the name of a [DCLPROTOTYPE](DCLPROTOTYPE.html) declaration, which indicates the parameters of the program to call. It’s only used when **Pgm** cannot be resolved at compile time.


**Err** 

Optional. Err determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - the program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Lr** 

Optional. The specified indicator is set to the value of * **INLR** of the called program.


### Remarks
**CALLD** is basically the same as [CALLB](CALLB.html), except that you can specify an assembly or prototype of the program to call. 

**Dynamic references** are used together with **CALLD** . They are the set of libraries (dll’s) the runtime searches for the class invoked in a **CALLD** . These libraries **must** be available at runtime, but not necessarily at compile time. During compilation of **CALLD** , if the **PGM** keyword is a constant, the compiler searches the available dynamic references to obtain the signature of the * **Entry** method of the class, and match it against the parameters of the **CALLD** . If they're not found, the parameters are assumed to be of the same type as the **DclParm** argument passed by reference, and with **Option(*nopass)** . 

Dynamic references can only be added to valid Monarch projects (i.e. Console app and class library). They are added by right-clicking the Project or the Dynamic References folder in the project and selecting **Add Dynamic Reference** . There are two ways to specify them: either using the assembly name (composed of simple name, culture, version, and public key token) or using a path if the dll exists. 

The following is the hierarchy used by ECR runtime to find the class name in a CALLD statement. 

Example: CALLD Pgm( " MyNamespace.MyProgram " ) 

1. <div>
                    ECR will first look for the class
                    name "MyProgram" in the assembly where the CALLD is made.
2. <div>
                    If the class is not found in the
                    prior step, then without regard to the entries in Dynamic References, ECR will
                    probe for the assembly named MyNamespace.MyProgram.dll and if found, will look
                    within the assembly for the class name "MyProgram".
3. <div>
                    If the class is not found in the
                    prior step, then each assembly in the Dynamic References list is probed in the
                    order in which the assemblies are listed. ECR will look within each assembly
                    found for the class name "MyProgram".

**Notes** : 

- <div>
                    No runtime error is issued for a
                    referenced assembly that cannot be found.
- <div>
                    The .NET Framework rules for probing are documented in MSDN .NET Framework
                    Developer Center. Search for "Locating Assembly through Probing".

### Example

```
 // Dynamic call to a dynamic program as a constant. CALLD Pgm (" M yNameSpace.MyProgram" ) ParmList (MyParmList)			

 // Dynamic call to a program as constant with the same Namespace as the caller. CALLD Pgm (*NS + "MyProgram") // Dynamic call to a program as a variable. DclFld PgmToCall type( *string ) PgmToCall = "MyProgram" CALLD Pgm ( *NS + PgmToCall ) ParmList ( Listout)			
```

### See Also
[BEGPROC](BEGPROC.html)

[CALLB](CALLB.html)

[DCLPARM](DCLPARM.html)

[*NS](StarNS.html)<!--Fix-->

