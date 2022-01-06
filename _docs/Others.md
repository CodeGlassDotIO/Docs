---
title: Other Pages and documents
description: Other pages that did not fit in any other category.
---
# Others

Here are all the other pages.

<div class="section-index">
    {% for post in site.docs  %}
    {% if post.title contains 'Others -' %}
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