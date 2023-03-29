---
title: Class Library

Id: aerLrfClassLibraryMain
TocParent: aerLrfLangRefMain
TocOrder: 1


---

Encore RPG programs rely on a class library for their execution. The library is a group of classes, interfaces, and value types, it also provides access to system functionality and contains links to the .NET classes in which applications, components, and controls are built. This library is composed of several assemblies which are named with the prefix ASNA.QSys and are formally known as the Monarch Base.


## Namespaces
The class library provides the following namespaces:

### [ASNA.QSys.Runtime](//asnaqsys.github.io/reference/asna-qsys-runtime/asna-qsys-runtime-section-intro.html) Namespace

The [ASNA.QSys.Runtime](//asnaqsys.github.io/reference/asna-qsys-runtime/asna-qsys-runtime-section-intro.html) namespace contains classes that support compilation and code generation using the Encore RPG for Visual Studio language. Most of the classes are reserved for the Encore RPG system. Some classes and their members  may be employed directly by the Encore RPG programmer.

Several ECR declaration commands rely directly on some of these classes or interfaces.  Here are a few:

| Declare Command | Underlying Class |
| --------------- | ---------------- |
| [DclDB](DCLDB.html) | [Database Class](https://asnaqsys.github.io/reference/asna-qsys-runtime/classes/database.html)
| [DclDiskFile](DCLDISKFILE.html) | [DatabaseFile Class](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/database-file.html)
| [DclPrintFile](DCLPRINTFILE.html) | [DatabaseFile Class](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/database-file.html)
| [DclWorkStnFile](DCLWORKSTNFILE.html) | [DatabaseFile Class](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/database-file.html)
| [DclDS](DCLDS.html) | [DataStructure Class](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/data-structure.html)
| [DclFld](DCLFLD.html) | *Char []() <br/> *Date [FixedDate Class](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/fixed-date.html) <br/> *Ind [Indicator Class](//asnaqsys.github.io/reference/asna-qsys-runtime/classes/indicator.html)



### [ASNA.QSys.Runtime.JobSupport](//asnaqsys.github.io/reference/asna-qsys-runtime-job-support/asna-qsys-runtime-job-support-section-intro.html) Namespace

The [ASNA.QSys.Runtime.JobSupport](//asnaqsys.github.io/reference/asna-qsys-runtime-job-support/asna-qsys-runtime-job-support-section-intro.html) namespace provides classes supporting the execution of Monarch migrated programs.  Some of the more salient classes are:

| Supported Feature | Class |
| ----------------- | ---------------- |
| Job | [Job Class](//asnaqsys.github.io/reference/asna-qsys-runtime-job-support/classes/job.html)
| Program | [Program Class](//asnaqsys.github.io/reference/asna-qsys-runtime-job-support/classes/program.html)
| Module | [Module Class](//asnaqsys.github.io/reference/asna-qsys-runtime-job-support/classes/module.html)



### [ASNA.DataGate.Client](//asnaqsys.github.io/reference/datagate-client/datagate-client-namespace.html) Namespace

The [ASNA.DataGate.Client](//asnaqsys.github.io/reference/datagate-client/datagate-client-namespace.html) namespace is the primary namespace used by client applications. It contains the most fundamental classes for accessing database server resources.

Most application access the facilities of DataGate.Client indirectly through the use of objects declared via DCLDB and DCLxxxxFILE.  However, sometimes it may be convinient to utilize directly some of the facilities provided by DataGate.Client.



---


