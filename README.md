# openvpn4mikrotik

OpenVPN installer for Debian, Ubuntu, Fedora, CentOS, Arch Linux, Oracle Linux, Rocky Linux and AlmaLinux which ensures a workable configuration for Mikrotik RouterOS devices as CLIENTS.

Please ensure that you upgraded the Mikrotik device to at least 7.3.1 to ensure compatibility.

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

In your home directory, you will have `.ovpn` files. These are the client configuration files. Download them from your server and connect using your favorite OpenVPN client for phones, computers etc.

## Client configuration for Mikrotik devices

1. Upload the openvpn client configuration via Files
2. Navigate to System - Certificates and do an Import on the file just uploaded
    - You should see 2 certificates, one mark with T and the other TK
3. Create a new PPP Profile (or change default). Specify settings as per your requirements
4. Create a new PPP connection with:
    - Public IP address of your server
    - Encryption settings as per your choices during installation (Defaults is SHA 256 and Cipher 128)
    - TLS 1.2
    - Add your username as the client configuration name you specified
    - Choose the correct certificate (If you did not change names, it will be 'client config name'_1 normally)
    - Decide whether you need to include this connection as a default route

## Final thoughts
I roughly modified the original script to create a Mikrotik RouterOS compatible setup. Google if you encouter any issues :-)
