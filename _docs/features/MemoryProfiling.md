---
title: Feature - Memory Profiling 
description: Realtime memory profiler.
---

# Memory Profiling

{% include alert.html  type="warning" title="Limited support" content="At this point the only languages to support this feature are Julia and .NET, but more will be added soon." %}

Leveraging our [realtime profiling](../features/RealtimeDataCollection.md) capabilities, CodeGlass provides a memory profiler that helps identify and resolve memory-related issues in your application. Unlike traditional tools, CodeGlass not only reveals which objects are being heavily allocated, but also shows which methods are responsible for those allocations via the [Allocated by CodePath View](../views/ApplicationInstanceDockWindow/AllocatedByCodePathView.md).

![assets/img/ApplicationInstanceWindow/MemoryStatisticsWindow.png](../../assets/img/ApplicationInstanceWindow/MemoryStatisticsWindow.png)

## Available Statistics

Memory statistics are available in multiple locations within the CodeGlass interface:

### Dedicated Memory Views
- [Memory Statistics View](../views/ApplicationInstanceDockWindow/MemoryStatisticsWindow.md)
- [Allocated by CodePath View](../views/ApplicationInstanceDockWindow/AllocatedByCodePathView.md)

### Integrated Statistics Views
In addition to the dedicated memory views, memory-related data is also available in:
- [Statistics View](../views/ApplicationInstanceDockWindow/StatisticsWindow.md)
- [Function Details View](../views/ApplicationInstanceDockWindow/CodeMemberDetailsView.md)
