---
title: Roadmap - Disable Time Measurement While Profiling.
description: To increase performance when you do not need time based metrics.
---
{% include Warnings/RoadmapWarning.html %}

# Disable Time Measurement While Profiling.
We spend allot of time optimizing our pipeline between the [profilers](../features/CodeGlassProfilers.md) and [hub](../features/CodeGlassHub.md) so that CodeGlass has as little overhead as possible.

In this quest we noticed that disabling [measuring the time](../features/TimeMessurement.md) of each call would give an enormous performance boost.
We want to give the user the option to enable or disable time measurement when they are not interested in those statistics e.g. You are only interested in the realtime callstack.


# See Also:
- [Feature - Time Measurement](../features/TimeMessurement.md)
