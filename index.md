---
layout: home
title: One Page Games 🎮
---

# One Page Games 🎮

A growing collection of tiny, single-file games. Click a version to play.

{% assign files = site.static_files | where: "extname", ".html" | sort: "path" %}
{% assign current = "" %}

<ul>
{% for f in files %}
  {%- comment -%} folder = first path segment after removing leading "/" {%- endcomment -%}
  {% assign folder = f.path | remove_first: "/" | split: "/" | first %}

  {% if folder == "" %}
    {% continue %}
  {% endif %}

  {% if folder != current %}
    {% if current != "" %}
        </ul>
      </details>
    </li>
    {% endif %}
    {% assign current = folder %}
    <li style="margin-bottom:1rem;">
      <strong>{{ current | replace: "_", " " }}</strong>
      <details>
        <summary>All versions</summary>
        <ul>
  {% endif %}

  <li><a href="{{ f.path | relative_url }}">{{ f.name }}</a></li>
{% endfor %}

{% if current != "" %}
        </ul>
      </details>
    </li>
{% endif %}
</ul>


Stay tuned for more!
See [https://mageworks.studio](https://mageworks.studio) and [https://mageworks.site](https://mageworks.site] to see more of my work.
![](https://i.imgur.com/KHOtK2O.png)