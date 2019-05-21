---
layout: post
title:  mysensors
date:   2018-09-23 21:16:35 +0200
category: Dev
---

[MySensors](https://www.mysensors.org/)

[Mosquitto MQTT Broker](https://mosquitto.org/)

[Domoticz](https://domoticz.com/)

[Node-Red](https://nodered.org/)


## Carte SD du pi

Montage de l'image

<https://askubuntu.com/questions/69363/mount-single-partition-from-image-of-entire-disk-device>

```
stephane@stephane-PC:/opt/sata/stephane$ fdisk -l pi-sd.img 
Disque pi-sd.img : 7,4 GiB, 7948206080 octets, 15523840 secteurs
Unités : secteur de 1 × 512 = 512 octets
Taille de secteur (logique / physique) : 512 octets / 512 octets
taille d'E/S (minimale / optimale) : 512 octets / 512 octets
Type d'étiquette de disque : dos
Identifiant de disque : 0x881f5fa7

	Périphérique Amorçage Début      Fin Secteurs Taille Id Type
	pi-sd.img1             8192    93813    85622  41,8M  c W95 FAT32 (LBA)
	pi-sd.img2            94208 15523839 15429632   7,4G 83 Linux

	imgstart=48234496
	sudo losetup -o $imgstart /dev/loop0 pi-sd.img
	sudo mount /dev/loop0 /mnt
```	

/etc/init.d/domoticz.sh

	OPTIONS="-www 8080 -loglevel=1 -log /tmp/domoticz.log"
	DAEMON_ARGS="$DAEMON_ARGS -sslwww 443"
	DAEMON_ARGS="$DAEMON_ARGS -log /tmp/domoticz.log"

