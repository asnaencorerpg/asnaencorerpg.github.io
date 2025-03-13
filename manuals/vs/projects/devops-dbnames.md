---
title: DevOps and Database Names

---

## Database Names and Runtime

For an overview of the “Database Name” concept and ways in which programs find databases at runtime please see [Database Store Naming Conventions](https://asnaqsys.github.io/manuals/configuration/database-names.html)

## Database Names and Compile Time 

### Compiling Encore RPG at your Desktop

As an Encore RPG developer, you most likely have setup your Database Names in your default `asnasettings.json` file which resides in

`C:\Users\{YourUserName}\AppData\Local\ASNA\DataGate\asnasettings.json`

This is the location where, by default, the compiler and QSys runtime look for Database Names.  

You can provide an additional file by utilizing the Encore RPG Project property `<AdditionalDBNamesFile/>`, for more information please see [Additional Database Name File](Config.html#additional-database-name-file).

### Building Encore RPG with DevOps

When compiling your application using Azure Pipelines or GitHub Actions, the ‘default’ `asnasettings.json` file typically does not exist, as it would in a developer environment. Fortunately, the `<AdditionalDBNamesFile/>` project property can be utilized to point the Encore RPG compiler to a file containing the database names.

The `<AdditionalDBNamesFile/>` property can be used effectively in a DevOps environment along with other facilities of MSBuild which is the underlying build engine of Encore RPG projects. For more information please see [MSBuild Project Property](Config.html#msbuild-project-properties).

One of these facilities is the `Directory.Build.props` file which can be used to establish the `<AdditionalDBNamesFile/>` property at the project level, or better yet at a ‘solution’ level.

If you have a solution directory with many projects in its subdirectories, then you can add a file named `Directory.Build.props` containing common properties for all the projects. In this file you can add the property `<AdditionalDBNamesFile/>` instructing the compiler where to locate the database names. 

### Example

If your solution had this structure:
```
C:/Source
├── MySolutionDirectory
    ├── ASolution.sln
    ├── Project_A_Dir
    ├── Project_B_Dir
    │   ├── ProjB.csproj
    │   ├── B1pgm.er
    │   ├── B2pgm.er
    │   └── MyJob.er
    └── Project_C_Dir
```

Then you could add a `Directory.Build.props` file to the MySolutionDirectory that would affect all the projects within it directory structure:
```
C:/Source
├── MySolutionDirectory
    ├── ASolution.sln
    ├── Directory.Build.props
    ├── Project_A_Dir
    ├── Project_B_Dir
    │   ├── ProjB.csproj
    │   ├── B1pgm.er
    │   ├── B2pgm.er
    │   └── MyJob.er
    └── Project_C_Dir
```

The `Directory.Build.props` file contents could be as simple as having a single property pointing the database names files to a hardcoded location like this:

```xml
<Project >
    <PropertyGroup>
        <AdditionalDBNamesFile>C:/SomeFolder/myasnasettings.json</AdditionalDBNamesFile>
    </PropertyGroup>
</Project>
```


Alternatively, you could provide the value in a conditional property group allowing a different value to be passed as a command line parameter while invoking msbuild. Like this:

```xml
<Project >
    <PropertyGroup Condition="'$(AdditionalDBNamesFile)'==''">
        <AdditionalDBNamesFile>C:/SomeFolder/myasnasettings.json</AdditionalDBNamesFile>
    </PropertyGroup>
</Project>
```

And then call `msbuild` or [dotnet build](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-build#:~:text=since%20.NET%206.-,%2Dp%7C%2D%2Dproperty%3A%3CPROPERTYNAME%3E%3D%3CVALUE%3E,-Sets%20one%20or) like this:

```shell
c:>cd /Source/MySolutionDirectory
c:>msbuild /p:AdditionalDBNamesFile="C:\OtherFolder\BuildAsnaSettings.json" ASolution.sln
```

### Compiling Against Different Environments

You may have the need to build your application against different environments, for instance you could build a QA version of your application against a QA database server and build a Production version against a different database server.

If that’s the case, then as part of your DevOps pipeline you could generate the contents of the database names file accordingly before invoking the msbuild process. 

Alternatively, you could change the contents of the `Directory.Build.props` file or the msbuild /p:AdditionalDBNamesFile parameter to point to the QA and Production environments.

