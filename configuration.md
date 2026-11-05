# System Configuration

System configuration files are generally stored under /etc.

## Hostname

The hostname identifies the machine on the local network.

## Filesystems

Persistent filesystem mounts are configured through /etc/fstab.

## Users

User account information is maintained through the standard system account files.

## Timezone

Install the required timezone data before configuring a timezone.

## Groups

Some devices and services require users to belong to specific groups.

## Repositories

Repository configuration is stored in:

    /etc/slate.conf/repos

Each repository entry contains a Git repository URL and a version or testing selection.

Example:

    https://example.org/slate-ports.git 0.6
    https://example.org/extra-ports.git testing

Blank lines and commented-out entries are ignored.

A release tag selects a specific repository version. The testing selection uses the latest development branch.

## Build Configuration

Slate uses the MAKETHREADS setting for build configuration.

Parallel compilation is not currently implemented.
