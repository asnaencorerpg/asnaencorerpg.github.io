---
title: "*Byte Data Type"

Id: Byte_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 2


---

***Byte** variables are stored as unsigned 8-bit (1-byte) numbers ranging in value from 0 through 255. 

The ***Byte** data type is used for containing binary data.  The equivalent .NET data type is System.Byte. 

## *BYTE is not *CHAR
The `*CHAR` is a text data type. It is used to store characters. `*BYTE` is a binary data type. It is used to store numbers. `*CHAR` and `*BYTE` are not interchangeable. They are not implicitly convertible to each other.

On IBM's RPG, `*CHAR` is used to hold Text with its byte content interpreted as EBCDIC. Sometimes, a CHAR(1) is used to hold a single byte of binary data, but in order to use it in numeric operations it is moved using a Data Structure to the low byte of a 2-byte integer field. This practice assumes that the numeric values use a Big-Endian encoding, which is true on the /400, but that is not true on all platforms, particularly those using x86 processors.

Encore RPG provides the additional type `*BYTE` to facilitate certain migration operations. `*BYTE` is a 1-byte nuemric field which has no implicit conversion to `*CHAR`.  `*BYTE` cannot be used in a MOVE operation.

## Non *BYTE Numeric Fields and *CHAR on IBM's RPG and Encore RPG
On Encore RPG and on IBM's RPG, when *CHARs interact with Numeric types using the MOVE opeartion, numeric data is converted to its decimal representation as a Zoned value but without a decimal point, and the resulting text is moved to or from the `*CHAR` field.

## Some examples

```cs
    DclFld CharBits Type(*Char) Len(1)
    DclFld ByteBits Type(*Byte)
    DclFld Int2 Type(*Integer2)

    DclArray ByteArray Type(*Byte) Rank(1) New(1)

    DclDs ByteFiddling
        DclDsFld CharIn1 Type(*Char) Len(1)
        DclDsFld ByteIn1 Type(*Byte) StartAt(1)
        DclDsFld ByteIn2 Type(*Byte) StartAt(2)

    BegSr DontMixCharWithBytes        
        ByteBits = H"4E"            // Hex 4E, Decimal 78, ASCII 'N', EBCDIC '+'
        
        // *BYTE can never be the Source or Target of a MOVE operation
        // Move ByteBits CharBits         <<< Produces a compile error
        // Move CharBits ByteBits         <<< Produces a compile error

        // *BYTE cannot be implicitly converted to or form *CHAR
        // CharBits = ByteBits            <<< Produces a compile error
        // ByteBits = CharBits            <<< Also produces an error

        // The Built-in %CHAR() function can be used to convert a *BYTE to a *CHAR.
        // %CHAR() converts a number to its corresponding Text. In this case "78"
        CharBits = %CHAR(ByteBits)          // CharBits = "7"
        Move %CHAR(ByteBits) CharBits       // CharBits = "8"

        // To 'convert' a *BYTE to its encoded character value, use a DataStructure to 
        // reinterpret the underlying bits. 
        ByteIn2 = *Zeros
        ByteIn1 = ByteBits
        // CharIn1 is 'N'; On the /400 it would have been a '+'.
        // This is because the /400 uses EBCDIC encoding, not Unicode.

        // You could also use one of the System.Text.Encoding classes to achive the save result
        ByteArray[0] = ByteBits
        CharIn1 = (*new System.Text.ASCIIEncoding()).GetString(ByteArray)

        // Byte fields can be asigned to/from other numeric types
        Int2 = ByteBits                     // Int2's value is now 78

    EndSr
```


## See Also
[Data Types](ecrLrfDataTypesMain.html)

[Integer Data Type](Integer_Data_Type.html) 
