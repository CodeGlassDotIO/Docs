---
title: View - Application Instance - Thread Details View
description: The details of a specific thread.
---
# Thread Details View
![assets/img/ApplicationInstanceWindow/ThreadDetailView.png](../../../assets/img/ApplicationInstanceWindow/ThreadDetailView.png)


This view shows you the current call stack of the thread, it also reflect [call stack (thread) steps](../../features/ApplicationInstanceStepping.md) that you might have made, forwards but also backwards! 

But you can also step this thread specifically by the [thread stepping controls](#thread-stepping-controls) in the toolbar of this view.

## Thread Stepping Controls
![assets/img/ApplicationInstanceWindow/ThreadDetailViewToolbar.png](../../../assets/img/ApplicationInstanceWindow/ThreadDetailViewToolbar.png)

{% include ExecutionControl/SteppingToolbar.md %}


{% include alertNoTitle.html  type="info" content="Please note that this does not cause this thread only to step, every thread will keep stepping till this specific thread does. <br/> If you are interested in only stepping this thread and keep the other threads paused see the <a href=\"../../Roadmap/ThreadOnlyStepping\">thread only stepping</a> roadmap item." %}

### Known Issues
The thread stepping control hotkeys only work when there is focus on the thread details view, else it will use the regular stepping controls from the [toolbar](Toolbar#stepping.md) above it.

<!-- # Application Breadcrumbs
- [Thread Explorer](ThreadExplorer.md) /  -->