---
layout: page
title: About
permalink: /about/
---

Hei, we're the Software Engineering research group at HVL!
Our "institutional home" is <https://www.hvl.no/en/research/group/software-engineering/>.
Here, we provide additional content as part of our social media efforts, as well as other
information.

# Group members
<!-- as per https://www.hvl.no/en/research/group/software-engineering/ -->
<!-- https://shopify.github.io/liquid/tags/control-flow/ -->

{%- for member in site.data.members -%}{%- if member.intext == "true" -%}
* {{ member.displayname }} ({{ member.title }}) [[@ HVL](https://www.hvl.no/en/employee/?user={{member.urlname}})]
{%- unless member.extinfo == "" -%} {{member.extinfo}} {% endunless %}
{% endif %} {% endfor %}

## External/part-time members

{%- for member in site.data.members -%}{% unless member.intext == "true" %}
* {{ member.displayname }} ({{ member.title }}) {{member.extinfo}}
{%- endunless -%} {% endfor %}

## PhD students

{% for member in site.data.stips -%}
* {{ member.displayname }} [[@ HVL](https://www.hvl.no/en/employee/?user={{member.urlname}})]
{% endfor %}
