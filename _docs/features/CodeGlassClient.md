---
title: Feature - CodeGlass Client
description: The UI Of Code Glass.
---
# CodeGlass Client

CodeGlass is from the ground up designed for remote profiling and to support any language, because of this, Code Glass excists out of multiple parts:
- Code Glass Client
- [Code Glass Hub](CodeGlassHub.md)
- [Code Glass Profilers](CodeGlassProfilers.md)

The Code Glass Client is nothing more than a light weight UI to manage the Code Glass [proflers](CodeGlassProfilers.md) and display the data of the [Code Glass Hub](CodeGlassHub.md), this allows us to easily adapt other clients, like a web interface, in the future.

From the Client you can start profiling any of the [supported runtimes](supportedruntimes.md) that are registered to the [hub](CodeGlassHub.md) by any connected ([remote](CodeGlassHub.md#remote-hub)) clients, not specifically by the current client or the current machine.

Our current implementation is a WPF based desktop application but we already have a few prototype clients that we might release in the future, like one for the Hololens (Unity) or for visual studio (VSIX)


# See Also:
- [Feature - Code Glass Hub](CodeGlassHub.md)
- [Feature - Code Glass Profilers](CodeGlassProfilers.md)
- [Feature - Supported Runtimes](supportedruntimes.md)
