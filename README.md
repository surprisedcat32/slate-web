# Slate Linux

Slate is a lightweight Linux distribution built around musl, sinit, and a custom package manager.

## Documentation

- [System overview](./system.md)
- [Boot process and initramfs](./boot.md)
- [Init system](./init.md)
- [Services](./services.md)
- [Networking](./networking.md)
- [System configuration](./configuration.md)
- [Package manager](./package-manager.md)
- [Ports layout](./ports-layout.md)
- [Creating and maintaining ports](./ports.md)
- [Building software](./building.md)
- [Installation](./installation.md)
- [Troubleshooting](./troubleshooting.md)

## Features

- musl libc
- Custom package manager
- Source-based ports collection
- Multiple repository support
- Minimal default installation
- X11 support
- Lightweight software selection
- Cross-compilation support
- Custom initramfs
- Shell-based initialization

## Package Management

Install a package:

    slate install <category>/<package>

Uninstall a package:

    slate uninstall <category>/<package>

List categories or packages in a category:

    slate list [<category>]

List installed packages:

    slate installed

Update repository information:

    slate update

## Configuration

The package manager repository configuration is stored in:

    /etc/slate.conf/repos

Repository entries contain a Git URL and a release tag or testing selection.

## Ports

Slate uses a ports collection to build software from source.

Ports are stored under /usr/ports and organized into categories. Each package has its own directory containing a port.sh script.

## System

Slate uses musl as its C library and sinit for system initialization.

The system is intentionally minimal. Software and services are provided without requiring everything to be installed or enabled by default.

This documentation describes Slate Linux and its 0.6 development direction.
