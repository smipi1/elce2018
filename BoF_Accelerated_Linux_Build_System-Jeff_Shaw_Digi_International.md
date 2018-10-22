# BoF: Accelerated Linux Build System - Jeff Shaw, Digi International

* Eraly days:
** Hard work
** Nothing for free
** Roll-your-own
* Distros

## Source distros

* Custom optimised kernel and apps
* Slow
* Ready made solutions?
* Off-course you can:
** Most of the time

## Popular systems

Yocto
* Steep learning curve
* Build times
* Resource use

Buildroot
* Simple, efficient, ...
* Single-target

## Accelerated Linux

Hist:
* uClinux evolved
* Created 1998
* Predates Buildroot by 3 years

Features:
* MMU / non-MMU
* Large nos of targets

Bottom-up methodology:
* Start with nothing
* Target
* Customize kernel
* Libc
* Config libc
* Packages
* F/W images

Single make command
* Config, compile and create image

Dependency checking
* KConfig

Customization
* make menucconfig

Optimised for
* Static devices
* Embedded
* No target package management
* Resource-limited

Small images

Root directory `$(ROOTDIR)`
* Documentation
* `REAMDE`
* `Makefile`

Four main source dirs
* `linux` - kernel
* `lib` - common libs
* `user` - public packages

Each dir
* `Makefile`

Non-source
* `vendors` - target configs
* `config` - current config
* `tools` - compilation / verification tools

Transient dirs
* `romfs` - ROM rootfs
* `images` - FW
* `staging` - cached apps / libs

Toolchain
* Not compiled as part of build
* Supplied for N targets
* 3rd party support

Advantages
* Reproducibility
* Simplicity
* ...

Open development
* No hardware
* QEMU

Single make command:

    make ${vendor}/${product}_default

* Target clean to image

Default compilation
* Fully parallelised + sync points
* Can make finding errors difficult

Custom compilation

    make single

Incremental build

During development
* Spec single area to recompile
* Single package/dir
* No target file-system update
* No firmware image rebuild

Update target FS

    make user_romfs

Regen image

    make image

Vendors and products
* `${ROOTDIR}/cendors/${vendor}/${product}`

Package types
* In-tree source files, built in place
* Automake, download and build when required

Build times
* Small target - 2 min, 3.5 MB
* Medium - 10 min, 14 MB
* Large - 14 min, 24 MB

Build PC
* 17 targets, 6 h 6 min

Nightly
* 147 targets, ...

https://github.com/AcceleratedLinux


