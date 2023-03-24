---
title: Commands

Id: Commands
TocParent: aerLrfSyntacticalElementsMain
TocOrder: 0


---

Every **command** name is considered a reserved word of the Encore RPG Language. Each command has its set of keywords that the command processor is aware of. 

Parameters can be provided either plain or keyworded. Each parameter has a position assigned to it, even if it's optional. A parameter can always be keyworded, but can only be plain if it is provided in the position assigned to it. 

<u>For Example</u>: 

The command [DELETE](DELETE.html) has 4 parameters as follows:


|---------|-----------|---------------|------------------|
| From( )<br /><br /> 1 | Key( )<br /><br /> 2  | NotFnd( )<br /><br /> 3  | Err ( )<br /><br /> 4 |


The following are valid uses of the command: 

|---------|-----------|---------------|------------------|
| DELETE | From(F) | Key(K) | NotFnd(N) | Err (E) | 
| DELETE | F | K | N | E | 
| DELETE | F | K | N | Err (E) 
| DELETE | From(F) | K | NotFnd(N) | Err (E) | 
| DELETE | Key(K) | From(F) | N | E 

Any time a list or expression is provided as a parameter value, it must be given in keyworded format. If an operand is provided in place of an expression, it can be provided in plain format, otherwise it must be keyworded. 

There are certain commands, such as [IF](IF.html), [DOWHILE](DOWHILE.html), [DOUNTIL](DOUNTIL.html) which have some built-in parameters that have no keyword associated with them. These parameters must always be provided positionally, even if they are expressions. 

There are 2 types of commands:

- **Declarative** - Commands which are	allowed anywhere.
- **Operational**  -Commands which are
                subdivided into 4 subgroups.

Most operational commands may be labeled and may have conditional indicators.

A Label consists of a valid RPG name followed by a colon (":") right before the command name. i.e.: 

```
    DoOpen: OPEN DISTMAST 
```

Above, DoOpen is a valid target for a [GOTO](GOTO.html) statement. Note that the [TAG](TAG.html) command provides an alternative way to specify a label in an RPG program. 

Operational commands that have a **Result** or **Target** parameter, can define the receiver as a global variable by providing the following Type and Len parameters as the last parameters of the command: 

```
Type (*NONE | *CHAR | *ZONED | *PACKED)
Len (Length, DecimalPositions)      
```

### Related Sections
[Expressions](Expressions.html) 

[Simple Types](Simple_Types.html) 

[Type Conversions](Type_Conversions.html) 

### See Also
[DELETE](DELETE.html)
[IF](IF.html)
[DOWHILE](DOWHILE.html)
[DOUNTIL](DOUNTIL.html)
[GOTO](GOTO.html)
[TAG](TAG.html)
[Encore RPG Language Reference](aerLrfLangRefMain.html)
[Syntactical Elements](aerLrfSyntacticalElementsMain.html) 
