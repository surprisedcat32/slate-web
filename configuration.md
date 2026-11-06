# Configuration

Slate stores its system configuration under `/etc/slate.conf/`.

## Repositories

The repository configuration is:

`/etc/slate.conf/repos`

Each entry defines a repository URL and the version to use.

Example:

`https://github.com/surprisedcat32/slate-ports.git 0.6`

Repositories can also use special version identifiers.

- `current` uses the version specified in `/etc/slate.conf/ver`.
- `testing` tracks the repository main branch.

Repositories are checked in configuration order. Earlier repositories take priority when duplicate packages are available.

## Version

The installed Slate version is stored in:

`/etc/slate.conf/ver`

## Build Options

Build options are stored in:

`/etc/slate.conf/makeopts`

For example:

`MAKETHREADS=4`

The package manager passes this setting to port scripts. Individual ports decide how to use it.

## Package Manager Configuration

The package manager supports selecting a sysroot and enabling options such as silent installation and forced removal.

See [Package Manager](package-manager.md) for details.

