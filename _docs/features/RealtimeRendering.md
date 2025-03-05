---
title: Feature - Realtime Rendering
description: Realtime rendering of different kinds of data in CodeGlass
---
# Realtime Rendering

With CodeGlass you can visualize the data from the profiled application in realtime. CodeGlass provides three different views to visualize your data.
These [render types](#render-types) include:
- [Call Tree](#realtime-call-tree-rendering)
- [Call Stack](#realtime-call-stack-rendering)
- [Code Heat map](#realtime-code-heatmap)

{% include Warnings/RenderingPhotosensitivityWarning.html  %}

## Render Types
### Realtime Call Tree Rendering
![assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering.png](../../assets/img/ApplicationInstanceWindow/RealtimeCallTreeRendering.png)

See [View - Realtime Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md) or [View - Exception Call Tree Rendering](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md#exception-call-tree-view) for view specific information.
 
This rendering view gives you a look into the call tree of your application as it is running. Because the amount of data can sometimes be overwhelming, you can apply filters. These filters allow you to focus on the parts that really matter to you. More information about filters can be found here: [profiling data filters](ProfilingDataFiltering.md).

The rendering does also reflect [call stack steps](ApplicationInstanceStepping.md) that you might have made, forwards but also backwards! 

To differentiate different threads, CodeGlass gives every thread its own color. 
Every thread is assigned the most different color available. This is why the first 3 threads are red, green and blue (RGB). Then it will start using the most different shades of RGB and so forward.

This render view does not combine calls to the same function, like the [call stack rendering](#realtime-call-stack-rendering) would do, but instead separates them per root function.

So for example
```
Thread 1 (red)   has a call stack of: A() -> B() -> C()
Thread 2 (green) has a call stack of: B() -> C()
Thread 3 (blue)  has a call Stack of: A() -> D() -> C()
```

would result in render:
```
A() r-> B() r-> C()
|   b-> D() b-> C()
B() g-> C()
```

### Realtime Call Stack Rendering
![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png](../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRendering.png)

See [View - Realtime Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md) or [View - Exception Call Stack Rendering](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md#exception-call-stack-view) for view specific information.

This rendering view gives you a look into the call stack of your application as it is running. Because the amount of data can sometimes be overwhelming, you can apply filters. These filters allow you to focus on the parts that really matter to you. More information about filters can be found here: [profiling data filters](ProfilingDataFiltering.md).

The rendering does also reflect [call stack steps](ApplicationInstanceStepping.md) that you might have made, forwards but also backwards!

To differentiate different threads, CodeGlass gives every thread its own color. Every thread is assigned the most different color available. This is why the first 3 threads are red, green and blue (RGB). Then it will start using the most different shades of RGB and so forward.

Unlike the [call tree rendering](#realtime-call-tree-rendering) this rendering view does combine all the calls to the same function.

So for example
```
Thread 1 (red)   has a call stack of: A() -> B() -> C()
Thread 2 (green) has a call stack of: A() -> D() -> C()
Thread 3 (blue)  has a call Stack of: A() -> F() -> E()
```

would result in:
```
A() r-> B() 
|           rg-> C()
|   g-> D()
|   b-> F() b -> E();
```

### Realtime Code Heatmap
![assets/img/ApplicationInstanceWindow/CodeHeatMapWindow.png](../../assets/img/ApplicationInstanceWindow/CodeHeatMapWindow.png)


See [View - Realtime Code Heat map](../views/ApplicationInstanceDockWindow/CodeHeatMap.md) for view specific information.

This rendering view shows the statistics of your application in the form of a heat map.
In this view you can group and sort your data in multiple different ways.

For C# applications you can group the data by setting the `Object Type` option to one of the following values:
- Method
- Property
- Class
- Namespace
- Process

To change what type of statistics it should sort by you can change the `Statistics` value. You can choose from the following options:
- None
- Total Calls
- Total Call Duration
- Average Call Duration
- Active Calls
- Active Threads
- Longest Call
- Shortest Call


## Example Use cases
### Find racing conditions
To find racing conditions in your code using CodeGlass, you can use the [call stack rendering](#realtime-call-stack-rendering) view. By looking where two active threads cross each other when calling the same function you can get an idea of where the racing might be happening.

To see exactly what happened in your code, you can use [stepping](ApplicationInstanceStepping.md) to go forwards or backwards into the call stack of your application.


### Find why your application is slowing down or why it is unresponsive
By using the [call tree renderer](#realtime-call-tree-rendering) or the [call stack renderer](#realtime-call-stack-rendering) you can instantly see what code your application is running. This way you can find out what it is slowing down on what causes it to be unresponsive.

## Limitations
Currently non of the renderers show you where an exception was thrown. This is an feature that will be added in the future. To see all the exceptions that your application has thrown you can take a look at the [exception explorer](../views/ApplicationInstanceDockWindow/ExceptionExplorer).

## Views using this feature
- [View - Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
- [View - Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
- [View - Code heat map](../views/ApplicationInstanceDockWindow/CodeHeatMap.md)
