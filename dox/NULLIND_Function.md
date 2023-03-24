---
title: "%NULLIND Function"

Id: NULLIND_Function
TocParent: Functions_overview
TocOrder: 32


---

**%NULLIND** [built-in function](Functions_overview.html) built-in function can be used to query or set the null indicator for null-capable fields. 

```

 **%NULLIND (Fieldname)** 
        
```

### Parts

**Fieldname** 

Required. The name of the field.


### Remarks
The nullability of a field determines if the record in the file can contain a null value for that field. A null value, or NULL, is not the same as zero (0), blank, or a zero-length character string such as "". NULL means that no entry has been made. The presence of NULL usually implies that the value is either unknown or undefined. For example, a null value in the price field of the titles file of the pubs database does not mean that the book has no price; NULL means that the price is unknown or has not been set. 

The fieldname can be a null-capable array element, data structure, stand-alone field, subfield, or multiple occurrence data structure. 

This built-in function can be used on the left hand side of an assignment expression to set the Null value capability of a field. When used on the left-hand side of an expression, this function can be used to set the null indicator for null-capable fields to *ON or *OFF, or *TRUE or *FALSE. The content of a null-capable field remains unchanged. 

### Example

```
// Test the null indicator for a null-capable field.

IF %NULLIND (myFieldName)
..
..
Endif
// Set the null indicator for a null-capable field. 

%NULLIND(myFieldName) = *True 	// myFieldName is null
%NULLIND(myFieldName) = *False 	// myFieldName is not null
```

### See Also
[Built-in Function Overview](Functions_overview.html) 
