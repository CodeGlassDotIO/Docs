---
title: Roadmap - Thread Only Stepping
description: To only let a specific thread to step and keep the other threads paused.
---
{% include Warnings/RoadmapWarning.html %}

# Thread Only Stepping
Thread only steppings is only stepping a specific thread and keeping the other threads paused.

This feature was thought of when we made the original [Thread stepping](../features/ApplicationInstanceStepping.md#thread-stepping) which steps every thread till the specific thread stepped.
We decided not on implementing this as we did not see a good use-case. 

We also saw that it could causes many problems in the profiled application, like racing conditions.
However funny enough we then thought that could not be a bug but a feature for us, we could make a Test mode in Code Glass that automatically stops threads and let others run so you can check if your application is prone for that kind of issues like racing conditions.

This currently does not have a high priority on our roadmap but please let us know if you have high need or see more use cases in this!



# See Also:
- [Feature - Stepping](/docs/features/ApplicationInstanceStepping.md)
- [View - Thread Details](/docs/views/ApplicationInstanceDockWindow/ThreadDetailsView.md)