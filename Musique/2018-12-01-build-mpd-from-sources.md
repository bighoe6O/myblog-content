Title:  Build MPD from sources
Date:   2018-12-01 11:44:54 +0100
Tags: MPD, Players


<https://www.musicpd.org/>

[Forum](https://forum.musicpd.org/)

# Sous Ubuntu

<http://taudac.com/building-mpd-from-source/>

## Messon build system

<https://github.com/mesonbuild/meson>

    pipenv install meson

<https://www.musicpd.org/doc/html/user.html>

<https://github.com/MusicPlayerDaemon/MPD>

    # git clone https://github.com/MusicPlayerDaemon/MPD

    wget https://www.musicpd.org/download/mpd/0.21/mpd-0.21.3.tar.xz
    xz -dc mpd-0.21.3.tar.xz | tar xf -
    cd mpd-0.21.3
    meson . output/release --buildtype=debugoptimized -Db_ndebug=true
    meson configure output/release
    ninja -C output/release
    ninja -C output/release install

## Raspberry PI

    sudo apt-get install g++ libboost-dev libicu-dev libglib2.0-dev
    
    sudo apt-get install libsqlite3-dev libmpdclient-dev libexpat1-dev \
    libid3tag0-dev libflac-dev libaudiofile-dev libmad0-dev libmp3lame-dev \
    libasound2-dev libcurl4-gnutls-dev libsystemd-dev
## Qobuz

<https://github.com/Qobuz/api-documentation/blob/master/endpoints/track/getFileUrl.md#parameters>

# Pour Android

<https://developer.android.com/studio/install>

# Compilation croisée pour raspberry-pi

