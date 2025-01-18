---
title: Source Editing
description: The Visual Studio editor extensions for editing code with completion, signature help, and other time saving language service short cuts are documented here.

Id: aerVsSourceEditing
TocParent: Editor Features
TocOrder: 15


---

Encore RPG for Visual Studio provides IntelliSense® features via its own in-process language service and editor extensions. These provide most of the "basic" IntelliSense features and a few extras:

* Themed, customizable Encore syntax colorization.
* Class, method, code-block, and `#region` collapsibility and brace matching.
* Code window UI for tracking and locating classes, members, and Encore data structures in the editor.
* Syntax-aware auto-indentation when entering code.
* Encore opcode and keyword `F1` help documentation.
* Encore statement signature help and code completion.
* Method call signature help and code completion.
* Go-to-definition support for Encore code.
* Mouse cursor-hovering "quick info" support with Encore syntax.
* Most features configurable via **Tools\|Options**.

Some of the above are self explanatory, and others are discussed below and in [Source Navigation](ecrVsSourceNav).

* [Syntax Coloring](#syntax-coloring)
* [Regions and Braces](#code-and-non-code-regions)
* [Smart Indentation](#smart-indentation)
* [Opcode Completion](#encore-opcode-completion-and-signature-help)
* [Metadata Completion](#metadata-completion)
* [Method Signature Help](#method-signature-help)

---
### Syntax Coloring

Encore RPG for Visual Studio colors certain syntactic elements shown in the Encore editor. The colors displayed depend on the current Visual Studio [color theme](https://learn.microsoft.com/visualstudio/ide/how-to-change-fonts-and-colors-in-visual-studio#change-the-color-theme) and user preferences.

> Encore RPG provides default colors for the default theme and the Visual Studio "OEM" themes (blue/dark/light), which can be customized.

To customize the available Encore syntactic elements, use the **Options..** command on the **Tools** menu. In the options dialog tree view on the left, select the **Environment** and then **Fonts and Colors**, as shown below.  Ensure that "Text Editor" is selected in the "Show settings for" drop-down box at the top of the dialog. Next, look for the entries in the "Display Items" list that begin with "Encore RPG", as shown. This dialog not only configures the colors of these items, you may also change their font attributes.

![Changing font and/or color in Encore RPG.]({{ page.vs_images_path }}EditorColorChangeDialog.png)

> Font and color modifications are saved in the user's [Visual Studio settings](https://learn.microsoft.com/visualstudio/ide/personalizing-the-visual-studio-ide), and are applied only to the current theme.

---
### Code and Non-code Regions

The language service identifies various "regions" in the Encore ile being edited, and the editor displays these in a couple of ways. For code regions, the outer-most scope is displayed as a vertical line in the left margin beginning at the start of the scope with a origin glyph and ending with a termination glyph at the end of the scope.  Each visible inner scope will also show an origin scope on the line at its starting line. The origin glyph, shown as a rotating "V" caret below, can be clicked to "collapse" the region, only showing the first few characters of its first line, as shown in this animation (you may need to refresh the page):

![Animation displaying the collapsibility of code regions.]({{ page.vs_images_path}}EditorRegionCollapseToggle.gif)

> Non-code regions may also be created and similarly used with the [`/Region` and `/EndRegion`](ecrConHidingandCollapsingCode) compiler directives.

Some regions identify code "braces": sections of code that are "scoped" by Encore keywords such as `If`/`Endif`, or `BegFunc`/`DclSrParm`/`EndFunc`. Identifying the "partner" elements of braced code sections is easy. Move the cursor to one of the keywords, as shown below with `EndConstructor`.  The keyword and its scope-defining partners are moderately highlighted in the editor. This is particularly useful in large or deeply-nested scope constructs.

> This feature may be enabled/disabled via the "Enable brace pair" option in **Tools\|Options**, and then restarting the editor.

![Brace matching `BegConstructor` in the editor.]({{ page.vs_images_path }}EditorBraceMatching.png)

---
### Smart Indentation

This feature automatically sets the cursor at a configurable offset from the current line when **Enter** is pressed.  For example, after an `If` statement is entered, the block containing the code to be executed when the `If` condition is true should usually be indented slightly, for clarity.  The language service detects this, and sets the cursor at the indentation point on the next line.

![Smart indenting after an `If` statement.]({{ page.vs_images_path }}EditorSmartIndenting.png)

> Smart Indentation, tab offsets, and similar features are configurable. Search for "Encore Tabs" in **Tools\|Options**.

---
### Encore Opcode Completion and Signature Help

The editor's "code completion" feature is helpful when coding complex Encore "command" opcodes, such as [`DclDB`](DCLDB). Optional or required keywords for the command are shown as a scrollable prompt containing lists of candidate keyword values. The lists dynamically update, based on the keywords already entered, and/or their implied position, to help jog your memory regarding proper usage.

![Command signature help prompts help you design the perfect DclDB statement.]({{ page.vs_images_path }}EditorCommandSigHelp.png)

> In the list of keywords in the prompt shown above, optional keywords are shown in braces. Required keywords, like `Name`, do not have braces.

> As in the prompt above, keywords are displayed in "positional" order; that is, the order the compiler would expect their values when the command keyword is *implied* rather than *specified explicitly*.

> The term "signature" here refers to a valid usage of an Encore command.

Some keywords, such as `Access` in `DclDB` only accept certain values. Below, the allowed values are prompted in a "completion list" after the open-parenthesis character is entered. You can select one of the values with the **Up**/**Dn** keys then press **Tab** to enter the value in the editor.  Alternatively, you can use the mouse to select an item in the list.

![Completion list for the `Access` keyword.]({{ page.vs_images_path }}EditorKeywordCompletion.png)

> Code completion and signature help features can be enabled/disabled in **Tools\|Options**, via the "Auto-list members", and "Parameter information" options.

> Additionally, the Encore editor supports [online help documentation](ecrVsSourceNav#f1-encore-opcode-help) for most opcodes.

---
### Metadata Completion

Code completion also works with .NET member references and method parameters. In the editor shown below, the user has just entered the '.' character on line 39. The editor responded by querying the Encore language service for metadata references related to the `DateOnly` reference preceding the character. The language service resolved this to the fully-qualified type[`System.DateOnly`](https://learn.microsoft.com/dotnet/api/system.dateonly), and listed its publicly accessible class members (or `*Shared` members) as valid completion candidates.

![Code completion for class members of the `System.DateOnly` type.]({{ page.vs_images_path }}EditorMetadataCompletion.png)

Note that the currently selected member, `FromDateTime`, is a method whose definition is shown in the pop-up to the right of the selection.

> Code completion also works with non-`*Shared` members when the reference is an object reference.

> Code completion is only invoked when the language service can successfully resolve the reference to a .NET object or class that is [visible](https://learn.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers) in the current scope.

---
### Method Signature Help

Continuing on from the previous example, the user clicks `FromDateTime` (or uses the **Tab** key) to enter the selection into the editor. Now the user enters the '(' character, as shown in the animation below. This provides the details of the method, including a required parameter in Encore syntax.  As the user enters parameter information, the completion list narrows in size, until the desired item, [`DateTime` class](https://learn.microsoft.com/dotnet/api/system.datetime) is found and selected. The user then goes on to enter characters for the desired `DateTime` member, `Now`, to finish the method call.

> If the animation below has stopped, please [refresh the page](#method-signature-help).

![Code completion animation showing mechanics of method signature help and completion.]({{ page.vs_images_path}}EditorCompletionAnimation.gif)

> Note that the completion list control includes buttons below the list to narrow the scope of the list based on a desired syntactic element, e.g., method, property, field, class, language keyword, etc.

> The term "signature" in this case refers to a valid usage of a .NET method.

{% include er4vs_foot_links.html %}