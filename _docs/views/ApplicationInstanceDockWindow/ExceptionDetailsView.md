---
title: View - Application Instance - Exception Details View
description: The details of a thrown exception.
---
# Exception Details View
![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails.png)

## Toolbar
![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails_Toolbar.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails_Toolbar.png)


- Opens the [Info Tab](#exception-info-view) 
- Opens the [Call Tree View](#exception-call-tree-view)
- Opens the [Call Stack View](#exception-call-stack-view)


### Exception Info View

This view shows you data from the thrown exception, this includes:
- The Exception Type
- When the exception occurred.
- What function threw the exception.
- What function caught the exception.
- The call stack that got unwound when the exception happened.
- The [collected call stack](../../features/RealtimeDataCollection.md#callstack) of the remaining stack after it was caught .


This feature will be expanded upon with finer control and more information in the future. ([Roadmap](../../Roadmap/ImprovingExceptions.md))


### Exception Call Tree View
![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails_CallTree.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails_CallTree.png)

{% include Rendering/RealtimeRenderingCodeMemberHeader.md  isException=true %}


#### Call Tree Toolbar
{% include Rendering/RealtimeRenderingCodeMemberToolbar.md stepping=true %}
- Open the [Settings window](#call-tree-settings-window)


#### Call Tree Settings Window
![assets/img/ApplicationInstanceWindow/RealtimeCallTreeRenderingSettingsWindow.png](../../../assets/img/ApplicationInstanceWindow/RealtimeCallTreeRenderingSettingsWindow.png)

Most of the settings are quite self explainitory.

You can choose to save these settings as your new default for new renders or only for this render.

### Exception Call Stack View
![assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails_CallStack.png](../../../assets/img/ApplicationInstanceWindow/AppInstanceExceptionDetails_CallStack.png)

#### Call Stack Toolbar
{% include Rendering/RealtimeRenderingCallStackToolbar.md stepping=true %}
- Open the [Settings window](#call-stack-settings-window)


## Call Stack Settings Window
![assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRenderingSettings.png](../../../assets/img/ApplicationInstanceWindow/RealtimeGroupedCallStackRenderingSettings.png)

Most of the settings are quite self explainitory.

You can choose to save these settings as your new default for new renders or only for this render.

## Item Context Menu
{% include Rendering/RealtimeRenderingCodeMemberContextMenu.md %}



## Threads and Coloring
{% include Rendering/ThreadsAndColoring.md %}


# Application Breadcrumbs
- { All paths leading to } /  [Thread Explorer](ExceptionExplorer.md) / 