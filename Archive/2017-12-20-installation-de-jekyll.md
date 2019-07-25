Title:  "Installation de Jekyll"
Date:   2017-12-20 00:17:13 +0100
Tags: Jekyll

# Options du fichier de configuration

<https://jekyllrb.com/docs/configuration/options/>

# Installation sous linux

```
sudo apt-get install ruby ruby-dev ruby-bundler
sudo apt-get install libffi-dev

git clone ssh://git@duloup.org/myblog
cd myblog
bundle install
```

# Utilisation des tags

<https://dev.to/rpalo/jekyll-tags-the-easy-way>


# Problèmes

<https://stackoverflow.com/questions/39057405/unable-to-build-a-jekyll-site-invalid-date>

    exclude:
      - vendor

# Utilitaire permettant de générer des posts et des pages
(entre autres)

<https://github.com/gummesson/jekyll-rake-boilerplate>

# Framework Octopress

<https://github.com/imathis/octopress>

# Lancement sous windows

```dos
e:
cd e:/repo/myblog
bundle exec jekyll serve
```

# Admin

https://github.com/jekyll/jekyll-admin

Ajoût de la ligne suivante au fichier Gemfile

`gem 'jekyll-admin', group: :jekyll_plugins`

Installation du paquet

`bundle install --path vendor/bundle`
