---
title: Roadmap - Advanced Rendering Filters
description: Specific rendering needs.
doNotShow: false
---
{% include Warnings/RoadmapWarning.html %}

# Advanced Rendering Filters

At CodeGlass we want to implement more advanced rendering filters.

## Function Specific Rendering
We want to implement a way to filter everything not belonging to a specific function so it becomes possible to fully trace said function.


## Thread Specific Rendering

### Thread Details Rendering
Currently you only see a [textual call stack](../views/ApplicationInstanceDockWindow/ThreadDetailsView.md) of a specific thread, we want to add rendering to this like the [other renderers](../features/RealtimeRendering.md), which also shows you the history of the thread.


### Thread separated rendering
We want to make another [render type](../features/RealtimeRendering.md#render-types), one that is like [call tree rendering](../features/RealtimeRendering.md#realtime-call-tree-rendering) but fully separated by thread, so even when it is called from the same root it will still be separated. 

# See Also:
- [View - Thread Details](../views/ApplicationInstanceDockWindow/ThreadDetailsView.md)
- [Feature - Realtime Rendering](../features/RealtimeRendering.md)