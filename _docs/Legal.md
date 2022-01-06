---
title: Legal Docs
description: All Legal documentats
---
# Legal Documents

Here are all the legal documents and documentation

<div class="section-index">
    {% for post in site.docs  %}
    {% if post.title contains 'Legal -' %}
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