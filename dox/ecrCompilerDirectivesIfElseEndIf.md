---
title: /IF /ELSE /ELSEIF /ENDIF (Encore RPG)

Id: aerCompilerDirectivesIfElseEndIf
TocParent: aerCompilerDirectivesMain
TocOrder: 4


---

The /IF /ELSE /ELSEIF /ENDIF directives conditionally compile selected blocks of Encore RPG code. 

### Remarks
**/IF** <condition> - tests a condition expression for conditional compilation. 

**/ELSEIF** <condition> - tests a subsequent condition inside a /IF or /ELSEIF group 

**/ELSE** - unconditionally selects source lines to be read following afailed /IF or /ELSEIF test. 

**/ENDIF** - ends the most recent /IF, /ELSEIF or /ELSE group. 

where <condition> is **DEFINED** (<symbol>) or **NOT DEFINED** (<symbol>) 

Code that is passed over due to a /IF /ELSE /ENDIF isn’t just skipped during execution (like a normal if else endif), but it is totally skipped over during **compilation** . So a block of code held by a /IF that evaluates to false can have anything at all within it (c#, pascal, gibberish, etc.) and the compiler will **not let the user know** because it is simply not compiled. Thus, the very act of changing a defined symbol to undefined, or vice versa could potentially cause huge differences in the compilation results. 

- An /IF group can contain at most one /ELSE and must me matched by a terminating /ENDIF 

- /ELSEIF and /ELSE are not valild outside an /IF group, and an /ELSEIF cannot follow an /ELSE 

- An /IF group must be contained within the same source file; it's not valid to have an /IF in a file with /ELSEIF or /ELSE directives, or the matching /ENDIF in a /COPY file. 

### Example
See example in [/DEFINE](ecrCompilerDirectivesDefine.html).

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[Compiler Directives](ecrCompilerDirectivesMain.html) 

[/DEFINE](ecrCompilerDirectivesDefine.html) 
