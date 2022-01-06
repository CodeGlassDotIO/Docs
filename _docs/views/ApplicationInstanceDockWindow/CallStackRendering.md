---
title: View - Application Instance - Realtime Call Stack Rendering
description: The realtime rendering of the call stack.
---
# Realtime Call Stack Rendering
![assets/img/ApplicationInstanceWindow/RealtimeCallStackRendering.png](../../../assets/img/ApplicationInstanceWindow/RealtimeCallStackRendering.png)

{% include Warnings/RenderingPhotosensitivityWarning.html  %}

{% include alertNoTitle.html  type="warning" content="This view might be retired in future versions as <a href=\"GroupedCallStackRendering\">Grouped Call Stack Rendering</a> grouped by function gives nearly the same view." %}


See [Feature - Realtime call stack Rendering](../features/RealtimeRendering.md#realtime-call-stack-rendering) for more information about the feature.

Hovering over an item will show you information about the Last and current threads using that function.

Hovering over a line will show you where it comes from and where it goes to. 

Right click on an item will open the [Context Menu](#item-context-menu).

Double clicking or with the conext menu of an item will open the [Function Detail View](CodeMemberDetailsView.md) of that item.

{% include alertNoTitle.html  type="info" content="You can improve the rendering performance in the <a href=\"#settings-window\">Settings Window</a>." %}
{% include alertNoTitle.html  type="warning" content="This render now does have quite an impact on profiling performance, this will be improved in future releases, like <a href=\"GroupedCallStackRendering\">Grouped Call Stack Rendering</a> does not have such an impact." %}

{% include Rendering/RealtimeRenderingCodeMemberToolbar.md %}

{% include Rendering/RealtimeRenderingCodeMemberContextMenu.md %}

## Threads and Coloring
![assets/img/ApplicationInstanceWindow/RealtimeCallStackRenderingThreads.png](../../../assets/img/ApplicationInstanceWindow/RealtimeCallStackRenderingThreads.png)

{% include Rendering/ThreadsAndColoring.md %}

{% include Rendering/RenderingSettings.md %}

# Application Breadcrumbs
- { All paths leading to } /  [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 



# See Also:
- [Realtime Call Tree Rendering](CallTreeRendering.md)
- [Realtime Grouped Call Stack Rendering](GroupedCallStackRendering.md)