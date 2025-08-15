---
layout: home
title: One Page Games 🎮
---

A growing collection of tiny, single-file games. Click to play!

{% comment %}
Collect every HTML file anywhere under the repo
{% endcomment %}
{% assign all_html = site.static_files | where_exp: "f", "f.extname == '.html'" %}

{% comment %}
Group by the first-level directory name (the game folder).
This assumes structure like /Starfall_Raiders/starfallRaiders.html
If you have deeper nesting, adjust the slice.
{% endcomment %}
{% assign grouped = all_html | group_by_exp: "f", "f.path | split: '/' | slice: 1,1 | first" %}

{% comment %}
Optional: ignore html files at repo root (no folder). Remove this if you want root files listed.
{% endcomment %}
{% assign grouped = grouped | where_exp: "g", "g.name != nil and g.name != ''" %}

<ul>
{% for group in grouped %}
  {% assign game_name = group.name %}

  {%- comment -%}
  Find a primary "play" target inside this folder:
  1) index.html
  2) latest.html
  3) otherwise pick the lexicographically last (often newest by versioned names)
  {%- endcomment -%}
  {% assign files = group.items | sort: "name" %}
  {% assign primary = nil %}
  {% for f in files %}
    {% if f.name == "index.html" %}
      {% assign primary = f %}
      {% break %}
    {% endif %}
  {% endfor %}
  {% if primary == nil %}
    {% for f in files %}
      {% if f.name == "latest.html" %}
        {% assign primary = f %}
        {% break %}
      {% endif %}
    {% endfor %}
  {% endif %}
  {% if primary == nil %}
    {% assign primary = files | last %}
  {% endif %}

  <li style="margin-bottom:1rem;">
    <strong>{{ game_name | replace: '_', ' ' }}</strong>
    &nbsp;—&nbsp;
    <a href="{{ primary.path | relative_url }}">Play</a>
    <details>
      <summary>All versions</summary>
      <ul>
        {% for f in files %}
          <li><a href="{{ f.path | relative_url }}">{{ f.name }}</a></li>
        {% endfor %}
      </ul>
    </details>
  </li>
{% endfor %}
</ul>

> Convention: inside each game folder, add **`index.html`** (or **`latest.html`**) to control which version the main **Play** link targets.
