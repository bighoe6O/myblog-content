Title: Jekyll: Publish to site
Date: 2018-09-20 14:33:42 +0200
Tags: Jekyll, Git


<https://www.inmotionhosting.com/support/website/jekyll/how-to-publish-a-jekyll-site-with-git>

hooks/post-receive

	#!/bin/sh
	git --work-tree=/e/repo/myblog-site --git-dir=/e/repo/myblog.git checkout -f
	


## Installation de gitolite

<http://gitolite.com/gitolite/>

### steps to install

First, prepare the ssh key:

* login to "git" on the server
* make sure ~/.ssh/authorized_keys is empty or non-existent
* make sure your ssh public key from your workstation has been copied as $HOME/YourName.pub

Next, install gitolite by running these commands:

	git clone https://github.com/sitaramc/gitolite
	mkdir -p $HOME/bin
	gitolite/install -to $HOME/bin

Finally, setup gitolite with yourself as the administrator:

	gitolite setup -pk YourName.pub
	
Création d'un dépôt
	
	cd repositories/
	mkdir myblog.git
	cd myblog.git
	git init --bare
	
Clonage du dépôt principal
	
	git clone gittest@duloup.org:myblog
	cd myblog

Push dans le nouveau dépôt

	git push ~/repositories/myblog.git
	
Fichier /home/git/repostitories/myblog.git/hooks/post-receive

	#!/bin/sh
	umask 002
	git --work-tree=/home/git/myblog --git-dir=/home/git/repositories/myblog.git checkout -f

Rendre le fichier exécutable

	chmod +x /home/git/repostitories/myblog.git/hooks/post-receive
	
Editer la configuration (depuis le client)

	git clone git@pi0:gitolite-admin
	
Editer le fichier conf pout ajouter le nouveau dépôt

Installer Ruby et Jekyll
	
	sudo apt-get install ruby ruby-dev
	sudo gem install jekyll
	
Lancer le serveur Jekyll

	cd myblog
	bundle exec jekyll serve --incremental

Tester le service

	http://pi0:4000/

<https://www.booleanworld.com/get-unix-linux-environment-windows-msys2/>

	ufw --dry-run allow in 4000/tcp
	ufw allow in 4000/tcp

	bundle install --path vendor/bundle
	
	bundle exec jekyll serve -B

Lancement du serveur

	cd public_html
	bundle exec jekyll serve --incremental --force-polling -B -H 0.0.0.0 > ~/jekyll.out 2>&1

Passage sous apache, le serveur jekyll ne prenant pas en compte les modifications

	bundle exec jekyll build --incremental --watch

<https://davidegan.me/hide-git-repos-on-public-sites/>

## Problèmes de cache persistant sous apache

```
<IfModule mod_expires.c>
  # Turn on the module.
  ExpiresActive on
  # Set the default expiry times.
  ExpiresByType text/html "modification plus 5 seconds"
  ExpiresByType text/javascript "modification plus 5 seconds"
  ExpiresDefault "access plus 2 days"
</IfModule>
```
