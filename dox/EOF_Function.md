---
title: "%EOF Function"

Id: EOF_Function
TocParent: Functions_overview
TocOrder: 17


---

<span style="FONT-WEIGHT: bold">%EOF</span> [built-in function](Functions_overview.html) returns **True** if the most recent read operation or write to a subfile ended in an end of file or beginning of file condition; otherwise, it returns **False** . 

```
%EOF  {(File_name)}
```

### Parameters

**File_name** 

Optional.  The name of the file. **%EOF**  is only
                available if the file name is specified for primary and secondary files.


### Remarks
The operations that set **%EOF** are:

- [READ](READ.html) (Read a Record)
- [READC](READC.html) (Read Next Changed Record)
- [READE](READE.html) (Read Equal Key)
- [READP](READP.html) (Read Prior Record)
- [READPE](READPE.html) (Read Prior Equal)
- [WRITE](WRITE.html) (Create New Records - subfile only)

When a full-procedural file is specified, this function returns True if the previous operation in the list above, for the specified file, resulted in an end of file or beginning of file condition. 

This function is allowed for input and update files, and for display files allowing **WRITE** to subfile records. 

### See Also
[Built-in Function Overview](Functions_overview.html)
        <br />
        [READ](READ.html)
        <br />
        [READC](READC.html)
        <br />
        [READE](READE.html)
        <br />
        [READP](READP.html)
        <br />
        [READPE](READPE.html)
        <br />
        [WRITE](WRITE.html)
        <br />
        [IsEof Property](IsEofPropertyDbFileClass.html)

