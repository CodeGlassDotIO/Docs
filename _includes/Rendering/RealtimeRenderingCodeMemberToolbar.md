{% if include.stepping %}
![assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar_WithSteps.png](../../../assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar_WithSteps.png)
{% else %}
![assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar.png](../../../assets/img/ApplicationInstanceWindow/RealtimeRenderingCodeMemberToolbar.png)
{% endif %}

With the toolbar you can do the following:


- Select what [filter](../../features/ProfilingDataFiltering) tyoe you want to use for filtering
    - Current Filters
    - Start Filters, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFIlterType)
    - No Filter, see [Roadmap - Rendering Filter Types](../../Roadmap/RenderingFIlterType)
- [Filter](../../features/ProfilingDataFiltering) the current rendered items
- Clear the current render screen
- Reposition screen to default zoom and position 
- [Steps Back Out](../../features/ApplicationInstanceStepping#step-back-out) (Ctrl + Shift + F11) the current function back to before the current function was called
- [Steps Back Over](../../features/ApplicationInstanceStepping#step-back-over) (Ctrl + F10) the previous function
- [Steps Back Into](../../features/ApplicationInstanceStepping#step-back-into) (Ctrl + F11) the previous function
- [Steps Into](../../features/ApplicationInstanceStepping#step-into) (F11) the next function
- [Steps Over](../../features/ApplicationInstanceStepping#step-over) (F10) the next function
- [Steps Out](../../features/ApplicationInstanceStepping#step-out) (Shift + F11) the current function {% endif %}
- Open the [Settings window](#settings-window)