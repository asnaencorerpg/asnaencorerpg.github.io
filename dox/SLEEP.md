---
title: SLEEP

Id: SLEEP
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

Sleep suspends execution of the current thread for the specified milliseconds.

```
SLEEP 
 Interval  (Expression)
```

### Parts

**Interval** 

Required. Specifies the time, in milliseconds, for which to suspend execution.


### Remarks
A thread can relinquish the remainder of its time slice by calling this function with a sleep time of zero milliseconds. 

You have to be careful when using **SLEEP** and code that directly or indirectly creates windows. If a thread creates any windows, it must process messages. Message broadcasts are sent to all windows in the system. If you have a thread that uses **SLEEP** with infinite delay, the system will deadlock. 
