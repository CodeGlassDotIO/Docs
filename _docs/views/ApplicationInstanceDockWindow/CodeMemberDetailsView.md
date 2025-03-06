---
title: View - Application Instance - function Details View
description: Details about the function / method
---
# Function Details View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png)

{% include alert.html  type="warning" title="Only Functions Use This View" content="This view is used only by functions, others use the <a href=\"ObjectDetailsView\" >object details view</a>." %}

This view has three inner views, [code body view](#code-body-view), [code body statistics view](#code-body-statistics-view) and the [statistics view](#statistics-view). Both of these are described below.


## Code Body View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png)
{% include alert.html  type="warning" title="Experimental Feature" content="This feature is still very experimental, though it is available in all <a href=\"../../Editions\" >editions</a>, for more info see the the <a href=\"../../features/CodeBodyReconstruction\" >code body reconstruction feature</a> description." %}

{% include alert.html  type="warning" title="This is not done by decompiling your application!" content="This feature does <b>not</b> work by decompiling your application and inspecting your code, for info on how it does work see the the <a href=\"../../features/CodeBodyReconstruction\" >code body reconstruction feature</a> description." %}
From this view you can see on the left what functions call this function and how much time the function took for the caller.

On the right you see the embodiment of our [code body reconstruction feature](../../features/CodeBodyReconstruction.md). <br/>
This view shows you not only wich functions were called in real time by this function but so much more, inluding:
- Where in the code a function call was made. 
- What paths needs to be taken inside the function to reach a specific function call 
- How much time is spend in the body of the function between each function call. (This iliminates a huge part of the need to add stopwatches to your code)
- How many times a loop was executed
- How many times a path is taken
- Where a thread is in the function.
- Hot Paths
- Cold Paths
- Possibilities for optimizations, like loop unroling. 
- How your code really behaves against what you wrote.
- How much memory this function has allocated. (Only available with an [experimental license](../../Editions/Experimental.md))
- Where memory gets allocated. (Only available with an [experimental license](../../Editions/Experimental.md))
- see [code body reconstruction feature](../../features/CodeBodyReconstruction.md) for more.

{% include alertNoTitle.html  type="info" content="Keep in mind that what you will see is highly dependent on the <a href=\"../../features/ProfilingDataFiltering#application-instance-start-filters\" >application instance start filters</a>." %}

Please keep in mind that this is an experimental feature available to anyone, for more information and help with any issues you might come across, check out [code body reconstruction feature](../../features/CodeBodyReconstruction.md).

## Code Body Statistics View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewBodyStats.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewBodyStats.png)

This view gives you statistics on the code paths within the function, it shows you the same information what the [code body view](#code-body-view) shows but in a flat table that you can sort.

{% include Statistics/BasicStatisticsColumnExplaination.md %}

## Memory Statistics
If you have an [experimental license](../../Editions/Experimental.md) and you have memory profiling enabled, this view will give more information about allocations in your code.<br>
Code paths that allocate can also be expanded to see which objects it has allocated. Double clicking on the allocated object will open the [allocated by code path view](AllocatedByCodePathView.md).


## Statistics View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewStatistics.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewStatistics.png)

This view looks and works allot like the [statistics view](StatisticsWindow.md), the only difference is that it only shows the data from this object instead of the whole profiled application instance by namespace, classes, methods, etc.

{% include Statistics/BasicStatisticsExplaination.md %}

# Application Breadcrumbs
- [Application Instance Window](../ApplicationInstanceDockWindow.md) / 
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Statistics View](StatisticsWindow.md) /
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Application Explorer](ApplicationExplorer.md) /
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Call Tree Rendering](CallTreeRendering.md) /
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Call Stack Rendering](CallStackRendering.md) /