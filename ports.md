# Maintaining Ports

Slate ports are shell scripts used to build and install software.

Each package has a `port.sh` file inside its package directory.

## Example Port

```sh
#!/bin/sh
set -e

cd "$PORTS_DIR"

curl -LO https://example.org/package-1.0.tar.xz
tar -xf package-1.0.tar.xz

cd package-1.0

./configure --prefix=/usr
make -j"$MAKETHREADS"
make DESTDIR="$DESTDIR" install
