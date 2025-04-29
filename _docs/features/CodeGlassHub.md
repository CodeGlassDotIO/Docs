---
title: Feature - CodeGlass Hub
description: The central nervous system and brain of CodeGlass
---
# CodeGlass Hub
CodeGlass is from the ground up designed for remote profiling and to support any language, because of this CodeGlass exists out of multiple parts:
- [CodeGlass Client](CodeGlassClient.md)
- CodeGlass Hub
- [CodeGlass Profilers](CodeGlassProfilers.md)

The Hub is the brain of the application, it processes all the data send by the [profilers](CodeGlassProfilers.md) and prepairs that data for the [clients](CodeGlassClient.md).
You can connect as many profilers and clients to an hub, as long as your machine has the resources for it.

## Remote Hub
You are also not bound to run the hub on the same machine as the application you want to profiler. You can also connect clients and profilers from another machine to the same hub. 
However we highly suggest you run the profiler and hub on the same machine for performance reasons.

Connecting to a remote Hub makes it possible for you and a college can look together at the same profiling data, without having to sit on each others lap. 

The performance penalty for running your [client](CodeGlassClient.md) on another machine is negatable.

CodeGlass is not response for the security, we of course have some security implemented but for the sake of arguments just assume it is nothing. 
So it is up to the user to keep the remote hub safe, we recommend keeping access within a trusted local network and using a VPN when you want to go beyond that. 

## Local Hub
If you want to keep your hub local, the only thing you have to do is prevent access to it trough you PC's firewall. 

# See Also:
- [Feature - CodeGlass Client](CodeGlassClient.md)
- [Feature - CodeGlass Profilers](CodeGlassProfilers.md)



