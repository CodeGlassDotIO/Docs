---
title: View - Application Instance - Performance View
description: The performance graphs of the application instance window.
---
# Performance View
![assets/img/ApplicationInstanceWindow/AppInstancePerformanceView.png](../../../assets/img/ApplicationInstanceWindow/AppInstancePerformanceView.png)

The performance view shows you all kind of performance counters, currently they include:

- Profiled functions (/s).
- CPU (%)
- Memory (MB)
- Active Threads.

{% include alertNoTitle.html  type="info" content="The profiled functions value is calculated by the amount of calls and returns that happened and that divided by 2." %}

## Limitations
- [UWP](../../features/supportedruntimes.md#uwp) might not show you CPU or Memory, this is because of the nature of UWP having really limited access granted by Microsoft.

## Known Issues
- Currently it does not hide metric graphs that a runtimes not always supports (like UWP).

# Application Breadcrumbs
- [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 
