---
title: Commitment Control

Id: Comittment_Control
TocParent: aerLrfLangElementsMain
TocOrder: 150


---

With **Commitment** **Control** , you ensure one of two outcomes for the file operations: either all of the file operations are successful or none of the file operations has any effect. In this way, you process a group of operations as a unit. 

**<u>To use Commitment Control, you do the following:</u>** 

- Use the CL commands CRTJRN (Create Journal), CRTJRNRCV (Create Journal Receiver) and STRJRNPF (Journal Physical File) to prepare for using commitment control, and the CL commands STRCMTCTL (Start Commitment Control) and ENDCMTCTL (End Commitment Control) to notify the system when you want to start and end commitment control. See the CL Reference for information on these commands.
- Specify commitment control on the file-description specifications of the files you want under commitment control.
- Use the [COMMIT](COMIT.html) operation code to apply a group of changes to files under commitment control, or use the [ROLLBACK](ROLBACK.html) operation code to eliminate the pending group of changes to files under commitment control.

**<u>Starting and Ending Commitment Control</u>** 

The CL command STRCMTCTL notifies the system that you want to process files under commitment control. 

The LCKLVL (Lock Level) parameter allows you to select the level at which records are locked under commitment control. 

When you complete a group of changes with a **COMMIT** operation, you can specify a label to identify the end of the group. In the event of an abnormal job end, this identification label is written to a file, message queue, or data area so that you know which group of changes is the last group to be completed successfully. You specify this file, message queue, or data area on the STRCMTCTL command. 

Before you call any program that processes files specified for commitment control, issue the STRCMTCTL command. If you call a program that opens a file specified for commitment control before you issue the STRCMTCTL command, the opening of the file will fail. 

The CL command ENDCMTCTL notifies the system that your routing step has finished processing files under commitment control. 

**<u>Specifying Files for Commitment Control</u>** 

When a program specifies commitment control for a file, the specification applies only to the input and output operations made by this program for this file. Commitment control does not apply to operations other than input and output operations. It does not apply to files that do not have commitment control specified in the program doing the input or output operation. 

When more than one program accesses a file as a shared file, all or none of the programs must specify the file to be under commitment control. 

**<u>Commitment Control Operations</u>** 

The **COMMIT** operation tells the system that you have completed a group of changes to the files under commitment control. The **ROLLBACK** operation eliminates the current group of changes to the files under commitment control. 

If the system fails, it implicitly issues a **ROLLBACK** operation. You can check the identity of the last successfully completed group of changes using the label you specify in F1 of the **COMMIT** operation code, and the notify-object you specify on the STRCMTCTL command. 

At the end of a routing step, or when you issue the ENDCMTCTL command, the OS/400 system issues an implicit **ROLLBACK** , which eliminates any changes since the last **ROLLBACK** or **COMMIT** operation that you issued. To ensure that all your file operations have effect, issue a COMMIT operation before ending a routing step operating under commitment control. 

The **OPEN** operation permits input and output operations to be made to a file and the **CLOSE** operation stops input and output operations from being made to a file. However, the **OPEN** and **CLOSE** operations do not affect the COMMIT and ROLLBACK operations. A **COMMIT** or **ROLLBACK** operation affects a file, even after the file has been closed. For example, your program may include the following steps: 

- Issue **COMMIT**  (for files already opened under commitment
                control).
- 2. Open a file specified for commitment control.
- 3. Perform some input and output operations to this file.
- 4. Close the file.
- 5. Issue **ROLLBACK** .

The changes made at step 3 are rolled back by the **ROLLBACK** operation at step 5, even though the file has been closed at step 4. T he **ROLLBACK** operation could be issued from another program in the same routing step. 

A program does not have to operate all its files under commitment control, and to do so may adversely affect performance. The **COMMIT** and **ROLLBACK** operations have no effect on files that are not under commitment control. 

When multiple devices are attached to an application program, and commitment control is in effect for the files this program uses, the **COMMIT** or **ROLLBACK** operations continue to work on a file basis and not by device. The database may be updated with partially completed **COMMIT** blocks or changes that other users have completed may be eliminated. It is your responsibility to ensure this does not happen. 

**<u>Commitment Control Locks</u>** 

On the STRCMTCTL command, you specify a level of locking, either LCKLVL (*ALL) or LCKLVL (*CHG). When your program is operating under commitment control and has processed an input or output operation on a record in a file under commitment control, the record is locked by commitment control as follows: 

- Your program can access the record.
- Another program in your routing step, with this file under commitment control, can read the record. If the file is a shared file, the second program can also update the record.
- Another program in your routing step that does not have this file under commitment control cannot read or update the record.
- Another program in a separate routing step, with this file under commitment control, can read the record if you specified LCKLVL (*CHG), but it cannot read the record if you specified LCKLVL (*ALL). With either lock level, the next program cannot update the record.
- Another program that does not have this file under commitment control and that is not in your routing step can read but not update the record.
- Commitment control locks are different than normal locks, depend on the LCKLVL specified, and can only be released by the **COMMIT** and **ROLLBACK** operations.
- The **COMMIT** and **ROLLBACK** operations release the locks on the records. The **UNLCK** operation will not release records locked using commitment control. See the CL Reference for details on lock levels.
- The number of entries that can be locked under commitment control before the **COMMIT** or **ROLLBACK** operations are required may be limited.

**<u>Commitment Control in the Program Cycle</u>** 

Commitment control is intended for full procedural files, where the input and output is under your control. Do not use commitment control with primary and secondary files, where input and output is under the control of the RPG/400 program cycle. The following are some of the reasons for this recommendation: 

- You cannot issue a **COMMIT** operation for the last total output in your program.
- It is difficult to program within the cycle for recovery from a locked-record condition.
- Level indicators are not reset by the **ROLLBACK** operation.
- After a **ROLLBACK** operation, processing matching records may produce a sequence error.

### See Also
[COMMIT](COMIT.html)
[ROLLBACK](ROLBACK.html) 
