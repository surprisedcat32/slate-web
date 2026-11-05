# Slate Package Manager

Slate uses its own package manager to install and manage software from configured repositories.

## Commands

Install a package:

    slate install <category>/<package>

Uninstall a package:

    slate uninstall <category>/<package>

List categories:

    slate list

List packages in a category:

    slate list <category>

List installed packages:

    slate installed

Update repository information:

    slate update

## Package Names

Packages use category/package identifiers.

Examples:

    slate install lib/zlib
    slate install net/curl
    slate install x11/dillo

## Meta Packages

The meta category contains collections of related packages.

## Repositories

Repository configuration is stored in:

    /etc/slate.conf/repos

Slate supports multiple repositories and repository version selection.

## Package Management Notes

- Use complete package identifiers.
- Check required build dependencies before installing ports.
- Review repository configuration.
- Test package installation and uninstallation.
