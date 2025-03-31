---
title: Feature - Profiling Snapshots
description: Snapshots of the current or previously profiled applications.
---
# Profiling Snapshots
In CodeGlass you can make profiling snapshots of a (running) application instance or even other snapshots.
It creates a copy of all information CodeGlass collected so you can compare different states of the application.

You can even dump this information to a file to later reload (on a different [client](CodeGlassClient.md) / [hub](CodeGlassHub.md)) to replay that snapshot (By [realtime rendering](RealtimeRendering.md) and [stepping](ApplicationInstanceStepping.md) for example).


## Use Cases
Below are some examples how you can use this function. 

### Feature That Used to Work
You created a snapshot of a specific feature of your application. 
After an update that feature starts to fail, now you can replay that snapshot to see what is different between the working state and current state.


### Issue Only Happens on Specific PC.
Your application fails on a specific pc, like on one of a customer.
You create a snapshot of the application on their pc and then take that snapshot to your pc. There you compare what your pc does with their snapshot. 

You can also read the above as the famous "it works on my pc" one. 


# Views using this feature
 - [Application Instance - Toolbar](../views/ApplicationInstanceDockWindow/Toolbar.md#snapshots)
 - [Main Menu - Applications ](../views/mainwindow/application.md)
 - [Main Menu - Application Instances](../views/mainwindow/applicationInstance.md)
 
# See Also:
- [Feature - CodeGlass Client](CodeGlassClient.md)
- [Feature - CodeGlass Hub](CodeGlassHub.md)
- [Feature - Realtime Rendering](RealtimeRendering.md)
- [Feature - Stepping](ApplicationInstanceStepping.md)


