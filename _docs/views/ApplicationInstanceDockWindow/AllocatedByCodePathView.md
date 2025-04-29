---
title: View - Application Instance - Allocated by Code Path Memory Statistics View
description: The profiling memory statistics of a profiled application by code path.
---

# Allocated by Code Path Memory Statistics View
![assets/img/ApplicationInstanceWindow/AllocatedByCodePathMemoryStatsWindow.png](../../../assets/img/ApplicationInstanceWindow/AllocatedByCodePathMemoryStatsWindow.png)

This view shows all the function that have allocated this specific object. The nested functions shows between which function calls, in the body of the parent function, the object was allocated.

Just above the statistics tree view, you find the toolbar. The toolbar contains the following items:
- Force Garbage Collection allows you to force the garbage collection to run. (This option is grayed out if the integration does not support this feature.)

When you double click on one of the tree view items it will open the [code member details view](CodeMemberDetailsView).

## Available Data
{% include MemoryStatistics/BasicMemoryStatisticsExplaination.md %}