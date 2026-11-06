# Building Slate

This document describes the basic build environment used for Slate Linux.

## Requirements

A working Linux build environment is required.

The build environment should include:

- Git
- Make
- CMake
- GCC
- Binutils
- musl toolchain
- Standard build utilities

## Toolchain

Slate uses a musl cross-compilation toolchain.

The current compiler executable is:

`x86-linux-musl-gcc`

The toolchain is located in `~/toolchain`.

## Sysroot

The Slate sysroot is located at:

`~/distro/sysroot`

The sysroot contains the filesystem being assembled for the distribution.

## Building

Ports are used to compile and install software into the sysroot.

The package manager supports a custom sysroot using:

`slate --sysroot DIR install category/package`

## Build Threads

Slate reads build options from:

`/etc/slate.conf/makeopts`

The `MAKETHREADS` setting is passed to port scripts. Ports must use this variable when invoking parallel builds.

For example:

`make -j"$MAKETHREADS"`

## ISO

The ISO build process assembles the sysroot, initramfs, kernel, and bootloader files into a bootable image.

Refer to the build scripts in the Slate repository for the current image creation procedure.

