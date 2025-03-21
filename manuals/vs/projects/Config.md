---
title: Encore Project Configuration
description: This page documents the configuration of Encore projects for both development and migration scenarios, via the Visual Studio Project Designer.

Id: aerVsProjConfig
TocParent: Projects
TocOrder: 5


---
Encore SDK and Encore compiler provide several options for use in special cases. Many of these can be configured in Visual Studio project settings exposed by the **Project Properties** window. 

Encore-specific properties are presented in two sections in the Encore RPG section of the **Project Properties**: **Build** and **Translation to C#**.  Links to each section are visible the left margin of the Project Properties window under **Encore RPG**.

To open Project Properties use the "**\<project name\> Properties**" command on the Visual Studio **Project** menu:

![Opening project properties.](images/GetProjectDesigner.png)

<br/>

* [Encore RPG Build](#encore-rpg-build-options)
--
    * [Additional Database Name File](#additional-database-name-file)
    * [Enable File Definition Cache](#enable-file-definition-cache)
    * [File Definition Cache Location](#file-definition-cache-location)
    * [Run-time Arithmetic Overflow/Underflow](#run-time-arithmetic-overflowunderflow)
    * [Default `DATEDIT` Format](#default-datedit-format)

* [Translation to C#](#translation-to-c-options)
--
    * [Translation Output Folder](#translation-output-folder)
    * [Overwrite Output Folder](#overwrite-output-folder)
    * [Character Replacement Option File](#character-replacement-option-file)

* [Other .NET Project Options](#miscellaneous-options)
--
    * [Project Properties UI Options](#project-properties-ui)
    * [MSBuild Common Project Properties](#msbuild-project-properties)

---
## Encore RPG Build Options

These options effect the behavior of, and code generated by Encore compiler.

![Encore project properties links.](images/EncorePropertiesLinks.png)

---
### Additional Database Name File

***Default Value:*** (not specified).

***MSBuild Property:*** `<AdditionalDBNamesFile/>`

When specified, the compiler looks in the given *secondary* file location for available database name information.

> Encore database names are constant string aliases for DataGate database connection parameter sets. They are specified in Encore statements, such as the `DBNAME` keyword of [`DCLDB`](DCLDB).

Encore compiler first searches for referenced database names in the *primary* database names file. The primary file resides in the logged-on user's "local app data," identified as `%LOCALAPPDATA%\ASNA\DataGate\asnasettings.json`. Thus if "Bob" is the logged-on user, the primary file path typically resolves to `C:\Users\Bob\AppData\Local\ASNA\DataGate\asnasettings.json`. 

> Note that .NET configuration data is gathered *cumulatively*, meaning that typed connection parameters of a database name defined in the primary `asnasettings.json` file will be *overridden* by same-typed connection parameters of the same database name appearing in the secondary file (if specified). After the primary and secondary files are visited, [any build-time user secrets, project secrets, and environment variables](https://learn.microsoft.com/aspnet/core/fundamentals/configuration/) are examined to compose the final set of database names available to the compiler.

As an example usage, setting this option as shown below allows the secondary database names file to reside in the source control repo containing the project:

![Define a secondary database name file local to the project.](images/LocalAsnaSettings.png)

Any file containing valid JSON-encoded text may be specified here. Database names in the file must be defined using the ASNA DataGate "sources" JSON schema. When set in the **Project Properties** window, the value may be set per project configuration, e.g. `Debug|AnyCPU`.

> Note that in the above example, the `appsettings.json` file is specified, typically found in ASP.NET-related projects as a general settings file.

---
### Enable File Definition Cache

***Default Value:*** `False` (disabled).

***MSBuild Property:*** `<UseFileDefinitionCache/>`

When enabled, each compilation will use the Encore SDK externally-described file cache feature, which may improve overall build performance in large solutions and when accessing databases with high response latency. 

Note: this feature should only be used with an understanding of its potential side-effects. Please see [File Definition Caching](FileDefCaching.html) before enabling this feature.

![The file definition cache is shown "disabled"](images/FileDefCacheDisabled.png)

> When set in the **Project Properties** window, the value may be set per configuration, e.g. `Debug|AnyCPU`.

---
### File Definition Cache Location

***Default Value:*** `$(LOCALAPPDATA)\ASNA\DataGate\caching`

***MSBuild Property:*** `<FileDefinitionCacheRoot/>`

> This option is only visible in **Project Properties** when the File Definition Cache option is [enabled](#enable-file-definition-cache).

Specifies the folder containing file definition cache. See [File Definition Caching](FileDefCaching.html) for more details. The **Open file definition cache folder** hyperlink appears as shown below, allowing immediate inspection of the designated folder using the system file browser.

![File definition cache folder and hyperlink.](images/FileDefCacheDirectoryOption.png)

> In development builds and almost all other cases, the default value is recommended.

> The folder specified here should be reserved for the exclusive use of the Encore build.

---
### Run-time Arithmetic Overflow/Underflow

***Default Value:*** `False` (disabled).

***MSBuild Property:*** `<CheckForOverflowUnderflow/>`

When enabled, the compiler generates run-time checks for overflow and underflow conditions in arithmetic operations.

> This option is identical to a similar option also shown in the **Build/Advanced** section of **Project Properties**.

---
### Default `DATEDIT` Format

***Default Value:*** Unspecified (resolves to `*NONE`).

***MSBuild Property:*** `<DatEdit/>`

Specifies one of four values to use as the format that would otherwise be specified by `DATEDIT` in edit code `Y` expressions when the `DATEDIT` keyword is omitted.

* `*YMD` Year, Month, Day
* `*MDY` Month, Day, Year
* `*DMY` Day, Month, Year
* `*NONE`

![`DATEDIT` configuration option.](images/DatEditOptionNone.png)

> When `*NONE`, the compiler uses a contextual default value, which typically resolves to `*YMD`.


---
## Translation to C# Options

The options in this section are relevant *only* to the behavior of the [**Translate to C# Project**](ProjGenCSharp.html#translate-to-c-project) migration command.

![Migrate project properties links.](images/TrekkerPropertiesLinks.png)

---
### Translation Output Folder

***Default Value:*** `$(MSBuildProjectDirectory)_CS`

***MSBuild Property:*** `<TrekkerOutput/>`

Defines the folder to contain the migrated C# project generated by the [**Translate to C# Project**](ProjGenCSharp.html#translate-to-c-project) command.

![Translate to C# output folder setting.](images/TrekkerOutputFolderOption.png)

The folder may or may not exist at the time the command is invoked. If the folder exists and is non-empty, the command's behavior is dictated by the [Overwrite Output Folder](#overwrite-output-folder) option.

---
### Overwrite Output Folder

***Default Value:*** `False` (disabled).

***MSBuild Property:*** `<Overwrite/>`

When enabled, the contents of the [translation output folder](#translation-output-folder) are removed before the [**Translate to C# Project**](ProjGenCSharp.html#translate-to-c-project) command is invoked. If this option is disabled and the folder is non-empty, the command will not produce the translation, and an error will be shown in the **Output Window** build log and **Error List**.

![Delete the migration output folder contents option.](images/TrekkerOverwriteOption.png)

---
### Character Replacement Option File

***Default Value:*** Unspecified.

***MSBuild Property:*** `<TrekkerOptions/>`

Pathname of an XML file containing character mappings used by the [**Translate to C# Project**](ProjGenCSharp.html#translate-to-c-project) command.

![Character replacement file option.](images/TrekkerCharReplacement.png)

---
## Miscellaneous Options

Many more generic .NET application properties are available in other areas of **Project Properties**. The **Search** text box in this window is helpful for finding a property of interest.  The next sections provide links to help get you started.

---
### Project Properties UI

**Project Properties**, also known as the [.NET Project Designer](https://learn.microsoft.com/visualstudio/ide/reference/project-properties-reference), exposes many more options common to most .NET SDK-based projects.  Some of these have no bearing on Encore projects however:

* [Application Settings](https://learn.microsoft.com/visualstudio/ide/reference/project-designer-dotnet-csharp#application-general-settings)
* [Resources and Manifests](https://learn.microsoft.com/visualstudio/ide/reference/project-designer-dotnet-csharp#application-win32-resources-settings)
* [General Build Settings](https://learn.microsoft.com/visualstudio/ide/reference/project-designer-dotnet-csharp#build-general-settings)
* [Warnings and Errors](https://learn.microsoft.com/visualstudio/ide/reference/project-designer-dotnet-csharp#build-errors-and-warnings-settings)
* [Debug Settings](https://learn.microsoft.com/visualstudio/ide/reference/project-designer-dotnet-csharp#debug-general-settings)

---
### MSBuild Project Properties

[MSBuild](https://learn.microsoft.com/dotnet/core/project-sdk/overview) is the underlying build engine for all .NET SDK projects including Encore. It provides many more properties, targets, and tasks to cover almost any .NET development scenario.

* [TargetFramework](https://learn.microsoft.com/dotnet/core/project-sdk/msbuild-props#framework-properties)
* [Items, References, and Metadata](https://learn.microsoft.com/dotnet/core/project-sdk/msbuild-props#items)
* [Common Properties](https://learn.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties)

{% include er4vs_foot_links.html %}