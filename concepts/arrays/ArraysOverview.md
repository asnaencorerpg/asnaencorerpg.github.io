---
title: Arrays Overview

Id: aerConArraysOverview
TocParent: aerConArrays
TocOrder: 0


---

Arrays allow you to refer to a series of variables by the same name and to use a number, called an *index* , to tell them apart. This helps you create shorter and simpler code in many situations, because you can set up loops that deal efficiently with any number of elements by using the index number. 

### Array Dimensions
An array can have one dimension or more than one. The *dimensionality* or ***rank*** corresponds to the number of subscripts used to identify an individual element. You can specify up to 32 dimensions, although more than three is extremely rare. Encore RPG allows you to specify the array dimensions by using the ```Rank``` keyword when using [BEGFUNC](/dox/BEGFUNC.html) , [BEGPROP](/dox/BEGPROP.html), [DCLARRAY](/dox/DCLARRAY.html) and [DCLSRPARM](/dox/DCLSRPARM.html). 

### Array Size
Every dimension of an array has a nonzero length. The elements of the array are contiguous along each dimension from subscript 0 through the highest subscript of that dimension. All arrays are 0-based. Because Encore RPG allocates space for an array element corresponding to each index number, you should avoid declaring any dimension of an array larger than necessary. 

A ***zero-length** array* is an array with no elements. It is sometimes necessary to specify such an array, for example when using Windows Forms. To do this, you declare one of the array's dimensions to be –1. The array is then empty, but it still exists. Therefore, a variable pointing to the array is not equal to ```*Nothing```. 

### Array Class
All arrays inherit from the **Array** class in the **System** namespace, and you can access the methods and properties of **System.Array** on any array. 

### Array Type (```*Object```)
Arrays are objects in Encore RPG, so every array type is an individual reference type. This has the following implications: 

- No two array variables are considered to be of the same data
                type unless they have the same **rank**  and element **data type** .
- When you assign one array variable to another, only the pointer is copied.
- An array variable holds a pointer to the data constituting the elements and the
                rank and length information.

### Array Element Type
An array declaration specifies a data type, and all its elements **must be of that type** . When the data type is **Object** , the individual elements can contain different kinds of data(objects, strings, numbers, and so on). 

You can also declare an array that contains other arrays as its elements. In this case, the constituent arrays must all have the same element data type, which you specify in the declaration. An array of arrays is called a *jagged array* because the constituent arrays do not have to have the same sizes. 

### Array Operation Codes/Operators
The following are the operation codes/operators that operate on every element of the array when a single dimension fixed sized array name is used as the result field of a command or assignment expression: 

- ```+``` (Uniary and binary plus), 
- ```-``` (uniary and binary minus), 
- ```*``` (multiply), 
- ```/``` (divide), 
- ```*Not```,  - ```*And```,  - ```*Or``` operators:

Example:  ```array1 = array2 + 5 - field3```

>  ```5``` is added and ```field3``` is subtracted to every element of ```array2``` and the result is assigned to every corresponding element of ```array2```.  If ```array1``` and ```array2``` have different element counts, the operation is done using the minimum count.

- [ADD](/dox/ADD.html), [DIV](/dox/DIV.html), [MULT](/dox/MULT.html), [SQRT](/dox/SQRT.html), [SUB](/dox/SUB.html), [ZADD](/dox/ZADD.html) and [ZSUB](/dox/Z_SUB.html) commands.
- [EXTRACT](/dox/EXTRACT.html), [ADDDUR](/dox/ADDDUR.html), and [SUBDUR](/dox/SUBDUR.html) commands.
- [MOVE](/dox/MOVE.html) commands.

Every array that is used by stating its name with these operators will participate in the "array indexing" of the expression. Array properties and functions that return arrays are not automatically indexed.

### Related Sections
[Array Usage](ArraysUsage.html)

[Language Concepts Main Topics](/concepts/LanguageConceptsMain.html) 

### See Also
[BEGFUNC](/dox/BEGFUNC.html)

[BEGPROP](/dox/BEGPROP.html)

[DCLARRAY](/dox/DCLARRAY.html)

[DCLDSFLD](/dox/DCLDSFLD.html)

[DCLOVERLAYGROUP](/dox/DCLOVERLAYGROUP.html)

[DCLSRPARM](/dox/DCLSRPARM.html) 
