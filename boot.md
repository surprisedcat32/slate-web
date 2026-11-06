# Boot Process

Slate uses an initramfs to locate and mount the installed root filesystem.

## Initramfs

The initramfs contains the utilities and programs required to locate the root filesystem and transfer control to the installed system.

Toybox provides basic userspace utilities.

## Boot Sequence

1. The kernel starts the initramfs.
2. The initramfs mounts `/proc`, `/sys`, and `/dev`.
3. Available block devices are enumerated.
4. `choose-root` identifies the root device.
5. The root filesystem is mounted at `/newroot`.
6. `slate-switch-root` transfers execution to the installed system.
7. The installed system starts `/sbin/init`.

## Root Filesystem

The root filesystem is mounted read-only during the initial root selection process. The installed initialization scripts handle the normal filesystem mounts and remounting.

## Troubleshooting

If Slate cannot boot:

- Check that the root filesystem exists.
- Verify that the root device can be detected.
- Check that the required filesystem support is available.
- Verify that the initramfs contains `choose-root` and `slate-switch-root`.
- Check the kernel command line and bootloader configuration.

