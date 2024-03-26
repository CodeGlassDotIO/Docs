---
title: Roadmap - Improving Exceptions
description: To do more with the collected exceptions.
---
{% include Warnings/RoadmapWarning.html %}

# Improving Exception collection and using that data

## Adding it to Code Body Reconstruction
Currently the [code body reconstruction](../features/CodeBodyReconstruction.md) does not show where an exception happend, we want to add that in the future.

## Improve pause on exception
It is currently not possible to specifiy the exceptions to pause on after the application started, we want to add that you can also specify this while the application is already running.

Also we want you to be able to more fine tune when the application should pause, like only when it is thrown by a particular method or catched by a particular method or if the message contains a specified text.

## Allow changes to exception settings while application already started
Currently it uses the application settings when the application started, we want to make it possible to change the settings while the application is already running.

## Reflect Exception details in function and object Details 
When you open a function or object details view from within an exception it shows you the current state of the application instead of that when the exception happend, we want to fix that.

## Ignore Exceptions and do not collect them
You might not be interested in all exceptions, so we want to make you able to specifiy which exceptions may be ignored for collection.

## Pause while exception search
To get an even more acurate view on where all threads where when an exception was thrown we can pause the application.
This prevents the call stacks of other threads to change while the exception handler is sought (the catch block)

Combine this [includeing all callstacks](#include-all-callstacks.md) (and its [history](#include-all-callstacks-its-history.md).md) and it can really show you where the application was during the exception. This would help by figuring out exceptions that are caused by racing conditions


# See Also:
- [Feature - Exceptions](../features/Exceptions.md)
- [Feature - Execution Control](../features/ApplicationInstanceExecutionControl.md)