# System Overview

Slate Linux is a minimal Linux distribution built around a simple userspace and a collection of independently maintained ports.

## Design

Slate follows a DIY philosophy. The base installation provides the essentials, while additional software is installed by the user.

The system avoids unnecessary dependencies and does not require a particular desktop environment.

## Components

### Userspace

Slate uses musl as its C library and provides standard utilities through its installed userspace packages.

### Package Manager

The Slate package manager installs and removes software from configured ports repositories.

### Ports

Software is built from shell-based port scripts. Ports download source archives, configure packages, compile them, and install their files into a staging directory.

### Init System

Slate uses a custom shell-based initialization system based on `/bin/rc.init` and scripts in `/etc/init.d/`.

### Boot

The initramfs uses Toybox utilities and Slate boot programs to locate and mount the root filesystem before switching into the installed system.

### Graphics

Slate supports X11. Desktop environments and window managers are installed separately.

## Philosophy

Slate is intended to remain small, understandable, and customizable. Users choose what software they install and how they configure their systems.

