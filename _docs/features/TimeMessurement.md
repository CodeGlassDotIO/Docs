---
title: Feature - Time Measurement
description: How CodeGlass Measures time.
---
# Time Measurement
We measure time in our application in Ticks; this is the smallest amount of time measurement you can currently get on a pc without specialized hardware.

How long a tick might differ per CPU and vary each time you start your PC.
You can see how long a tick is for each application instance in [view - application instance information](/docs/views/ApplicationInstanceSettingsWindow/Information.md#tick-duration)


Take note we are not talking about [DateTime.Ticks](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.ticks) but we are talking about [low-level hardware clock ticks](https://docs.microsoft.com/en-us/windows/win32/sysinfo/acquiring-high-resolution-time-stamps#low-level-hardware-clock-characteristics)

But to simplify this page, let's state a tick is 10.000th of an ms (100 nanoseconds), which it also is when running under Hyper-V.<br/>
So 1s = 1000ms = 10.000.000 ticks.

In our statistics (like in [view - Statistics](../views/ApplicationInstanceDockWindow/StatisticsWindow.md)) you will see these ticks, but most of the statistics are formatted like the following: <br/>
{days} {hour}:{minutes}:{seconds}.{miliseconds}.{ticks} 


While profiling, we remove the time caused by our profilers as much as possible; this causes the inaccuracy of our time metrics to be Lower or equal to one tick.
Because it can be lower than one tick, we cannot remove any more; the metrics else may state that a function finished before it started.

We also remove this overhead while you are [stepping](ApplicationInstanceStepping.md), [paused](ApplicationInstanceExecutionControl.md#pause) or do any other [execution control](ApplicationInstanceExecutionControl.md) to give you the best metrics possible.

Currently, we only support wall clock; this means that if a thread is suspended (not by CodeGlass), it will still include the time the thread was suspended.

We will support other time measurements like [CPU clock](/docs/Roadmap/CpuClock.md) in the future.

## Known Issues
- If your applications run longer than 100 years, the counter will roll over and may cause unexpected behavior; please get in touch with us in 2122  if this starts happening  ;).



# See Also:
- [Roadmap - CPU Clock](../Roadmap/CpuClock.md)
- [Feature - Stepping](ApplicationInstanceStepping.md)
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)
- [View - application instance information](../views/ApplicationInstanceSettingsWindow/Information.md)