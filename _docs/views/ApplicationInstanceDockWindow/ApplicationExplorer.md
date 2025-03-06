---
title: View - Application Instance - Application Explorer
description: Tree view that shows you all the data items like classes and methods.
---
# Application Explorer
![assets/img/ApplicationInstanceWindow/AppInstanceApplicationExplorerContextMenu.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceApplicationExplorerContextMenu.png)

The application explorer shows you the collected data objects, like classes and methods / functions, from the profiled application.

On this screen you can easily manage what you want to [filter](../../features/ProfilingDataFiltering.md) by right clicking or open the the [object details view](ObjectDetailsView.md) by double clicking on them.

The items you see are based on the [application instance filters](../../features/ProfilingDataFiltering.md#application-instance-filters) you select and apply, light gray items mean that the item is partially filtered and dark gray are fully filtered

More details below.

## Toolbar
The options from left to right:

- Select what [filter](../../features/ProfilingDataFiltering.md) type you want to filter the explorer on
    - [Current application instance filters](../../features/ProfilingDataFiltering.md#application-instance-filters),
    - [Start application instance filters](../../features/ProfilingDataFiltering.md#application-instance-start-filters),
    - No Filter
- Collapse all items
- Apply the current filters to [application filters](../../features/ProfilingDataFiltering.md#application-filters)
- Below these buttons, there is a search bar. Here you can search for a specific method by its name. When you click one of the search results, it will expand the tree view until the selected method.


## Context Menu
{% include Dso/DsoContextMenu.md  %}

# Application Breadcrumbs
- [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 
