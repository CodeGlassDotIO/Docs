---
title: Feature - Real-time profiling and data collection
description: The real-time data collection of CodeGlass instead of logging.
---
# Realtime Profiling and Data Collection
Code Glass is the first and only program that allows you to profile and use this data in real-time! 

Code Glass collects the data in real-time, including a real-time [callstack](#callstack) and [statistics](#statistics). It makes this data accessible to the user through the [client](CodeGlassClient.md), where all other profilers record it to some log file that you get access to after you finish recording.

The real-time data means that with Code Glass, you can press a button, call the API, enter a command, etc., on the profiled application and immediately see in Code Glass what happened with your application.

It can show you why your application is unresponsive at this moment, where a racing condition occurred, or what else it is doing through [real-time rendering](RealtimeRendering.md)
And so much more as it is one of the core components that makes Code Glass Special.


It does this all without such an overhead that the profiled application becomes unusable, though we recommend settings up [profiling data filters](ProfilingDataFiltering.md) to improve performance.

It is also not sampling, so it will never miss a call. However, it skips a call if you have it as a [start filter](profilingdatafiltering.md#application-instance-start-filters)

It is also possible to temporarily stop data collection by setting the profiler [Soft off](ApplicationInstanceExecutionControl.md#soft-off), which causes the application to run at nearly complete performance.


The Prominent data we collect in realtime currently is:
- The [callstack](#callstack)
- All kind of [statistics](#statistics)
- All [exceptions](#exceptions)

## Callstack
We collect the application's call stack in real-time, or more specific: every change to the call stack, be it a call, return, or tail call.

It is not sampling, so it will not miss a call; it, however, can skip a call if you have it as a [start filter](profilingdatafiltering.md#application-instance-start-filters)

This data is primarely used for our [realtime rendering](RealtimeRendering.md) and [code body reconstruction](CodeBodyReconstruction.md) feature.

## Statistics
We collect all kinds of statistics in real-time; these include but are not limited to:

- CPU, the percentage of CPU usage
- Memory, the amount of memory in use.
- Active Calls, The number of active calls under one item
- Active Threads, The number of active threads under one item <br/>
- Total Calls, The number of total calls made while profiling under one item.
- Total Call Duration, the total amount of [messured time](#time-messurement) spent under one item
- AVG, the average amount of [messured time](#time-messurement) spend under one item
- Longest Call, the longest [messured time](#time-messurement) spend under one item
- Shortest Call, the shortest [messured time](#time-messurement) spend under one item
- Δ Calls, Amount of calls Last second under one item
- Δ Duration, the amount of [messured time](#time-messurement) spend last second under one item

When you double-click an item in the tree view, it will open the [Object Details View](../views/ApplicationInstanceDockWindow/ObjectDetailsView.md) or [Function Details View](../views/ApplicationInstanceDockWindow/CodeMemberDetailsView.md) of the selected item.

### Time messurement
To get more information on how we messure time, see [Feature - Time Messurement](TimeMessurement.md)

## Exceptions
We currently collect any exceptions that occur in your application, even if you don't catch them. 
With the exception, we also collect the unrolled stack till it found a catch block and the [realtime collected callstack](#callstack), though this heavily depends on how you configured your [profiling data filters](ProfilingDataFiltering.md)

More information about our exception collection can be found at the [exceptions feature page](Exceptions)

## Memory
We currently do not collect memory data (except total memory usage) in real-time; however, we will implement that in the future.


# See Also:
- [Feature - Realtime Rendering](RealtimeRendering.md)
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)
- [Feature - Code Glass Client](CodeGlassClient.md)
- [Feature - Profiling Data Filtering](ProfilingDataFiltering.md)