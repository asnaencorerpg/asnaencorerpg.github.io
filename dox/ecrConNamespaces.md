---
title: Namespaces

Id: aerConNamespaces
TocParent: aerConLanguageConceptsMain
TocOrder: 15


---

Due to the .NET framework, Encore RPG .NET programs are organized using namespaces, both to internally organize a program, as well as to organize the way program elements are exposed to other programs. 

Unlike other entities, namespaces are open-ended, and may be declared multiple times within the same program and may be declared across many programs, with each declaration contributing members to the same namespace. 

Use the [DCLNAMESPACE](DCLNAMESPACE.html) command to declare a particular namespace in code. 

There is a global namespace that has no name and whose nested namespaces and types can always be accessed without qualification. The scope of a namespace member declared in the global namespace is the entire program text. 

### See Also
[DCLNAMESPACE](DCLNAMESPACE.html)

[Namespace Declarations](ecrConNamespaceDeclarations.html)

[Namespace Concepts](ecrConNamespacesConcepts.html) 
