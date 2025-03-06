---
title: View - Application Instance - Menu Bar
description: The menu bar of the main application instance window.
---
# Menu Bar
![assets/img/ApplicationInstanceWindow/MenuBar.png](../../../assets/img/ApplicationInstanceWindow/MenuBar.png)

## File Menu
![assets/img/ApplicationInstanceWindow/FileMenu.png](../../../assets/img/ApplicationInstanceWindow/FileMenu.png)
### New Instance
Clicking here will bring up a sub-menu. Clicking on "Start new instance" will start the new instance and open a new [application instance window](../ApplicationInstanceDockWindow).

Double-clicking "New Instance" will directly start a new instance. 
### Open Instance
Shows a sub-menu with the other profiled instances of this application; clicking on them will open another [application instance window](../ApplicationInstanceDockWindow.md) of that instance.
### Main Menu Window
Opens or brings the [main menu window](../mainwindow.md) to the foreground.
### Application Settings
Opens or brings the [application settings window](../ApplicationSettingsWindow.md) to the foreground.
### Instance Settings 
Opens or brings the [application instance settings window](../ApplicationInstanceSettingsWindow.md) to the foreground.
### User & Client Settings
Opens or brings the [client & user settings window](../clientusersettingswindow.md) to the foreground
### Close
Closes this  [application instance window](../ApplicationInstanceDockWindow.md).
### Exit
Shuts down the [CodeGlass client](../../features/CodeGlassClient.md)
{% include alertNoTitle.html  type="warning" content="This does not cause the <a href=\"../../features/CodeGlassHub\" target=\"_blanc\">CodeGlass Hub</a> to be shutdown." %}

## View Menu
![assets/img/ApplicationInstanceWindow/ViewMenu.png](../../../assets/img/ApplicationInstanceWindow/ViewMenu.png)
### Main
Opens the [main](MainWindow.md) window in a new tab or brings the tab to the foreground   

### Console
See [Roadmap - Remote Console](../../Roadmap/RemoteConsole.md)

### Statistics
Opens the [statistics](StatisticsWindow.md) window in a new tab or brings it to the foreground   

### Memory Statistics
Opens the [memory statistics](MemoryStatisticsWindow) window in a new tab or brings it to the foreground.

### Code Heat Map
This button opens a [code heat map](CodeHeatMap.md) in a new tab.

### Call Tree 
This button opens the [realtime call tree rendering](CallTreeRendering.md) in a new tab.

### Call Stack 
This button opens the [realtime call stack rendering](CallStackRendering.md) in a new tab.

### Performance
Opens the [performance](PerformanceView.md) view in a new tool window or brings it to the foreground   

### Thread Explorer
Opens the [thread Explorer](ThreadExplorer.md) in a new tool window or brings it to the foreground   

### Application Explorer
Opens the [application explorer](ApplicationExplorer.md) in a new tool window or brings it to the foreground   

### Exceptions Explorer
Opens the [exceptions explorer](ExceptionExplorer.md) in a new tool window or brings it to the foreground.

### GC Invocations Explorer
Opens the [GC invocations explorer](GCInvocationsExplorer.md) in a new tool window or brings it to the foreground.

## Process menu
![assets/img/ApplicationInstanceWindow/ProcessMenu.png](../../../assets/img/ApplicationInstanceWindow/ProcessMenu.png)

### Start
[Starts](../../features/ApplicationInstanceExecutionControl.md#start) the application if it is not already.

### Continue
[Continues](../../features/ApplicationInstanceExecutionControl.md#resume) the application when it is paused.

### Break
[Pauses](../../features/ApplicationInstanceExecutionControl.md#pause) the application when it is running or stops [stepping](../../features/ApplicationInstanceStepping.md).

### Stop
[Stops](../../features/ApplicationInstanceExecutionControl.md#stop) the application if it is not stopped yet.

### Restart
[Restarts](../../features/ApplicationInstanceExecutionControl.md#restart) the application.

### Throttle

![assets/img/ApplicationInstanceWindow/ProcessMenuThrottle.png](../../../assets/img/ApplicationInstanceWindow/ProcessMenuThrottle.png)

Double clicking [throttle](../../features/ApplicationInstanceExecutionControl.md#throttle) on the main menu will enable or disable the throttling.

{% include ExecutionControl/ThrottleContextMenu.md %}

### Console
![assets/img/ApplicationInstanceWindow/ProcessMenuConsole.png](../../../assets/img/ApplicationInstanceWindow/ProcessMenuConsole.png)

Create, attach a new console to the application, and close the old one if it had one.
- Show, shows the console if it had one.
- Hide, hide the console if it had one.
- Console Settings, opens or brings the console settings to the foreground.

## Bring to Front
It brings the application to the front, if it is still running.


### Step Into 
[Steps into](../../features/ApplicationInstanceStepping.md#step-into) (F11) the next function while the application is paused

### Step Back Into 
[Steps back into](../../features/ApplicationInstanceStepping.md#step-back-into) (Ctrl + F11) the previous function while the application is paused

### Step Over 
[Steps over](../../features/ApplicationInstanceStepping.md#step-over) (F10) the next function while the application is paused

### Step Back Over 
[Steps back over](../../features/ApplicationInstanceStepping.md#step-back-over) (Ctrl + F10) the previous function while the application is paused

### Step Out 
[Steps out](../../features/ApplicationInstanceStepping.md#step-out) (Shift + F11) the current function while the application is paused

### Step Back Out 
[Steps back out](../../features/ApplicationInstanceStepping.md#step-back-out) (Ctrl + Shift + F11) the current function back to before the current function was called while the application is paused

### Instance Settings
Opens or brings the [application instance settings window](../ApplicationInstanceSettingsWindow.md) to the foreground

## Help Menu
![assets/img/ApplicationInstanceWindow/AppInstanceHelpMenu.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceHelpMenu.png)

### View Help
Opens this website on the [getting help](../../Troubleshooting.md#getting-help) page.

### Send Feedback
Opens this website on the [sending feedback](../../Troubleshooting.md#sending-feedback) page.

### Get Support
Opens this website on the [getting support](../../Troubleshooting.md#getting-support) page.


### Online Privacy Statement
Opens this website on the [privacy statement](../../Legal/Privacy.md) page.

### Check for updates
Opens the [releases page](https://github.com/CodeGlassDotIO/CodeGlassDotIO/releases){:target="_blank"}

### About CodeGlass
Opens this website on the [about page](../../../pages/about.md)
