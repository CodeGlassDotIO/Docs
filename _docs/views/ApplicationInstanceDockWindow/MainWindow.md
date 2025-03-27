---
title: View - Application Instance - Main Window
description: The main application instance window of a (previously) profiled application.
---
# Main Window
![assets/img/ApplicationInstanceWindow/AppInstanceMainWindow.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceMainWindow.png)

This is the default window you see when you [start a new instance](../mainwindow/applicationInstance).

This just gives you a nice dashboard of your application, we might add more dashboard items in the future here.

You can click "Bring process to front" to bring the profiling application in front.

{% include alertNoTitle.html  type="info" content="The profiled functions value is calculated by the amount of calls and returns that happened and that divided by 2." %}

## Issues
The gauge can roll over, meaning that if it goes over 500.000 it just keep on rotating.

# Application Breadcrumbs
-  [Application Instance Window](../ApplicationInstanceDockWindow) / [View Menu](../ApplicationInstanceDockWindow/MenuBar#view-menu) / 

# See Also:
- [Application Instance View](../mainwindow/applicationInstance)