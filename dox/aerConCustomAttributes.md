---
title: Custom Attributes

Id: aerConCustomAttributes
TocParent: aerConAssemblies
TocOrder: 2


---

**Custom Attributes** are descriptive tags that provide additional information about programming elements such as classes, fields, methods, and properties. Other applications, such as the Encore RPG compiler or the Visual Studio designers, can refer to the extra information in attributes to determine how these items can be used at design-time and run-time. 

### Attributes and Metadata
Attributes are saved with the *metadata* of Encore RPG **assemblies** . Metadata is information that describes every element managed by the system runtime. This includes information required for debugging and garbage collection, as well as security attributes, marshalling data, extended class and member definitions, version binding, and any other information the runtime requires. 

With attributes, you specify the metadata in much the same way as you use special values like <code>* **Public** </code> and <code>* **Private** </code> to provide information about **Access** levels. However, unlike special values, most attributes are not Encore RPG-specific. Using attributes, you can extend the capabilities of the Encore RPG language without requiring changes to the compiler. 

### Functionality and Capabilities of Attributes
Some key points about attributes include: 

- You can apply one or more attributes to entire assemblies, or smaller program
                elements such as classes and properties.
- Attributes can accept arguments in the same way as methods and properties.
- Attributes fall into two groups: those that are used by the .NET Framework and
                Encore RPG, and custom attributes that are meaningful only to specific
                applications.
- While the .NET Framework contains many useful attributes, you can define your
                own custom attributes if necessary.

### The Attributes Keyword
The following commands have a new optional keyword called <code> **Attributes** </code> which allows you to provide one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas. 

- [BEGCLASS](BEGCLASS.html)
- [BEGCONSTRUCTOR](BEGCONSTRUCTOR.html)
- [BEGFUNC](BEGFUNC.html)
- [BEGPROP](BEGPROP.html)
- [BEGSR](BEGSR.html)
- [DCLARRAY](DCLARRAY.html)
- [DCLEVENT](DCLEVENT.html)
- [DCLFLD](DCLFLD.html)

You can also add attributes to the assembly by using the new command:

```
         SetAssemblyAttribute Attribute( attr )
```

To specify more than one attribute for the assembly use multiple [SetAssemblyAttribute](SETASSEMBLYATTRIBUTE.html) commands. This command can be coded in any of your classes but must be come before the <code> **BEGCLASS** </code> and after any [USING](USING.html) statements. 

It is common to create a dedicated source file called AssemblyInfo.vr where all assembly attributes are grouped. This file usually lacks a class definition, i.e.: it contains no <code>BegClass</code> whatsoever. 

### Related Sections

[Allocating Memory](aerConAllocatingMemory.html)

Describes how the garbage collector allocates and releases memory in .NET.


[Namespaces](aerConNamespacesStart.html)

Describes the concepts and declaration of using namespaces.


### See Also
[USING](USING.html)
[SetAssemblyAttribute](SETASSEMBLYATTRIBUTE.html)
[Language Concepts](aerConLanguageConceptsMain.html) 
