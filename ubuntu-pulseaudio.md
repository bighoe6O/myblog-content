Title: Pulse Audio
Date: 2019-06-06 10:15
Status: published
Slug: ubuntu-pulseaudio
Category: Système
Tags: Système, Linux

Problème: Dans la console de mixage apparait seulement la sortie HDMI

<https://askubuntu.com/questions/69820/how-do-i-set-a-pulseaudio-card-profile-persistently-across-reboots>

# Sélectionner le profil de la carte audio

    pacmd set-card-profile 0 output:analog-stereo
    
Ajoût de la commande dans /etc/pulse/default.pa
