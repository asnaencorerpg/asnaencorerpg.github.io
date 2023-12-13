---
title: BITOFF

Id: BITOFF
TocParent: aerLrfOpCodesMain
TocOrder: 150


---

Allows bits to be set off in the **Target** parameter based upon a mask specified in the **Mask** parameter. 

```
 BITOFF
Mask (Character Expression)
 Target (Character Expression)
Type (*BYTE)
```

### Parts

**Mask** 

Required. **Mask** can contain: 

- Bit numbers 0-7. Enclose the bit numbers in apostrophes. For example, to set bits 0, 3, 6 on, enter "036" in Factor 2.
- A valid character expression.
- Hexadecimal literal (H"85") for example (Binary 10000101).
- Named constant up to 8 positions long containing the bit numbers to be set OFF.


**Target** 

Required. It can specify a one-position character field, or it can be an array element if each element in the array is a one-position character field. **In ECR, this parameter of the "BITOFF" command requires a byte type or a type that can be converted to a byte.**


**Type** 

Optional. If specified, must be *BYTE.


### Remarks
When using Bit operations to format a character, you should use both [BITON](BITON.html) and **BITOFF** . **BITON** specifies the bits to be set on (=1). **BITOFF** to specify the bits to be set off (=0). You may not get the character you want unless you explicitly set all the bits in a character On or Off. 

### Example
<pre class="prettyprint">// Initialize HEX00 to H"00".
 BITOFF MASK("01234567") Target(HEX00)
BITON H"00" HEX00

// Initialize HEX01 to H"01".
 BITOFF "01234567" HEX01
BITON H"01" HEX01

//Initialize HEX21 to H"21".
 BITOFF "01234567" HEX21 
BITON H"21" HEX21<br /></pre>

### See Also
[BITON](BITON.html)

[TESTBITS](TESTBITS.html) 
