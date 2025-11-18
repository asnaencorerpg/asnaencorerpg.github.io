---
title: Array Usage

Id: aerConArraysUsage
TocParent: aerConArrays
TocOrder: 1


---

Because automatic array indexing is a compile-time operation, it applies only when the resulting field is an array declared using the `DIM` keyword, and does **NOT** apply when resulting fields are arrays that use the `RANK` keyword. This is particularly important on assignments of the form `array1 = <some expression>`. 

- If `array1` is a `DIM`-declared array, then the assignment expression **WILL** be indexed and follow the RPG rules (shorter array, etc). Any `RANK`-declared array in the expression will participate in indexing, and the user must be sure that the rank array contains sufficient elements, or a run-time error will occur.
- If `array1` is a **RANK** -declared array, then no automatic indexing will take place in expressions that have arrays as operands. i.e. `myArr1 = myArr2 * myArr3`. 

If you want to use arrays in expressions, then those arrays must be RPG arrays (`DIM` arrays).

For the commands that operate on arrays, the array in the `RESULT` field must be a `DIM` array. 

### Examples

// Example 1
 `dimArray1 = dimArray2 + rankArray1` becomes... 

```
 DO 0 <shorter length of dimArray1 and dimArray2 minus 1> Index
  dimArray1[ Index ] = dimArray2[ Index ] + rankArray1[ Index ]
 ENDDO
```
// remains the same, no code changes **rankArray1 = dimArray1**  

// this generates a compiler error rankArray1 = dimArray1 + dimArray2 


// Example 2 
`ZADD 3 dimArray1`  becomes...

```
 DO 0 <length of dimArray1 minus 1> Index 
   ZADD 3 dimArray1[ Index ] 
 ENDDO
```

// This generates a compiler  error
 **ZADD 4 rankArray1** 


### Related Sections
[Array Overview](ArraysOverview.html)

[Language Concepts Main Topics](/concepts/LanguageConceptsMain.html) 

### See Also
[BEGFUNC](/dox/BEGFUNC.html)

[BEGPROP](/dox/BEGPROP.html)

[DCLARRAY](/dox/DCLARRAY.html)

[DCLDSFLD](/dox/DCLDSFLD.html)

[DCLOVERLAYGROUP](/dox/DCLOVERLAYGROUP.html)

[DCLSRPARM](/dox/DCLSRPARM.html) 
