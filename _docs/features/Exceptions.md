---
title: Feature - Exceptions
description: The exception handling and collecting of CodeGlass
---

# Exceptions

This feature is still in its early stages and will be expanded significantly. See the [Improving Exceptions](../Roadmap/ImprovingExceptions.md) roadmap item for planned improvements.

Currently, the following functionality is available:

## Collection of Exceptions

CodeGlass captures all exceptions that occur within your application, including uncaught exceptions. For each exception, it collects:

- The unrolled stack trace up to the nearest catch block
- The [real-time collected call stack](RealtimeDataCollection.md#call-stack), if available

The level of detail in captured exceptions depends on your configured [profiling data filters](ProfilingDataFiltering.md).

![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png](../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png)

This data can be viewed in:
- [Exception Explorer](../views/ApplicationInstanceDockWindow/ExceptionExplorer.md)
- [Exception Details View](../views/ApplicationInstanceDockWindow/ExceptionDetailsView.md)

## Pause Execution on Exception

CodeGlass allows you to pause execution when specific exceptions occur. This enables early investigation and live debugging of critical error paths.

Configuration options for this feature are available in:
- [Application Profiler Settings](../views/ApplicationSettingsWindow.md)
- [Client & User Profiler Settings](../views/clientusersettingswindow.md)


### Limitations

- Exception pause settings must currently be configured before the application starts. This limitation will be removed in a future release.
- For future enhancements, see [Improving Exceptions](../Roadmap/ImprovingExceptions.md).

# See Also:
- [Feature - Execution Control](ApplicationInstanceExecutionControl.md)
- [Feature - Realtime profiling](RealtimeDataCollection.md)
