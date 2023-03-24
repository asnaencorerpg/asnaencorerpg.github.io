---
title: "<< Operator"

Id: aerLrfLeftShiftOperator
TocParent: aerLrfOperatorsMain
TocOrder: 4


---

Performs an arithmetic left shift on a bit pattern.

```
 ** *result = pattern &lt;&lt; bitCount* ** 
```

### Parts

*result* 

Required. Integral numeric value. The result of shifting the bit pattern. The
                datatype is the same as that of *pattern* .


*pattern* 

Required.  Integral numeric expression.  The bit pattern to be 	shifted.  The datatype must be ***Byte, *Integer** .


*bitCount* 

Required. Numeric expression. The number of bits to shift the bit pattern. The datatype must be ***Integer** .


### Remarks
The shift is an arithmetic left shift, the bits shifted beyond the range of the result datatype are discarded, and the bit positions vacated on the right are set to zero. 

To prevent shifting by more bits than the result can hold, ECR ensures that *bitCount* is less than the number of bits in the patter. If *bitCount* is zero, the value of *result* is identical to the value of *pattern* . If *bitCount* is negative, it is taken as an unsigned value and masked with the appropriate size mask. 

Arithmetic shifts never generate overflow exceptions.

### Example

```
BegSr
     shiftTest
     DclFld Byte *Byte        
     DclFldInt2 *Integer Len(2)
     DclFld Int4 *Integer Len(4)
     DclFld Int8 *Integer  
     DclFld string *String Byte = 7 
    		Int2 = 1 
    		Int4 = 7 
  		Int8 = 458752   // H"000070000" 
  		Byte = Byte &lt;&lt; 3 
  			System.Console.WriteLine
  			(Byte *as System.Int32) 
  		Byte = Byte &lt;&lt; 9             
 			System.Console.WriteLine(Byte *as System.Int32)
 		Byte = Byte &lt;&lt; 1 
  			System.Console.WriteLine (Byte *as System.Int32) Byte = Byte &gt;&gt; 1 
			System.Console.WriteLine (Byte *as System.Int32) Int2 = Int2 &lt;&lt; Int4               
 			System.Console.WriteLine (Int2 *as System.Int32)Int4 = Int4 &lt;&lt; Int2 
			System.Console.WriteLine (Int4) Int8 = Int8 &lt;&lt; 2
		Int8 = Int4 &lt;&lt; 94 
			System.Console.WriteLine (Int8) 
		Int2 = 17000 
		Int2 = Int2 &lt;&lt; 1 
		System.Console.WriteLine (Int2 *as System.Int32) 
		Int2 = Int2 &gt;&gt; 1
			System.Console.WriteLine (Int2 *as System.Int32)
EndSr 
```

### Results In
56 

112 

224 

112 

128 

7 

1835008 

-1073741824 

-31536 

-15768 

### See Also
[&gt;&gt; Operator](aerLrfRightShiftOperator.html)
[Operators](aerLrfOperatorsMain.html)
[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
