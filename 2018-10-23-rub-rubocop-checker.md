---
layout: post
title:  rub-rubocop-checker
date:   2018-10-23 09:36:31 +0200
category: Jekyll
tags: [Dev, Ruby, Jekyll]
---

[GitHub](https://github.com/rubocop-hq/rubocop/blob/master/config/default.yml)

[Configuration](https://rubocop.readthedocs.io/en/latest/configuration/)

```yaml
# .rubocop.yml
# inherit_from: ../.rubocop.yml

Style/Encoding:
  Enabled: false

Metrics/LineLength:
  Max: 99

Metrics/MethodLength:
  Max: 99

Metrics/AbcSize:
  Max: 49

Layout/EndOfLine:
  EnforcedStyle: lf
```
