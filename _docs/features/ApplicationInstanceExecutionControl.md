---
title: Feature - Application Instance Execution control
description: Control the execution of the profiled application.
---

# Execution Control
These are functions to control the execution of the application level, in the future we will also make it possible to do this on function level ([Roadmap](../Roadmap/PerFunctionAction.md)).

## Soft Off
Soft off stops the collection of most data, allowing the application to run at almost full performance.
This mode was made with production enviroments in mind, where an application starts to run slow after a while and then can disable Soft Off and then can start profiling it.

## Start
Starts an application on the ([remote](CodeGlassHub.md#remote-hub)) [client](CodeGlassClient.md).

## Pause 
Pause the execution of an application on the ([remote](CodeGlassHub.md#remote-hub)) [client](CodeGlassClient.md).
This can be done manually but also automatically like by [Exceptions](Exceptions.md)

## Resume
Resuming the execution of an application on the ([remote](CodeGlassHub.md#remote-hub)) [client](CodeGlassClient.md).

## Throttle
Limitting the amount of executed functions per seconds 

## Stop
Stops the execution of an application on the ([remote](CodeGlassHub.md#remote-hub.md)) [client](CodeGlassClient.md).

## Restart
Restarts the execution of an application on the ([remote](CodeGlassHub.md#remote-hub.md)) [client](CodeGlassClient.md).

## (Thread) Stepping Backwards / Forwards
See [Feature - Stepping](ApplicationInstanceStepping.md)


## Views using this feature
- [View - Application instance Window - Toolbar](../views/ApplicationInstanceDockWindow/Toolbar.md)


# See Also:
- [Feature - Stepping](ApplicationInstanceStepping.md)
- [Feature - Exception Collection](Exceptions.md)
- [Roadmap - Per function Execution Control](../Roadmap/PerFunctionAction.md)


