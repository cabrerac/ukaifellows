---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: "UK AI ATI Fellows Community"
---

<p>The AI ATI Fellows Community focuses on the development and application of artificial intelligence and machine learning technologies.</p>

<p>This website presents a list of events where the AI ATI Fellows Community shares knowledge and experiences from different research projects around the UK.</p>

<h3>Events</h3>

<ul>
{%- assign sorted = site.github.public_repositories | sort: 'created_date' -%}
{%- for repository in sorted reversed -%}{%- if repository.has_pages -%}{%- unless repository.name contains 'github.io' -%}
  {% assign firstletter = repository.name | slice: 0, 2 %}
    <b>{{ firstletter }}</b>
    {%-if firstletter=='e-'-%}
    <li>
    <a href="{{ repository.name | prepend: site.baseurlsite }}"><b>{{ repository.description }}</b></a>
    </li>
    {%-endif-%}
  {%- endunless -%}{%- endif -%}{%- endfor -%}
</ul>


