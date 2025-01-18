---
title: File Definition Caching
description: One bottleneck in the Encore development cycle is the compiler's resolution of externally-described file definitions via ASNA DataGate™. This page presents a potential remediation and its costs.

Id: aerVsProjFileDefCaching
TocParent: Projects
TocOrder: 5


---

Encore is designed for database applications accessing [so-called](https://www.ibm.com/docs/en/i/7.3?topic=df-defining-externally-described-files-1) "externally described files" in the traditional IBM RPG/400 paradigm. Encore needs file descriptions to generate the fields and structures used to model data columns and keys. The compiler must access the database, via ASNA DataGate™, to fetch the descriptions.

For small applications or applications with few database files, the price of accessing the file definitions is usually reasonable. For very large projects that access the same files over many compilations, the cost is higher. And in any case, the cost to access a database file scales with the power of the database platforms or network latency.

Encore SDK and the Encore compiler leverage the optional DataGate-enabled file definition caching feature to improve build performance in certain scenarios. File definitions can be cached on the Encore build machine, reducing the cost of fetching file descriptions from the database to near-zero. In very large applications or CI/CD builds, using this feature may significantly reduce build time.

File definition caching is supported by Encore RPG for Visual Studio extensions providing commands to manage and configure the cache.

> Note: file definition caching introduces the risk of unintended run-time failures if not properly managed. Please carefully review this entire document before integrating the feature in your project builds.

---
### When to CONSIDER Caching

There are only a few scenarios where using the cache can be useful and overcome potential [downsides](#when-to-avoid-caching):

1. **Applications with multiple projects that repetitively access files.** In CI/CD builds, a large applications may consist of dozens of projects, each requiring an Encore compiler invocation. Because file definition caching is persistent on the build machine, the definition of a file need only be fetched from the database once.  Thereafter, each successive compilation will use the cached definition.

2. **Development of a large project in an environment with slow database access.** In development scenarios, incremental builds occur often and should be fast. If the database is accessed over a slow network, or it resides on a platform with limited resources, caching could reduce build times and improve the development cycle.

---
### When to AVOID Caching

Even if caching seems attractive, there are pitfalls to be aware of if your development regime is fragile.

1. **When the database is under development with frequent, uncoordinated changes.** Database changes may render the cache "stale". If the change occurs during an application build, parts of the application could get out of sync with respect to file definitions, causing build failures at best and run-time failures at worst. Also note that use of `*LIBL` to qualify files in Encore must be considered. An administrator changing the build machine's credentials or the library list configuration also potentially fouls the cache. Library lists associated with the builder's database credentials, especially when using `*DOMAIN` authentication, must be scrutinized.

2. **When build times are OK.** It is probably not worth the effort of maintaining the caching scheme if you are satisfied with the performance of your build, whatever the scenario. Consider the file definition cache feature as a build optimization only. 

---
### Enabling the Cache

File definition caching is configured per-project. When the MSBuild property `<UseFileDefinitionCache/>` is set to `True`, Encore compiler will use the cache. You can set the property in several ways:

1. [**Project Settings**](ecrVsProjConfig#enable-file-definition-cache). Configuration in the IDE is simplest if your application has only one or very few projects. Enabling the cache this way sets the `<UseFileDefinitionCache/>` directly in the Encore project file.

2. [**Directory.Build.props**](https://learn.microsoft.com/visualstudio/msbuild/customize-by-directory#directorybuildprops-and-directorybuildtargets). If your build already has such a file for "default" settings, put the `<UseFileDefinitionCache/>` property there. Otherwise, create the file in a "root" folder that is an ancestor of all of the application's Encore projects. Thus, every project in the build inherits the property. This is the "only way to go" in development builds with many projects. Currently, `Directory.Build.props` cannot be managed by Visual Studio's Project Designer.

3. [**MSBuild Global Property**](https://learn.microsoft.com/visualstudio/msbuild/msbuild-properties#global-properties). The idea here is to set the `<UseFileDefinitionCache/>` property with a `-property` command-line switch, for example:
 
    ``
        msbuild.exe MyEncoreSolution.sln -property:UseFileDefinitionCache=true
    ``
    
    This obviously only works for command-line building, but may be the ideal solution for CI builds, where the caching feature may be most useful.  It is also an attractive option for simple benchmarking builds, to test whether caching provides adequate benefits.

---
### Clearing the Cache

The only maintenance to be performed by the user is flushing the cache "periodically". As mentioned above, when the cache becomes stale, it should be flushed. There are a few ways to do this in Visual Studio, and another "manual" way.  No matter the method used, after an enabled, configured cache is flushed, the projects associated with it are automatically re-built in a subsequent incremental build.

1. [**Rebuild and Clean**](https://learn.microsoft.com/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio). In Visual Studio, the cache is automatically cleared before the build, when it is invoked using any form of the **Rebuild** or **Clean** commands. Note that this *only* works in Visual Studio, not the command line or in other IDEs.

2. **Clear File Definition Cache** command as shown below. This command is available on the **Build** menu and context menus for solutions and projects.  Typically this is used when it is clear that a database change occurred that requires a cache refresh, but a solution rebuild is not desired.

    ![Using a Visual Studio menu command to clear the cache.]({{ page.vs_images_path }}FileDefCacheClearCommand.png)

3. **Delete the Cache Folder**. A single transient folder is dedicated for cache use only. Use any Windows method to delete the folder (or its *entire* contents). Be sure no builds using the cache are in-progress. To determine its location, you can use the [Visual Studio Project Designer](ecrVsProjConfig#file-definition-cache-location). The UI includes a handy link to open the folder in Windows Explorer to perform the flush.

{% include er4vs_foot_links.html %}