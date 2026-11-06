# Ports Layout

Slate organizes software into categories inside the ports tree.

The default ports directory is:

`/usr/ports`

## Categories

Packages are organized by purpose.

Examples include:

- `base`
- `dev`
- `lib`
- `net`
- `x11`
- `desktop`
- `utils`

## Package Structure

Each package has its own directory containing a `port.sh` script.

Example:

`/usr/ports/dev/bison/port.sh`

## Multiple Repositories

Slate supports multiple ports repositories.

Repositories are configured in `/etc/slate.conf/repos`.

This allows additional ports collections to be maintained separately from the main repository.

## Port Scripts

Each port script is responsible for downloading source code, extracting it, configuring the build, compiling the software, and installing files into the staging directory.

