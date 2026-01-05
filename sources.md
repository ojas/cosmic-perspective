---
title: Sources
description: All sources cited in the cosmic timeline, formatted in APA 7th edition style.
---

# Sources

All sources cited in the cosmic timeline.

{% for source in site.data.sources %}

<p class="source-entry" id="{{ source.id }}">
    <strong>[{{ source.id }}]</strong>
    {{ source.author }}.
    ({{ source.year }}).
    {% if source.type == "journal" %}
        {{ source.title }}.
        <em>{{ source.journal }}</em>,
        <em>{{ source.volume }}</em>{% if source.issue %}({{ source.issue }}){% endif %}{% if source.pages %}, {{ source.pages }}{% endif %}.
        {% if source.doi %}
        <a target="_blank" href="https://doi.org/{{ source.doi }}">https://doi.org/{{ source.doi }}</a>
        {% else %}
        <a target="_blank" href="{{ source.url }}">{{ source.url }}</a>
        {% endif %}
    {% elsif source.type == "report" %}
        <em>{{ source.title }}</em>.
        {{ source.publisher }}.
    <a target="_blank" href="{{ source.url }}">{{ source.url }}</a>
    {% elsif source.type == "website" %}
        <em>{{ source.title }}</em>.
        {{ source.publisher }}.
    <a target="_blank" href="{{ source.url }}">{{ source.url }}</a>
    {% elsif source.type == "encyclopedia" %}
        {{ source.title }}.
        In <em>{{ source.publisher }}</em>.
    <a target="_blank" href="{{ source.url }}">{{ source.url }}</a>
    {% endif %}
</p>

{% endfor %}
