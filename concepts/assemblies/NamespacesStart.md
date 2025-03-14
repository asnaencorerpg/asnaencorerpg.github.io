---
title: Namespaces

Id: aerConNamespacesStart
TocParent: aerConAssemblies
TocOrder: 1


---

Due to the .NET framework, Encore RPG .NET programs are organized using namespaces, both to internally organize a program, as well as to organize the way program elements are exposed to other programs. 

Unlike other entities, namespaces are open-ended, and may be declared multiple times within the same program and may be declared across many programs, with each declaration contributing members to the same namespace. 

Use the [DCLNAMESPACE](/dox/DCLNAMESPACE.html) command to declare a particular namespace in code. 

There is a global namespace that has no name and whose nested namespaces and types can always be accessed without qualification. The scope of a namespace member declared in the global namespace is the entire program text. 

### In This Section

[Namespace Declarations](/concepts/namespaces/NamespaceDeclarations.html)

Provides more detail on declaring namespaces.


[Namespace Concepts](/concepts/namespaces/NamespacesConcepts.html)

Provides additional information of the concepts of declaring namespaces.


### Related Sections

[Allocating Memory](AllocatingMemory.html)

Describes how the garbage collector allocates and releases memory in .NET.


[Custom Attributes](CustomAttributes.html)

Describes information on attributes that provide additional information about programming elements.


### See Also
[DCLNAMESPACE](/dox/DCLNAMESPACE.html)

[Language Concepts](/concepts/LanguageConceptsMain.html) 
