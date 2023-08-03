---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
author: vsto
---
Software engineering and how we develop software play a still more critical role for system development as software technology is becoming pervasive across all areas of society and industry.
Software engineering is concerned with the concepts, principles, methods and software tools used in the design, implementation, evaluation, deployment, and maintenance of software and IT systems.

> Our research activities encompass theoretical foundations, software development tools and technology, and implementation and evaluation of software system prototypes.

The group has a particular strong research track record in the areas of model-driven software engineering, concurrent and distributed systems, software verification and testing, software quality and security, code refactoring, and software architecture.

Our research group is involved in several projects in the areas of health-care, embedded systems, robotics and industrial automation, internet-of-things and cloud computing services, machine learning, and automotive software systems.

Furthermore, we have research collaboration with many national and international research institutions, and several national and international companies:
the University of Extremadura (ES), the [University of Lübeck (DE)](https://www.isp.uni-luebeck.de), University of Oslo (NO), [the University of Stavanger (NO)](https://www.ux.uis.no/~meling/), and [the University of Torino (IT)](https://www.cs.unito.it/do/home.pl).

## Selected Research Projects

* [SFI Smart Ocean](https://sfismartocean.no): Technology for monitoring and management of a healthy and productive ocean. Work Package leader for Software Technology in Centre for Research-based Innovation.
* [CROFLOW](https://croflow.github.io): Enabling Highly Automated Cross-Organisational Workflow Planning. Funded by the Norwegian Research Council.
* [DYNAMIC](https://www.hvl.no/en/project/2495578/): Reducing Fire Disaster Risk through Dynamic Risk Assessment and Management. Funded by the Norwegian Research Council.
* [PiV](https://helse-bergen.no/piv/workflow-optimization): Pathology services in the Western Norway Health Region – a centre for applied digitization. Workpackage on Workflows. Funded by Helse Vest.
* [COEMS](https://coems.eu): Continuous Observation of Embedded Multicore Systems. An EU H2020 funded RIA project.
* [INTROMAT](https://intromat.no): Introducing Personalized Treatment of Mental Health Problems using Adaptive Technology. IKTPLUSS Lighthouse project funded by the Norwegian Research Council.

Our "institutional home" is <https://www.hvl.no/en/research/group/software-engineering/>.

## Group members
<!-- as per https://www.hvl.no/en/research/group/software-engineering/ -->
<!-- https://shopify.github.io/liquid/tags/control-flow/ -->

<!-- TODO: should check if /user/ exists if requested here -->
{%- for member in site.data.members -%}{%- if member.intext == "true" -%}
* <a name="{{ member.shortname }}" /> {% if member.moreinfohere == "true" -%} [{{ member.displayname }} ({{ member.title }})](/{{ member.shortname }}/) {%- else -%} {{ member.displayname }} ({{ member.title }})  {%- endif %} [[@ HVL](https://www.hvl.no/en/employee/?user={{member.urlname}})]
{%- unless member.extinfo == "" %} {{member.extinfo}} {% endunless %}
{% endif %} {% endfor %}

## External/part-time members

{%- for member in site.data.members -%}{% unless member.intext == "true" %}
* {{ member.displayname }} ({{ member.title }}) {{member.extinfo}}
{%- endunless -%} {% endfor %}

## PhD students

{% for member in site.data.stips -%}
* <a name="{{ member.displayname }}" />{{ member.displayname }} [[@ HVL](https://www.hvl.no/en/employee/?user={{member.urlname}})]
{%- unless member.extinfo == "" %} {{member.extinfo}} {% endunless %}
{% endfor %}
