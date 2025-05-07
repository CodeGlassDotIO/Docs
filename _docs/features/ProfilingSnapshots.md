---
title: Feature - Profiling Snapshots
description: Snapshots of the current or previously profiled applications.
---

# Profiling Snapshots

CodeGlass allows you to create profiling snapshots of a running application instance, or even from existing snapshots. A snapshot captures all runtime data collected by CodeGlass at that moment, enabling side-by-side comparisons of different application states.

Snapshots can be exported to `.cgf` files, which can later be loaded on another [client](CodeGlassClient.md) or [hub](CodeGlassHub.md). This allows for detailed offline analysis using features like [realtime rendering](RealtimeRendering.md) and [stepping](ApplicationInstanceStepping.md).

Snapshot files can be associated with CodeGlass via the [Client Settings](../views/clientusersettingswindow.md#client-settings), making them directly openable from your file explorer.

## Use Cases

### Feature That Used to Work

Create a snapshot when a specific feature is working correctly. If the feature breaks after a change, you can replay the earlier snapshot to identify differences in control flow or memory usage between the working and broken versions.

### Issue Only Happens on a Specific PC

If an issue only reproduces on a specific machine, such as a customer's system, you can create a snapshot on that device and analyze it on your own machine. Compare its runtime behavior with your local execution to uncover environment-specific issues.

In other words, this is your tool for debugging the classic _"It works on my machine."_ problem.

# Views Using This Feature

- [Application Instance - Toolbar](../views/ApplicationInstanceDockWindow/Toolbar.md#snapshots)  
- [Main Menu - Applications](../views/mainwindow/application.md)  
- [Main Menu - Application Instances](../views/mainwindow/applicationInstance.md)

# See Also:
- [Feature - CodeGlass Client](CodeGlassClient.md)  
- [Feature - CodeGlass Hub](CodeGlassHub.md)  
- [Feature - Realtime Rendering](RealtimeRendering.md)  
- [Feature - Stepping](ApplicationInstanceStepping.md)
