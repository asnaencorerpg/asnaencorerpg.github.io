---
title: String Literal

Id: String_Literal
TocParent: aerLrfLiteralsMain
TocOrder: 6


---

A **String literal** can take three formats, where ccc is a string with no newlines, and mmm is a string including newline characters:

**Without Newlines:** 

- ```"<ccc>"``` : single line string. To have a ‘ inside it, write it twice, e.g. ‘bob’’s office’
- ```"<ccc>"``` : single line string. To have a " inside it, write it twice e.g. "bob said ""hello world"""

**With Newlines:** 

- ```@"<mmm>"``` : multiline string. To have a " inside it, write it twice e.g. "bob said ""hello world"""

### Remarks
Single line strings can be continued on the next line if and only if the last non-blank character of the line is a + sign. In this case, the string contains the characters up to the +, excluding the +, and the characters starting in the first column onwards of the continuation line. 

### Examples
<dl class="Code" />
            
```
    "hello world"
    ‘this is a string + 
	continued on the next line’ : this is equal to ‘this is a string continued of the next line’
    @"I want to have newlines
	in my string, so I use a multiline string!!!"
```

### See Also
[*Char Data Type](Character_Data_Type.html)

[*OneChar Data Type](Onechar_Data_Type.html)

[Literals](aerLrfLiteralsMain.html) 
