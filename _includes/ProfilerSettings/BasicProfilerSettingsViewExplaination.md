### Application Start Settings
Settings used at the start of the application instance can not be changed after the application instance has started.

- Disable all code optimizations
- Disable all function inlining
- Pause at the start, pauses the application before it ran any [not filtered](../../features/ProfilingDataFiltering) code.
- Additional Arguments, the set of command-line arguments to use when starting the application
- Memory profiling

Keep in mind that currently, with [Visual Studio solution runtime]({{site.baseurl}}/docs/features/supportedruntimes#visual-studio-solution), additional Arguments are supplied to the Visual Studio Process (devenv.exe) process, not to the process you are debugging with Visual Studio.
If you require CodeGlass to supply it to the debugging process let us know by filing an [issue on github](({{site.baseurl}}/docs/pages/contact.md#github)).

### Console Settings
These are the [console]({{site.baseurl}}/docs/features/AttachConsole) settings that you can attach to the application if it does not have one.

- Create a console, attach a console to the application if it does not have one.
- Force Console attaches a new console to the application, even if it has one.
- Hide Console, hides the (newly attached) console of the application.
- Disable quick edit mode, disables text selection on the console of the application (as this causes the application to freeze)
- Disable Line input mode, disables being able to type/give input in the application console.  
- Minimal buffer size, sets the buffer size of the console



### Exception Settings
- Pause while exception search, pauses the application while the catcher of an exception is searched, useful for exceptions that are caused by racing conditions. 
- Exceptions to pause execution on, a list to specify which exceptions CodeGlass should automatically pause execution. (Press Enter or delete inside the text block to add or remove items.)
- Maximum exception history, the number of exceptions it stores before deleting the oldest one. 
- Include call stack, If it should include the [collected callstack]({{site.baseurl}}/docs/features/RealtimeDataCollection) with the exception.
- Include all threads call stack; if it should include the [collected callstack]({{site.baseurl}}/docs/features/RealtimeDataCollection) of all threads, useful for exceptions that are caused by racing conditions.
- Include call stack history; if it should include the  [collected callstack]({{site.baseurl}}/docs/features/RealtimeDataCollection) history, with this, you can see what led to the exception.
<!-- - Pop call stack queue; When enabled (Recommended), it pops all items in the stepping queue and unprocessed call stack items before including the callstack to ensure we have the complete callstack.  -->

The estimate of minimal memory usage shows how much memory the current exception settings can cost; for example, including call stack history can cost a large amount of memory.


### CallStack Settings
How many call stack items are stored before removing the oldest one; this impacts how much [stepping backwards](../../features/ApplicationInstanceStepping) you can do.
It shows an estimate of how much memory it costs to store it.