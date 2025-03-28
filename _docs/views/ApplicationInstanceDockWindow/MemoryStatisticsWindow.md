---
title: View - Application Instance - Memory Statistics View
description: The profiling memory statistics of a profiled application.
---

# Memory Statistics View
![assets/img/ApplicationInstanceWindow/MemoryStatisticsWindow.png](../../../assets/img/ApplicationInstanceWindow/MemoryStatisticsWindow.png)

This view contains the general memory statistics of a profiled application. Each piece of memory is grouped by their namespace. Items that are blue are namespaces that contain other namespaces or allocatable objects (yellow).

{% include MemoryStatistics/BasicMemoryStatisticsExplaination.md %}

Just above the statistics tree view, you find a search bar that allows you to search for object by their name. When you click on one of the search results, the tree view will expand until the selected object is visible.

When you double click on one of the namespace tree view items, it opens a new memory window, but it will only show memory statistics for that specific namespace.

When you double click on one of the allocatable object tree view items, it opens the [code paths that allocated this object view](AllocatedByCodePathView).