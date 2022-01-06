---
title: Feature - Exceptions
description: The exception handling and collecting of CodeGlass
---
# Exceptions
This feature is still in its early stages but will expand much upon in the future; see [Improving Exceptions](../Roadmap/ImprovingExceptions.md) roadmap item for more information.

Currently, we have these functions:

## Collection of Exceptions
We currently collect any exceptions that occur in your application, even if you don't catch them. 
With the exception, we also collect the unrolled stack till it found a catch block and the [realtime collected callstack](RealtimeDataCollection.md), though this heavily depends on how you configured your [profiling data filters](ProfilingDataFiltering.md)

You can see this data in for example the following views:
- [Exception Explorer](../views/ApplicationInstanceDockWindow/ExceptionExplorer.md)
- [Exception Details View](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md)




## Pause execution on exception
You can specify that you want to pause the execution when specific exceptions happen.
This functionality will still be expanded much upon, see [Improving Exceptions](../Roadmap/ImprovingExceptions.md) for more information

You can configure these exceptions for example in the following views:
- [Appliations Profiler Settings](../views/ApplicationSettingsWindow/ProfilerSettings.md)
- [Client & User Profiler Settings](../views/clientusersettingswindow/profilingsettings.md)



### Limitations
- Currently, you can only specify these exceptions before an application starts; in the future, we will remove this limitation.


# See Also:
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)
- [Feature - Realtime profiling](RealtimeDataCollection.md)


