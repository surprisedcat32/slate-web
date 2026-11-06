# Networking

Slate provides basic networking through its initialization scripts and userspace networking utilities.

## Ethernet

The default networking initialization script configures the Ethernet interface.

The current setup uses:

- `ip`
- `sdhcp`

The default Ethernet interface is `eth0`.

## Loopback

The loopback interface is configured during initialization.

## DHCP

Slate uses `sdhcp` to obtain network configuration through DHCP.

## Wireless

Wireless networking requires additional software.

Common packages include:

- `iw`
- `wpa_supplicant`

These can be installed through the Slate package manager.

## Troubleshooting

Check the following when networking does not work:

- Verify that the network interface exists.
- Check the interface state with `ip link`.
- Verify that DHCP is running successfully.
- Check that the required firmware is installed.
- Verify that wireless authentication is configured correctly.

