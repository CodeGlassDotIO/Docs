---
title: View - Application Instance - Realtime Call Tree Rendering 
description: The realtime rendering of the call tree.
---
# Realtime Call Tree Rendering
![assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering.png](../../../assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering.png)

{% include Warnings/RenderingPhotosensitivityWarning.html  %}


See [Feature - Realtime call tree Rendering](docs/features/RealtimeRendering.md#realtime-call-tree-rendering) for more information about the feature.

Hovering over an item will show you information about the Last or current thread using that function.

Hovering over a line will show you where it comes from and where it goes to. 

Right click on an item will open the [Context Menu](#item-context-menu).

Double clicking or with the conext menu of an item will open the [Function Detail View](CodeMemberDetailsView.md) of that item.

{% include alertNoTitle.html  type="info" content="You can improve the rendering performance in the <a href=\"#settings-window\">Settings Window</a>." %}
{% include alertNoTitle.html  type="warning" content="This render now does have quite an impact on profiling performance, this will be improved in future releases, like <a href=\"GroupedCallStackRendering\">Grouped Call Stack Rendering</a> does not have such an impact." %}

{% include Rendering/RealtimeRenderingCodeMemberToolbar.md %}

{% include Rendering/RealtimeRenderingCodeMemberContextMenu.md %}


## Threads and Coloring
![assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering3Threads.png](../../../assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering3Threads.png)

{% include Rendering/ThreadsAndColoring.md %}


{% include Rendering/RenderingSettings.md %}



# Application Breadcrumbs
- { All paths leading to } /  [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 

# See Also:
- [Realtime Call Stack Rendering](CallStackRendering.md)
- [Realtime Grouped Call Stack Rendering](GroupedCallStackRendering.md)
