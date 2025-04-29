{% include Warnings/RenderingPhotosensitivityWarning.html  %}

See [Feature - Realtime call tree Rendering](/Docs/docs/features/RealtimeRendering#realtime-call-tree-rendering) for more information about the feature.

Hovering over an item will show you information about the last or current thread using that function.

Hovering over a line will show you where it comes from and where it goes to. 

Right click on an item will open the [context menu](#item-context-menu).

Double clicking, or with the context menu of an item, will open the [function detail view](CodeMemberDetailsView) of that item.
{% if include.isException %} However, the details will reflect the current state of the application, not when the exception happened. ([Roadmap](/Docs/docs/Roadmap/ImprovingExceptions)) {% endif %}

{% include alertNoTitle.html  type="info" content="You can improve the rendering performance in the <a href=\"#settings-window\">settings window</a>." %}

{% if include.isException == false %}
{% include alertNoTitle.html  type="warning" content="Rendering does have an impact on profiling performance, this will be improved in future releases." %}
{% endif %}

