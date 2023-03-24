---
title: DCLDISKFILE UseKeyBuffer

Id: DCLDISKFILE
TocParent: aerLrfOpCodesMain
TocOrder: 410



---



                [**UseKeyBuffer**](DCLDISKFILEUseKeyBuffer.html)

Optional. <code>UseKeyBuffer</code> specifies whether any keyed operation on the file (e.g. <code>CHAIN</code>) will consider its key parameter to be a key buffer, i.e. it will be considered as containing pieces of the key up to its length. <code>*NO</code> is the default. 

- <code><u>*NO</u></code> (default) - indicates that the key parameter will not be considered a key buffer.
- <code>*YES</code> - indicates that any keyed operation on the file (e.g. <code>CHAIN</code>) will consider its key parameter to be a key buffer.


### Example
For example, assume a file <code> **F** </code> has two key fields, <code> **K1** </code> which is <code>*char len(5)</code> and <code> **K2** </code> which is <code>*zoned len(2,0)</code>.<br /> Let <code> **B7** </code> be a field in the program with type <code>*char len(7)</code> and value <code>"abcde32"</code>.<br /> Let <code> **B6** </code> be a <code>*char len(6)</code> with value <code>"abcde3"</code>.<br /> Let <code> **B5** </code> be a <code>*char len(5)</code> with value <code>"abcde"</code>.<br /> 

Assume <code> **F** </code> has the following records
<table>
            <tr><td>K1</td><td>K2</td><td>...</td></tr>
            <tr><td>"aabcd"</td><td>36</td><td>...</td></tr>
            <tr><td>"abcde"</td><td>20</td><td>...</td></tr>
            <tr><td>"abcde"</td><td>30</td><td>...</td></tr>
            <tr><td>"abcde"</td><td>32</td><td>...</td></tr>
</table>

<code>chain F Key(B7)</code> will read with full key the **fourth** record, as <code>"abcde"</code> will be moved into the first key field (K1) and 32 will be the moved into the second key field (K2) before the CHAIN. <code>chain F Key(B6)</code> will read with full key the **third** record, as <code>"abcde"</code> will be moved into the first key field (K1) and 3 with padding will be moved into the second key field (i.e. K2 = 30) <code>chain F Key(B5)</code> will read with partial key the **second** record, as <code>"abcde"</code> will be moved into the first key field (K1). 

Internally the key buffer is put into a CHAR field, and then the CHAR field is chopped into pieces that are either MOVEd or byte-wise converted (as is the case for packed fields) into the key parts. If any MOVE fails you’ll get a runtime error.

If all the MOVEs succeed, and assuming whatever was moved ends up not being an existing key, the I/O operation will return the proper value according to its behavior (‘not found’ for CHAIN for instance, other operations like SETLL may succeed and set flags). 

### Remarks
The new behavior will occur only if: 

- A **single field**  is used in the Key parameter
- The single field is **NOT a keylist**

Otherwise the "normal" behavior will occur.
<br />

**Example Program** <br /> 

```

Using System
Using System.Collections
Using System.Text

BegClass Program

       dcldb name(elm) DBName("elm")

       dcldiskfile myfile DB(elm) File("*LIBL/CSMASTERL2") type(*Input) org(*Indexed) impopen(*no) usekeybuffer(*yes)

       dclds myDS
              dcldsfld oneChar type(*char) len(5)
              dcldsfld one type(*packed) len(9,0) overlay(oneChar)
              dcldsfld two type(*zoned) len(4,0)

       dclfld fld len(9)

       BegSr Main Shared(*Yes) Access(*Public) Attributes(System.STAThread())
              DclSrParm args Type(*String) Rank(1)
              (*new Program()).fil()
       EndSr

       begsr fil
              connect elm
              open myfile
              one = 200
              two = 1994
              fld = myDS.Dump()
              chain myfile Key(fld)             // new behavior
              console.WriteLine( "{0} {1}", CSCUSTNO, CSYEAR )
              chain myfile Key(myDS)            // new behavior
              console.WriteLine( "{0} {1}", CSCUSTNO, CSYEAR )
              chain myfile Key(one, two)        // old behavior
              console.WriteLine( "{0} {1}", CSCUSTNO, CSYEAR )
              Console.ReadLine()
              close myfile
              disconnect elm
       endsr
EndClass


```

### See Also
[<code>CLOSE</code>](CLOSE.html)
[<code>COMMIT</code>](COMIT.html)
[<code>DCLDS</code>](DCLDS.html)
[<code>DCLDSFLD</code>](DCLDSFLD.html)
[<code>DCLFLD</code>](DCLFLD.html)
[<code>DCLPRINTFILE</code>](DCLPRINTFILE.html)
[<code>LOOKUP</code>](LOOKUP.html)
[<code>OPEN</code>](OPEN.html)
[<code>ROLLBACK</code>](ROLBACK.html)
[DBFile Class Members](aerLrfDBFileMembers.html)
[DBFile Class](aerLrfDBFileClass.html) 
