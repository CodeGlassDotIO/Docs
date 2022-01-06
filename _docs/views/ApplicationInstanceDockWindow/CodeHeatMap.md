---
title: View - Application Instance - Realtime Code Heatmap
description: The realtime rendering of the code heat map by statistics and data type.
---
# Code Heat Map
![assets/img/ApplicationInstanceWindow/CodeHeatMapWindow.png](../../../assets/img/ApplicationInstanceWindow/CodeHeatMapWindow.png)

{% include alertNoTitle.html  type="info" content="If you are color blind please see <a href=\"../../Roadmap/ColorBlindMode\">Color blind mode</a>." %}

See [Feature - Realtime Code Heat Map](../features/RealtimeRendering.md#realtime-code-heatmap) for more information about the feature.

In the toolbar on top you can do multiple actioms, in order they appear:
- Dropdown to select wich object types you want to see.
- Dropdwon to Select wich statistic you want to use
- Icon Button to Reorder the render to sort the items by the selected statistic.
- Icon Button to open the [Heat map Visible items Tool pane](#heat-map-visible-items-tool-pane) (Visible on the left of the screenshot).
- Icon Button to open the [Heat map settings Window](#heat-map-settings-window) (Visible on the far right).


When you double click an item in the tree view it will open the [Object Details View](ObjectDetailsView.md) or [Function Details View](CodeMemberDetailsView.md) of the selected item.

{% include alertNoTitle.html  type="info" content="You can improve the heat map performance in the <a href=\"#heat-map-settings-window\">Heat Map Settings Window</a>." %}
{% include alertNoTitle.html  type="info" content="For more information on how we messure time, see  <a href=\"..\..\features\TimeMessurement\">Feature - Time Messurement</a>." %}



## Heat Map Visible Items Tool Pane
You can open the tool pane by clicking on the button in the toolbar, this window shows all items that are currently visible to the user in order of selected statistic.
You can see an example of this pane in the screenshot above on the left side.


When you double click an item in the tree view it will open the [Object Details View](ObjectDetailsView.md) or [Function Details View](CodeMemberDetailsView.md) of the selected item.


## Heat Map Settings Window
![assets/img/ApplicationInstanceWindow/CodeHeatMapSettingsWindow.png](../../../assets/img/ApplicationInstanceWindow/CodeHeatMapSettingsWindow.png)

Most of the settings are quite self explainitory.

You can choose to save these settings as your new default for Heat map rendering or only for this Heat map.


# Application Breadcrumbs
- { All paths leading to } /  [Application Instance Window](../ApplicationInstanceDockWindow.md) / [View Menu](../ApplicationInstanceDockWindow/MenuBar.md#view-menu) / 


# See Also
- [Application Instance Window](../ApplicationInstanceDockWindow.md)