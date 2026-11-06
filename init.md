# Initialization

Slate uses a custom shell-based init system.

## Main Init Program

The main initialization program is:

`/bin/rc.init`

It sets the system PATH and executes scripts located in:

`/etc/init.d/`

## Init Scripts

Scripts are executed in filename order.

Numeric prefixes can be used to control execution order.

For example:

- `01-filesystems`
- `02-network`
- `03-hostname`

Scripts ending in `.sh` or `.rc` are skipped by the initialization runner.

## Boot Logging

Boot output is recorded in:

`/var/log/boot.log`

## Services

Services are managed through scripts in `/etc/init.d/`.

The behavior of service scripts depends on their implementation. Some support arguments such as `start`, `stop`, and `restart`.

## Gettys

Slate starts three virtual terminal gettys.

## Failure Handling

A failing init script does not necessarily prevent later scripts from executing. Check the boot log when troubleshooting initialization problems.

