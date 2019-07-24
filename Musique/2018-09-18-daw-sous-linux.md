Title:  DAW sous Linux
Date:   2018-09-18 16:24:34 +0200
Category: Musique
Tags: Linux, MAO, DAW


## Synthétiseur midi

Timidity fonctionne mal

FluidSynth semble mieux fontionner

Fontes utilisées :

* <https://osdn.net/projects/sfnet_androidframe/downloads/soundfonts/SGM-V2.01.sf2/>

## Séquenceurs

* [Ardour](http://ardour.org/)
* [Manuel](http://manual.ardour.org/working-with-midi/)

## Accompagnement

### [Impro-Visor](https://www.cs.hmc.edu/~keller/jazz/improvisor/)

En java

### [LinuxBand](http://linuxband.org/)

Interface graphique à MMA

### [MMA](https://www.mellowood.ca/mma/) (Musical MIDI Accompaniment)

# Wine

<https://www.reddit.com/r/FL_Studio/comments/4ucx0i/tutorial_how_to_install_fl_studio_on_linux/>

## Kontakt5

Native Access

Crash (librairie qt5.2 manquante)

	ERROR: ld.so: object 'libgtk3-nocsd.so.0' from LD_PRELOAD cannot be preloaded (cannot open shared object file): ignored" 

<https://www.linuxquestions.org/questions/blog/the-dsc-472367/getting-rid-of-error-ld-so-object-libgtk3-nocsd-so-0-from-ld_preload-cannot-be-preloaded-cannot-open-shared-object-file-ignored-37823/>

	sudo apt-get install libgtk3-nocsd0:i386

<https://tehnick.github.io/q4wine/>

	sudo add-apt-repository ppa:tehnick/q4wine
	sudo apt-get install q4wine

<https://bugs.winehq.org/show_bug.cgi?id=44138>

<http://linuxmao.org/Wine+-+WineASIO>

<https://kxstudio.linuxaudio.org/Documentation:Manual:wineasio_and_reaper>
