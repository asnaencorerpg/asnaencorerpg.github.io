---
title: RPG Cycle

Id: aerCycle_Overview
TocParent: aerConLanguageConceptsMain
TocOrder: 100


---

Encore RPG 8.2 and above feature RPG Cycle support for Monarch migrated applications. Since most ECR programmers already "know" the RPG Cycle, only an overview of how the cycle works and is supported with Encore RPG is included. For more information, please see the **Cycle Support** topic in the Monarch Migration manual or the Cocoon help file. 

The RPG compiler supplies part of the logic for an RPG program. That logic is called the *program cycle* or *RPG cycle* . The program cycle is a series of ordered steps that the main procedure goes through for each record read. 

The information specifies when records should be read or written. The RPG compiler can supply the logical order for these operations when your source program is compiled. Depending upon the specifications you code, your program may or may not use each step in the cycle. 

Primary and secondary files indicate input is controlled by the program cycle. a full procedural file indicates that input is controlled by program-specified calculation operations (for example, ```READ``` and ```CHAIN```). 

To control the cycle, you can have: 

- One primary file and, optionally, one or more secondary files
- Only full procedural files
- A combination of one primary file, optional secondary files, and one or more
                full procedural files in which some of the input is controlled by the cycle,
                and other input is controlled by the program.
- No files (for example, input can come from a parameter list or a Dataarea
                Data structure).![](Images/cycle.bmp)

1. [*StartCycle](aerCycle_StartCycleMethod.html) is the name of the
                subroutine that performs the Cycle. It assumes the primary and all secondary
                files are already open, which causes the first record from the primary and all
                secondary files to be read, and all program fields have their correct values
                including first page indicator (```*IN1P``` – it is initialized to *ON in the class
                constructor).
2. If ```*IN1P``` is ```*ON``` (this is the first time ```*StartCycle```
                is called), go to step 3. Otherwise, go to step 4.
3. Perform header and detail output (```*DetailOutput```
                ). Set ```*OFF *IN1P```.
4. Set ```*OFF```
                all record identifying and L1 through L9 indicators.
5. If ```*INLR```
                is ```*ON```, go to step 6, otherwise go to step 7.
6. Set ```*ON```
                the level indicators ```*INL1``` through ```*INL9```, and go to step 18.
7. If this is not the first program cycle, read a record from the last file
                processed.
8. If [FORCE](FORCE.html)
                was issued on the previous cycle, go to step 9, otherwise go to step 10.
9. The forced file is selected for processing. If the forced file is at EOF, go to
                step 10. Otherwise, the match record indicator (```*INMR```) is set to *OFF and the
                match fields in the forced file are saved. Continue at step 13.
10. If match fields are used in the program, go to step 11. Otherwise go to step
                12.
11. The match field routine selects the next file. Continue at step 13.
12. The next file is selected. It will be either the primary if it’s not at EOF, or
                the first secondary that is not at EOF selected according to the order they are
                specified in the program.
13. If all files are at ```EOF```, then go to 14. Otherwise go to
                15.
14. Set ```*ON```
                ```*INLR``` and all level indicators ```*INL1``` through ```*INL9```. Continue at 18.
15. The record identifying indicator is set *ON for the record selected for
                processing.
16. If there is a control break, go to 17, otherwise go to 18.
17. The appropriate level break indicator (```*INL1``` through ```*INL9```) is set ```*ON```.
                All lower level indicators are also set ```*ON```.
18. Determine whether totals need to be executed and if so go to 19, otherwise go
                to 20.  If no control levels are specified for any record, totals are
                bypassed on the first cycle and are always processed after the first cycle. If
                control levels are specified, totals are bypassed until the first record
                containing control fields has been processed.
19. ```*TotalCalculations``` and ```*TotalOutput```
                are processed.
20. If ```*INLR```
                is ```*ON```, go to step 22.
21. The match record indicator (```*INMR```)
                is set ```*ON``` or ```*OFF``` depending on whether the record read is a
                matching record.
                Data from the last record read is made available for processing.
                ```*DetailCalculations``` are processed. Continue at step 3.
22. Return to the caller.

#### See Also
[Cycle Overview](aerCycle_Overview.html)

[DCLPRINTFILE](DCLPRINTFILE.html)

[Level Break Indicators](aerCycle_LevelBreakIndicators.html)

[Matching Record Indicators](aerCycle_MatchingRecordIndicators.html)

[Overflow Indicators](aerCycle_OverflowIndicators.html)

[```*DetailCalc``` Method](aerCycle_DetailCalcMethod.html)

[```*FetchOverflow``` Method](aerCycle_FetchOverflowMethod.html)

[```*StartCycle``` Method](aerCycle_StartCycleMethod.html)

[```*TotalCalc``` Method](aerCycle_TotalCalcMethod.html) <br /> 
