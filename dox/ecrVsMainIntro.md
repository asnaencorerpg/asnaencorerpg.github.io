---
title: Encore RPG for Visual Studio

Id: aerVsMainIntro
TocParent: Welcome
TocOrder: 50


---


Encore for RPG integrates with Visual Studio, the industry-standard IDE for .NET applications, to create, build, and debug Encore libraries and apps, including console and web applications.

This integration leverages the .NET project system and Encore SDK to provide a rich .NET development experience to both Encore and C# programmers, including MSBuild and `dotnet` command-line development and production.

Additionally, Encore RPG for Visual Studio provides a simple command gateway to migrate Encore applications to first-class C# applications, free of Encore SDK.

### Prerequisites

#### Visual Studio
Encore RPG for Visual Studio has the same hardware and operating system requrements as [Visual Studio](https://learn.microsoft.com/en-us/visualstudio/releases/2022/system-requirements).

> Encore RPG supports **{{ page.vssku }} {{ page.vsver_min }}** or later.

The Encore for Visual Studio Windows installer ensures that version dependencies are met before installing the extensions and Encore SDK. However, it does not install or update Visual Studio. The user is responsible for ensuring a compatible release of {{ page.vssku }} is installed and/or updated. 

> Note that Visual Studio Installer is generally unaware of non-Microsoft extension products such as Encore RPG. After updating or repairing {{ page.vssku }}, it is usually necessary to update the Encore RPG installation as well. If no Encore update is available, try repairing the existing Encore installation, via [Windows App settings **Modify** or **Repair** command](https://support.microsoft.com/windows/repair-apps-and-programs-in-windows-e90eefe4-d0a2-7c1b-dd59-949a9030f317).

#### .NET SDK
Encore SDK supports creation of applications targetting one or more specific "long-term support" .NET SDK versions.

> Encore RPG applications may target **{{ page.dotnetver1 }}** or **{{ page.dotnetver2 }}** **ONLY** .

> Note that an application targetting a particular .NET SDK [may run with .NET **runtime** release of the same or later version](https://learn.microsoft.com/en-us/dotnet/core/versions/selection).  For example, Encore applications targeting {{ page.dotnetver2 }} can usually run with {{ page.dotnetverNext }} runtime. Similarly, {{ page.dotnetverNext }} SDK can build applications targeting {{ page.dotnetver2 }}.

One or more of the .NET SDKs supporting the target framework must be installed to build Encore projects. Otherwise, Visual Studio will refuse to load the Encore project, and should direct you to an appropriate .NET SDK download page.

Be aware that the most recent {{ page.vssku }} update will typically install the most recently supported version of .NET SDK. For example, Visual Studio 2022 v17.12 installs .NET 9 SDK **only**. Please consult [Microsoft documentation regarding Visual Studio and .NET SDK version compatibility]() for further information.

---
### [Projects](ecrVsProjects)

[Hello Encore!](ecrVsHelloWorld)

The basics: Create an Encore RPG application from scratch.

---
### Source Editing

[Editor Features]()

Introducing Encore-enabled [IntelliSense™](https://learn.microsoft.com/en-us/visualstudio/ide/using-intellisense).

---
### Source Debugging

[Debugging Features]()

Debugging Encore code in the IDE.

---
### A Few Encore-Specific Features

[Project Designer and Encore SDK]()

A brief introduction to Encore SDK and features enabled by the Project Designer.

---
### C# Migration

[Migrate to C#]()

Migrate your entire Encore project to C# in one click.

---
### Build Optimization

[File Definition Caching]()

One way to scale development of Very Large Encore applications.

---
### Known Issues and Limitations

[Review of Missing Features]()

A review of a few popular missing features and workarounds.


---
### Additional Information

{% include er4vs_foot_links.html %}
