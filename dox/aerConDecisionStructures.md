---
title: Decision Structures

Id: aerConDecisionStructures
TocParent: aerConControlFlow
TocOrder: 0


---

Decision structures allow you to execute one or more lines of code based upon conditions tested, and then perform different operations depending on the results of that test. You can test for a condition being true or false, for specific values of an expression, or for various exceptions generated when you execute statements. The decision structures supported by Encore RPG include: 

- [IF](IF.html)...THEN...[ELSE](ELSE.html) process a
                group of
                commands when a comparison expression evaluation is True(<code> **IF** </code>),
                or False(<code> **ELSE).** </code> The comparison expression is evaluated
                at the end of the commands, and if the expression is true, the group of
                commands are executed again.  An [ENDIF](ENDIF.html) or
                [END](END.html)
                command is required to end the group of commands.
- [SELECT](SELECT.html) conditionally processes one of several
                alternative sequences of operations.  It consists of a <code> **SELECT** </code>
                statement, zero or more [WHEN](WHEN.html) groups, an
                optional [OTHER](OTHER.html) group, and terminates with an <code>
                    [END](END.html)
                </code> or [ENDSL](ENDSL.html) statement.  You can also
                use [CASE](CASE.html), to specify a comparison
                expression to select a subroutine for processing when the condition
                evaluates <code>True</code>.
- [TRY..CATCH..FINALLY](TRYCATCHFINALLY.html) provides a way to trap
                possible errors that may occur in code segments, while still running the
                code.  The <code> **TRY** </code> statements are executed first, any
                exceptions are trapped with the <code> **CATCH** </code> commands, and <code> **FINALLY** </code>
                commands are executed when no exceptions are trapped.  An <code>
                    [ENDTRY](ENDTRY.html)
                </code> command is required to end the group of commands.

### Related Sections

[Loop Structures](aerConLoopStructures.html)

Discusses control-flow commands used to repeat processes.


[Nested Control Structures](aerConNestedControlOpCodes.html)

Explains control-flow commands inside other control-flow commands.


### See Also
[CASEDFT](CASEDFT.html)
[TRY](TRY.html)
[CATCH](CATCH.html)
[FINALLY](FINALLY.html)
[Encore RPG Language Reference](aerLrfLangRefMain.html) 
