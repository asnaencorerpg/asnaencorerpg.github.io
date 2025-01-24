---
title: SETASSEMBLYATTRIBUTE

Id: SETASSEMBLYATTRIBUTE
TocParent: aerLrfOpCodesMain
TocOrder: 1440


---

Allows you to set an attribute on an assembly.

```
SETASSEMBLYATTRIBUTE 
 Attribute  (Argument)
```

### Parameters

**Attribute** 

Required **.** Specifies the attribute to be set.


### Remarks
To specify more than one attribute for the assembly use multiple **SETASSEMBLYATTRIBUTE** commands. This command can be coded in any of your classes, but must come **before** the **BEGCLASS** and after any **USING** commands. 

Typically, custom attributes' names end up with the word ‘Attribute’, so the Attribute part of the name can be omitted. 

It is common to create a dedicated source file called AssemblyInfo.vr where all assembly attributes are grouped. This file usually lacks a class definition, i.e.: it contains no **BEGCLASS** whatsoever. 

### Example
Here is an example of an <span style="FONT-FAMILY: 'Courier New'">AssemblyInfo.vr:</span> 

```
Using System.Reflection
 **SetAssemblyAttribute Attribute**  (AssemblyDescription("AllParms_Test")
 **SetAssemblyAttribute**  AssemblyCompany("ASNA")
 **SetAssemblyAttribute**  AssemblyVersionAttribute("1.0.0")
 **SetAssemblyAttribute**  AssemblyTitle("THE ALLPARMS PROGRAM")
 **SetAssemblyAttribute**  AssemblyTrademark("ASNA")
```

### See Also
<a href="ADDDUR.htm9">Custom Attributes</a> 
