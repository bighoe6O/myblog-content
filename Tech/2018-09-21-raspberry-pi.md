Title:  raspberry-pi
Date:   2018-09-21 20:38:33 +0200
Slug: tech-pi
Tags: Pi, MiniPC
Category: MiniPC


[Forcer un fsck au boot](https://raspberrypi.stackexchange.com/questions/61723/raspberry-pi-3-and-raspbian-jessie-how-to-run-fsck-at-boot)

[Raspberry Pi and realtime, low-latency audio](https://wiki.linuxaudio.org/wiki/raspberrypi)

[Raspberry Pi Going Realtime with RT Preempt](http://www.frank-durr.de/?p=203)

[#Raspberry Pi: Real Time System - Preempt-RT Patching Tutorial for Kernel 4.14.y ](https://lemariva.com/blog/2018/07/raspberry-pi-preempt-rt-patching-tutorial-for-kernel-4-14-y)

	~/rpi-kernel$ export ARCH=arm
	~/rpi-kernel$ export CROSS_COMPILE=~/rpi-kernel/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian/bin/arm-linux-gnueabihf-
	~/rpi-kernel$ export INSTALL_MOD_PATH=~/rpi-kernel/rt-kernel
	~/rpi-kernel$ export INSTALL_DTBS_PATH=~/rpi-kernel/rt-kernel

	export ARCH=arm
	export CROSS_COMPILE=~/rpi-kernel/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian/bin/arm-linux-gnueabihf-
	export INSTALL_MOD_PATH=~/rpi-kernel/rt-kernel
	export INSTALL_DTBS_PATH=~/rpi-kernel/rt-kernel
	export CROSS_COMPILE=~/rpi-kernel/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian-x64/bin/arm-linux-gnueabihf-


Rasbperry Pi 1/1.2 B(+), A(+), Zero (W):

    ~/rpi-kernel$ export KERNEL=kernel
    ~/rpi-kernel$ cd ~/rpi-kernel/linux/
    ~/rpi-kernel/linux/$ make bcmrpi_defconfig
	
export KERNEL=kernel
cd ~/rpi-kernel/linux/
make bcmrpi_defconfig
	

Rasbperry Pi 2, 3 B(+):

    ~/rpi-kernel$ export KERNEL=kernel7
    ~/rpi-kernel$ cd ~/rpi-kernel/linux/
    ~/rpi-kernel/linux/$ make bcm2709_defconfig

<https://github.com/raspberrypi/userland>

<https://blog.georgmill.de/2015/02/18/update-for-wolfson-audio-card-on-raspberry-pi/>

Configuration du wifi

<https://kerneldriver.wordpress.com/2012/10/21/configuring-wpa2-using-wpa_supplicant-on-the-raspberry-pi/>

<https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md>

Carte audio Wolfson 

<https://blog.georgmill.de/2015/02/18/update-for-wolfson-audio-card-on-raspberry-pi/>

Noyau basse latence

<https://hackaday.io/project/123415-real-time-kernel-preempt-rt-for-raspberry-pi/details>

Audio

<https://wiki.linuxaudio.org/wiki/raspberrypi>
