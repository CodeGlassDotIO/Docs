---
title: Feature - CodeGlass Hub
description: The central nervous system and brain of CodeGlass
---
# Code Glass Hub
Code Glass is from the ground up designed for remote profiling and to support any language, because of this Code Glass excists out of multiple parts:
- [Code Glass Client](CodeGlassClient.md)
- Code Glass Hub
- [Code Glass Profilers](CodeGlassProfilers.md)

The Hub is the brain of the application, it processes all the data send by [Profilers](CodeGlassProfilers.md) and prepairs that data for the [clients](CodeGlassClient.md).
You can connect as many profilers and clients to an hub that your machine has resources for.




## Remote Hub
You are also not bound to run the hub on the same machine, you can connect clients and profilers from another machine to the same hub. 
However we highly suggest you run the profiler and hub on the same machine for performance reasons.

This makes it possible for instance that you and a collega can look together to the same profiling data, without needing to sit on eachothers lap. 

The performance penality for running your [client](CodeGlassClient.md) on another machine is neglectable.

Code Glass is not response for the security, we ofcource have some security implemented but for the sake of arguments just assume it is nothing. 
So it is up to the user to keep the remote hub safe, we recommend keeping access within a trusted local network and using a VPN when you want to go beyond that. 

## Local Hub
If you want to keep your hub local, the only thing you have to do is prevent access to it trough you PC's firewall. 

# See Also:
- [Feature - Code Glass Client](CodeGlassClient.md)
- [Feature - Code Glass Profilers](CodeGlassProfilers.md)



