---
title: Feature - CodeGlass Hub
description: The central nervous system and brain of CodeGlass
---

# CodeGlass Hub

CodeGlass is designed from the ground up for remote profiling and language-agnostic analysis. As a result, it is composed of several components:
- [CodeGlass Client](CodeGlassClient.md)
- CodeGlass Hub
- [CodeGlass Profilers](CodeGlassProfilers.md)

The **CodeGlass Hub** acts as the central processing unit of the system. It ingests runtime data from connected [profilers](CodeGlassProfilers.md), processes it, and makes it accessible to [clients](CodeGlassClient.md) for analysis and visualization.

You can connect multiple profilers and clients to a single Hub, provided the host system has sufficient resources to handle the load.

## Remote Hub

The Hub does not need to run on the same machine as the application being profiled. Clients and profilers can connect remotely to the same Hub, allowing distributed workflows and collaborative analysis.

For best performance, we recommend running the profiler and the Hub on the same machine.

Remote connectivity enables shared access to profiling sessions—for example, multiple engineers can analyze the same data in real time from different machines.

Running the [Client](CodeGlassClient.md) on a separate machine from the Hub introduces negligible performance overhead.

> **Security Note:**  
> CodeGlass includes basic security mechanisms, but users should not rely on them for production-grade protection.  
> Treat remote Hubs as untrusted by default. We recommend:
> - Restricting access to a trusted local network
> - Using a VPN when operating across broader networks

## Local Hub

To keep your Hub instance local, simply block external access using your PC’s firewall.

# See Also:
- [Feature - CodeGlass Client](CodeGlassClient.md)
- [Feature - CodeGlass Profilers](CodeGlassProfilers.md)
