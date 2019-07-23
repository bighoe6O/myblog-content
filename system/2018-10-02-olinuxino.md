---
layout: post
title:  olinuxino
date:   2018-10-02 16:55:28 +0200
updated: 2018-11-09 11:11:01 +0100
category: Dev
tags: [Olinuxino]
---

<https://www.olimex.com/Products/OLinuXino/A13/A13-OLinuXino/>

<https://www.olimex.com/Products/OLinuXino/A13/A13-OLinuXino/resources/A13-Brief.pdf>

<http://shawnhymel.com/87/getting-wifi-working-on-the-a13-olinuxino-micro/>

<https://www.olimex.com/wiki/index.php?title=Configuration_of_hardware_in_the_debian_image>

<https://linux-sunxi.org/Sunxi-tools>

	git clone https://github.com/linux-sunxi/sunxi-tools
	sudo apt-get install libusb-1.0
	make tools

<https://linux-sunxi.org/Olimex_A13-OLinuXino>

GPIO

<https://olimex.wordpress.com/2012/10/23/a13-olinuxino-playing-with-gpios/>

<https://web.archive.org/web/20140502013613/http://www.allwinnertech.com/en/clq/processora/2014/0223/266.html>

# Autres images

<https://en.opensuse.org/HCL:A13-OLinuXino>

# Création d'une image

Compilation du noyau

<https://www.olimex.com/wiki/Build_Bootable_SD_Card_with_Debian#Setup_of_the_toolchain>

	sudo apt-get install gcc-arm-linux-gnueabihf
	
Nécessite un gcc-4, complètement obosolète, n'est plus présent dans les dépôts

[Wiki U-Boot](https://github.com/linux-sunxi/u-boot-sunxi/wiki)

<https://github.com/linux-sunxi/u-boot-sunxi/tree/lichee/a1x-stable>

	make 'A13-OLinuXino' CROSS_COMPILE=arm-linux-gnueabihf-

Erreurs de compilation

<https://archlinuxarm.org/wiki/Distcc_Cross-Compiling>

[Installation d'une ArchLinux](/dev/2018/11/10/olinuxino-a13-archlinux.html)
