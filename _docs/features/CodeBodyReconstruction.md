---
title: Feature - Code Body Reconstruction
description: Reconstructing the code body of a function without decompilation.
---
# Code body Reconstruction
{% include alert.html  type="warning" title="Experimental feature" content="This feature is still very experimental, though it is available in all <a href=\"../Editions\" >editions</a>, for more info see the <a href=\"#experimental-warning\" >Experimental warning</a> below." %}

![assets/img/Features/CodeBodyReconstruction.png](../../assets/img/Features/CodeBodyReconstruction.png)

Unlike other profilers that simply show how much time is spent in a function, CodeGlass goes a step further by analyzing the collected data to reconstruct the function body as accurately as possible, without decompiling or needing access to your source code!

This allows CodeGlass to provide a detailed view of your function's behavior, including:
- Where time is spent within the function.
- The number of times a loop is executed.
- How often different code paths are taken (hot and cold paths).
- The current position of a thread within the function.
- Time taken by the function when called from different functions (e.g., Function "A" vs. Function "B").
- The exact point where a function call was made in the code.
- The paths that need to be taken inside the function to reach a specific call.
- Time spent in the function body between function calls.
- Insights into potential optimizations, like loop unrolling.
- How your code behaves compared to your expectations.

Because this analysis is based on collected data instead of decompilation, CodeGlass shows you what your function is actually doing, and showing you the difference between your expectations and its actual behavior. Paths that are never taken are excluded from the analysis, ensuring only relevant information is displayed.

With these insights, you can uncover surprises like unexpected loop iterations or frequently called code paths. It also eliminates the need to manually add stopwatches to your code, as CodeGlass provides similar insights in environments where adding them is not possible.

## Experimental Warning
This feature is still highly experimental but is available in all [editions](../Editions.md). We didn’t want to limit it to paid versions only, even though it’s currently in a testing phase. It’s already proving to be very helpful, so we’ve made it accessible beyond just the [experimental Edition](../Editions/Experimental.md).

We encourage you to report any issues you encounter in CodeGlass, but please note that you don’t need to report when this render fails, as you will receive an appropriate error message. We understand that this feature doesn't always perform perfectly, but we feel it’s too valuable to restrict it to the [experimental Edition](../Editions/Experimental.md) despite its current state.

Rest assured, this feature should never cause CodeGlass to crash; it’s not that experimental ;)

## Limitations
Because this rendering is an assumptions based on data, it can never be perfect. Collecting every possible path would take a massive amount of RAM (even downloading more is not enough), so we settled on doing it within the confinement of limited ram.
That does not mean that it will not improve in the future, but currently it is far from perfect and can still be improved on a lot (which we are also planning to do). 


## Known issues
- In some cases where reconstruction should be possible, it still fails.

## Views using this feature
- [Function Details View](../views/ApplicationInstanceDockWindow/CodeMemberDetailsView.md#code-body-view)