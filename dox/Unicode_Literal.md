---
title: Unicode Literal

Id: Unicode_Literal
TocParent: aerLrfLiteralsMain
TocOrder: 20


---

A **Unicode Literal** allows strings to be specified as a chain of unicode characters (often those that cannot be produced by simple keystrokes) written in hexadecimal notation (same as RPG ILE U literals). 

### Remarks
Each unicode character is represented with 4 hex digits, as in the format U"xxxx...", where xxxx is the hex representation of a unicode character. 

The type of a unicode constant is * **String** . 

The number of hex digits must be a multiple of four (a single unicode character requires 4). 

### Example
U"00310032000d" 

u"30c3"

### See Also
[Hexadecimal Literal](Hexadecimal_Literal.html)
[String Data Type](String_Data_Type.html)
[Literals](aerLrfLiteralsMain.html)
[Unicode Overview](aerConUnicode.html) 
