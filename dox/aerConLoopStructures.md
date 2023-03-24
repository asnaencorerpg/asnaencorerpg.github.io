---
title: Loop Structures

Id: aerConLoopStructures
TocParent: aerConControlFlow
TocOrder: 1


---

Loop structures allow you to execute one or more lines of code repetitively. You can repeat the commands until a condition is true, until a condition is false, a specified number of times, or once for each object in a collection. The loop structures supported by Encore RPG include: 

- [Do](DO.html) begins a group of operations and indicates the number
                of times the group will be processed.  An [ENDDO](ENDDO.html)
                statement marks the end of the group.
- [DOWHILE](DOWHILE.html) executes a block of commands while a
                comparison expression evaluates true. An <code> **ENDDO** </code>
                statement marks the end of the group.
- [DOUNTIL](DOUNTIL.html) executes a block of commands until a
                comparison expression evaluates true.  An <code> **ENDDO** </code>
                statement marks the end of the group.
- [FOR](FOR.html) executes a block of commands a specified number
                of times, until the index value is greater than or less than the limit value,
                depending on the keyword values.  After the number of iterations has been
                completed, control is transferred to the next statement following the <code> **FOR** /[ENDFOR](ENDFOR.html)</code>
                block.
- [FOREACH](FOREACH.html) executes a block of commands for each
                element in an array or collection.  After the iteration has been
                completed for all the elements in the collection, control is transferred to the
                next statement following the <code> **FOREACH** /[ENDFOR](ENDFOR.html)</code>
                block.

### Related Section

[Decision Structures](aerConDecisionStructures.html)

Explains control-flow commands used for branching.


[Nested Control Structures](aerConNestedControlOpCodes.html)

Explains control-flow commands inside other control-flow commands.


### See Also
[Encore RPG Language Reference](aerLrfLangRefMain.html) 
