Based on GhostFS https://github.com/raphaelsc/ghostfs by Raphael S.
Carvalho. I'm sincerely grateful for his help.

### The Lion ...
```
       #######
      ###   ###
     ### ^ ^ ###.-.-.-.-.´%%\
     ###  Y  ###%%%%%%%%%/ \%.
      ###`-´###%%%%%%%%%%\  %\
       #######%/%%%%%%%\%%\ ##
        \%\  \%\   /%/  /%/
._._._._##._.##_._##._.##_._._._._._
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
```
# lionfs (Link Over Network File System)

## What is it?

Use something like `ln -s http://website/file.ext local_file` and you will
have a local file that points to a network file. It is the purpose.

## How it works?

Basically we do the background when you call the *read()* operation in a
symlink created by lionfs and fill the data with the content received over
a http request to the host. We don't have cache.

## How do I install it?

First you will need **libfuse** library, which probably is already present
in your system.

NOTE: Currently we aren't using *make* because I don't known how to
implement it and I'm with RSI (pt-br LER), typing with only one hand.

Later you simply type `./compile-all.sh` in source directory and if all
goes right a binary called **lionfs** will be created. See next!

## How do I use it?

You will not execute the binary directly, instead you will execute a script
called `lion-mount.sh` which is found in the source directory too. Use
`lion-mount.sh --help` for more details.

NOTE: At the moment we don't have an install script and then you need to
execute the program in the source directory. Modules are default searched
in *./modules/* or *\<ld_library_paths\>/lionfs/modules/* directories.

## Supported protocols:

Only **HTTP**

----------

Any contribution is welcome :-)

Any question mail me at pasqualirb at gmail dot com
