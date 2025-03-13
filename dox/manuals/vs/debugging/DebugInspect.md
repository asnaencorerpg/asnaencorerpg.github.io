---
title: Inspect Variables and Program State
description: Introduction to some of the many ways to analyze running Encore programs while debugging in the IDE.

Id: aerVsDebugInspect
TocParent: Projects
TocOrder: 5


---

Every installation of Visual Studio provides [nearly two dozen tool windows](https://learn.microsoft.com/visualstudio/debugger/debugger-windows) to help analyze the state of .NET programs running in the debugger. Encore RPG for Visual Studio extends these with familiar Encore syntax in both the tools and the editor.

* View variable values, and in many cases modify them if desired.
* Most values and expressions use Encore syntax.

---
### Example Class

In the walkthroughs of the following sections, we will use a simple Encore class that "models" a weather forecast (the logic in this example was borrowed from an [ASP.NET Core template](https://learn.microsoft.com/aspnet/core/web-api/)).  The `WeatherForecast` object defines four simple properties as follows:

```code
BegClass WeatherForecast Access(*Public)

    DclProp Type(*Date) TimFmt(*YMD) Name(Date) Access(*Public) 

    DclProp Type(*Integer4) Name(TemperatureC) Access(*Public)

    BegProp Like(TemperatureC) Name(TemperatureF) Access(*Public)
        BegGet
            LeaveSr 32 + (TemperatureC / 0.5556)
        EndGet
    EndProp
    
    DclProp Type(*String) Name(Summary) Access(*Public)

EndClass
```

---
### Watch Window Functions

In the example application, instances of `WeatherForecast` are created on-demand to build an array representing "5 day" weather predictions, using the following code running in the debugger. At line 42, the program will assign an array element with the value of the `forecast` reference created in the preceding lines.

![This running application hit a breakpoint just after constructing a `WeatherForecast` object.](images/InspectSetup.png)

We could use the **Watch** window to monitor the creation of WeatherForecast objects in the code above. Or, if we just want a quick summary view of the `forecast` value, we can hover the mouse cursor over a code reference to the variable, and let the editor's IntelliSense® features do the job:

![Hovering over `forecast` causes the editor to display a condensed watch window view.](images/InspectCursorQuickWatch.png)

> Encore class objects implicitly define indicator members `*IN`. Also, note that the value for `Date` is shown in the *YMD format defined by the property declaration in `WeatherForecast`.

Now, right-click on a `forecast` reference in the code, and select the **Add Watch...** command. A similar display is shown in the **Watch** window tool, which includes a Search box useful for finding certain members or values in complex objects. You can optionally type in `forecast` in the last row of the **Watch** window to with the same effect:

![Adding the `forecast` variable to the Watch window tool.](images/InspectWatchWindow.png)

> Most syntactic elements can be observed in watch windows, including member variables, arrays, and in some cases simple method calls.

> Values in watch window displays are only valid when the debugger is stopped on a breakpoint.

---
### Locals Window

The **Locals** window provides similar capabilities as the **Watch** window. However, the only variables shown by **Locals** are the local "automatic" variables in the scope of the current code. Member variables are excluded by **Locals**, when in a member method, the `*this` reference can be accessed:

![Viewing the value of `*this` in the **Locals** window.](images/InspectThisViaLocals.png)

{% include er4vs_foot_links.html %}