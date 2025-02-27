---
title: View - Application Instance - Memory Statistics View
description: The profiling statistics of a (previously) profiled application.
---

# Memory Statistics View
![assets/img/ApplicationInstanceWindow/MemoryStatisticsWindow.png](../../../assets/img/ApplicationInstanceWindow/MemoryStatisticsWindow.png)

The view contains the general memory statistics of the profiled application by namespace and allocated objects.

{% include MemoryStatistics/BasicMemoryStatisticsExplaination.md %}

When you double click on one of the namespace tree view items it will open the same screen, but it will only show memory statistics for that specific namespace.

When you double click on one of the object tree view items it will open the [Code Paths that allocated this object view](AllocatedByCodePathView).