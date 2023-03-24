---
title: Namespace Concepts

Id: aerConNamespacesConcepts
TocParent: aerConNamespaces
TocOrder: 10


---

Namespaces organize the objects defined in an assembly. Assemblies can contain multiple namespaces, which can in turn contain other namespaces. Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries. 

For example, the .Net Framework defines the ListBox class in the System.Windows.Forms namespace. The following code fragment shows how to declare a variable using the fully qualified name for this class: 
<pre class="prettyprint">DCLFLD accountList TYPE(System.Windows.Forms.ListBox)</pre>

By default, every executable file you create with Encore RPG contains a namespace with the same name as your project. For example, if you define an object within a project named <code class="ce">MyProject</code>, the executable file, MyProject.exe, contains a namespace called <code class="ce">MyProject</code>. This default namespace can be changed in the project properties window, or set in code using the <code>DCLNAMESPACE</code> command. 

Multiple assemblies can use the same namespace. Encore RPG treats them as a single set of names. For example, you can define classes for a namespace called <code class="ce">MyNameSpace</code> in an assembly named My <code class="ce">Assemb1y1</code>, and define additional classes for the same namespace from an assembly named <code class="ce">Assembly2</code>. 

### Fully Qualified Names
Fully qualified names are object references that are prefixed with the name of the namespace where the object is defined. You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code. The following code fragment shows how to use the fully qualified name for an object from another project's namespace: 
<pre class="prettyprint"><code class="lang-aer">DCLFLD MyField *New (MyProject.Form1.ListBox() )</code></pre>

If you attempt to use <code class="ce">a class</code> without fully qualifying it, Encore RPG produces an error stating that the name <code class="ce"> Class1 </code> is ambiguous. 

### Namespace Level Statements
Within a namespace, you can define items such as programs, interfaces, classes, delegates, enumerations, structures, and other namespaces. You cannot define items such as properties, procedures, variables and events at the namespace level. These items must be declared within containers such as modules, structures, or classes. 

### Related Section

[Namespace Declarations](aerConNamespaceDeclarations.html)

Provides more detail on declaring namespaces.


### See Also
[DCLNAMESPACE](DCLNAMESPACE.html) 
