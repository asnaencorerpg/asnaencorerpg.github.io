---
title: Array Usage

Id: aerConArraysUsage
TocParent: aerConArrays
TocOrder: 1


---

Because automatic array indexing is a compile-time operation, it applies only when the resulting field is an array declared using the <code> **DIM** </code> keyword, and does **NOT** apply when resulting fields are arrays that use the <code> **RANK** </code> keyword. This is particularly important on assignments of the form <code>array1 = &lt;some expression&gt;</code>. 

- If <code>array1</code> is a <code> **DIM** </code>-declared array, then the assignment expression **WILL** be indexed and follow the RPG rules (shorter array, etc). Any <code>RANK</code>-declared array in the expression will participate in indexing, and the user must be sure that the rank array contains sufficient elements, or a run-time error will occur.
- If <code>array1</code> is a **RANK** -declared array, then no automatic indexing will take place in expressions that have arrays as operands. E.g. <code>"myArr1 = myArr2 * myArr3"</code>. 

If you want to use arrays in expressions, then those arrays must be RPG arrays (<code> **DIM** </code> arrays).

For the commands that operate on arrays, the array in the <code> **RESULT** </code> field must be a <code> **DIM** </code> array. 

### Examples

```
// Example 1
 **dimArray1 = dimArray2 + rankArray1** 
    becomes... 
 DO 0 &lt;shorter length of dimArray1 and dimArray2 minus 1&gt; Index
  dimArray1[ Index ] = dimArray2[ Index ] + rankArray1[ Index ]
 ENDDO

// remains the same, no code changes **rankArray1 = dimArray1**  

// this generates a compiler error **rankArray1 = dimArray1 + dimArray2** 

// Example 4 **ZADD 3 dimArray1** 
   becomes...
 DO 0 &lt;length of dimArray1 minus 1&gt; Index 
 **ZADD 3 dimArray1[ Index ]** 
 ENDDO

// This generates a compiler  error
 **ZADD 4 rankArray1** 
```

### Related Sections
[Array Overview](aerConArraysOverview.html)
[Language Concepts Main Topics](aerConLanguageConceptsMain.html) 

### See Also
[BEGFUNC](BEGFUNC.html)
[BEGPROP](BEGPROP.html)
[DCLARRAY](DCLARRAY.html)
[DCLDSFLD](DCLDSFLD.html)
[DCLOVERLAYGROUP](DCLOVERLAYGROUP.html)
[DCLSRPARM](DCLSRPARM.html) 
