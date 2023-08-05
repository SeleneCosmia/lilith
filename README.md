## Note:
> This is a **HUGE** project, and the original hasn't been updated for a few years.
>    
> ... So what *are* my goals with this project?      
> For the most part, this is being used as a learning experience for myself,     
> I don't intend to dedicate most of my time to this project for quite some time, 
> so expect this to stay stale for the time being.
>
## 
Once I am able I intend to do the following:

- [ ] Update the code-base to Crystal v1.10.* (or later)
- [ ] Determine whether the parts coded in C can now be transitioned into crystal, and if so, update it accordingly
- [ ] Rewrite the window manager and:
  - [ ] Transition it to Wayland <sup>maybe?</sup>
  - [ ] Allow configuration in lua or another similarly easy to use scripting lang
- [ ] Write a shell in crystal to support the os with [fish-shell](https://fishshell.com) like features
- [ ] and other features yet to be determined...



## lilith


A POSIX-like x86-64 kernel and userspace written in Crystal.

## Screenshot

![screenshot](https://raw.githubusercontent.com/ffwff/lilith/master/img/05012020.png "screenshot of lilith")

## Building

See [BUILDING.md](./BUILDING.md).

## Running

A CPU with x64 support is required to run the OS. The Makefile provides a script which will run QEMU on the kernel:

```
make run
```

To run with storage, an MBR-formatted hard drive image with a FAT16 partition must be provided in the running directory with the name `drive.img`. The kernel will automatically boot the `main.bin` executable on the hard drive, or panic if it can't be loaded.

Issue this command to run with gdb attached:

```
make rungdb_img
```

## Features

* Basic x86-64 support
* Hybrid conservative-precise incremental garbage collector
* IDE/ATA support (well, it can only load from primary master)
* FAT16 support
* Unix syscalls (open, read, write, spawn,...)
* Preemptive multitasking!
* Userspace C library written in Crystal (mostly)
* A window manager and some graphical programs (terminal emulator, file manager)

## License

Lilith is licensed under MIT. See [LICENSE](./LICENSE) for more details.
