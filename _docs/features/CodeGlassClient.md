---
title: Feature - CodeGlass Client
description: The UI Of CodeGlass.
---

# CodeGlass Client

CodeGlass is designed from the ground up for remote profiling and language independence. To achieve this, it is composed of multiple components:
- CodeGlass Client
- [CodeGlass Hub](CodeGlassHub.md)
- [CodeGlass Profilers](CodeGlassProfilers.md)

The **CodeGlass Client** is a lightweight UI responsible for managing [profilers](CodeGlassProfilers.md) and visualizing data received from the [CodeGlass Hub](CodeGlassHub.md). Its modular design enables future extensions, such as a web-based interface.

Through the Client, you can initiate profiling for any of the [supported runtimes](supportedruntimes.md) that have been registered with the [Hub](CodeGlassHub.md), regardless of whether they were registered by the local machine or a [remote](CodeGlassHub.md#remote-hub) client.

The current implementation is a WPF-based desktop application. A prototype of a web-based client also exists and may be released in the future.

# See Also:
- [Feature - CodeGlass Hub](CodeGlassHub.md)
- [Feature - CodeGlass Profilers](CodeGlassProfilers.md)
- [Feature - Supported Runtimes](supportedruntimes.md)
