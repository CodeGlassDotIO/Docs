---
title: Feature - Console
description: Attaching a new or opening the current console of the profiled application.
doNotShow: true
---
# Console
It is possible to attach a console to a running application, even if it is not a console application. <br/>
This is the first part of the road map item [Remote Console](../Roadmap/RemoteConsole.md).


## Functionality:
- Attach a console to a running application
- Show / Hide the console.
- Set Console buffer size.
- Prevent user input on a console.
- Prevent selection in console.


## Limitations
- This feature does not work for non console UWP applications, this is a limitation by Microsoft as it does not have access to the default output stream.



## Views using this feature
- [Application Instance - Menu - Process](../views/ApplicationInstanceDockWindow/MenuBar.md#console)
- [Application Settings - Profiler Settings Tab](../views/ApplicationSettingsWindow/ProfilerSettings.md#console-settings)
- [Client & User settings - Profiler settings Tab](../views/clientusersettingswindow/profilingsettings.md#console-settings)

# See Also:
- [Roadmap - Remote Console](../Roadmap/RemoteConsole.md)


