---
layout: post
title: "Installing SDL2 on Ubuntu for Game Development"
date: 2013-10-12 16:00:00
tags: sdl2, game programming
---

I recently began game programming in C++ again, and I have decided to go
with [SDL2](http://www.libsdl.org) for the development library to start with. I chose SDL2
because it is cross-platform, and I enjoy using and developing on
Ubuntu. However, at the time of writing this, SDL2 has not been added to
apt-get for installation. This means that you have to install SDL2 from
source.

Here are the steps I took to install SDL2 on Ubuntu 13.04 from the source:

1. Download the SDL 2.0.0 source:
   http://www.libsdl.org/release/SDL2-2.0.0.tar.gz

2. Untar the source

  ```
  tar xvf SDL2-2.0.0.tar.gz  
  ```
3. `cd` into the repo

  ```
  cd SDL2-2.0.0.tar.gz
  ```
4. Execute configure
  ```
  ./configure
  ```
5. Run `make`
  ```
  make
  ```
6. Run `make installl`
  ```
  sudo make install
  ```

You should be all set to work with SDL2.

Don't forget to do the same for the other components of SDL you want to
work with:

* [SDL_image](http://www.libsdl.org/projects/SDL_image/) - for working with images
* [SDL_mixer](http://www.libsdl.org/projects/SDL_mixer/) - for working with audio
* [SDL_net](http://www.libsdl.org/projects/SDL_net/) - for working with networking
* [SDL_ttf](http://www.libsdl.org/projects/SDL_ttf/) - for working with TrueType Fonts

The process for installing them is the same, download the source and run
the same commands as above.

[SDL projects and libraries live here.](ttp://www.libsdl.org/projects/)

Note: if you are having issues getting SDL2 to compile on your machine
with a GPU, you may need to install the following packages:

```
sudo apt-get install build-essential xorg-dev libudev-dev libts-dev libgl1-mesa-dev libglu1-mesa-dev libasound2-dev libpulse-dev libopenal-dev libogg-dev libvorbis-dev libaudiofile-dev libpng12-dev libfreetype6-dev libusb-dev libdbus-1-dev zlib1g-dev libdirectfb-dev
```
