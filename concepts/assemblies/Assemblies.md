---
title: Assemblies

---

Assemblies are the building blocks of the .NET Framework, and take the form of an executable (.exe) file or dynamic link library (.dll) file. They provide the common language runtime with the information it needs to be aware of type implementations. You can think of an assembly as a collection of types and resources that form a logical unit of functionality and are built to work together. 

With Encore RPG for Visual Studio, you use the contents of assemblies, and add references to them. What makes assemblies different from .exe or .dll files in earlier versions of Windows, however, is that they contain all the information you would find in a type library, plus information about everything else necessary to use the application or component. 

### Assembly Manifest
Within every assembly is an *assembly manifest* . Similar to a table of contents, the assembly manifest contains the following: 

- A file table describing all the other files that make up the assembly, including, for example, any other assemblies you created that your .exe or .dll file relies on, or even bitmap or Readme files.
- The assembly's identity (its name and version).
- An *assembly reference list*, which is a list of all external dependencies — .dlls or other files your application needs that may have been created by someone else.  Assembly references contain references to both global and private objects.  Global objects reside in the global assembly cache, an area available to other applications, somewhat like the System32 directory.  The **ASNA.QSys**  namespace is an example of an assembly in the global assembly cache.  Private objects must be in a directory at either the same level as or below the directory in which your application is installed.

Because assemblies contain information about content, versioning, and dependencies, the applications you create with Encore RPG for Visual Studio do not rely on registry values to function properly. Assemblies reduce DLL conflicts and make your applications more reliable and easier to deploy. 

### In This Section

[Allocating Memory](AllocatingMemory.html)

Describes how the garbage collector allocates and releases memory in .NET.


[Namespaces](NamespacesStart.html)

Describes the concepts and declaration of using 	namespaces.


[Custom Attributes](CustomAttributes.html)

Describes information on attributes that provide additional information about programming elements.


### See Also
[Language Concepts](/concepts/LanguageConceptsMain.html) 
