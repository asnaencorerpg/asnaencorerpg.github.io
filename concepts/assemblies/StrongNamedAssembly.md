---
title: Strong-Named Assemblies

Id: aerLrfStrongNamedAssembly
TocParent: aerConAssemblies
TocOrder: 35


---

**To create and sign an assembly with a strong name** 

At the command prompt, type the following command:
<pre class="prettyprint">SN  -k c:\source\AvrUnits\TSR\TsrKey.snk</pre>

**To sign an assembly with a strong name using attributes** 

- In a code module, use the command to point to the key,
                    as shown in the following:.

<span style="FONT-SIZE: 10pt; FONT-FAMILY: Arial"> ** SetAssemblyAttribute ** AssemblyKeyFile("c:\source\AvrUnits\TSR\TsrKey.snk") </span> 

<span style="FONT-SIZE: 10pt; FONT-FAMILY: Arial"> **SetAssemblyAttribute** AssemblyDelaySign(*False) </span> 

### See Also
[SETASSEMBLYATTRIBUTE](/dox/SETASSEMBLYATTRIBUTE.html) 
