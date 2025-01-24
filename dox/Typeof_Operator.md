---
title: "*TypeOf Operator"

Id: Typeof_Operator
TocParent: aerLrfOperatorsMain
TocOrder: 16


---

Returns a **Type** object for the specified type. The **Type** object can be used to retrieve information about the type such as its properties, methods, and events. 
<pre class="prettyprint">  *Typeof(typename)<br /></pre>


### Parameters

*typename* 

The name of the type for which information is desired.


### Remarks
The * **Typeof** operator is used to obtain the **System.Type** object for a type. If you want to get the type object of an object variable, use **Type.GetType** method. 

**Example** 

```

   DclFld myType Type(Type)
     MyType = ***typeof** ( system.Web.HttpWorkerRequest ) 
```

### See Also
[Operators](ecrLrfOperatorsMain.html)

[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
