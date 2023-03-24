---
title: Comments

Id: Comments
TocParent: aerLrfLangElementsMain
TocOrder: 0


---

As you're writing code or reading the code examples, you will encounter the comment symbols (// or start with a **/*** and ended with a ***/'** ). These symbols tells the Encore RPG compiler to ignore the text following it, or the *comment* . Comments are brief explanatory notes added to code for the benefit of those reading it. 

The comment to occupy an entire line starts with //. You do not need to add anything at the end of the comment. 

The comment symbol to occupy multiple lines, or to include a comment on the same line as code starts with a **/*** and ends with a ***/.** This type of comment can go anywhere white space (tab, new-line, and carriage return) is permitted and is treated as such. 

It is good practice to begin all subroutines and functions with a brief comment describing the functional characteristics of the procedure (what it does), for your own benefit and the benefit of anyone else who examines the code. 

Comments can follow a statement on the same line, or occupy an entire line. Both are illustrated in the following code: 

**Comments that occupy an entire line (using //):** 
<pre class="prettyprint"><code class="language=avr">// This comment occupies an entire line. 
System.Windows.Forms.Application.DoEvents()
      - or -
System.Windows.Forms.Application.DoEvents()  //This comment is on the same line.</code></pre>
 **<br />Comments using /* to Start and */ to End Comment:** 
        <pre class="prettyprint"><code class="language=avr">/* This comment occupies an entire line.  You must end with a */.        
 System.Windows.Forms.Application.DoEvents() 
<br />- or - System.Windows.Forms.Application.DoEvents() /* This comment is on the same line. */</code></pre>
        If your comment expands more than one line, simply use the // symbol at the beginning or each <br />line, or add the */ symbol at the end of the last line of comments.

        
```
// This text is too long to fit on one line, so we'll add
// another line. Routines, and procedures should be named clearly enough that **inline** 
		commenting is needed only for complex implementation details.
		
```

- Comments cannot follow a **line-continuation**  sequence ( +) on
                the same line.

You can add or remove comment symbols for a block of code by selecting two or more lines of code and choosing the **Comment** <img id="IMG1" alt="" src="Images/comments.JPG" border="0" height="22" width="23" /> and **Uncomment** <img alt="" src="Images/uncomment.JPG" border="0" /> buttons on the **Edit** toolbar. 

### See Also
[Continuation Lines](Continuation_Lines.html)

[Language Elements](aerLrfLangElementsMain.html)
