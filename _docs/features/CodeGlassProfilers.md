---
title: Feature - CodeGlass Profilers
description: The different supported data collection profilers of CodeGlass
---

# CodeGlass Data Collection Profilers

CodeGlass is built with remote profiling and cross-language support at its core. As such, the system is divided into multiple components:
- [CodeGlass Client](CodeGlassClient.md)
- [CodeGlass Hub](CodeGlassHub.md)
- CodeGlass Profilers

In the context of CodeGlass, **profilers** refer specifically to the **data collection** layer. They are responsible for gathering runtime telemetry from supported applications. All data processing is handled by the [Hub](CodeGlassHub.md), and visualization is performed in the [Client](CodeGlassClient.md).

For details on the runtimes currently supported, refer to [supported runtimes](supportedruntimes.md).

# See Also:
- [Feature - CodeGlass Hub](CodeGlassHub.md)
- [Feature - CodeGlass Client](CodeGlassClient.md)
- [Roadmap - Non .NET Profiler](../Roadmap/MoreRuntimeSupport.md)
