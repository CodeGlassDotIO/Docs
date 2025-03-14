---
title: Feature - Interaction Tracking
description: The tracking of interactions that happened in your application
---

# Interaction Tracking
This feature allows you to easily see key interactions that occurred in your application. An interaction can be multiple things. An interaction can be something like an event but it can also be an API endpoint that was called, etc. At this point we only support the tracking of events but tracking of other interactions like an API call will be added soon.

{% include alert.html type="warning" title="Limited support" content="At this point the only language to support this feature is C#, but more will be added soon." %}

![assets/img/ApplicationInstanceWindow/InteractionsOverview.png](../../assets/img/ApplicationInstanceWindow/InteractionsOverview.png)

## How It Works
This view can be found on both the [call tree renderer](../views/ApplicationInstanceDockWindow/CallTreeRendering.md) and the [call stack renderer](../views/ApplicationInstanceDockWindow/CallStackRendering.md)

The interactions view has two lists. The "Active Interactions" and "Interactions History" lists. The active list shows all the interactions that have been called but have not yet returned. The history list shows all the interactions that can be found in the stored call stack history. The amount of items shown in the history list is limited to the value that is set in [render settings](../views/ApplicationInstanceDockWindow/CallTreeRendering.md#settings-window).

The interaction lists are updated based on stepping events. If you step into or out of an method that is also an interaction, the "Active Interactions" list will add or remove the item. In the "Interaction History" list items are grayed out when they are in the "future" of the current position in the callstack. The further you step back into the history of the callstack, the more items will be grayed out.

Clicking on an active item will move that method into the viewport of your rendering screen, and will not change the state of your callstack. When you click on an item in the history the callstack will be moved until it reaches the point that this interaction was called. If this item cannot be found in you callstack history anymore nothing will happen. 

Note that the callstack will only change when your application is in a paused state. If you forget to pause your application and try to click on one of the interactions, CodeGlass will give you a little popup to tell you that your application should be paused for this operation to be executed.

## Coloring
Every interaction item has a colored border around it. The color of the border is equal to the color of the thread that this interaction was called on. For more information about the coloring see [this](../views/ApplicationInstanceDockWindow/CallTreeRendering.md#threads-and-coloring) page.

## Max Interactions Reached
There is a very small change that you will get the warning "Max Interactions Reached" when using this feature. When you leave a rendering view open and 4,294,967,295 (uint32 max value) interactions happen, our id for tracking interactions overflows. If this happens please close and reopen your rendering view, as this will reset the id counter.