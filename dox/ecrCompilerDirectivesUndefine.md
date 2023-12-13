---
title: /UNDEFINE (Encore RPG)

Id: aerCompilerDirectivesUndefine
TocParent: aerCompilerDirectivesMain
TocOrder: 7


---

**/UNDEFINE** defines conditions for conditional compilation. 

```
 /UNDEFINE <symbol>       
```

### Parts

**symbol** 

Symbol can be any valid RPG name.  Symbols are defined by the user either by using the /DEFINE directive, or
                by specifying them in the Build tab of a Project's Property page under the "Conditional Compilation Symbols" textbox. 
                a symbol definition is valid for the compilation of a program, which is
                the equivalent of the compilation of a.vr source file (and all of its /COPY include files).


### Remarks
**/UNDEFINE** will make the specified symbol evaluate to False in a **/IF DEFINED** directive and True in an **/IF NOT DEFINED** directive. / **DEFINE** will do the opposite. 

/ **DEFINE** and / **UNDEFINE** are not used by anything other than / **IF** / **ELSEIF** . 

### Example

```
/DEFINE Debug
/IF DEFINED (Debug)

    //This block is compiled and executed

    /ELSEIF NOT DEFINED (Debug1)

    //This block is not compiled

    /ELSE

    //This block is not compiled

/ENDIF

/UNDEFINE Debug
```

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[Compiler Directives](ecrCompilerDirectivesMain.html) 

[/Undefine](ecrCompilerDirectivesUndefine.html) <br /> 
