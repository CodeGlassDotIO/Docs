---
title: Feature - Interaction Tracking
description: The tracking of interactions that happened in your application
---

# Interaction Tracking
This feature allows you to easily see key interactions that occurred in your application. An interaction can be multiple things. An interaction can be something like an event but it can also be an API endpoint that was called, etc. At this point we only support the tracking of events but tracking of other interactions like an API call will be added soon.

{% include alert.html  type="warning" title="Limited support" content="At this point the only language to support this feature is C#, but more will be added soon." %}

If you have the execution of your application paused, you can click on these interactions and have CodeGlass move your callstack to the point that this interaction occurred. This way you can quickly see what the user did and start following all the functions from there.
