---
title: Strong-Named Assemblies

Id: aerLrfStrongNamedAssembly
TocParent: aerConAssemblies
TocOrder: 35


---

### To create and sign an assembly with a strong name

At the command prompt, type the following command:

```
SN  -k c:\source\AvrUnits\TSR\TsrKey.snk
```

### To sign an assembly with a strong name using attributes

In a code module, use the command to point to the key,  as shown in the following:.

**SetAssemblyAttribute**

```
AssemblyKeyFile("c:\source\AvrUnits\TSR\TsrKey.snk")

AssemblyDelaySign(*False)
```

### See Also
[SETASSEMBLYATTRIBUTE](/dox/SETASSEMBLYATTRIBUTE.html) 
