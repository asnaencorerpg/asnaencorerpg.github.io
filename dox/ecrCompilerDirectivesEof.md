---
title: /EOF (Encore RPG)

Id: aerCompilerDirectivesEof
TocParent: aerCompilerDirectivesMain
TocOrder: 3


---

**/EOF** acts as an end-of-file; which tells the compiler to ignore the rest of the source lines in the current source member. 

```
 **/EOF**       
```

### Remarks
**/EOF** is used to indicate that the compiler considers that end-of-file has been reached for the current source file. 

**/EOF** is used mostly within an **/IF** **/ENDIF** block. However, it can reside anywhere in code. If a line of code states / **EOF** , then all code **after** that point in the file is ignored and will not be compiled. 

### Remarks
See example in [/DEFINE](ecrCompilerDirectivesDefine.html). 

### Requirements
**Namespace:** ASNA.VisualRPG. Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG. Runtime .dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[Compiler Directives](ecrCompilerDirectivesMain.html) 

[/DEFINE](ecrCompilerDirectivesDefine.html) 
