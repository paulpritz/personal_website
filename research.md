---
layout: page
permalink: /research/
title: Research
---

## Publications

{% assign thumbnail="left" %}

{% for pub in site.data.pubs %}
{% if pub.image %}
{% include image.html url=pub.image caption="" height="100px" align=thumbnail %}
{% endif %}
[**{{pub.title}}**]({% if pub.internal %}{{pub.url | prepend: site.baseurl}}{% else %}{{pub.url}}{% endif %})<br />
{{pub.author}}<br />
*{{pub.journal}}*
{% if pub.note %} *({{pub.note}})*
{% endif %} *{{pub.year}}* {% if pub.doi %}[[doi]({{pub.doi}})]{% endif %}
{% if pub.pdf %}<br />PDF: {% for article in pub.pdf %}[[{{article.name}}]({{article.url}})]{% endfor %}{% endif %}

{% endfor %}

## Talks

{% if site.data.talks %}
{% for talk in site.data.talks %}
[**{{talk.title}}**]{% if talk.url %}({% if talk.internal %}{{talk.url | prepend: site.baseurl}}{% else %}{{talk.url}}{% endif %}){% endif %}<br />
{% if talk.speaker %}{{talk.speaker}} – {% endif %}{{talk.event}}{% if talk.location %}, {{talk.location}}{% endif %}{% if talk.date %} — {{talk.date}}{% endif %}
{% if talk.slides %}<br />Slides: {% for slide in talk.slides %}[[{{slide.name}}]({{slide.url}})]{% endfor %}{% endif %}
{% if talk.video %}<br />Video: {% for vid in talk.video %}[[{{vid.name}}]({{vid.url}})]{% endfor %}{% endif %}

{% endfor %}
{% else %}
No talks added yet.
{% endif %}
