---
title: Feature - (Thread) Stepping Forwards & Backwards
description: Step the profiled application forwards and backwards
---

# (Thread / Exception) Stepping Forwards & Backwards

This feature provides precise control over the execution timeline of your application. You can step forward to follow execution flow in real time, or step backward to analyze previously recorded states, effectively emulating the application's runtime behavior at that point in time.

![assets/img/ApplicationInstanceWindow/ToolbarStepping.png](../../assets/img/ApplicationInstanceWindow/ToolbarStepping.png)

Stepping will automatically stop if the defined step instruction is not reached within the configured timeout.

## Step Instructions

### Step Into

Advances to the next execution event, including function calls, returns, or tail calls.

### Step Over

The implementation is dependant on the type of stepping.
- For **thread-specific stepping**, it continues stepping until the application returns to the current function or exits it.  
- When **stepping across all threads**, this means stepping continues until the number of function calls is **less than or equal to** the number of returns and tail calls encountered.

### Step Out

The implementation is dependant on the type of stepping.
- For **thread-specific stepping**, it continues stepping until the application exits the current function.  
- When **stepping across all threads**, this means stepping continues until the number of function calls is **less than** the number of returns and tail calls encountered.

### Step Back Into

Steps to the previous recorded execution event, including calls, returns, or tail calls.

### Step Back Over

The implementation is dependant on the type of stepping.
- For **thread-specific stepping**, it continues stepping backwards until the application exits the current function.  
- When **stepping across all threads**, this means stepping continues until the number of function calls is **more than or equal to** the number of returns and tail calls encountered.

### Step Back Out

The implementation is dependant on the type of stepping.
- For **thread-specific stepping**, it continues stepping backwards until the application exits the current function.  
- When **stepping across all threads**, this means stepping continues until the number of function calls is **more than** the number of returns and tail calls encountered.

## Views Using This Feature

- [Realtime Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
- [Realtime Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
- [Thread Detail View](../views/ApplicationInstanceDockWindow/ThreadDetailsView.md#thread-stepping-controls)
- [Process Menu](../views/ApplicationInstanceDockWindow/MenuBar.md#process-menu)

# See Also:
- [Application Instance Execution Control](ApplicationInstanceExecutionControl.md)
