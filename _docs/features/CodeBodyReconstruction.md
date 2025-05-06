---
title: Feature - Code Body Reconstruction
description: Reconstructing the code body of a function without decompilation.
---

# Code Body Reconstruction
{% include alert.html  type="warning" title="Experimental feature" content="This feature is still very experimental, though it is available in all <a href=\"../Editions\" >editions</a>. For more info, see the <a href=\"#experimental-warning\">experimental warning</a> below." %}

![assets/img/Features/CodeBodyReconstruction.png](../../assets/img/Features/CodeBodyReconstruction.png)

Unlike traditional profilers that only show time spent per function, CodeGlass analyzes collected runtime data to **reconstruct the function body**—without decompilation or access to your source code.

This enables detailed insights into how a function behaves during execution, including:

- Time spent within specific parts of the function
- Loop iteration counts
- Hot vs. cold code paths
- The current thread position within the function
- Execution time by call origin (e.g., Function A vs. Function B)
- Exact call sites within the function body
- Required execution paths to reach a call
- Time between internal function calls
- Optimization candidates (e.g., loop unrolling)
- Gaps between expected and actual behavior

Because reconstruction is based on runtime data, only the paths actually taken during execution are shown. This avoids clutter and focuses on relevant control flow, exposing unexpected behavior without requiring manual instrumentation.

This feature can reveal:
- Hidden loop iterations
- Frequently hit branches
- Timing irregularities
- Profiling insights in environments where code instrumentation isn’t possible

## Experimental Warning
This feature is still highly experimental but is available in all [editions](../Editions.md), including free tiers. We chose not to restrict access to the [Experimental Edition](../Editions/Experimental.md), as the feature is already proving valuable, even in its current state.

We encourage you to report any issues encountered in CodeGlass. However, if reconstruction fails, you will receive a descriptive error, so reporting these specific failures is not required.

Despite being experimental, this feature is stable: it will never cause CodeGlass to crash.

## Limitations
Because this reconstruction is based on execution data, it is inherently imperfect. Mapping every possible path would require excessive memory, so we currently operate within practical memory constraints (We tried downloading some more, but even that wouldn't work).

We continue to improve accuracy and coverage over time.

## Known Issues
- In some cases, reconstruction may fail even when sufficient data appears to be available.

## Views Using This Feature
- [Function Details View](../views/ApplicationInstanceDockWindow/CodeMemberDetailsView.md#code-body-view)
