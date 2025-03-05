---
title: Feature - Exceptions
description: The exception handling and collecting of CodeGlass
---
# Exceptions
This feature is still in its early stages but we will expand much upon in the future; see [Improving Exceptions](../Roadmap/ImprovingExceptions.md) roadmap item for more information.

Currently, we do have these functions:

## Collection of Exceptions
CodeGlass captures all exceptions that occur in your application, even if they are not caught.
Along with the exception, we collect the unrolled stack trace up to the nearest catch block, as well as the [real-time collected callstack](RealtimeDataCollection.md#call-stack). However, the level of detail depends on how you have configured your [profiling data filters](ProfilingDataFiltering.md).

![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png](../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png)

You can see this data in the following views:
- [Exception Explorer](../views/ApplicationInstanceDockWindow/ExceptionExplorer.md)
- [Exception Details View](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md)

## Pause Execution on Exception
You can configure CodeGlass to pause execution when specific exceptions occur.
This feature will be further enhanced in future updates. For more details, see [improving exceptions](../Roadmap/ImprovingExceptions.md).

You can configure these exceptions in the following views:
- [Applications Profiler Settings](../views/ApplicationSettingsWindow/ProfilerSettings.md)
- [Client & User Profiler Settings](../views/clientusersettingswindow/profilingsettings.md)



### Limitations
- Currently, you can only specify these exceptions before an application starts; in the future, we will remove this limitation.


# See Also:
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)
- [Feature - Realtime profiling](RealtimeDataCollection.md)


