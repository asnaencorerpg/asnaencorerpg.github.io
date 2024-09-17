---
title: Encore RPG vs. Visual RPG Language
---

## Similar But Different

If you have ever used ASNA's other programming language [**ASNA Visual RPG**](//docs.asna.com/documentation/Help170/AVRRuntime/_HTML/Welcome.htm){:target="_blank"}&#x1F875; (AVR), you will find **ASNA Encore RPG** (ECR) to be similar to AVR, however there are some differences on its [lexical elements](#lexical-elements) and supported [opcodes](#opcodes-and-keywords).

Visual RPG produces .NET Framework assemblies while Encore RPG generates .NET assemblies.


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

 + Some Built-In functions have been renamed:   
       `%IsOmitted` is now `%Omitted`

 + Obsolete Built-In functions:   
       `%SubArr`

## Array  Differences
AVR and ECR have two ways of declaring an Array. An array is defined with the [DCLARRAY](/dox/DCLARRAY.html) command using either the keyword:
 - `DIM`
 - `RANK`

### DIMed Arrays
In AVR and in ECR, an array defined via the DIM keyword gets its storage allocated as part of the `DCLARRAY` command. In AVR the array can have multiple dimension, however, in ECR the array can only have one dimmension. In ECR, multidimensional arrays have to be defined via the `RANK` keyword.

### RANKed Arrays
Arrays declared with the `RANK` keyword are similar in AVR and ECR, both implementations allow for one or more dimensions and require the array to be initialized explicitly via the `NEW` keyword, the `*NEW` operator or an assignment.

## Data Structure Differences
The implementation of Data Structures in ECR is closer to that of RPG than the one AVR had.

The `DCLDS` opcode can have have `LEN` keyword and it only supports basic RPG types (no `*string`, no `*decimal`, no objects) and the `DCLDSFLD` command has a `START` keyword.

## Obsolete Commands
 The following AVR commands are not present in ECR:
 + `DclAlias & DclAliasGroup`
 + `DclDelegate`
 + `DclMemoryFile`
 + `DclOverlayGroup`
 + `DclPrototype`
 + `DsDumpToBuffer/DsLoadFromBuffer`
 + `Set`

### No support for Window and Web Forms
Because ECR does not support the creation of applications with Window Forms, then the following Opcodes are not present in ECR.

 + `Show, Hide, NewForm, Unload, MsgBox`
 + `LoadPicture, SetMousePtr`
 + `DclEvent, DoEvents, AddHandler, RemoveHandler`
 + `DclSubfile, DclSubfileFld`

## Additional Notes
 + The `BEGSR` and `BEGFUNC` opcodes do not have the `EVENT` keyword.
