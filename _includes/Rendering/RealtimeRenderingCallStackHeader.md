{% include Warnings/RenderingPhotosensitivityWarning.html  %}

See [Feature - Realtime call stack Rendering](../../features/RealtimeRendering.md#realtime-call-stack-rendering) for more information about the feature.

You can select to wich data object type you want to combines all calls in the [toolbar](#toolbar).

Hovering over an item will show you information about the Last and current threads using that function.

Hovering over a line will show you where it comes from and where it goes to. 

Right click on an item will open the [Context Menu](#item-context-menu).

Double clicking or with the conext menu of an item will open the [Object Detail View](ObjectDetailsView.md) of that item.

{% include alertNoTitle.html  type="info" content="You can improve the rendering performance in the <a href=\"#settings-window\">Settings Window</a>." %}

{% if include.isException == false %}
{% include alertNoTitle.html  type="warning" content="Rendering does have an impact on profiling performance, this will be improved in future releases." %}
{% endif %}

