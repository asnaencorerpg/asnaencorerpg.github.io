---
title: DBFile.BlockingFactor Field

Id: BlockingFactorFieldDBFileClass
TocParent: aerLrfDbFileFieldsMain
TocOrder: 0


---

**BlockingFactor** contains the client/server record blocking size. 

```

 *dbfile* . **BlockingFactor Type(*IConnteger)** 
```

### Remarks
**BlockingFactor** ***must*** be set prior to opening the file (see [OPEN](OPEN.html) command). 

If **BlockingFactor** is not set, the **NetblockFactor** parameter value specified in the [DCLDISKFILE](DCLDISKFILE.html) command is used. 

**BlockingFactor** determines if and how many database records will be blocked across the Network for better performance when reading groups of records. Network blocking significantly reduces the network burden of transferring records between server and client machines, and this is demonstrated by the substantial increase of data throughput due to the reduced number of TCP/IP packet requests. 

The database file must be declared in the **DCLDISKFILE** command as **Type( *Input )** and **AddRec( *NO )** before network blocking can used. 

The blocking factor is expressed as the maximum number of records to block. Valid values are: 

-1 ........... The blocking factor will be computed automatically (6K/record length). 

0 or 1 ..... One record at a time will be transported across the network. 

nnn ........ nnn records at a time will be blocked.

When a file is network blocked, the block is delivered when the database engine receives the first read request. This means the client will wait to receive the block before competing the processing of the request. The subsequent read requests will retrieve the records from the cached block held by the client. When the cache is empty, the next block is retrieved when the database engine receives the next read request. 

It is prudent to set the blocking factor to a value less than or equal to the number of records being processed at one time. For instance, if your application is adding 50 records at a time to a DataGrid, then the blocking factor should not be greater than 50. 

When you employ [SETRANGE](SETRANGE.html) & [READ](READ.html)/[READP](READP.html) and [READRANGE](READRANGE.html) & [READ](READ.html)/[READP](READP.html) idioms, the database engine will place no more records in the block than needed to satisfy the range. 

**Hint:** If you are using a **progress bar** to show the progress of reading the next *n* records, make the blocking factor a fraction of the total records to be processed. For example, if processing 50 records at a time, set BlockingFactor to 10. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[DBFile Class](aerLrfDBFileClass.html)
[DBFile Members](aerLrfDBFileMembers.html)
[DCLDISKFILE](DCLDISKFILE.html)
[OPEN](OPEN.html) 
