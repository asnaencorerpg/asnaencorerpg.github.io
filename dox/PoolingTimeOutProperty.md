---
title: Database.PoolingTimeOut Property

Id: PoolingTimeOutProperty
TocParent: aerLrfDatabasePropertiesMain
TocOrder: 8


---

**PoolingTimeOut** gets or sets the amount of time (in minutes) in which a connection will remain idle in the pool until it is closed and removed from the pool. 

```
 *database* . **PoolingTimeOut =** *<integerVal>* 
```

### Property Value
***<integerVal>** is of type ** Integer and contains the amount of time (in minutes) in which a connection will remain idle in the pool until it is closed and removed from the pool. 

### Remarks
Connection pooling timeout applies only to DataGate connections to the System i. When a pooled DataGate job is idle for the timeout period, the job is terminated. 

When database connection pooling is enabled, the communication to the server and to the server resources are kept in a special ‘pool’. The next time the application requires database services, one of the available connections in the ‘pool is assigned to it. Thus, enabling Pooling Connections results in faster database connections. 

If connection pooling is not enabled, when a database and all its associated files are closed, the connection and server resources are ended (i.e., in the case of DataGate, the DataGate Job ends). When the same application needs the database services again, a new connection and corresponding job has to be established. This overhead wastes resources and slows down the application 

The **PoolingTimeout** property is also used in conjunction with the [CreateName](CreateName_Method.html) and [UpdateName](UpdateName_Method.html) methods. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows Server 2012, Windows Server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](ecrLrfRuntimeNamespace.html)

[Database Class](Date_Formats.html)

[Database Class Members](ecrLrfDatabasePropertiesMain.html)

[Database Class Methods](ecrLrfDatabaseMethods.html)

[Database Class Properties](ecrLrfDatabasePropertiesMain.html)

[DCLDB](DCLDB.html)

[CreateName Method](CreateName_Method.html)

[UpdateName Method](UpdateName_Method.html) 
