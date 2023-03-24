---
title: "*BitNot Operator"

Id: BitNot_Operator
TocParent: aerLrfOperatorsMain
TocOrder: 9


---

The ***BitNot** operator specifies the result of a bitwise NOT operation performed on a numeric value. 

```
*BitNot ( *nExpression* )   
```

### Parts

*nExpression* 

Specifies the numeric value on which the bitwise NOT operation is performed. If *nExpression* is not an integer, it is converted to an integer before its bits are shifted.


### Example

```
dclconst   Hex24  Value( H"24" )
dclfld       Byte1   Type( *byte )       INZ( H"46")
dclfld       Byte2   Type( *byte )
dclfld       Int1      Type( *integer2 ) INZ( H"46" )
dclfld       Int2      Type( *integer2 )
dclfld       Bool1    Type( *Boolean ) 	INZ( *true )
dclfld       Bool2    Type( *Boolean )
dclfld       Str2      Type( *string )

Byte2  = Byte1    *BitOr ( *BitNot Hex24 )        // Byte2 = H"DF"
Int2    = *BitNot    ( Int1 *BitAnd Hex24  )        // Int2 = -5 or H"FFFB"
Bool2  = ( *BitNot Int2)    *BitXor H"11"            // Bool2 = True
Str2    = *BitNot ( Int1      *BitAnd Hex24 )      // Str2 = "-5"
Int2    = (*BitNot Bool1)    *BitOr H"0C00"        // Int2 = -2 or H'FFFE"			
```

### See Also
[*BitAnd Operator](BitAnd_Operator.html)
[Operators](BitOr_Operator"> *BitOr Operator </a> <br /> <a href="aerLrfOperatorsMain.html)
[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
