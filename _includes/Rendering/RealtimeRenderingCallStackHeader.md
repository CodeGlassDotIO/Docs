{% include Warnings/RenderingPhotosensitivityWarning.html  %}

See [Feature - Realtime call stack Rendering](../../features/RealtimeRendering#realtime-call-stack-rendering) for more information about the feature.

You can select to which data object type you want to combines all calls in the [toolbar](#toolbar).

Hovering over an item will show you information about the last and current threads using that function.

Hovering over a line will show you where it comes from and where it goes to. 

Right click on an item will open the [context menu](#item-context-menu).

Double clicking, or with the connext menu of an item, will open the [object detail view](ObjectDetailsView) of that item.

{% include alertNoTitle.html  type="info" content="You can improve the rendering performance in the <a href=\"#settings-window\">settings window</a>." %}

{% if include.isException == false %}
{% include alertNoTitle.html  type="warning" content="Rendering does have an impact on profiling performance, this will be improved in future releases." %}
{% endif %}

