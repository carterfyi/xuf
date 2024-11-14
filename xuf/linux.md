# Linux
Linus Torvald's little bazaar that ate the technological world.

## Networking
There are lots of ways of configuring networking. Here's the ones I've used.

### 0. The Good 'ol GUI
Whatever Networking GUI is available in the desktop environment. e.g.: the GNOME networking configuration applet, which is a frontend for the NetworkManager system service.
### 1. `nmtui` - The NetworkManager Terminal Interfaces
`nmtui` is a terminal interface for the NetworkManager system service. This is my go-to for headless machines.
[nmcli Docs](https://networkmanager.dev/docs/api/latest/nmcli.html)

### 2. `/etc/network/interfaces` & `ifup`/`ifdown`
The lowest level, old-school method. I've used this on Debian-based systems, specifically to set up multiple IP addresses for a single NIC across different VLANs & subnets.

### 3. `systemd-networkd`
[systemd.network](https://wiki.archlinux.org/title/Systemd-networkd) is a system service that manages network configurations. I haven't used this, but it's worth mentioning.

### 4. `raspi-config` - Raspberry Pi Configuration
This is a Raspberry Pi-specific configuration tool that includes a network configuration section. Comes bundled with the Raspberry Pi OS, therefore the logical choice for its netconfig.

### 5. `netplan` - The 'new' declarative way for headless systems
[Netplan](https://netplan.io/) is a high-level declarative network configuration tool that acts as a frontend for lower-level managers like `systemd-networkd` and `NetworkManager`. Never used, but I dig the declarative pattern & may implement it on top of one of the above methods in the future given half an excuse.