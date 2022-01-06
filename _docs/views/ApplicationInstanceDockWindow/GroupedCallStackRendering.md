---
title: View - Application Instance - Grouped Call Stack Rendering
description: The rendering of the call stack grouped by the specified data type, like class or namespace.
---
# Realtime Grouped Call Stack Rendering
![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png](../../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png)

{% include Warnings/RenderingPhotosensitivityWarning.html  %}

See [Feature - Realtime grouped call stack Rendering](../../features/RealtimeRendering.md#realtime-grouped-call-stack-rendering) for more information about the feature.

You can select to wich data object type you want to combines all calls in the [toolbar](#toolbar).

Hovering over an item will show you information about the Last and current threads using that function.

Hovering over a line will show you where it comes from and where it goes to. 

Right click on an item will open the [Context Menu](#item-context-menu).

Double clicking or with the conext menu of an item will open the [Object Detail View](ObjectDetailsView.md) of that item.

{% include alertNoTitle.html  type="info" content="You can improve the rendering performance in the <a href=\"#settings-window\">Settings Window</a>." %}

## Toolbar
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png)

With the toolbar you can do the following:


- Select what [filter](../../features/ProfilingDataFiltering.md) tyoe you want to use for filtering
    - Current Filters
    - Start Filters, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFilterType.md)
    - No Filter, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFilterType.md)
- [Filter](../../features/ProfilingDataFiltering.md) the current rendered items
- Clear the current render screen
- Selecting the object type new rendered items will be grouped by.
- Forcing all rendered items to be grouped by the selected object type.
- Open the [Settings window](#settings-window)

## Item Context Menu
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingContextMenu.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingContextMenu.png)

When you right click an item you have the following options:

- Open in item view, this opens the [Function Detail View](CodeMemberDetailsView.md).
- Open in Visual Studio, see [Roadmap - Open Item In Visual Studio](../../Roadmap/OpenItemInVisualStudio.md)

You can [filter](../../features/ProfilingDataFiltering.md) the item by:
- Filter (Remove all allowed access modifiers)
- Don't Filter (Allowing All Access Modifiers)
- Change its [allowed access modifiers](../../features/ProfilingDataFiltering.md#access-modifiers) (Under Advanced)

Change the grouping by:
- Add to the parent object (e.g. the function will be added to its class rendering object.)
- Seperate into children (e.g. a class will seperate itself into the functions.)
- Collect all children (e.g. a already rendered class will collect all seperated functions rendered.)

## Threads and Coloring
![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRenderingThreads.png](../../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRenderingThreads.png)

{% include Rendering/ThreadsAndColoring.md %}

## Settings Window
![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRenderingSettings.png](../../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRenderingSettings.png)

Most of the settings are quite self explainitory.

You can choose to save these settings as your new default for new renders or only for this render.

# Application Breadcrumbs
- { All paths leading to } /  [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 



# See Also:
- [Realtime Call Tree Rendering](CallTreeRendering.md)
- [Realtime Call Stack Rendering](CallStackRendering.md)
