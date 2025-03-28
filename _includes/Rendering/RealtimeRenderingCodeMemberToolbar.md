{% if include.stepping %}
![assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar_WithSteps.png](../../../assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar_WithSteps.png)
{% else %}
![assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar.png](../../../assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar.png)
{% endif %}

With the toolbar you can do the following:


- Select what [filter](../../features/ProfilingDataFiltering) type you want to use for filtering
    - Current Filters
    - Start Filters, see [Roadmap - Rendering Filter Types](../../Roadmap/ImprovedRenderingFilterType)
    - No Filter, see [Roadmap - Rendering Filter Types](../../Roadmap/ImprovedRenderingFilterType)
- [Filter](../../features/ProfilingDataFiltering) the current rendered items
- Clear the current render screen
- Reposition screen to default zoom and position 
- Opens the [interactions explorer](../../features/Interactions) pane.
 {% if include.stepping %}
- [Steps Back Out](../../features/ApplicationInstanceStepping#step-back-out) (Ctrl + Shift + F11) the current function back to before the current function was called
- [Steps Back Over](../../features/ApplicationInstanceStepping#step-back-over) (Ctrl + F10) the previous function
- [Steps Back Into](../../features/ApplicationInstanceStepping#step-back-into) (Ctrl + F11) the previous function
- [Steps Into](../../features/ApplicationInstanceStepping#step-into) (F11) the next function
- [Steps Over](../../features/ApplicationInstanceStepping#step-over) (F10) the next function
- [Steps Out](../../features/ApplicationInstanceStepping#step-out) (Shift + F11) the current function 
{% endif %}
- Search bar to search for methods by their name (Ctrl + F). Clicking on the search result will move the renderer to this method. By default you can only search for items within your rendering view.
- Prev and Next. These buttons behave different based if the "stepping in history" toggle is enabled. If this toggle is not enabled, Prev and Next will jump between occurrences of the searched method within the rendering view. If "stepping in history" is enabled, Prev and Next will jump in the callstack towards the searched method.
- Toggling this button allows you to search for methods in history. This allows you to search for methods that are not in the rendering view right now.
- Toggling this button enables "stepping in history".
- Open the [settings window](#settings-window).