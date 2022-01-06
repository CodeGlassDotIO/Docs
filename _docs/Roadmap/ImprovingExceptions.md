---
title: Roadmap - Improving Exceptions
description: To do more with the collected exceptions.
---
# Improving Exception collection and using that data

## Adding to rendering
Currently the [renderers](../features/RealtimeRendering.md) do not show where an exception happend, we want to add that in the future.

## Adding it to Code Body Reconstruction
Currently the [code body reconstruction](../features/CodeBodyReconstruction.md) does not show where an exception happend, we want to add that in the future.

## Improve pause on exception
It is currently not possible to specifiy the exceptions to pause on after the application started, we want to add that you can also specify this while the application is already running.

Also we want you to be able to more fine tune when the application should pause, like only when it is thrown by a particular method or catched by a particular method or if the message contains a specified text.

## Ignore Exceptions and do not collect them
You might not be interested in all exceptions, so we want to make you able to specifiy which exceptions may be ignored for collection.

## Include Callstack history
We want to add an option to include the threads call stack history so you can play it back and see what happen just before the exception happend.

## Include all callstacks
We want to add an option to include all threads its call stack, this would help by figuring out exceptions that are caused by racing conditions. 

## Include all callstacks its history
We want to add an option to include the history off all threads its call stack so you can play it back and see what all threads were doing before the exception happend, this can help by figuring out exceptions that are caused by racing conditions.

## Pause while exception search
To get an even more acurate view on where all threads where when an exception was thrown we can pause the application.
This prevents the call stacks of other threads to change while the exception handler is sought (the catch block)

Combine this [includeing all callstacks](#include-all-callstacks.md) (and its [history](#include-all-callstacks-its-history.md).md) and it can really show you where the application was during the exception. This would help by figuring out exceptions that are caused by racing conditions


# See Also:
- [Feature - Exceptions](../features/Exceptions.md)
- [Feature - Execution Control](../features/ApplicationInstanceExecutionControl.md)