---
title: View - Application Instance - Statistics View
description: The profiling statistics of a (previously) profiled application.
---
# Statistics View
![assets/img/ApplicationInstanceWindow/StatisticsWindow.png](../../../assets/img/ApplicationInstanceWindow/StatisticsWindow.png)


{% include Statistics/BasicStatisticsExplaination.md %}

## Memory Statistics
If you have an [Experimental License](../../Editions/Experimental.md) and you have Memory Profiling enabled, this view will give insight in the memory usage per namespace, class and method.<br>
In this view you can choose to toggle the visibilty of the memory statistics by pressing the "Toggle Memory Stats" button.


For memory profiling the following columns have been added to this table:
- Self Allocations, the amount of allocations that happen in this function.
- Self Deallocation, the amount of deallocations that happen in this function.
- Callee Allocations, the total sum of allocations that happen in functions called by this function.
- Self Bytes Allocated, the amount of bytes allocated in this function.
- Self Bytes Deallocated, the amount of bytes deallocated in the fucntion.
- Callee Bytes Allocated, the total sum of bytes allocated by functions called by this function.

# Application Breadcrumbs
- { All paths leading to [Application Instance Window](../ApplicationInstanceDockWindow.md) } /   / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 

# See Also:
- [Application Instance Window](../ApplicationInstanceDockWindow.md)
- [Object Details View](ObjectDetailsView.md)
- [Function Details View](CodeMemberDetailsView.md)
- [Feature - Time Messurement](../../features/TimeMessurement.md)
- [Feature - Profiling data filtering](../../features/ProfilingDataFiltering.md)
