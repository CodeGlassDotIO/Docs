---
title: View - Application Instance - GC Invocations Details View
description: The details of a specific garbage collection invocation
---

# GC Invocations Details View
![assets/img/ApplicationInstanceWindow/GarbageCollectionInvokedWindow.png](../../../assets/img/ApplicationInstanceWindow/GarbageCollectionInvokedWindow.png)

{% include alert.html  type="warning" title="Experimental Feature" content="This feature is still very experimental, though it is available in all <a href=\"../../Editions\" >editions</a>, for more info see the the <a href=\"../../features/GarbageCollection\" >garbage collection invocations feature</a> description." %}

{% include alert.html  type="warning" title="Limited support" content="At this point the only language to support this feature is Julia, but more will be added soon." %}

This feature allows you to gain insights into what your application does during garbage collection. This can help you track down objects that do not get removed or find objects that get removed to fast.

## Garbage Collection Statistics
Besides seeing all the garbage collections that have happened, you can also view what happened during the garbage collection. The following pieces of information are available:
- The method that was being executed when the garbage collection was triggered.
- The type of the object that was being allocated when garbage collection was triggered.
- The amount of time the garbage collection took.
- The amount of bytes that were freed by the garbage collection.
- Every object that was deallocated, including the method that originally allocated that object.