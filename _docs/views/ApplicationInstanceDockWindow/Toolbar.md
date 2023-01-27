---
title: View - Application Instance - Toolbar
description: The toolbar of the main application instance window.
---
# Toolbar
![assets/img/ApplicationInstanceWindow/Toolbar.png](../../../assets/img/ApplicationInstanceWindow/Toolbar.png)

## Snapshots
![assets/img/ApplicationInstanceWindow/ToolbarSnapshots.png](../../../assets/img/ApplicationInstanceWindow/ToolbarSnapshots.png)
- Creates a snapshot of the current application, visible as a [snapshot instance](../mainwindow/applicationInstance.md) of this application.
- Creates a snapshot of the current application and stores it as a file so you can share it. <br/>
    The file is saved in the folder you installed CodeGlass in on the connected [hub](../../features/CodeGlassHub.md).

For more information see [Feature - Profiling Snapshots](../../features/ProfilingSnapshots.md)

## Execution control
![assets/img/ApplicationInstanceWindow/ToolbarExecutionControl.png](../../../assets/img/ApplicationInstanceWindow/ToolbarExecutionControl.png)
- [Soft off](../../features/ApplicationInstanceExecutionControl.md#soft-off), disables the collection of data but keeps the application running.
- [Continues](../../features/ApplicationInstanceExecutionControl.md#pause--resume) the applicatio when it is paused
- [Throttle](../../features/ApplicationInstanceExecutionControl.md#throttle) the application to a specific fps (Functions per second)
- [Pauses](../../features/ApplicationInstanceExecutionControl.md#pause--resume) the applicatio when it is running or stops [stepping](../../features/ApplicationInstanceStepping.md)
- [Stops](../../features/ApplicationInstanceExecutionControl.md#stop) the application if it is not stopped yet.
- [Restars](../../features/ApplicationInstanceExecutionControl.md#restart) the application

![assets/img/ApplicationInstanceWindow/ToolbarThrottle.png](../../../assets/img/ApplicationInstanceWindow/ToolbarThrottle.png)

The Throttle button also has a dropdown with the following items:
{% include ExecutionControl/ThrottleContextMenu.md %}


![assets/img/ApplicationInstanceWindow/ToolbarRestart.png](../../../assets/img/ApplicationInstanceWindow/ToolbarRestart.png)

The restart button also has a dropdown with the following items:
{% include ExecutionControl/RestartContextMenu.md %}

For more information see [Feature - Application Instance Execution Control](../../features/ApplicationInstanceExecutionControl.md)

## Stepping
![assets/img/ApplicationInstanceWindow/ToolbarStepping.png](../../../assets/img/ApplicationInstanceWindow/ToolbarStepping.png)

{% include ExecutionControl/SteppingToolbar.md %}

## Realtime Rendering
![assets/img/ApplicationInstanceWindow/ToolbarRendering.png](../../../assets/img/ApplicationInstanceWindow/ToolbarRendering.png)

- Opens the [Code Heat Map](CodeHeatMap.md) in a new tab.
- Opens the [Call Tree](CallTreeRendering.md) in a new tab.
- Opens the [Call Stack](CallStackRendering.md) in a new tab.
<!-- - Opens the [Grouped Call Stack Rendering](GroupedCallStackRendering.md) in a new tab. -->

For more information see [Feature - Realtime Rendering](../../features/RealtimeRendering.md)
# See Also:
- [Application Instance Window](../ApplicationInstanceDockWindow.md)
- [Feature - Application Instance Execution Control](../../features/ApplicationInstanceExecutionControl.md)

