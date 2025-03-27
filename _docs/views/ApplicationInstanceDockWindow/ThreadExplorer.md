---
title: View - Application Instance - Thread Explorer
description: A list of all threads of an application.
---
# Thread Explorer
![assets/img/ApplicationInstanceWindow/AppInstanceThreadExplorer.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceThreadExplorer.png)

The thread explorer shows all threads used by the profiled application.

The first number is the id assigned by CodeGlass, the second number is the thread id assigned by the application itself ({CodeGlass thread id}:{Thread id}).

You can order the list by the thread status by the button in the toolbar.
- Active, (Threads shown in white)
- Not Active / Destroyed (Threads shown in gray).

When you double click a thread it opens the [thread details view](ThreadDetailsView.md).

Each threads is also identified by color, as shown on the thread icon. For more information about the coloring see [this](../../views/ApplicationInstanceDockWindow/CallTreeRendering.md#threads-and-coloring) page.

# Application Breadcrumbs
-  [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 

# See Also:
- [Thread details window](ThreadDetailsView.md).
