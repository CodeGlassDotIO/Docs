This view contains the general statistics of the profiled application.
The statistics are updated in real-time while the application is running.

In the toolbar, you have multiple buttons. Each of them are described below.
- Show [current application instance filters](../../features/ProfilingDataFiltering#application-instance-filters).
- Show [application instance start filters](../../features/ProfilingDataFiltering#application-instance-start-filters).
- Apply no filters.
- Collapse all items in the tree view.
- Open the [recording](../../views/applicationInstanceDockWindow/StatsRecordingView) menu.
- Toggle showing memory statistics in the tree view (this options is automatically enabled if you have memory profiling enabled).
- Force Garbage Collection allows you to force the garbage collection to run. (This option is grayed out if the integration does not support this feature.)

Below all these buttons, there is a search bar (Ctrl + F). Here you search for method using its name. When you select one of the suggestions, it will automatically expand the tree view until the searched method.

{% include Statistics/BasicStatisticsColumnExplaination.md %}