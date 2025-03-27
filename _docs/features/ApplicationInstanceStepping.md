---
title: Feature - (Thread) Stepping Forwards & Backwards
description: Step the profiled application forwards and backwards
---
# (Thread / Exception) Stepping Forwards & Backwards
This feature provides precise control over the execution of your application. You can step forward through execution or step back to review collected history, emulating the application's state at that moment.
<br>

![assets/img/ApplicationInstanceWindow/ToolbarStepping.png](../../assets/img/ApplicationInstanceWindow/ToolbarStepping.png)

Stepping automatically stops if a specific step instruction is not reached within the set timeout.

## Step instructions

### Step Into
Steps to the next execution step include a function call, return or tail call.

### Step Over
Keeps stepping until it returns to this function or leaves the current function, or more technical: When the number of calls is smaller or equal to the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate. 

### Step Out
Keeps stepping until the current function returns, or more technical: When calls are smaller than the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate.

### Step Back Into
Steps to the previous recorded execution step include a function call, return or tail call.

### Step Back Over
Keeps stepping back to previously recorded execution until it returns to this function or leaves the current function, or more technical: When the number of calls is smaller or equal to the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate. 

### Step Back Out
Keeps stepping back to previously recorded execution steps before the current function is called, or more technical: When the number of calls is smaller than the amount of return and tail calls.
The non-technical explanation is correct for thread-specific stepping, but in other cases, since we are stepping on all threads, the technical explanation is more appropriate. 

## Views Using This Feature
 - [Realtime Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
 - [Realtime Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
 - [Thread Detail View](../views/ApplicationInstanceDockWindow/ThreadDetailsView.md#thread-stepping-controls)
 - [Process Menu](../views/ApplicationInstanceDockWindow/MenuBar.md#process-menu)

# See Also:
- [Application Instance Execution Control](ApplicationInstanceExecutionControl.md)
