---
title: Roadmap
description:  The Future of Code Glass
---
# Roadmap
This is not our entire roadmap, as we have so much more planned for Code Glass as the sky is not anymore the limit, this generation goes to Mars!

These are only the ones we wrote down here so we could reference them from other pages.

We might (and probably will) make that you can vote on roadmap items that you want to see next.

## items
<div class="section-index">
    {% for post in site.docs  %}
    {% if post.title contains 'Roadmap -' %}
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
# See Also:

