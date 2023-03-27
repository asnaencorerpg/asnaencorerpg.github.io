---
title: Variable Declaration

Id: aerConVariableDeclaration
TocParent: aerConVariables
TocOrder: 01


---

You declare a variable to specify its name and characteristics. The declaration statement for variable declaration is the ```DCLFLD``` statement. Its location and contents determine the variable's characteristics. 

### Declaration Levels
A *local variable* is one that is declared within a procedure. A *module variable* is declared at module level, inside the module but not within any procedure internal to that module. 

In a class or structure, the category of a nonlocal variable depends on whether or not it is shared. If it is declared with the ```Shared``` keyword, it is a *shared variable* , and it exists in a single copy shared among all instances of the class or structure. Otherwise it is an *instance variable* , and a separate copy of it is created for each instance of the class or structure. a given copy of an instance variable is available only to the instance for which it was created. 

### Declaring DataType
The ```*As``` datatype in the declaration statement allows you to define the datatype or object type of the variable you are declaring. You can specify any of the following types for a variable: 

- An elementary datatype, such as ```*Boolean```, or ```*Integer```.
- A composite datatype, such as an array or structure.
- An object type, or class, from Encore RPG or another application, such as ```Label```
                        or ```TextBox```.

In the following statement, the variable declaration <code class="ce">x``` is declared as type ```*Integer``` and changed to **```*Boolean```** : 

```
 DCLFLD x Type(*Integer) *As (*Boolean).
```

For more information on datatypes, see [DataTypes](aerConDataTypes.html).

### Declaring Lifetime
The *lifetime* of a variable is the period of time during which it is available for use. A local variable declared with a ```DCLFLD``` statement exists only as long as its procedure is executing. When the procedure terminates, all its local variable declarations disappear and their values are lost. However, if you declare a local variable using the **Static** (*YES) keyword, it continues to exist and preserve its value even when the procedure ends. 

For more information on lifetime, see [Lifetime](aerConDeclaredElementsLifetime.html).

### Declaring Accessibility
The *accessibility, or scope* of a variable is the set of all code that can refer to it without qualifying its name. a variable's scope is determined by where the variable is declared. Code located in a given region can use the variable declaration defined in that region without having to qualify their names. When declaring scope, the following rules apply: 

- The scope of a module variable is the entire namespace in which the module is defined.
- The scope of a shared or instance variable is the structure or class in which it is declared.
- The scope of a local variable is the procedure in which it is declared.
- However, if you declare a local variable within a block, its scope is that
                        block only. A block is a set of statements terminated by an  ```If...Then...Else...End 		If``` construction.

### See Also
[DataType Summary](Data_type_summary.html)

[DCLFLD](DCLFLD.html)

[Lifetime](aerConDeclaredElementsLifetime.html)


