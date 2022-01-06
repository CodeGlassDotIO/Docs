---
title: View - Application Instance - function Details View
description: Details about the function / method
---
# Function Details View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png)

{% include alert.html  type="warning" title="Only functions use this view" content="This view is used only by functions, others use the <a href=\"ObjectDetailsView\" >Object Details View</a>" %}


This view has two inner views, [Code Body View](#code-body-view) and the [statistics view](#statistics-view).

See them for more information.



## Code Body View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsView.png)
{% include alert.html  type="warning" title="Experimental feature" content="This feature is still very experimental, though it is available in all <a href=\"../../Editions\" >Editions</a>, for more info see the the <a href=\"../../features/CodeBodyReconstruction\" >Code Body Reconstruction feature</a> description." %}

{% include alert.html  type="warning" title="This is not done by decompiling your application!" content="This feature does <b>not</b> work by decompiling your application and inspecting your code, for info on how it does work see the the <a href=\"../../features/CodeBodyReconstruction\" >Code Body Reconstruction feature</a> description." %}
From this view you can see on the left what functions call this function and how much time the function took for the caller.

On the Right you see the embodiement  of our [Code Body Reconstruction feature](../../features/CodeBodyReconstruction.md). <br/>
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
- see [Code Body Reconstruction feature](../../features/CodeBodyReconstruction.md) for more.

{% include alertNoTitle.html  type="info" content="Keep in mind that what you will see is highly dependent on the <a href=\"../../features/ProfilingDataFiltering#application-instance-start-filters\" >Application Instance Start Filters</a>." %}

Please keep in mind that this is an experimental feature available to anyone, for more information and help with any issues you might come across, check out [Code Body Reconstruction feature](../../features/CodeBodyReconstruction.md).

## Code Body Statistics View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewBodyStats.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewBodyStats.png)

This view gives you statistics on the code paths within the function, it shows you the same information what the [CodeBodyView](#code-body-view) shows but in a flat table that you can sort.

{% include Statistics/BasicStatisticsColumnExplaination.md %}




## Statistics View
![assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewStatistics.png](../../../assets/img/ApplicationInstanceWindow/CodeMemberDetailsViewStatistics.png)

This view looks and works allot like the [Statistics View](StatisticsWindow.md), the only exception is that it only shows the data  from this object instead of the whole profiled application instance by  namespace, classes, methods, etc.

{% include Statistics/BasicStatisticsExplaination.md %}

# Application Breadcrumbs
- {All paths leading to} /  [Application Instance Window](../ApplicationInstanceDockWindow.md) / 
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Statistics View](StatisticsWindow.md) /
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Application Explorer](ApplicationExplorer.md) /
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Call Tree Rendering](CallTreeRendering.md) /
    - [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / [Call Stack Rendering](CallStackRendering.md) /