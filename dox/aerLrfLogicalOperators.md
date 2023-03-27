---
title: Logical Operators

Id: aerLrfLogicalOperators
TocParent: aerLrfOperatorsMain
TocOrder: 0


---

The ***BitAnd** , ***BitOr** , ***BitXor** operators are called the logical operators. The operators are evaluated as follows: 

- For the * **Boolean**  type:
                <ul type="disc">
                    <li>
                        a logical * **BitAnd** 
                        operation is performed on its two operands.
- a logical * **Or** 
                        operation is performed on its two operands.
- a logical exclusive * **BitXOr** operation is performed on its two 	operands.

</li>
            <li>
                For * **Byte** , * **Char** , * **Integer** , ***String** , and
                all enumerated types, the specified operation is performed on each bit of the
                binary representation of the two operands:

- ***BitAnd** : The result bit is 1 if both bits are 1; otherwise the result bit is 0.
- ***BitOr** : The result bit is 1 if either bit is 1; otherwise the result bit is 0.
- ***BitXor** : The result bit is 1 if either bit is 1 but not both bits; 	otherwise the result bit is 0 (that is, 1 ***BitXor**  0 = 1, 1 * **BitXor** 
                        1 = 0).

</li>
        </ul>

### See Also
[Operators](aerLrfOperatorsMain.html)

[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
