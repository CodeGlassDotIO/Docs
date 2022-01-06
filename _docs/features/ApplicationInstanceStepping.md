---
title: Feature - (Thread) Stepping Forwards & Backwards
description: Step the profiled application forwards and backwards
---
# (Thread) Stepping Forwards & Backwards

Allowing to step the execution of the application forwards, but also watching it back by stepping back through the collected history and emulating the application's state at that point. 

Stepping stops automatically if a specific step instruction is not reached within the specified timeout.

## Thread stepping
You can also step specific threads, and please note that this does not cause this thread only to step. Every thread will keep stepping till this particular thread does. <br/> If you are interested in only stepping a specific thread and keeping the other threads paused, see the [thread only stepping](../Roadmap/ThreadOnlyStepping.md) roadmap item.

## Step instructions

### Step Into
Steps to the next execution step include a function call, return or tailcall.

### Step Over
Keeps stepping until it returns to this function or leaves the current function, or more technical: When the number of calls is smaller or equal to the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate. 

### Step Out
Keeps stepping until the current function returns, or more technical: When calls are smaller than the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate.

### Step back into
Steps to the previous recorded execution step include a function call, return or tail call.

### Step back over
Keeps stepping back to previously recorded execution until it returns to this function or leaves the current function, or more technical: When the number of calls is smaller or equal to the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate. 


### Step back out
Keeps stepping back to previously recorded execution steps before the current function is called, or more technical: When the number of calls is smaller than the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate. 

## Views using this feature
 - [Realtime Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
 - [Realtime Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
 - [Realtime Grouped Call Stack Rendering](../views/ApplicationInstanceDockWindow/GroupedCallStackRendering.md)
 - [Thread Detail View](../views/ApplicationInstanceDockWindow/ThreadDetailsView.md#thread-stepping-controls)
 - [Process Menu](../views/ApplicationInstanceDockWindow/MenuBar.md#process-menu)

# See Also:
- [Application Instance Execution Control](ApplicationInstanceExecutionControl.md)


