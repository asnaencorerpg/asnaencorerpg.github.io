---
title: DCLDISKFILE UseKeyBuffer

Id: DCLDISKFILE
TocParent: aerLrfOpCodesMain
TocOrder: 410



---



                [**UseKeyBuffer**](DCLDISKFILEUseKeyBuffer.html)

Optional. ```UseKeyBuffer``` specifies whether any keyed operation on the file (e.g. ```CHAIN```) will consider its key parameter to be a key buffer, i.e. it will be considered as containing pieces of the key up to its length. ```*NO``` is the default. 

- ```<u>*NO</u>``` (default) - indicates that the key parameter will not be considered a key buffer.
- ```*YES``` - indicates that any keyed operation on the file (e.g. ```CHAIN```) will consider its key parameter to be a key buffer.


### Example
For example, assume a file ```F``` has two key fields, ```K1``` which is ```*char len(5)``` and ```K2``` which is ```*zoned len(2,0)```.<br /> Let ```B7``` be a field in the program with type ```*char len(7)``` and value ```"abcde32"```.<br /> Let ```B6``` be a ```*char len(6)``` with value ```"abcde3"```.<br /> Let ```B5``` be a ```*char len(5)``` with value ```"abcde"```.<br /> 

Assume ```F``` has the following records
<table>
            <tr><td>K1</td><td>K2</td><td>...</td></tr>
            <tr><td>"aabcd"</td><td>36</td><td>...</td></tr>
            <tr><td>"abcde"</td><td>20</td><td>...</td></tr>
            <tr><td>"abcde"</td><td>30</td><td>...</td></tr>
            <tr><td>"abcde"</td><td>32</td><td>...</td></tr>
</table>

```chain F Key(B7)``` will read with full key the **fourth** record, as ```"abcde"``` will be moved into the first key field (K1) and 32 will be the moved into the second key field (K2) before the CHAIN. ```chain F Key(B6)``` will read with full key the **third** record, as ```"abcde"``` will be moved into the first key field (K1) and 3 with padding will be moved into the second key field (i.e. K2 = 30) ```chain F Key(B5)``` will read with partial key the **second** record, as ```"abcde"``` will be moved into the first key field (K1). 

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
[```CLOSE```](CLOSE.html)

[```COMMIT```](COMIT.html)

[```DCLDS```](DCLDS.html)

[```DCLDSFLD```](DCLDSFLD.html)

[```DCLFLD```](DCLFLD.html)

[```DCLPRINTFILE```](DCLPRINTFILE.html)

[```LOOKUP```](LOOKUP.html)

[```OPEN```](OPEN.html)

[```ROLLBACK```](ROLBACK.html)

[DBFile Class Members](ecrLrfDBFileMembers.html)

[DBFile Class](ecrLrfDBFileClass.html) 
