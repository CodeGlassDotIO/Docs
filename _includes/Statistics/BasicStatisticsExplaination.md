This view contains the general statistics of the profiled application by namespace, classes, methods, etc.
The statistics are updated in real-time while the application is running.

In the toolbar, you have multiple options; the first 3 define what data you want to see. The options are:
- [current application instance filters](../../features/ProfilingDataFiltering#application-instance-filters)
- [application instance start filters](../../features/ProfilingDataFiltering#application-instance-start-filters)
- Show all, CodeGlass will apply no filter.

Next to that, you also have to option to collapse all items in the tree view.<br/>
Next to that one there is the button to start making snapshots. <br/>
The last button is used to enable or disable showing memory statistics in the statistics window (this options is automatically enabled if you have memory profiling enabled).

Below all these buttons, there is a search bar. Here you search for method using its name. When you select one of the suggestions, it will automatically expand the tree view until the searched method.

{% include Statistics/BasicStatisticsColumnExplaination.md %}