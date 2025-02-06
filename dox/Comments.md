---
title: Comments

Id: Comments
TocParent: aerLrfLangElementsMain
TocOrder: 0


---

As you're writing code or reading the code examples, you will encounter the comment symbols `//` or starting with a `\*` and ending with a `*/`. These symbols tell the Encore RPG compiler to ignore the text following it, or *comment*. Comments are brief explanatory notes added to the code for the benefit of those reading it.

Encore RPG recognizes two types of comments:

- Line comments start with `//` and continue to the end of the line.
- Multiline comments start with a `/*` and end with `*/`.

Comments can appear anywhere in the source file:

- As stand alone in a line or block of lines

```c
// This subroutine computes the income taxes
// and finds the net salary

/* This class represents a sales record and has the
functionality associated with the sale, like computing
totals and sales tax */
```

- In the same line with code

```c
DclFld Name Type(*char) Len(30) // Name of the starship

BegSr Liftoff /* Shoot the rocket!*/ Access(*Public)
```

Sometimes it is very convenient to comment blocks of lines, e.g. when debugging. For this, you can use Visual Studio's **Comment selection** and **Uncomment selection** menu options.

### See Also

[Continuation Lines](Continuation_Lines.html)

[Language Elements](ecrLrfLangElementsMain.html)
