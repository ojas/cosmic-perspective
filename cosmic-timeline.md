---
title: Cosmic Timeline
multi_section: true
sticky_heading: true
---

# The Cosmic Year

13.8 billion years compressed into a single calendar year.

**January 1** represents the origin of the universe.
**December 31** represents the present moment.

Modern history occupies only the final seconds.

{% for entry in site.data.cosmic_timeline %}

<section>
  <h2>{{ entry.cosmic_placement | date: "%B %-d %H:%M:%S" }}</h2>
  <p class="subtitle">{{ entry.timescale }}</p>
  <p>
    <span class="marginnote"><strong>Qur'an:</strong> {{entry.quran_option_1}}</span>
    {% if entry.hadith %}
    <span class="marginnote"><strong>Hadith:</strong> {{ entry.hadith }}</span>
    {% endif %}
    {{ entry.description }}
  </p>
  <p>Sources: {% if entry.sources %}
  {% for source in entry.sources %}
  <a href="sources#{{source}}">{{source}}</a>{% unless forloop.last %}, {% endunless %}
  {% endfor %}
  {% else %}
  none
  {% endif %}
  </p>
</section>

{% endfor %}
