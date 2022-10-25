{% if include.stepping %}
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar_WithSteps.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar_WithSteps.png)
{% else %}
![assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png](../../../assets/img/ApplicationInstanceWindow/GroupedCallStackRenderingToolbar.png)
{% endif %}


With the toolbar you can do the following:


- Select what [filter](../../features/ProfilingDataFiltering.md) tyoe you want to use for filtering
    - Current Filters
    - Start Filters, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFilterType.md)
    - No Filter, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFilterType.md)
- [Filter](../../features/ProfilingDataFiltering.md) the current rendered items
- Clear the current render screen
- Selecting the object type new rendered items will be grouped by.
- Forcing all rendered items to be grouped by the selected object type.{% if include.stepping %}
- [Steps Back Out](../../features/ApplicationInstanceStepping#step-back-out) (Ctrl + Shift + F11) the current function back to before the current function was called
- [Steps Back Over](../../features/ApplicationInstanceStepping#step-back-over) (Ctrl + F10) the previous function
- [Steps Back Into](../../features/ApplicationInstanceStepping#step-back-into) (Ctrl + F11) the previous function
- [Steps Into](../../features/ApplicationInstanceStepping#step-into) (F11) the next function
- [Steps Over](../../features/ApplicationInstanceStepping#step-over) (F10) the next function
- [Steps Out](../../features/ApplicationInstanceStepping#step-out) (Shift + F11) the current function {% endif %}