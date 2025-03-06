{% if include.stepping %}
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar_WithSteps.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar_WithSteps.png)
{% else %}
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png)
{% endif %}


With the toolbar you can do the following:


- Select what [filter](../../features/ProfilingDataFiltering) type you want to use for filtering
    - Current Filters
    - Start Filters, see [Roadmap - Rendering Filter Types](../../Roadmap/ImprovedRenderingFilterType)
    - No Filter, see [Roadmap - Rendering Filter Types](../../Roadmap/ImprovedRenderingFilterType)
- [Filter](../../features/ProfilingDataFiltering) the current rendered items
- Clear the current render screen
- Selecting the object type new rendered items will be grouped by.
- Forcing all rendered items to be grouped by the selected object type. {% if include.stepping %}
- [Steps back out](../../features/ApplicationInstanceStepping#step-back-out) (Ctrl + Shift + F11) the current function back to before the current function was called
- [Steps back over](../../features/ApplicationInstanceStepping#step-back-over) (Ctrl + F10) the previous function
- [Steps back into](../../features/ApplicationInstanceStepping#step-back-into) (Ctrl + F11) the previous function
- [Steps into](../../features/ApplicationInstanceStepping#step-into) (F11) the next function
- [Steps over](../../features/ApplicationInstanceStepping#step-over) (F10) the next function
- [Steps out](../../features/ApplicationInstanceStepping#step-out) (Shift + F11) the current function {% endif %}
- Search bar to search for methods by their name. Clicking on the search result will move the renderer to this method. By default you can only search for items within your rendering view.
- Toggling this button allows you to search for methods in history. This allows you to search for methods that are not in the rendering view right now.
- Step to Prev/Next Call, pressing these buttons will jump in the callstack to the searched method.
- Open the [settings window](#settings-window)