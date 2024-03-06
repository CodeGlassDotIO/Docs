---
title: Roadmap - Disable Time Messurment while profiling.
description: To Increase performance when you do not need time based metrics.
---
{% include Warnings/RoadmapWarning.html %}

# Disable Time Messurment while profiling.
We spend allot of time optimizing our pipeline between the [profilers](../features/CodeGlassProfilers.md) and [hub](../features/CodeGlassHub.md) so that code glass has as little overhead as possible.

In this Quest we noticed that disabling [messuring the time](../features/TimeMessurement.md) of each call would give an enourmous performance boost.
We want to give the user the option to enable or disable time messurment when they are not interested in those statistics e.g. You are only interested in the realtime callstack.


# See Also:
- [Feature - Time Messurement](../features/TimeMessurement.md)
