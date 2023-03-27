---
title: Arithmetic Operators

Id: aerConArithmeticOperators
TocParent: aerConOperators
TocOrder: 0


---

Arithmetic operators are used to perform many of the familiar arithmetic operations that involve the calculation of numeric values represented by literals, variables, other expressions, function and property calls, and constants. 

### Arithmetic Operations
You can add two values in an expression together with the ```+``` operator, or subtract one from another with the ```-``` operator, as shown in the following examples: 

```
DCLFLD x Type (*Integer) Len (4)
x = 67 + 34
x = 32 - 12
```

Negation also uses the ```-``` operator, but with somewhat different syntax, as shown below: 

```
DCLFLD x Type (*Integer) Len (4)<br /> x = 65
DCLFLD y As Integer
y = -x
```

Multiplication and division use the ```*``` and ```/``` arithmetic operators, respectively, as in these examples: 

```
DCLFLD y Type (*Integer) Len (4)<br />

y = 45 * 55.23
y = 32 / 23
```

Exponentiation uses the ```^``` operator, as shown below:

```
DCLFLD z Type (*Integer) Len (4) <br />

z = 23 ^ 3    // z equals the cube of 23.
```

Integer division is carried out using the ```\``` operator. Integer division returns the number of times one integer can evenly divide into another. Only integral types (```*Byte```, ```*Float```, and ```*Integer```) can be used with this operator. All other types must be converted to an integral type first. The following is an example of integer division: 

```
DCLFLD k Type (*Integer)
k = 23 \ 5      // k = 4
```

### Division by Zero
Division by zero has different results depending on the data types involved. In integral divisions ( ```*Integer```, ```*Packed```, ```*Float```), a ```System.DivideByZeroException``` is thrown. In division operations on the ```*Decimal``` or ```*Packed``` data type, Encore RPG also throws a ```System.DivideByZeroException``` exception. In floating-point divisions with the ```Double``` variable type, however, the result is the class member representing ```NaN```, ```PositiveInfinity```, or ```NegativeInfinity```, depending on the dividend. The following table summarizes the various results of attempting to divide by zero. 

### Bitwise Operations
Bitwise operations evaluating two values in binary (base 2) form, compare the bits at corresponding positions, and then assign values based on the comparison, as in the demonstration below of bitwise ```And```: 

```
DCLFLD x Type (*Integer) Len (4)
x = 3 And 5   // x = 1
```

In this example, the value of ```x``` is ```<code class="ce">1```.``` Here's why: 

- First, the values are converted to binary form, as shown below:

```3``` in binary form = ```011``` 

```5``` in binary form = ```101```
- Next, the binary representations are compared, one binary position at
                a time. If both bits at a given position are ```1```, then a ```1``` is placed in that position in the result.
                If either bit is ```0```, then a ```0``` is placed in that position in the result. In our example this works
                out as follows:

```011``` ```3``` in binary form 

```101``` ```5``` in binary form 

```001``` The result, in binary form 

Converting back to decimal, ```001``` is the binary representation of ```1```, so ```x = 1```.

The bitwise ```*BitOr``` operation is similar, except that a ```1``` is assigned to the result bit if either of the compared bits is ```1```. ```*BitXor``` assigns a ```1``` to the result bit if only one of, but not both of, the compared bits is ```1```. ```*Not``` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result. This means that for positive numbers, ```*Not``` always returns a negative. Likewise, for negative numbers, ```*Not``` always returns a positive or zero. 

<b class="le">Note &#8211;</b> Bitwise operations can be performed on integral types only. Floating point values must be converted to integral types before bitwise operation can proceed. 

### Bit Shift Operations
A bit shift operation performs an arithmetic shift on a bit pattern. The pattern is contained in the operand on the left, while the operand on the right specifies the number of positions to shift the pattern. The data type of the pattern operand must be ```*Byte```, ```*Integer```, or ```*DECIMAL | *FLOAT```. The data type of the shift amount operand must be ```*Integer``` or must widen to ```*Integer```. 

Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end. The bit positions vacated by a shift are set as follows: 

- Zero for an arithmetic left shift
- Zero for an arithmetic right shift of a positive number
- Zero for an arithmetic right shift of any pattern
                with data type ```*Byte```
- One for an arithmetic right shift of a negative number (```*Integer```)

In the following example, an ```Integer``` value is shifted both left and right: 

```
DCLFLD Pattern Type (*Integer)Len (4)<br /> x= 12 // Low-order bits are 0000 1100
```
        
```
LResult Type (*Packed) *As Type (*Integer)
LResult = Pattern << 3   // Left shift of 3 bits produces value of 96
RResult = Pattern >> 2   // Right shift of 2 bits produces value of 3
```

Arithmetic shifts never generate overflow exceptions.

#### Type Safety
Operands should normally be of the same type. For example, if you are adding an ```*Integer``` variable, you should add it to another ```*Integer``` variable, and the variable that the value is assigned to should be of type ```*Integer``` as well. 
