---
title: Feature - Decompilation
description: Explanation of where and why we use decompilation (Because that can be scary, right?)
---

# Decompilation

From the beginning, we intentionally avoided decompilation to ensure users had full confidence that CodeGlass does not access or interpret their source code.

However, after extensive evaluation, we introduced a limited decompilation capability, outlined below, because there was no viable alternative for this specific use case.

This page is intended to clarify our reasoning and explain why standard decompilation libraries are included in the CodeGlass assembly.

## Decompilation for Filters

We value transparency, especially regarding features that may raise concerns. The presence of decompilation libraries is deliberate and limited in scope.

Decompilation is only invoked when a user explicitly triggers it via the [application filter views](../views/ApplicationSettingsWindow#decompilation). This is used to assist in defining [profiling data filters](ProfilingDataFiltering.md) *before* any runtime data has been collected.

This functionality is particularly helpful when profiling scenarios that are difficult to reproduce, such as issues that only occur on first launch after installation. By leveraging decompilation, users can configure filters in advance without having to run the target application.

> **Note:**  
> Decompilation is never used implicitly. It is strictly opt-in and only occurs through a user-initiated action.  

We understand that trust is critical. If this behavior is a concern, please let us know. We are open to making decompilation support an optional install-time feature based on user feedback.

# See Also:
- [Profiling data filtering](ProfilingDataFiltering.md)
- [View - Application Filters](../views/ApplicationSettingsWindow.md#application-filters)
