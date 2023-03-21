---
title: View - Application Instance - Call Stack Rendering
description: The rendering of the call stack grouped by the specified data type, like class or namespace.
---
# Realtime Call Stack Rendering
![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png](../../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png)

{% include Rendering/RealtimeRenderingCallStackHeader.md  isException=false %}


## Toolbar
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png)

With the toolbar you can do the following:


- Select what [filter](../../features/ProfilingDataFiltering.md) tyoe you want to use for filtering
    - Current Filters
    - Start Filters, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFilterType.md)
    - No Filter, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFilterType.md)
- [Filter](../../features/ProfilingDataFiltering.md) the current rendered items
- Clear the current render screen
- Reposition screen to default zoom and position 
- Selecting the object type new rendered items will be grouped by.
- Forcing all rendered items to be grouped by the selected object type.
- Open the [Settings window](#settings-window)

## Item Context Menu
{% include Rendering/RealtimeRenderingCodeMemberContextMenu.md %}

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
- [(Deprecated) Realtime Grouped Call Stack Rendering](GroupedCallStackRendering.md)
