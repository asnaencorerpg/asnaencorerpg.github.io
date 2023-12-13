---
title: FOR

Id: FOR
TocParent: aerLrfOpCodesMain
TocOrder: 1080


---

Starts a FOR/[ENDFOR](ENDFOR.html) loop.

```
 FOR
Index (index expression)
To (Expression)
DownTo (Expression)
By (Expression)
```

### Parts

**Index** 

Required. The index expression is either an assignment expression (<field> = <expression>), or a field (<field>). <field> represents a valid numeric field with 0 decimal positions (any of the integral types is allowed). <expression>, if given, represents the initial value of the field.


**To** 

Optional. Represents the upper limit of an upward-going iteration.


**DownTo** 

Optional. Represents the lower limit of a downward-going iteration.


**By** 

Optional. Represents the amount to be added or subtracted from the field given in the INDEX keyword. It defaults to 1.


### Remarks
**FOR/ENDFOR** blocks mimic the RPG ILE free-format **FOR** opcode. The **FOR** operation is performed as follows: 

1. If specified, the initial value is assigned to the index name.  Otherwise,
                the index name retains the same value it had before the start of the loop.
2. If specified, the limit value is evaluated and compared to the index name. 
                If no limit value is specified, the loop repeats indefinitely until it
                encounters a statement that exits the loop (such as a LEAVE or GOTO) or that
                ends the program or procedure (such as a LEAVESR).
                <br />
                If the **To**  clause is specified and the index name value
                is greater than the limit value, control passes to the first statement
                following the ENDFOR command.  If **DownTo** 
                is specified and the index name is less than the limit value, control passes to
                the first statement after the ENDFOR.
3. The operations in the
                FOR group are processed.
4. If the increment value is specified, it is evaluated.  Otherwise, it
                defaults to 1.
5. The increment value is either added to (for **To** ) or subtracted
                from (for **DownTo** ) the index name.  Control passes to
                step 2.
6. The statement after the END or ENDFOR command is processed when the index
                value is greater than (for **To** ) or less than (for **DownTo** )
                the limit value (step 2), or when the index value overflows.

**Note** 

If the **FOR** loop is performed *n* times, the limit value is evaluated *n+1* times and the increment value is evaluated *n* times. This can be important if the limit value or increment value is complex and time-consuming to evaluate, or if the limit value or increment value contains calls to subprocedures with side-effects. If multiple evaluation of the limit or increment is not desired, calculate the values in temporaries before the **FOR** loop and use the temporaries in the **FOR** loop. 

### See Also
[ENDFOR](ENDFOR.html) 
