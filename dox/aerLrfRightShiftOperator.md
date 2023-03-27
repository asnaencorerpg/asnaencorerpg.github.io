---
title: ">> Operator"

Id: aerLrfRightShiftOperator
TocParent: aerLrfOperatorsMain
TocOrder: 5


---

Performs an arithmetic right shift on a bit pattern.

```
 ** *result*  = *pattern*  >> *bitCount* **    
```

### Parts

*result* 

Required. Integral numeric value. The result of shifting the bit pattern. The
                data type is the same as that of *pattern* .


*pattern* 

Required. Integral numeric expression. The bit pattern to be shifted. The data
                type must be ***Byte** , ***Integer** .


*bitCount* 

Required. Numeric expression. The number of bits to shift the bit pattern. The
                data type must be ***Integer** .


### Remarks
The shift is an arithmetic right shift, the bits shifted beyond the range of the result data type are discarded, and the leftmost bit (sign) is propagated into the bit *positions* vacated by the shift. This means that if *pattern* has a negative value, the vacated positions are set to one; otherwise they are set to zero. 

Note that data type ***Byte** is considered unsigned, so there is no sign bit to propagate. If *pattern* is of type ***Byte** , the vacated positions are always set to zero. 

To prevent shifting by more bits than the result can hold, ECR ensures that *bitCount* is less than the number of bits in the patter. If *bitCount* is zero, the value of *result* is identical to the value of *pattern* . If *bitCount* is negative, it is taken as an unsigned value and masked with the appropriate size mask. 

Arithmetic shifts never generate overflow exceptions. 

### Example

```
BegSr shiftTest
      DclFld Byte *Byte
      DclFld Int2 *Integer Len(2)
      DclFld Int4 *Integer Len(4)
      DclFld Int8 *Integer Len(8)
      DclFld string *String

      Byte = 7
      Int2 = 1
      Int4 =  7
      Int8 = 458752    // H"000070000"
      Byte = Byte << 3
      System.Console.WriteLine (Byte *as System.Int32)
      Byte = Byte << 9
      System.Console.WriteLine (Byte *as System.Int32)
      Byte = Byte << 1
      System.Console.WriteLine(Byte *as System.Int32)
      Byte = Byte >> 1
      System.Console.WriteLine (Byte *as System.Int32)
      Int2 = Int2 << Int4
      System.Console.WriteLine (Int2 *as System.Int32)
      Int4 = Int4 << Int2
      System.Console.WriteLine (Int4)
      Int8 = Int8 << 2
      System.Console.WriteLine (Int8)
      Int8 = Int4 << 94
      System.Console.WriteLine (Int8)
      Int2 = 17000
      Int2 = Int2 << 1
      System.Console.WriteLine (Int2 *as System.Int32)
      Int2 = Int2 >> 1
      System.Console.WriteLine (Int2 *as System.Int32)
EndSr     
```

### See Also
[<< Operator](aerLrfLeftShiftOperator.html)

[Operators](aerLrfOperatorsMain.html)

[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
