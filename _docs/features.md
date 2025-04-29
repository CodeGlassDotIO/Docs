---
title: Features of CodeGlass
description: Documentation by feature
---

# Features of CodeGlass

CodeGlass has many features that might not even be described in the items below.
This is because the documentation is written from the [View](views.md) perspective. When multiple views reference a feature it is written down in the items below.

Keep in mind that the features described here do not go into much detail about how they are used or configured but about how they work, however links are provided on each page to the view where they are used.

## Features

<div class="section-index">
    {% for post in site.docs  %}
    {% if post.title contains 'Feature -' %}
        {%if post.doNotShow and post.doNotShow == true  %}
        {% else %}
        <div class="entry">
        <h5><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h5>
        <p>{{ post.description }}</p>
        
        </div>
        {% endif %}
    {% endif %}
    {% endfor %}
    
</div>
