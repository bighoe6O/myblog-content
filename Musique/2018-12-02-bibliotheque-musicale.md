Title:  Bibliotheque musicale
Date:   2018-12-02 23:00:45 +0100
Category: Musique
Tags: MPD, Players


## Suppression des doublons de la bibliothèque

<https://github.com/worldveil/dejavu>

## Raspberry PI

* Utilisation de la carte Cirrus Logic
* installation de mpd
## conversion de la bibliothèque au format ogg-vorbis

```
#!/usr/bin/env python3
# music-flac2ogg.py

from os import path
import os
import subprocess

MPD_LIBRARY = os.environ['MPD_LIBRARY']
OGGDIR = '/media/stephane/BUFFALO/OGG'

if not path.isdir(MPD_LIBRARY):
    raise Exception("directory not found: " + MPD_LIBRARY)

FLACDIR = MPD_LIBRARY

if not path.isdir(FLACDIR):
    raise Exception("directory not found: " + FLACDIR)

if not path.isdir(OGGDIR):
    raise Exception("directory not found: " + OGGDIR)


for root, dirs, files in os.walk(FLACDIR):
    for myfile in files:
        # process(os.path.join(root, file))
        # os.remove(os.path.join(root, file))
        if myfile.endswith('.flac'):
            oggdir = root.replace(FLACDIR, OGGDIR)
            flacfile = path.join(root, myfile)
            oggfile = path.join(oggdir, myfile.replace('.flac', '.ogg'))
            if not path.isfile(oggfile):
                print(oggfile)
                if not path.isdir(path.dirname(oggfile)):
                    os.makedirs(path.dirname(oggfile))
                print("oggenc -q 6 -o '{:s}' '{:s}'".format(oggfile, flacfile))
                subprocess.run(['oggenc', '-q', '6', '-o', oggfile, flacfile])
```

## Vérification de la présence du fichier source flac pour les fichiers ogg

But: éviter les doublons ogg en cas de renommage des fichiers sources flac

```
#!/usr/bin/env python3
# music-ogg-check.py

from os import path
import os
import subprocess

MPD_LIBRARY = os.environ['MPD_LIBRARY']

if not path.isdir(MPD_LIBRARY):
    raise Exception("directory not found: " + MPD_LIBRARY)

# FLACDIR = path.join(MPD_LIBRARY, 'Librairie')
FLACDIR = MPD_LIBRARY
OGGDIR = '/media/stephane/BUFFALO/OGG'
# FLACDIR = '/home/stephane/Dev/Projets/flac'
# OGGDIR = '/home/stephane/Dev/Projets/ogg'


if not path.isdir(FLACDIR):
    raise Exception("directory not found: " + FLACDIR)

if not path.isdir(OGGDIR):
    raise Exception("directory not found: " + OGGDIR)


for root, dirs, files in os.walk(OGGDIR):
    for myfile in files:
        # process(os.path.join(root, file))
        # os.remove(os.path.join(root, file))
        if myfile.endswith('.ogg'):
            oggfile = path.join(root, myfile)
            flacdir = root.replace(OGGDIR, FLACDIR)
            flacfile = path.join(flacdir, myfile.replace('.ogg', '.flac'))
            if not path.isfile(flacfile):
                print("{:s} not found. removing...".format(flacfile))
                os.remove(oggfile)
```

## Synchronisation de la bibliothèque sur le Raspberry Pi

```
#!/bin/bash
# music-rsync-pi.sh

cd /media/stephane/BUFFALO/OGG/ && rsync -avr --delete . pi@192.168.1.15:mpdmusic/
```
