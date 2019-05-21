---
layout: post
title:  developper-un-plugin-jekyll
date:   2018-10-07 08:03:02 +0200
category: Jekyll
tags: [Jekyll]
---

<https://tuananh.org/2014/08/04/writing-your-first-jekyll-plugin/>

```
module Jekyll
  module Checked
    def checked(text)
      text.sub(%r{\[x\]}i, '<span class="ballot_box_with_check"></span>').sub(%r{\[\]}i, '<span class="ballot_box"></span>')
    end
  end
end

Liquid::Template.register_filter(Jekyll::Checked)
```

Groupement des scans par mot clé (keyword)

<https://www.marktrapp.com/blog/2014/01/07/group-posts-jekyll-front-matter/>
