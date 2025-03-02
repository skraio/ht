
```bash
sudo apt-get install bridge-utils
```

```bash
# Set up interfaces manually, avoiding conflicts with, e.g., network manager
iface eth0 inet manual
iface eth1 inet manual

# Bridge setup
auto br0
iface br0 inet static
    bridge_ports eth0 eth1
    address 192.168.1.2
    broadcast 192.168.1.255
    netmask 255.255.255.0
    gateway 192.168.1.1
```
