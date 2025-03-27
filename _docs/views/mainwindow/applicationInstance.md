---
title: View - Main Menu - Application Instances
description: All Previously run application instances or to start a new one.
---
# Application Instances
![assets/img/mainwindow/MainMenuAppInstances.png](../../../assets/img/MainMenu/MainMenuAppInstances.png)

On this view you see all the instances that were started since the [CodeGlass Hub](../../features/CodeGlassHub.md) started.
You can [view the profiled instance](../ApplicationInstanceDockWindow.md)  by double clicking on them or pressing on the "Open" button on the bottom right.

From this view it is also possible to [start a new instance](../ApplicationInstanceDockWindow.md), [remove the current application](#remove-application) and open the [application settings](../ApplicationSettingsWindow.md).

You can also add an application by the log file you created with the [profiling snapshots](../../features/ProfilingSnapshots.md) by pressing the "Add by log file" button.
If the new instance does not show up make sure that you used a log file from this application, you can check the [applications](application.md) to be sure.

You also see the placeholder button for [Roadmap - Attach To Running Applications](../../Roadmap/AttachToRunningApplication.md)

# Remove application
![assets/img/mainwindow/RemoveApplicationConfirmation.png](../../../assets/img/MainMenu/RemoveApplicationConfirmation.png)

When you press the "Remove Application" button you will get this confirmation window.

This window states that the application will first be archived and removed after the [CodeGlass Hub](../../features/CodeGlassHub.md) restarts. <br/>
This is to ensure data integrity, the full removal of the application data and prevent unexpected behavior if others are logged in into the same hub and profiling that application.


# Application Breadcrumbs: 
- [Splashscreen](../Splashscreen.md) / [Main Menu - Applications](application.md) /


# See Also:
 - [Main Window ](../mainwindow.md)
 - [Applications ](application.md)
 - [Client and user settings](../clientusersettingswindow.md)
 - [Application settings](../ApplicationSettingsWindow.md)