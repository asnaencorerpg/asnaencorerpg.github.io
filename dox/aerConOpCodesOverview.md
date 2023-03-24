---
title: Operation Codes Overview

Id: aerConOpCodesOverview
TocParent: aerConOpCodes
TocOrder: 0


---

An operation code, or command in Encore RPG, is a complete instruction. It can contain keywords, operators, variables, constants, and expressions. Each command belongs to one of the following two categories: 

- Declaration commands, which name a variable, constant, or
                procedure and can also specify a data type. For more information, see [Declaration Operation Codes](aerConDeclarationOpCodes.html).
- Executable commands, which initiate actions. These commands can execute a
                method or function, and they can loop or branch through blocks of code.
                Executable commands include assignment commands, which assign a value or
                expression to a variable or constant. For more information, see [Executable Operation Codes](aerConExecutableOpCodes.html) and [Assignment Operation Codes](aerConAssignmentOpCodes.html).

### Continuing a Statement over Multiple Lines
An operation code usually fits on one line, but when it doesn't, you can continue a long command onto the next line using a line-continuation character, which consists of a **plus** sign. In the following example, the <code> **DCLFLD** </code> command is continued over two lines: 

```
 DCLFLD myVar Type (*String) Shared (*YES) +
  WithEvents (*YES)
```

### Adding Comments
To help document code, it is useful to make liberal use of embedded comments. Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later. Encore RPG ignores comments, however, when it runs your procedures. 

Comment lines begin with a double slash (<code>//</code>), and can be added anywhere in code. Comments can also go on their own separate line. To extend comments over multiple lines, you can either add a double slash at the beginning of each line, or use a <code> ***/** </code> at the beginning of the comment and end the comment with a <code> **/*** </code>. 

### See Also
[Assignment Operation Codes](aerConAssignmentOpCodes.html)
[Declaration Statements](aerConDeclarationOpCodes.html)
[Executable Operation Codes](aerConExecutableOpCodes.html) 
