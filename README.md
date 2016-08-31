# MSYS2 Wine Wrapper

The goal of this humble script is to simplify installation and management of
MSYS2 under Wine. 

Although it might seem easy to use, you are still likely to
hit a few bugs here and there. Please see the following wiki for more info on
MSYS2 under wine, in case you need to tune something manually:

https://github.com/fracting/wine-fracting/wiki/MSYS2-on-Wine

Feel free to post issues, I will try to incorporate fixes and/or workarounds
into this script. However, I'm no wine expert and all bugs should still be
reported upstream.

## Prerequisites

 - recent version of Wine Staging (tested with 1.9.17):
 - Perl (any version will do)
 - wget (any version will do)

## How to use it

There is help available in the program, just run `./msysww -h`. But the basic
workflow looks like this:
```
./msysww --init
./msysww -c
```
Now you've got MSYS shell in your hands. You can run pacman and do other stuff,
as you're used to. If you need the MINGW64 environment, just run:

```
./msysww --shell=mingw64 --console
```

Or if you want 32bit environment:

```
./msysww --arch=i686 --init
./msysww --arch=i686 -c
```

You can have both `i686` and `x86_64` variants installed, `x86_64` is the default.

If you screwed up, just delete `msys64` or `msys32` in `~/.msysww/drive_c`, you
usually won't need to delete the whole prefix. However if you have to you might
want to store `drive_c/pkgcache`, as it contains downloaded packages (shared
across `i686` and `x86_64` versions).

## Credits

This script was made thanks to the TeaCI project by Qian Hong
(@fracting). Without it, MSYS2 would probably not work under wine at all!

Moreover, I took a lot of inspiration from his docker scripts, located in
TeaCI/msys2-docker repository.


