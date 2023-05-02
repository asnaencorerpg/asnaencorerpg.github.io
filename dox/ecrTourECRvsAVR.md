---
title: Encore RPG vs. Visual RPG Lnaguage
---

## Similar But Different

If you have ever used ASNA's other programming language [**ASNA Visual RPG**](//docs.asna.com/documentation/Help170/AVRRuntime/_HTML/Welcome.htm){:target="_blank"}&#x1F875; (AVR), you will find **ASNA Encore RPG** (ECR) to be similar to AVR, however there are some differences on its [lexical elements](#lexical-elements) and supported [opcodes](#opcodes-and-keywords).

## Lexical Elements

 + Class, Field, Property and Method Names are Case-Sensitive.

 + `*INxx` indicators are uppercase.

 + Commands, Keywords and Figurative Constants are Case-Less

 + Arrays must use square brackets:  
     `Sales[month] = 0`

 + String constants must use double quotes:  
      `DclFld Copyright *Char Init("ASNA, Inc.")`

 + Single character constants use single quotes (what used to be O'f' in AVR):   
       `DclFld MyOneChar *OneChar Init('f')`

## Opcodes and Keywords
Several Opcodes and Keywords are not present in ECR.

### Data Structures 
The implementation of Data Structures in ECR is closer to that of RPG than the one AVR had.

The `DCLDS` opcode can have have `LEN` keyword and it only supports basic RPG types (no `*string`, no `*decimal`, no objects) and the `DCLDSFLD` command has a `START` keyword.

 + The following commands are not present in ECR:
 + `DclAlias & DclAliasGroup`
 + `DclOverlayGroup`
 + `DsDumpToBuffer/DsLoadFromBuffer`
 + `Set`

### No support for Window and Web Forms
Because ECR does not support the creation of applications with Window Forms, then the following Opcodes are not present in ECR.

 + `Show, Hide, NewForm, Unload, MsgBox`
 + `LoadPicture, SetMousePtr`
 + `DclEvent, DoEvents, AddHandler, RemoveHandler`
 + `DclSubfile, DclSubfileFld`

Additionally the `BEGSR` and `BEGFUNC` opcodes do not have the `EVENT` keyword.
