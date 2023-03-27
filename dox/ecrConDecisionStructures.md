---
title: Decision Structures

Id: aerConDecisionStructures
TocParent: aerConControlFlow
TocOrder: 0


---

Decision structures allow you to execute one or more lines of code based upon conditions tested, and then perform different operations depending on the results of that test. You can test for a condition being true or false, for specific values of an expression, or for various exceptions generated when you execute statements. The decision structures supported by Encore RPG include: 

- [IF](IF.html)...THEN...[ELSE](ELSE.html) process a
                group of
                commands when a comparison expression evaluation is True(```IF```),
                or False(```ELSE).``` The comparison expression is evaluated
                at the end of the commands, and if the expression is true, the group of
                commands are executed again.  An [ENDIF](ENDIF.html) or
                [END](END.html)
                command is required to end the group of commands.
- [SELECT](SELECT.html) conditionally processes one of several
                alternative sequences of operations.  It consists of a ```SELECT```
                statement, zero or more [WHEN](WHEN.html) groups, an
                optional [OTHER](OTHER.html) group, and terminates with an ```
                    [END](END.html)
                ``` or [ENDSL](ENDSL.html) statement.  You can also
                use [CASE](CASE.html), to specify a comparison
                expression to select a subroutine for processing when the condition
                evaluates ```True```.
- [TRY..CATCH..FINALLY](TRYCATCHFINALLY.html) provides a way to trap
                possible errors that may occur in code segments, while still running the
                code.  The ```TRY``` statements are executed first, any
                exceptions are trapped with the ```CATCH``` commands, and ```FINALLY```
                commands are executed when no exceptions are trapped.  An ```
                    [ENDTRY](ENDTRY.html)
                ``` command is required to end the group of commands.

### Related Sections

[Loop Structures](ecrConLoopStructures.html)

Discusses control-flow commands used to repeat processes.


[Nested Control Structures](ecrConNestedControlOpCodes.html)

Explains control-flow commands inside other control-flow commands.


### See Also
[CASEDFT](CASEDFT.html)

[TRY](TRY.html)

[CATCH](CATCH.html)

[FINALLY](FINALLY.html)

[Encore RPG Language Reference](ecrLrfLangRefMain.html) 
