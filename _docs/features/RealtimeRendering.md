---
title: Feature - Realtime Rendering
description: Realtime rendering of different kinds of data in CodeGlass
---

# Realtime Rendering

CodeGlass allows you to visualize profiling data from a running application in real time. There are three primary rendering views available:
- [Call Tree](#realtime-call-tree-rendering)
- [Call Stack](#realtime-call-stack-rendering)
- [Code Heat Map](#realtime-code-heatmap)

{% include Warnings/RenderingPhotosensitivityWarning.html %}

## Render Types

### Realtime Call Tree Rendering

![assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering.png](../../assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering.png)

See [View - Realtime Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md) or [View - Exception Call Tree Rendering](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md#exception-call-tree-view) for view-specific details.

This view displays the live call tree of your application. Because the volume of data can be large, filters can be applied to help narrow your focus. See [profiling data filters](ProfilingDataFiltering.md) for configuration guidance.

The rendering reflects [call stack steps](ApplicationInstanceStepping.md), including forward and backward navigation.

Each thread is assigned a distinct color, starting with red, green, and blue. Subsequent threads use increasingly different shades to ensure clarity. For thread-color mapping details, refer to [Threads and Coloring](../views/ApplicationInstanceDockWindow/CallTreeRendering.md#threads-and-coloring).

This view does not merge calls to the same function. Instead, it separates them by root function.

Example:

```

Thread 1 (red)   → A() → B() → C()
Thread 2 (green) → B() → C()
Thread 3 (blue)  → A() → D() → C()

```

Renders as:

```

A() r→ B() r→ C()
|   b→ D() b→ C()
B() g→ C()

```

### Realtime Call Stack Rendering

![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png](../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png)

See [View - Realtime Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md) or [View - Exception Call Stack Rendering](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md#exception-call-stack-view) for more information.

This view displays the live call tree of your application. Because the volume of data can be large, filters can be applied to help narrow your focus. See [profiling data filters](ProfilingDataFiltering.md) for configuration guidance.

The rendering reflects [call stack steps](ApplicationInstanceStepping.md), including forward and backward navigation.

Each thread is assigned a distinct color, starting with red, green, and blue. Subsequent threads use increasingly different shades to ensure clarity. For thread-color mapping details, refer to [Threads and Coloring](../views/ApplicationInstanceDockWindow/CallTreeRendering.md#threads-and-coloring).

This view also displays the live call stack, but unlike the call tree, it groups repeated calls to the same function.

Example:

```

Thread 1 (red)   → A() → B() → C()
Thread 2 (green) → A() → D() → C()
Thread 3 (blue)  → A() → F() → E()

```

Renders as:

```

A() r→ B()
|          rg→ C()
|   g→ D()
|   b→ F() b→ E()

```

### Realtime Code Heatmap

![assets/img/ApplicationInstanceWindow/CodeHeatMapWindow.png](../../assets/img/ApplicationInstanceWindow/CodeHeatMapWindow.png)

See [View - Realtime Code Heat Map](../views/ApplicationInstanceDockWindow/CodeHeatMap.md) for configuration and usage.

This view presents statistical data in a heat map format. You can group and sort data in several ways.

For C# applications, group by:
- Method
- Property
- Class
- Namespace
- Process

Sort by:
- None
- Total Calls
- Total Call Duration
- Average Call Duration
- Active Calls
- Active Threads
- Longest Call
- Shortest Call

## Example Use Cases

### Find Race Conditions

Use the [call stack rendering](#realtime-call-stack-rendering) view to identify when multiple active threads enter the same function. This can help pinpoint areas in your code where race conditions may occur.

Navigate the execution flow with [stepping](ApplicationInstanceStepping.md) to understand the exact sequence of operations.

### Identify Performance Bottlenecks or Unresponsiveness

Use either the [call tree renderer](#realtime-call-tree-rendering) or the [call stack renderer](#realtime-call-stack-rendering) to identify which parts of your application are currently executing. This makes it easier to identify slow or unresponsive code paths.

## Limitations

Currently, none of the rendering views indicate where exceptions were thrown. This feature is planned for a future update. For now, use the [Exception Explorer](../views/ApplicationInstanceDockWindow/ExceptionExplorer.md) to view exception details.

## Views Using This Feature

- [View - Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
- [View - Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
- [View - Code Heat Map](../views/ApplicationInstanceDockWindow/CodeHeatMap.md)
