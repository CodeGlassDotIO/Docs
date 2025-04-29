---
title: View - Application Instance - Application Explorer
description: Tree view that shows you all the data items like classes and methods.
---
# Application Explorer
![assets/img/ApplicationInstanceWindow/AppInstanceApplicationExplorerContextMenu.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceApplicationExplorerContextMenu.png)

The application explorer shows all the collected data objects, like namespaces, classes and methods / functions, of the profiled application.

On this screen you can easily manage what you want to [filter](../../features/ProfilingDataFiltering.md). This can be done by right clicking on an item or by opening the [object details view](ObjectDetailsView.md) by double clicking on an item.

The items you see are based on the [application instance filters](../../features/ProfilingDataFiltering.md#application-instance-filters). Items that are light gray are partially filtered and items that are dark gray are fully filtered.

## Toolbar
At the top of panel you can see the toolbar. The buttons are described below from left to right.
- Show [current application instance filters](../../features/ProfilingDataFiltering.md#application-instance-filters),
- Show [start application instance filters](../../features/ProfilingDataFiltering.md#application-instance-start-filters),
- Apply no filters.
- Collapse all items.
- Apply the current filters to [application filters](../../features/ProfilingDataFiltering.md#application-filters).

Below these buttons, there is a search bar. Here you can search for a specific method by its name. When you click one of the search results, it will expand the tree view until the selected method.


## Context Menu
{% include Dso/DsoContextMenu.md  %}

<!-- # Application Breadcrumbs
- [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) /  -->
