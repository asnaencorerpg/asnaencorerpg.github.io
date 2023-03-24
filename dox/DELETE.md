---
title: DELETE

Id: DELETE
TocParent: aerLrfOpCodesMain
TocOrder: 640


---

**Database file** : Physically deletes a record from a file. The file must be an update file. 

**SubfileControl** : Removes the record from the subfile (equivalent to the **RemoveItem** method). 

```

 **DELETE
From**  (file Name | Format Name)
Key (<u>*CURRENT</u> | Operand)
NotFnd (Indicator Variable)
Err (Indicator Variable | *EXTENDED)
```

### Parts

**From** 

Required. The name of a record format, file or subfile.


**Key** 

Optional. The search argument to use when deleting a file. *CURRENT is the default. Refer to [%KDS](KDS_Function.html) to use this built-in function to establish search arguments (Key) for Data Structures.


**NotFnd** 

Optional. Used to determine if the record was found while executing this command.


Note that you can also use the [%FOUND](FOUND_Function.html) function. However, be aware that %FOUND and the NotFnd indicator have **opposite** meanings: one will be **False** when the other one is **True** and vice versa.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


### Remarks
**Database File** - Unless a search argument (Key) is specified, the last record read from the file is deleted. If there has been no record read, the error indicator will be set. 

**SubfileControl** - The record referenced by the subfile's RRN variable (specified in **RRNFldName** property) is deleted. The record does not have to be previously read. If the RRN value is invalid, the error indicator will be set. 

Once a record has been deleted, it cannot be retrieved by any I/O operation. Note that a record deleted from an AS/400 or Acceler8DB database still occupies space in the file. 

### Example

```
/* In this example, the file, MyFile, is retrieved in update mode by key MyKey. 
   The record is found but the user does not have authority to delete this record. 
   Error indicator 42 is turned on and the user issued the message. */

  ReadRand MfFile MyKey NotFnd(*In42) 
   If *In41 = *Off
    Delete MyFile Err (*In42) If *In42 MSGBOX "You do not have authority to perform this function"
   Endif
  Endif

/* In this example, the file, MyFile, is retrieved in update mode by key MyKey 
   and deleted all in the same step. Error indicator 42 is turned on if there was 
   an error and indicator 41 is turned on if the record was not found.*/

Delete MyFile MyKey NotFnd(*In41) Err (*In42)
   If *In41
     Exsr RecordNotFound
   Endif 

   If *In42
     Exsr ErrorOnAuthority
   Endif      
```

### See Also
[%KDS](KDS_Function.html)
[%FOUND](FOUND_Function.html)
[%KDS](KDS_Function.html) 
