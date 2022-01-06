---
title: Roadmap - One Click run
description: To Run CodeGlass with one click, especially on remote hardware.
---
# One click Run solution
A one click run preconfigured Code Glass to profile a specific application with a set of [presets](Presets.md)

## Main reason of feature
Iliminate not reproducable issues

## Use case example
The customer calls that the app crashes when she tries to log in.
You try it on your machine and it does not happen.

You create a one click run with the login [preset](Presets.md) configuration in Code Glass.

Now you remote into the customer pc and copy the one click run to that pc, now you start the one click run and let the customer do the action that makes it crash.
Now you have a [snapshot file](../features/ProfilingSnapshots.md) with the information needed to rerun the issue on your own machine and find out where the problem is.
Especially when you can [automatically compare this snapshot](CompareProfilingSnapshots.md) with your own working one.


# See Also:
- [Feature - Profiling Snapshots](../features/ProfilingSnapshots.md)
- [Roadmap - Compare snapshots](CompareProfilingSnapshots.md)
- [Roadmap - Presets](Presets.md)
