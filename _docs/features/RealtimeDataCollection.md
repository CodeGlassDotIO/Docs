---
title: Feature - Real-Time Profiling and Data Collection
description: The real-time data collection of CodeGlass instead of logging.
---

# Real-Time Profiling and Data Collection

What sets CodeGlass apart from traditional profilers is its ability to capture and utilize profiling data in real time. Rather than waiting for logs to be written and processed, CodeGlass delivers immediate insights as your application runs.

CodeGlass continuously collects real-time data such as the live [call stack](#call-stack), detailed [statistics](#statistics), and system-level events. This data is made instantly available in the [CodeGlass Client](CodeGlassClient.md) which enables real-time analysis of your application’s behavior while it’s running.

With real-time visible data, you can trigger actions in your app (e.g., button clicks, API calls) and instantly observe the internal effects. This is particularly useful for identifying performance bottlenecks, race conditions, or unexpected behaviors through our [real-time renderers](RealtimeRendering.md).

Although CodeGlass captures full call activity (not samples), it maintains low overhead. We recommend configuring [profiling data filters](ProfilingDataFiltering.md) to further reduce performance impact.

If necessary, you can pause data collection with [Soft Off mode](ApplicationInstanceExecutionControl.md#soft-off) to restore practically normal performance.

Currently, CodeGlass collects the following data types in real time:
- [Call stack](#call-stack)
- [Statistics](#statistics)
- [Exceptions](#exceptions)
- [Memory allocations and deallocations (experimental)](#memory)
- [Garbage collection invocations (experimental)](#garbage-collection-invocations)

## Call Stack

CodeGlass captures every call and return operation, including tail calls, as they happen. This real-time call stack data powers features like [Realtime Rendering](RealtimeRendering.md) and [Code Body Reconstruction](CodeBodyReconstruction.md).

Unlike sampling-based profilers, CodeGlass does not skip or estimate calls. Data is only excluded if explicitly filtered out via [start filters](ProfilingDataFiltering.md#application-instance-start-filters).

## Statistics

CodeGlass collects a wide range of runtime statistics:

- **CPU**: Percentage of CPU used  
- **Memory**: Memory in use  
- **Active Calls**: Current number of live calls  
- **Active Threads**: Number of active threads per item  
- **Total Calls**: Aggregate number of calls to a function  
- **Total Call Duration**: Cumulative execution time  
- **AVG**: Average execution time  
- **Longest Call**: Longest recorded duration  
- **Shortest Call**: Shortest recorded duration  
- **Δ Calls**: Number of calls in the last second  
- **Δ Duration**: Execution time in the last second  

![assets/img/ApplicationInstanceWindow/StatisticsWindow.png](../../assets/img/ApplicationInstanceWindow/StatisticsWindow.png)

Double-clicking an item in the statistics tree opens the [Object Details View](../views/ApplicationInstanceDockWindow/ObjectDetailsView.md) or [Function Details View](../views/ApplicationInstanceDockWindow/CodeMemberDetailsView.md) for deeper analysis.

### Time Measurement

See [Feature - Time Measurement](TimeMessurement.md) for a detailed explanation of how execution time is measured.

## Exceptions

All exceptions, caught or uncaught, are collected by CodeGlass, along with:

- The unrolled stack trace up to the nearest catch block  
- The real-time [call stack](#call-stack) at the point of failure  

The level of detail depends on your [profiling data filters](ProfilingDataFiltering.md).

![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png](../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png)

For more information, see [Feature - Exceptions](Exceptions)

## Memory

Memory profiling is currently experimental and available in the [Experimental Edition](../Editions/Experimental.md) for supported [runtimes](supportedruntimes.md).

CodeGlass captures:

- **Total allocations**: Number of allocations by type  
- **Total bytes allocated**: Aggregate memory used  
- **Total deallocations**: Number of objects released  
- **Total bytes deallocated**: Memory freed  

In addition to aggregate stats, CodeGlass shows which methods are responsible for allocating specific types, and how frequently.

![assets/img/ApplicationInstanceWindow/MemoryStatisticsOverview.png](../../assets/img/ApplicationInstanceWindow/MemoryStatisticsOverview.png)

For more details, see [Feature - Memory Profiling](MemoryProfiling)

## Garbage Collection Invocations

Also experimental, this feature tracks all garbage collections triggered during application execution. Currently supported on [Julia](supportedruntimes.md#julia) and [.NET](supportedruntimes.md#net-framework) runtimes.

Captured metrics include:

- The function that triggered GC  
- Duration of the GC process  
- Total memory deallocated  
- Deallocated objects and their originating allocation site  

![assets/img/ApplicationInstanceWindow/GarbageCollectionInvokedWindow.png](../../assets/img/ApplicationInstanceWindow/GarbageCollectionInvokedWindow.png)

See [Feature - Garbage Collection](GarbageCollection) for more details.

# See Also:
- [Feature - Realtime Rendering](RealtimeRendering.md)  
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)  
- [Feature - CodeGlass Client](CodeGlassClient.md)  
- [Feature - Profiling Data Filtering](ProfilingDataFiltering.md)
