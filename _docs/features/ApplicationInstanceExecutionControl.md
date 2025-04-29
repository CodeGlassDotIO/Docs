---
title: Feature - Application Instance Execution control
description: Control the execution of the profiled application.
---

# Execution Control
When profiling an application, CodeGlass provides various actions to modify its execution. These functions allow control at the application level. In the future, we plan to extend this functionality to the function level as well ([roadmap](../Roadmap/PerFunctionAction.md)).

The screenshot below shows the toolbar that contains all the buttons used to perform the available action described below.

![assets/img/ApplicationInstanceWindow/Toolbar.png](../../assets/img/ApplicationInstanceWindow/Toolbar.png)

## Soft Off
Soft Off temporarily stops most data collection, allowing the application to run at near full performance.

This mode is designed for production environments where performance may degrade over time. Soft Off can be enabled to address this without losing performance to CodeGlass. When the performance issue arises, Soft Off can be disabled to begin profiling without restarting the application.

## Pause 
Pause temporarily stops the execution of the application on the ([remote](CodeGlassHub.md#remote-hub)) [client](CodeGlassClient.md).

It can be triggered manually or configured to pause automatically in response to specific events, such as [exceptions](Exceptions.md).

## Continue
Continues the execution of an application on the ([remote](CodeGlassHub.md#remote-hub)) [client](CodeGlassClient.md).

## Throttle
Limits the amount of functions that can be executed per seconds 

## Stop
Stops the execution of an application on the ([remote](CodeGlassHub.md#remote-hub.md)) [client](CodeGlassClient.md).

## Restart
Restarts the execution of an application on the ([remote](CodeGlassHub.md#remote-hub.md)) [client](CodeGlassClient.md).

<!-- ## (Thread) Stepping Backwards / Forwards
See [Feature - Stepping](ApplicationInstanceStepping.md) -->


# See Also:
- [Feature - Stepping](ApplicationInstanceStepping.md)
- [Feature - Exception Collection](Exceptions.md)
- [Roadmap - Per function Execution Control](../Roadmap/PerFunctionAction.md)
