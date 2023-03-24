---
title: Arithmetic Operators

Id: aerConArithmeticOperators
TocParent: aerConOperators
TocOrder: 0


---

Arithmetic operators are used to perform many of the familiar arithmetic operations that involve the calculation of numeric values represented by literals, variables, other expressions, function and property calls, and constants. 

### Arithmetic Operations
You can add two values in an expression together with the <code> **+** </code> operator, or subtract one from another with the <code> **-** </code> operator, as shown in the following examples: 

```
DCLFLD x Type (*Integer) Len (4)
x = 67 + 34
x = 32 - 12
```

Negation also uses the <code> **-** </code> operator, but with somewhat different syntax, as shown below: 

```
DCLFLD x Type (*Integer) Len (4)<br /> x = 65
DCLFLD y As Integer
y = -x
```

Multiplication and division use the <code> ***** </code> and <code> **/** </code> arithmetic operators, respectively, as in these examples: 

```
DCLFLD y Type (*Integer) Len (4)<br />

y = 45 * 55.23
y = 32 / 23
```

Exponentiation uses the <code> **^** </code> operator, as shown below:

```
DCLFLD z Type (*Integer) Len (4) <br />

z = 23 ^ 3    // z equals the cube of 23.
```

Integer division is carried out using the <code> **\** </code> operator. Integer division returns the number of times one integer can evenly divide into another. Only integral types (<code>* **Byte** </code>, <code>* **Float** </code>, and <code>* **Integer** </code>) can be used with this operator. All other types must be converted to an integral type first. The following is an example of integer division: 

```
DCLFLD k Type (*Integer)
k = 23 \ 5      // k = 4
```

### Division by Zero
Division by zero has different results depending on the data types involved. In integral divisions ( <code> ***Integer** </code>, <code> ***Packed** </code>, <code> * **Float** </code>), a <code> **System.DivideByZeroException** </code> is thrown. In division operations on the <code>* **Decimal** </code> or <code>* **Packed** </code> data type, Encore RPG also throws a <code> **System.DivideByZeroException** </code> exception. In floating-point divisions with the <code> **Double** </code> variable type, however, the result is the class member representing <code> **NaN** </code>, <code> **PositiveInfinity** </code>, or <code> **NegativeInfinity** </code>, depending on the dividend. The following table summarizes the various results of attempting to divide by zero. 

### Bitwise Operations
Bitwise operations evaluating two values in binary (base 2) form, compare the bits at corresponding positions, and then assign values based on the comparison, as in the demonstration below of bitwise <code> **And** </code>: 

```
DCLFLD x Type (*Integer) Len (4)
x = 3 And 5   // x = 1
```

In this example, the value of <code>x</code> is <code><code class="ce">1</code>.</code> Here's why: 

- First, the values are converted to binary form, as shown below:

<code>3</code> in binary form = <code>011</code> 

<code>5</code> in binary form = <code>101</code>
- Next, the binary representations are compared, one binary position at
                a time. If both bits at a given position are <code>1</code>, then a <code>1</code> is placed in that position in the result.
                If either bit is <code>0</code>, then a <code>0</code> is placed in that position in the result. In our example this works
                out as follows:

<code>011</code> <code>3</code> in binary form 

<code>101</code> <code>5</code> in binary form 

<code>001</code> The result, in binary form 

Converting back to decimal, <code>001</code> is the binary representation of <code>1</code>, so <code>x = 1</code>.

The bitwise <code> ***BitOr** </code> operation is similar, except that a <code>1</code> is assigned to the result bit if either of the compared bits is <code>1</code>. <code>* **BitXor** </code> assigns a <code>1</code> to the result bit if only one of, but not both of, the compared bits is <code>1</code>. <code>* **Not** </code> takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result. This means that for positive numbers, <code>* **Not** </code> always returns a negative. Likewise, for negative numbers, <code>* **Not** </code> always returns a positive or zero. 

<b class="le">Note &#8211;</b> Bitwise operations can be performed on integral types only. Floating point values must be converted to integral types before bitwise operation can proceed. 

### Bit Shift Operations
A bit shift operation performs an arithmetic shift on a bit pattern. The pattern is contained in the operand on the left, while the operand on the right specifies the number of positions to shift the pattern. The data type of the pattern operand must be <code>* **Byte** </code>, <code> ***Integer** </code>, or <code> ***DECIMAL | *FLOAT** </code>. The data type of the shift amount operand must be <code> ***Integer** </code> or must widen to <code> ***Integer** </code>. 

Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end. The bit positions vacated by a shift are set as follows: 

- Zero for an arithmetic left shift
- Zero for an arithmetic right shift of a positive number
- Zero for an arithmetic right shift of any pattern
                with data type <code> ***Byte** </code>
- One for an arithmetic right shift of a negative number (<code> ***Integer** </code>)

In the following example, an <code> **Integer** </code> value is shifted both left and right: 

```
DCLFLD Pattern Type (*Integer)Len (4)<br /> x= 12 // Low-order bits are 0000 1100
```
        
```
LResult Type (*Packed) *As Type (*Integer)
LResult = Pattern &lt;&lt; 3   // Left shift of 3 bits produces value of 96
RResult = Pattern &gt;&gt; 2   // Right shift of 2 bits produces value of 3
```

Arithmetic shifts never generate overflow exceptions.

#### Type Safety
Operands should normally be of the same type. For example, if you are adding an <code>* **Integer** </code> variable, you should add it to another <code>* **Integer** </code> variable, and the variable that the value is assigned to should be of type <code>* **Integer** </code> as well. 
