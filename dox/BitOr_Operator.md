---
title: "*BitOr Operator"

Id: BitOr_Operator
TocParent: aerLrfOperatorsMain
TocOrder: 10


---

Used to perform a logical disjunction on two Boolean expressions, or a bitwise disjunction on two integer values. 

```
 ** *result* **  = ** *expression1* **  *BitOr ** *expression2* ** 
```


### Parts

**result** 

Required. Any Boolean or numeric expression. For Boolean comparisons, the result is the logical disjunction of two expressions. For bitwise operations the result is a numeric value resulting from the bitwise disjunction of two numeric expressions.


**expression1** 

Required. Any Boolean or numeric expression.


**expression2** 

Required. Any Boolean or numeric expression.


### Remarks
For **Boolean** comparison, if either *expression1* or *expression2* evaluates to **True** , result is **True** . If *expression1* evaluates to **True** , and *expression2* evaluates to False, the result is **True** . The following table illustrates how the *result* is determined: 
<table class="dtTABLE" id="Table3" cellspacing="0">
                <tr valign="top">
                    <th colspan="1" rowspan="1" width="33%">
                        If *expression1*  is
                    </th>
                    <th colspan="1" rowspan="1" width="33%">
                        And *expression2*  is
                    </th>
                    <th colspan="1" rowspan="1" width="34%">
                        Then *result*  is
                    </th>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%" height="22">True</td>
                    <td colspan="1" rowspan="1" width="33%" height="22">True</td>
                    <td colspan="1" rowspan="1" width="34%" height="22">True</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%">True</td>
                    <td colspan="1" rowspan="1" width="33%">False</td>
                    <td colspan="1" rowspan="1" width="34%">True</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%" height="21">False</td>
                    <td colspan="1" rowspan="1" width="33%" height="21">True</td>
                    <td colspan="1" rowspan="1" width="34%" height="21">True</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%">False</td>
                    <td colspan="1" rowspan="1" width="33%">False</td>
                    <td colspan="1" rowspan="1" width="34%">False</td>
                </tr>
</table>

For **bitwise** operations, the *bitOr operator performs a bitwise comparison of identically positioned bits in two numeric expressions and sets the corresponding bit in *result* according to the following table: 
<table class="dtTABLE" id="Table2" cellspacing="0">
                <tr valign="top">
                    <th colspan="1" rowspan="1" width="33%">
                        If bit in *expression1*  is
                    </th>
                    <th colspan="1" rowspan="1" width="33%">
                        And bit in *expression2*  is
                    </th>
                    <th colspan="1" rowspan="1" width="34%">
                        Then *result*  is
                    </th>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%" height="22">0</td>
                    <td colspan="1" rowspan="1" width="33%" height="22">0</td>
                    <td colspan="1" rowspan="1" width="34%" height="22">0</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%">0</td>
                    <td colspan="1" rowspan="1" width="33%">1</td>
                    <td colspan="1" rowspan="1" width="34%">1</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%" height="24">1</td>
                    <td colspan="1" rowspan="1" width="33%" height="24">0</td>
                    <td colspan="1" rowspan="1" width="34%" height="24">1</td>
                </tr>
                <tr valign="top">
                    <td colspan="1" rowspan="1" width="33%">1</td>
                    <td colspan="1" rowspan="1" width="33%">1</td>
                    <td colspan="1" rowspan="1" width="34%">1</td>
                </tr>
</table>

**Note** Since the logical/bitwise operators have a lower precedence than other arithmetic and relational operators, any bitwise operations should be enclosed in parentheses to ensure accurate execution. 

If the operands consist of one **Boolean** expression and one numeric expression, the result **Boolean** expression will be converted to a numeric value (-1 For True, and 0 For False) and the bitwise operation will result. 

### Example

```
	dclconst   Hex24  Value( H"24" )
	dclfld     Byte1  Type( *byte ) INZ( H"46")
	dclfld     Byte2  Type( *byte )
	dclfld     Int1   Type( *integer2 ) INZ( H"46" )
	dclfld     Int2   Type( *integer2 )
	dclfld     Bool1  Type( *Boolean ) INZ( *true )
	dclfld     Bool2  Type( *Boolean ) 
	dclfld     Str2   Type( *string )

	Byte2 = Byte1 *BitOr Hex24      // Byte2 = H"66"
        Int2  = Int1 *BitOr Hex24  	// Int2 = 102 or H"0066"
	Bool2 = Int2 *BitOr  H"11"      // Bool2 = True
	Str2   = Int1 *BitOr Hex24  	// Str2 = "102"
	Int2   = Bool1 *BitOr H"0C00"   // Int2 = 3073 or H'0C01"
```

### See Also
[*BitAnd Operator](BitAnd_Operator.html)

[Operators](BitNot_Operator"> *BitNot Operator </a> <br /> <a href="BitOr_Operator">*BitOr Operator</a> <br /> <a href="aerLrfOperatorsMain.html)

[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
