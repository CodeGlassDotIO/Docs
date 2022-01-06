---
title: Feature - Decompilation
description: Explanation of where and why we use decompilation (Because that can be scary, right?)
---

# Decompilation
From the start, we did not want to use any decompilation, as we did not want anyone to think we were doing something with it and did not want any knowledge of your code.

However, we added the following feature below as we did not see another way around it.

So we made this page to clarify why there are standard decompilation libraries in our assembly.

## Decompilation for Filters
We wanted to make this page as we want to be transparent with everything Code Glass does, and we can imagine that people might get anxious when they see standard decompilation libraries in our assembly.
And that the use-case we use it for here is very useful.

We only use decompilation when the user presses the decompilation buttons in [apllication filter views](../views/applicationsettingswindow/ApplicationFilters.md#decompilation). You supply data for the [Profiling data filtering feature](ProfilingDataFiltering.md)with this.
Then you do not have to run the application first and maybe a while to get the data you want to filter.
Decompilation can be very helpful, especially in cases where you do not want to run it the first time (Like solving bugs that only happen at first launch after installation).


Of course, you have to take our word for it, and we hope that is enough. However, if that is still a dealbreaker for you, feel free to submit a ticket, then we will make it an installation option in the future.
 


# See Also:
- [Profiling data filtering](ProfilingDataFiltering.md)
- [View - Application Filters](../views/applicationsettingswindow/ApplicationFilters.md)


