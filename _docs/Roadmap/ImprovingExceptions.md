---
title: Roadmap - Improving Exceptions
description: To do more with the collected exceptions.
---
{% include Warnings/RoadmapWarning.html %}

# Improving Exception Collection and Using That Data

## Improve Pause On Exception
It is currently not possible to specify the exceptions to pause on after the application started, we want to add that you can also specify this while the application is already running.

Also we want you to be able to more fine tune when the application should pause, like only when it is thrown by a particular method or caught by a particular method or if the message contains a specified text.

## Allow Changes To Exception Settings While Application Already Started
Currently it uses the application settings when the application started, we want to make it possible to change the settings while the application is already running.

## Reflect Exception Details In Function And Object Details 
When you open a function or object details view from within an exception it shows you the current state of the application instead of that when the exception happened, we want to fix that.

## Ignore Exceptions And Do Not Collect Them
You might not be interested in all exceptions, so we want to make you able to specify which exceptions may be ignored for collection.

## Pause While Exception Search
To get an even more accurate view on where all threads where when an exception was thrown we can pause the application.
This prevents the call stacks of other threads to change while the exception handler is sought (the catch block)

Combine this including all callstacks (and its history) and it can really show you where the application was during the exception. This would help by figuring out exceptions that are caused by racing conditions.


# See Also:
- [Feature - Exceptions](../features/Exceptions.md)
- [Feature - Execution Control](../features/ApplicationInstanceExecutionControl.md)