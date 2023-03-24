---
title: Using NetBlockFactor

Id: aerConUsingNetblockfactor
TocParent: aerConObjects
TocOrder: 60


---

```<span style="FONT-WEIGHT: bold; COLOR: #000080">NetBlockFactor</span>``` determines if and optionally how many database records will be blocked across the Network for better performance when reading or writing groups of records. Network blocking significantly reduces the network burden of transferring records between server and client machines, and this is demonstrated by the substantial increase of data throughput. 

Unless NetBlockFactor is ```*NONE```, network blocking is employed for input and output files as described below. 

```<span style="FONT-WEIGHT: bold; COLOR: #000080">INPUT</span>``` - The file is declared with ```<span class="expandspot" style="COLOR: #0000ff">Type</span>(<span style="COLOR: #ff0000">*INPUT</span>)``` and ```AddRec(<span style="COLOR: #ff0000">*NO</span>)```. When an input file is "blocked", the buffered data resides on the client PC. This allows successive ```READ``` and ```READE``` statements to execute quickly. Be aware that should records be updated in other definitions of the file, those changed are not correspondingly updated in the buffer. 

```<span style="FONT-WEIGHT: bold; COLOR: #000080">OUTPUT</span>``` - The [disk file](DCLDISKFILE.html) is declared with ```<span style="COLOR: #0000ff">Type</span>(<span style="COLOR: #ff0000">*OUTPUT</span>)``` and ```Cachewrites(<span style="COLOR: #ff0000">*YES</span>)```. When an output file is "blocked", the buffered data resides on the client PC until the block has been filled or the file is closed. Then the block is sent to the server in a single transaction. Be aware that I/O errors at the server are returned only during processing of the block. In other words, if the 33rd record in a block of 100 records had a duplicate key, your application would not be aware of it until after writing the 100th record. Therefore, the use of network blocking for output files should be employed only when your application can be restarted. 

I/O operations that will reset the buffer are [SETLL](SETLL.html), [SETGT](SETGT.html), [SETRANGE](SETRANGE.html), [CHAIN](CHAIN.html) ([READRAND](READRAND.html))  and [READRANGE](READRANGE.html). 

- ```<span style="FONT-WEIGHT: bold">*CALC</span>``` - The system will calculate the number of records to block. The blocking factor is 6000 divided by the file's record length. If the record length is greater than 3000 (1/2 the block size), ```*CALC``` will compute a record blocking Factor of 1 (one).
- ```*<span style="FONT-WEIGHT: bold">NONE</span>``` - No blocking will occur on the file. This is the default when the <span style="FONT-WEIGHT: bold">Type</span> is other than ```*INPUT```.
- <span style="FONT-WEIGHT: bold"> Record Count - </span> The maximum number of records to include in the block. Note, the number of records in the block for [SETRANGE](SETRANGE.html) with [READ](READ.html) operations, and for [READRANGE](READRANGE.html) operations will be less than the record count if the set of records in the range is smaller than the maximum block size. Because of this dynamic blocking, the use of ```SETRANGE``` and ```READRANGE``` can realize even better performance than [SETLL](SETLL.html) and [READE](READE.html), for example.

Record blocking requires additional memory to work. Blocking reserves memory for the complete block of each blocked file. For example, a record length of 2560 and a blocking factor of 100 will require an additional 256K of memory. 

### See Also
[ENDCLASS](ENDCLASS.html)
[Understanding Classes](aerTourClassesBlueprintsforObjects.html) 
