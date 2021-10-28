Title: Site: Installer un certificat SSL
Date: 2021-10-25 19:44
Status: published
Slug: Tech/2021-10-25-site-certificats-ssl
Tags: Site, Blog

<https://certbot.eff.org/lets-encrypt/debianstretch-apache>

## Installer snapd

    sudo apt install snapd

## S'assure que la version de snapd est à jour

    sudo snap install core; sudo snap refresh core
    
## Installer Cerbot

    sudo snap install --classic certbot

## Préparer la commande Certbot

    sudo ln -s /snap/bin/certbot /usr/bin/certbot
    
## Choisir comment installer Certbot

    sudo certbot --apache

Au bout de cinq erreurs, il faut attendre une heure il peut être préférable d'utiliser le [staging environment](https://letsencrypt.org/docs/staging-environment/)

    certbot --apache --dry-run
