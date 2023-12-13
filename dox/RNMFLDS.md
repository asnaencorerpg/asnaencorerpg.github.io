---
title: RNMFLDS

Id: RNMFLDS
TocParent: aerLrfOpCodesMain
TocOrder: 1390


---

**RNMFLDS** allows fields from an externally described record format to be individually renamed to an internal field name. 

```
RNMFLDS 
 Fmt     (Format name)
 DSName  (Data Structure name)
 Flds    (External field name, Internal field name, ...)
```

### Parts

**Fmt** 

**Fmt** must contain the name of the record format containing the fields to be renamed. 

Either **Fmt** or **DSName** is Required.


**DSName** 

**DSName** must contain the name of the Data Structure containing the fields to be renamed.

Either **Fmt** or **DSName** is Required.


**Flds** 

Required. **Flds** must contain matched pairs of external field and internal field names. The maximum number of field names is 32,767. For readability, a colon may be used to separate pairs of field names.


### Example

```
RnmFlds Fmt ( RCMasterL2) Flds ( CMCustNo, myCust#,       +
                                 CMName, myName,          +
                                 CMAddr2, myAddress  )

RnmFlds Fmt ( myFormat ) Flds ( Fieldone, myFld1, FieldTwo, myFld2, Fieldthree, myFld3 ) 
RnmFlds Fmt ( myFormat ) Flds ( Field1, myFld1 : Field2, myFld2 : Field3, myFld3 )

RnmFlds DSName(MyDS)                                +
Flds                                                +
(                                                   +
      AEAFCD    ,  AE_NumeroPedido               ,  +
      AEABNB    ,  AE_CodigoCliente              ,  +
      AEAECD    ,  AE_CodigoProducto             ,  +
      AEADDA    ,  AE_FechaCreacionPedido        ,  +
      AEAKTX    ,  AE_UsuarioCreacionPedido      ,  +
      AEAEDA    ,  AE_FechaModificacionPedido    ,  +
      AEALTX    ,  AE_UsuarioModificacionPedi    ,  +
      AEADST    ,  AE_EstadoPedido                  + 
) 

```

### See Also
[DCLDISKFILE](DCLDISKFILE.html)

[DCLPRINTILE](DCLPRINTFILE.html)

[DCLDS](DCLDS.html) 
