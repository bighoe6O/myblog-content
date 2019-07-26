Title:  Génération des README.md pour les sketches arduino
Date:   2018-01-08 11:43:19 +0100
Tags: Electronique


```bash
for dir in *; do if [ -d "$dir" ]; then if [ ! -f "$dir/README.md" -a -f "$dir/$dir.ino" ]; then echo $dir;  cat README.tmpl | sed -e "s#@title@#$dir#" > $dir/README.md; fi; fi; done
```

README.tmpl

```
---
title: @title@
layout: inopage
---
```
