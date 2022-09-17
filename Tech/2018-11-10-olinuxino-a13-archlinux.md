Title: Olinuxino: Installation d'une ArchLinux
Date:   2018-11-10 00:02:32 +0100
Tags: Olinuxino, Linux, MiniPC


<https://archlinuxarm.org/platforms/armv5/olinuxino>

<https://aur.archlinux.org/packages/uboot-a13-olinuxino/>

<https://elementztechblog.wordpress.com/2014/05/11/installing-xfce-desktop-in-archlinux-for-olinuxino/>

<https://archlinuxarm.org/platforms/armv7/allwinner/a20-olinuxino-micro>

# Installation de ArchLinux sur une carte SD

Pas besoin de compiler, tout est disponible

	sudo dd if=/dev/zero of=/dev/mmcblk0 bs=1M count=8
	sudo fdisk /dev/mmcblk0
	sudo mkfs.ext4 /dev/mmcblk0p1
	mkdir mnt
	sudo mount /dev/mmcblk0p1 mnt/
	wget http://de4.mirror.archlinuxarm.org/os/sunxi/boot/a13-olinuxino/u-boot-sunxi-with-spl.bin
	sudo dd if=u-boot-sunxi-with-spl.bin of=/dev/mmcblk0 bs=1024 seek=8
	sudo wget http://de4.mirror.archlinuxarm.org/os/sunxi/boot/a13-olinuxino/boot.scr -O mnt/boot/boot.scr
	sudo tar zxf ArchLinuxARM-armv7-latest.tar.gz -C mnt/
	sudo umount mnt
	sync


```
# /etc/netctl/wireless-wpa
Description='A simple WPA encrypted wireless connection'
Interface=wlan0
Connection=wireless

Security=wpa
IP=dhcp

ESSID='Livebox-DF4A'
# Prepend hexadecimal keys with \"
# If your key starts with ", write it as '""<key>"'
# See also: the section on special quoting rules in netctl.profile(5)
Key='3A2CDCFDFD5561F347C9DF3556'
# Uncomment this if your ssid is hidden
#Hidden=yes
# Set a priority for automatic profile selection
#Priority=10
```

    # /etc/dhcpd.conf
	#noipv4ll
	
Fonctionne ...

## Problème pacman gpg lors de l'installation de paquets

	error: failed to synchronize any databases
	error: failed to init transaction (invalid or corrupted database (PGP signature))
	
Solution:

	pacman-key --populate archlinuxarm

## Samba

	pacman -S samba

Copie de pi0:/etc/samba/smb.conf

	useradd -m stephane
	usermod -G users -a stephane
	smbpasswd -a stephane

	systemctl enable smb nmb
	systemctl start smb nmb
	
## swap

	sudo fallocate --length 1GiB /swapfile
	sudo mkswap /swapfile

    # /etc/fstab
    # <file system> <dir> <type> <options> <dump> <pass>
    /swapfile none            swap    sw              0       0	

## Compilation du noyau

<https://archlinuxarm.org/forum/viewtopic.php?t=6419>

<https://github.com/archlinuxarm/PKGBUILDs.git>

<https://wiki.archlinux.org/index.php/Kernel/Arch_Build_System>

	$ cd ~/
	$ mkdir build
	$ cd build/
	$ asp update linux
	$ asp checkout linux

	# linux/trunk/PKGBUILD
	pkgbase=linux-custom

	updpkgsums	
	makepkg -s
	

## locales

	tmux: need UTF-8 locale (LC_CTYPE) but have ANSI_X3.4-1968

	/etc/locale.gen
	sudo locale-gen
	sudo localectl set-locale LANG=fr_FR.UTF-8

## GPIO

<https://linux-sunxi.org/GPIO#Example:_Controlling_GPIO_on_Olimex.27s_A13-OLinuXino_.28sunxi-3.4.29>

