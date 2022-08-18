# openvpn4mikrotik

OpenVPN installer for Debian, Ubuntu, Fedora, CentOS, Arch Linux, Oracle Linux, Rocky Linux and AlmaLinux which ensures a workable configuration for Mikrotik RouterOS devices as CLIENTS.

This script will let you setup your own secure VPN server in just a few seconds.

## Usage

You need to run the script as root and have the TUN module enabled.
```
modprobe tun
```
Next, get the script:

```bash
curl -O https://raw.githubusercontent.com/Real-Ztrawberry/openvpn4mikrotik/master/openvpn4mikrotik-install.sh
```

Make it executable:
```
chmod +x openvpn4mikrotik-install.sh
```

Then run it:

```sh
./openvpn4mikrotik-install.sh
```

The first time you run it, you'll have to follow the assistant and answer a few questions to setup your VPN server.

When OpenVPN is installed, you can run the script again, and you will get the choice to:

- Add a client
- Remove a client
- Uninstall OpenVPN

In your home directory, you will have `.ovpn` files. These are the client configuration files. Download them from your server and connect using your favorite OpenVPN client.
