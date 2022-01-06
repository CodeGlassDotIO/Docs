---
title: Feature - Profiling Snapshots
description: Snapshots of the current or previously profiled applications.
---
# Profiling Snapshots
In Code Glass you can make profiling snapshots of a (running) application instance or even other snapshots.
It creates a copy of all information Code Glass Collected so you can compare different states of the application.

You can even dump this information to a file to later reload (on a different [client](CodeGlassClient.md) / [hub](CodeGlassHub.md)) to replay that snapshot (By [realtime rendering](RealtimeRendering.md) and [stepping](ApplicationInstanceStepping.md) for example).


## Use cases
These are some examples how you can use this function. 

### Feature that used to work
You created a snapshot of a specific feature of your application. 
After an update that feature stats to fail, now you can replay that snapshot  to see what is different between the working state and current state.


### Only happens on specific PC.
Your application failes on a specific pc, like one of a customer.
You create a snapshot of the appliation on their pc and then takes that snapshot to your pc and compare what your pc does and their snapshot. 

You can also read the above as the famous "it works on my pc" one. 


# Views using this feature
 - [Application Instance - Toolbar](../views/ApplicationInstanceDockWindow/Toolbar.md#snapshots)
 - [Main Menu - Applications ](../views/mainwindow/application.md)
 - [Main Menu - Application Instances](../views/mainwindow/applicationinstance.md)
 
# See Also:
- [Feature - Code Glass Client](CodeGlassClient.md)
- [Feature - Code Glass Hub](CodeGlassHub.md)
- [Feature - Realtime Rendering](RealtimeRendering.md)
- [Feature - Stepping](ApplicationInstanceStepping.md)


