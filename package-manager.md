# Package Manager

Slate uses its own package manager to install, remove, and manage software from ports repositories.

## Commands

### Install

Install a package:

`slate install category/package`

### Uninstall

Remove a package:

`slate uninstall category/package`

Force removal:

`slate uninstall --force category/package`

### List

List available packages:

`slate list`

List packages in a category:

`slate list category`

### Installed

List installed packages:

`slate installed`

### Search

Search for packages:

`slate search package`

### Update

Update configured repositories:

`slate update`

Update the installed Slate version information:

`slate update-version`

## Options

| Option | Description |
| --- | --- |
| `--sysroot DIR` | Select a target sysroot |
| `-S DIR` | Short form of `--sysroot` |
| `--force` | Force package removal |
| `-f` | Short form of `--force` |
| `--silent` | Suppress normal installation output |
| `-s` | Short form of `--silent` |

## Repositories

Repositories are configured in:

`/etc/slate.conf/repos`

Multiple repositories are supported.

Repositories are processed in configuration order. Earlier repositories have priority when duplicate package names exist.

The special repository versions are:

- `current`
- `testing`

## Port Environment

When executing a port, the package manager provides:

| Variable | Description |
| --- | --- |
| `PORT_NAME` | Package name |
| `PORT_DIR` | Package port directory |
| `PORTS_DIR` | Package port directory |
| `DESTDIR` | Temporary installation staging directory |
| `MAKETHREADS` | Configured build thread count |

`PORTS_DIR` points to the individual port directory, not the root of the ports tree.

## Staging

Ports install into the temporary `DESTDIR` provided by the package manager.

After a successful build, staged files are copied into the selected sysroot.

## Manifests

The package manager records installed package files and their checksums.

During removal, file checksums are used to detect files that have changed since installation.

Forced removal bypasses the normal changed-file refusal.

## Logs

Silent installation logs are stored under:

`/var/log/slate/`

## Dependencies

Slate does not automatically resolve and install build dependencies. Users are responsible for installing the required dependencies before building a port.

