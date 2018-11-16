# SWI-Prolog on Android

This repository contains pre-built packages for [SWI-Prolog](http://swi-prolog.org/) on [termux](https://termux.com/). When SWI-Prolog is officially added to termux we will delete this repository.

:grin: Quick'n Easy start
-------------------------------
1. Install [termux](https://termux.com/) on your android device
2. Start termux, and type the following in the terminal:
```sh
wget -O - https://raw.githubusercontent.com/erlanger/swipl-termux/master/install | sh
```
3. Done! :tada:
4. Now run it, typing this in the termux terminal:
```
$ swipl
Welcome to SWI-Prolog (threaded, 32 bits, version 7.7.21)
SWI-Prolog comes with ABSOLUTELY NO WARRANTY. This is free software.
Please run ?- license. for legal details.

For online help and background, visit http://www.swi-prolog.org
For built-in help, use ?- help(Topic). or ?- apropos(Word).

?- write('Hello, swipl on Android!').
Hello, swipl on Android!
true.

```

---
The [install script.](https://raw.githubusercontent.com/erlanger/swipl-termux/master/install) does the following:
1. Download the latest termux debian package from this repository
2. Install this package on your device
---
:construction: Building it yourself
-----------------------

SWI-Prolog for android is built with the docker file used by `termux` to build packages.

The erlanger termux-packages repository contains the patches and scripts to build the SWI-Prolog `deb` file for Android.

The docker file will be downloaded automatically. SWI-Prolog library dependencies  will also be downloaded automatically into the docker container.

To build the deb files yourself, do the following:
```sh
git clone https://github.com/erlanger/termux-packages
cd termux-packages
./scripts/run-docker.sh ./build-package.sh -a arm -f swi-prolog
```

You should now have the  `.deb` files in the `debs` directory.
