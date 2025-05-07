---
title: Feature - Time Measurement
description: How CodeGlass Measures time.
---

# Time Measurement

CodeGlass measures time using hardware-level ticks. A tick is the smallest unit of time measurement available on standard PCs without specialized hardware.

The duration of a tick may vary per CPU and can change each time the system starts. You can view the tick duration for a specific application instance in the [Application Instance Information](../views/ApplicationInstanceSettingsWindow.md#tick-duration) view.

> **Note:**  
> This is not the same as [.NET's DateTime.Ticks](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.ticks). We use [low-level hardware clock ticks](https://docs.microsoft.com/en-us/windows/win32/sysinfo/acquiring-high-resolution-time-stamps#low-level-hardware-clock-characteristics).

For simplicity, assume one tick equals 100 nanoseconds (or 10,000 ticks per millisecond), which aligns with behavior under Hyper-V.

So:  
1 second = 1,000 milliseconds = 10,000,000 ticks

In statistics views such as the [Statistics Window](../views/ApplicationInstanceDockWindow/StatisticsWindow.md), time is displayed in the following format:  
`{days} {hours}:{minutes}:{seconds}.{milliseconds}.{ticks}`

## Accuracy and Overhead Removal

To ensure accuracy, CodeGlass removes the overhead caused by its own profiling operations wherever possible. This reduces time measurement inaccuracies to one tick or less. 

In fact, if we attempted to reduce the overhead further, we could end up reporting negative durations, which would suggest a function completed before it started.

Profiler overhead is excluded even during:
- [Stepping](ApplicationInstanceStepping.md)
- [Paused](ApplicationInstanceExecutionControl.md#pause) state
- Any [execution control](ApplicationInstanceExecutionControl.md) operation

## Current and Future Time Measurement Modes

Currently, we only support wall clock time. This means that if a thread is suspended by the system (not by CodeGlass), the suspended duration is still counted.

In the future, we plan to support more accurate modes such as [CPU clock time](../Roadmap/CpuClock.md), which excludes time when threads are not actively running on the CPU.

## Known Issues

- If your application runs longer than 100 years, the counter may roll over and cause undefined behavior. Please contact us in the year 2125 if this becomes a problem.

# See Also:
- [Roadmap - CPU Clock](../Roadmap/CpuClock.md)
- [Feature - Stepping](ApplicationInstanceStepping.md)
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)
- [View - Application Instance Information](../views/ApplicationInstanceSettingsWindow.md#information)
