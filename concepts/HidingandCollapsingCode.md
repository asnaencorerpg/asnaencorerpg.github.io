---
title: Collapsing and Hiding Code

Id: aerConHidingandCollapsingCode
TocParent: aerConLanguageConceptsMain
TocOrder: 60


---

The Encore RPG code editor has the ability to collapse and hide code regions. These regions follow the general trend of making it easier to read your code, thus serving the function of reducing clutter. This will allow you to see, or to hide the sections of code that take place "behind the scenes". For example, the code to create and draw forms is tucked away in collapsed regions. 

Developers who want or need more complete access to the underlying code have it; all others can simply let VS and Encore RPG draw the windows for them. 

The `/Region` directive enables you to collapse and hide sections of code in Encore RPG for .NET files. `/Region` lets you specify a block of code that you can expand or collapse when using the `/Region` and `/EndRegion` commands. The ability to hide code selectively makes your files more manageable and easier to read. 

>`/Region` directives are not supported within functions.

### Syntax
The syntax for `\Region` is as follows:

```
/Region "identifier string"
  code region
/EndRegion
```

The `identifier string` requires the quotes and acts as the title of the region when it is collapsed. The region is collapsed by default. 

### To collapse and hide a section of code

Place the section of code between the `/Region`  and `/EndRegion` statements. 

The following example shows a section of system-generated code that the editor has added the collapse/hide ability for you.

```
/region Windows Form Designer generated code 
 // Required method for Designer support - do not modify 
 // the contents of this method with the code editor.  

   BegSr InitializeComponent   
	// 
	// Form1
	// 

	*this.AutoScaleBaseSize = *new System.Drawing.Size(5, 13) 
	*this.ClientSize = *new System.Drawing.Size(292, 266) 
	*this.Name = "Form1" 
	*this.Text = "Form1" 						
   EndSr 
 /endregion
```

### Multiple /Region Blocks

The `/Region` and `/EndRegion` blocks can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed. 

`/Region` blocks also can be nested within other `/Region` blocks. 
