---
title: Installation and Setup

Id: aerInstallationandsetup
TocParent: aerGettingStartedMain
TocOrder: 1


---

As you install Encore RPG, you will have the opportunity to choose among several different installation and setup options. This topic will help you familiarize yourself with these options, and direct you to appropriate help. 

* [Requirements and Prerequisites](#requirements-and-prerequisites)
* [Installation](#to-install-encore-rpg)

---
### Requirements and Prerequisites

Encore RPG for Visual Studio relies on development tools provided by both Visual Studio and .NET SDK.
<br/><br/>

#### Visual Studio
Encore RPG for Visual Studio is a set of extensions for {{ page.vs_sku }}. Thus, the hardware and operating system requrements are equivalent to those of Visual Studio.

Please review [{{ page.vs_sku }} system requirements]({{ page.vs_requirements_url }}).

> Encore RPG supports **{{ page.vs_sku }} {{ page.vs_ver_min }}** or later.

Though Encore for Visual Studio Windows Installer will only proceed after all prerequisite software is installed, it cannot install or update Visual Studio for you. A compatible release of {{ page.vs_sku }} must be installed and/or updated using Visual Studio Installer first.

> Note that Visual Studio Installer is a general-purpose maintenance tool used to *install, update, and repair* a Visual Studio deployment.  When updating, it is generally unaware of non-Microsoft extension products such as Encore RPG. After updating or repairing {{ page.vs_sku }}, it is usually necessary to update or repair the Encore RPG installation as well. If no Encore update is available, try repairing the existing Encore installation, via [Windows App settings **Modify** or **Repair** command](https://support.microsoft.com/windows/repair-apps-and-programs-in-windows-e90eefe4-d0a2-7c1b-dd59-949a9030f317).

<br/>
#### .NET SDK
Encore SDK supports creation of applications targetting one or more specific "long-term support" .NET SDK versions.

> Encore RPG applications may target **{{ page.dotnet_ver1 }}** or **{{ page.dotnet_ver2 }}** **ONLY** .

> Note that an application targetting a particular .NET SDK [may run with .NET **runtime** release of the same or later version](https://learn.microsoft.com/dotnet/core/versions/selection).  For example, Encore applications targeting {{ page.dotnet_ver2 }} can usually run with {{ page.dotnet_ver_next }} runtime. Similarly, {{ page.dotnet_ver_next }} SDK can build applications targeting {{ page.dotnet_ver2 }}.

One or more of the .NET SDKs supporting the target framework must be installed to build Encore projects. Otherwise, Visual Studio will refuse to load the Encore project, and should direct you to an appropriate .NET SDK download page.

Be aware that the most recent {{ page.vs_sku }} update will typically install the most recently supported version of .NET SDK. For example, Visual Studio 2022 v17.12 installs .NET 9 SDK **only**. Please consult [Microsoft documentation regarding Visual Studio and .NET SDK version compatibility](https://learn.microsoft.com/dotnet/core/porting/versioning-sdk-msbuild-vs) for further information.

---
### To Install Encore RPG

1. [Carefully review the hardware and software prerequisites outlined above](#requirements-and-prerequisites).
1. Go to the ASNA product downloads site at [https://asna.com/en/support/downloads/](https://asna.com/en/support/downloads/) and log in (create an account if you haven't already).
2. Click on **Encore RPG**  in the General Availability section.
                Your browser will download the latest version.
3. Open your browser's downloads folder, and click on the
                ecr-setup-4.0.XX.0.exe file (labeled **ASNA Encore RPG** ).
4. The ASNA Installer will run, ensuring that your hardware and
                software are compatible and prompting you to configure the new
                installation of Encore RPG.

The main screens that will occur are:
- License Agreement
- Registration
- Directory locations and selecting which files to install

