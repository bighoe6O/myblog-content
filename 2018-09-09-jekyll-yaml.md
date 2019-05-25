---
layout: post
title:  "Jekyll: YAML"
date:   2018-09-09 07:04:49 +0200
category: Dev
tags: Jekyll, YAML
---

[YAML tutorial in the context of Jekyll](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_yaml_tutorial)

## Example 1: Simple mapping

```
name:
  husband: Tom
  wife: Shannon
```

{% raw %}
```
Husband's name: {{site.data.samplelist.name.husband}}

Wife's name: {{site.data.samplelist.name.wife}}
```
{% endraw %}

Husband's name: {{site.data.samplelist.name.husband}}

Wife's name: {{site.data.samplelist.name.wife}}

## Example 2: Line breaks

```
feedback: >
  This is my feedback to you.
  Even if I include linebreaks here,
  all of the linebreaks will be removed when the value is inserted.

block: |
  This pipe does something a little different.
  It preserves the breaks.
  This is really helpful for code samples,
  since you can format the code samples with
  the appropriate
```

{% raw %}
```
**Feedback**

{{site.data.samplelist.feedback}}

**Block**

{{site.data.samplelist.block}}
```
{% endraw %}

**Feedback**

{{site.data.samplelist.feedback}}

**Block**

{{site.data.samplelist.block}}

## Example 3: Simple list

```
bikes:
  - title: mountain bikes
  - title: road bikes
  - title: hybrid bikes
```

{% raw %}
```
{% for item in site.data.samplelist.bikes %}* {{item.title}}
{% endfor %}
```
{% endraw %}

{% for item in site.data.samplelist.bikes %}* {{item.title}}
{% endfor %}

## Example 4: List items

YAML:

```
salesteams:
- title: Regions
 subfolderitems:
   - location: US
   - location: Spain
   - location: France
```

{% raw %}
```
{% for item in site.data.samplelist.salesteams %}
### {{item.title}}
{% for entry in item.subfolderitems %}* {{entry.location}}
{% endfor %}
{% endfor %}
```
{% endraw %
}
{% for item in site.data.samplelist.salesteams %}
### {{item.title}}
{% for entry in item.subfolderitems %}* {{entry.location}}
{% endfor %}
{% endfor %}

## Example 5: Table of contents

```
toc:
  - title: Group 1
    subfolderitems:
      - page: Thing 1
      - page: Thing 2
      - page: Thing 3
  - title: Group 2
    subfolderitems:
      - page: Piece 1
      - page: Piece 2
      - page: Piece 3
  - title: Group 3
    subfolderitems:
      - page: Widget 1
      - page: Widget 2 it's
      - page: Widget 3
```

{% raw %}
```
{% for item in site.data.samplelist.toc %}
### {{item.title}}
{% for entry in item.subfolderitems %}* {{entry.page}}
{% endfor %}
{% endfor %}
```
{% endraw %}

{% for item in site.data.samplelist.toc %}
### {{item.title}}
{% for entry in item.subfolderitems %}* {{entry.page}}
{% endfor %}
{% endfor %}

## Example 6: Variables

{{ site.data.samplelist.myref }}

##Example 7: Positions in lists
### YAML

```
about:
 - zero
 - one
 - two
 - three
```

### Markdown

```
{{ site.data.samplelist.about[0] }}
```

{{ site.data.samplelist.about[0] }}

## Example 8: Properties from list items at specific positions

### YAML:

```
numbercolors:
 - zero:
   properties: red
 - one:
   properties: yellow
 - two:
   properties: green
 - three:
   properties: blue
```

### Markdown + Liquid:

{% raw %}
```
{{ site.data.samplelist.numbercolors[0].properties }}
```
{% endraw %}

{{ site.data.samplelist.numbercolors[0].properties }}

## Example 9: Conditions

### YAML:

```
mypages:
- section1: Section 1
  audience: developers
  product: acme
  url: facebook.com
- section2: Section 2
  audience: writers
  product: acme
  url: google.com
- section3: Section 3
  audience: developers
  product: acme
  url: amazon.com
- section4: Section 4
  audience: writers
  product: gizmo
  url: apple.com
- section5: Section 5
  audience: writers
  product: acme
  url: microsoft.com
```

### Markdown + Liquid:

{% raw %}
```
{% for sec in site.data.samplelist.mypages %}{% if sec.audience == "writers" %}* {{sec.url}}
{% endif %}{% endfor %}
```
{% endraw %}

{% for sec in site.data.samplelist.mypages %}{% if sec.audience == "writers" %}* {{sec.url}}
{% endif %}{% endfor %}

{% raw %}
```
{% for sec in site.data.samplelist.mypages %}{% if sec.audience == "writers" and sec.product == "gizmo" %}* {{sec.url}}
{% endif %}{% endfor %}
```
{% endraw %}

{% for sec in site.data.samplelist.mypages %}{% if sec.audience == "writers" and sec.product == "gizmo" %}* {{sec.url}}
{% endif %}{% endfor %}

