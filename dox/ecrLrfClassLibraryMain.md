---
title: Class Library

Id: aerLrfClassLibraryMain
TocParent: aerLrfLangRefMain
TocOrder: 1


---

Encore RPG programs rely on a class library for their execution. The library is a group of classes, interfaces, and value types, it also provides access to system functionality and contains links to the .NET classes in which applications, components, and controls are built. This library is composed of several assemblies which are named with the prefix ASNA.QSys and are formally known as the Monarch Base.


## Namespaces
The class library provides the following namespaces:

### [ASNA.QSys.Runtime](//asnaqsys.github.io/reference/runtime/qsys-runtime/landing-page-namespace.html) Namespace

The [ASNA.QSys.Runtime](//asnaqsys.github.io/reference/runtime/qsys-runtime/landing-page-namespace.html) namespace contains classes that support compilation and code generation using the Encore RPG for Visual Studio language. Most of the classes are reserved for the Encore RPG system. Some classes and their members  may be employed directly by the Encore RPG programmer.

Several ECR declaration commands rely directly on some of these classes or interfaces.  Here are a few of them:

| Declare Command | Underlying Class |
| --------------- | ---------------- |
| [DclDB](DCLDB.html) | [Database Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/database.html)
| [DclDiskFile](DCLDISKFILE.html) | [DatabaseFile Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/database-file.html)
| [DclPrintFile](DCLPRINTFILE.html) | [PrintFile Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/print-file.html)
| [DclWorkStnFile](DCLWORKSTNFILE.html) | [WorkstationFile Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/workstation-file.html)
| [DclDS](DCLDS.html) | [DataStructure Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/data-structure.html)
| [DclFld](DCLFLD.html) | *Bin, *Packed, *Zoned [FixedDecimal Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/fixed-decimal-2.html) <br/> *Char [FixedString Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/fixed-string-1.html) <br/> *Date [FixedDate Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/fixed-date-2.html) <br/> *Ind [Indicator Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/indicator.html) <br/> *Time [FixedTime Class](//asnaqsys.github.io/reference/runtime/qsys-runtime/fixed-time-2.html)



### [ASNA.QSys.Runtime.JobSupport](//asnaqsys.github.io/reference/runtime/qsys-runtime-job-support/landing-page-namespace.html) Namespace

The [ASNA.QSys.Runtime.JobSupport](//asnaqsys.github.io/reference/runtime/qsys-runtime-job-support/landing-page-namespace.html) namespace provides classes supporting the execution of Monarch migrated programs.  Some of the more salient classes are:

| Supported Feature | Class |
| ----------------- | ---------------- |
| Job | [Job Class](//asnaqsys.github.io/reference/runtime/qsys-runtime-job-support/job.html)
| Program | [Program Class](//asnaqsys.github.io/reference/runtime/qsys-runtime-job-support/program.html)
| Module | [Module Class](//asnaqsys.github.io/reference/runtime/qsys-runtime-job-support/module.html)



### [ASNA.DataGate.Client](//asnaqsys.github.io/reference/datagate/datagate-client/landing-page-namespace.html){:target="_blank"}&#x1F875; Namespace

The [ASNA.DataGate.Client](//asnaqsys.github.io/reference/datagate/datagate-client/landing-page-namespace.html){:target="_blank"}&#x1F875; namespace is the primary namespace used by client applications. It contains the most fundamental classes for accessing database server resources.

Most application access the facilities of DataGate.Client indirectly through the use of objects declared via DCLDB and DCLxxxxFILE.  However, sometimes it may be convenient to utilize directly some of the facilities provided by DataGate.Client.


---


