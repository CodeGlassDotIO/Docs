---
title: Feature - Garbage Collection Invocations
description: The tracking of every executed garbage collection
---

# Garbage Collection Invocations

![assets/img/ApplicationInstanceWindow/GarbageCollectionInvokedWindow.png](../../assets/img/ApplicationInstanceWindow/GarbageCollectionInvokedWindow.png)

This feature provides insight into your application’s behavior during garbage collection. It can help you identify memory leaks (objects not being collected) or objects that are being collected too aggressively.

{% include alert.html  type="warning" title="Limited support" content="At this point the only languages to support this feature are Julia and .NET, but more will be added soon." %}

## Garbage Collection Invocations Explorer

The Garbage Collection Invocations Explorer displays all garbage collection rounds that occurred during the application's execution. This enables a quick assessment of whether your application is triggering more or fewer collections than expected.

## Garbage Collection Statistics

In addition to listing each garbage collection event, detailed metrics are provided for analysis:

- The method being executed when garbage collection was triggered
- The type of the object being allocated at the time of trigger
- The duration of the garbage collection event
- The number of bytes freed during the event
- A full list of deallocated objects, including the method responsible for their original allocation
