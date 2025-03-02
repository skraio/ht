
```bash
lsmod | grep 8021q
```


Load the 8021q kernel module:
```bash
sudo modprobe 8021q
```

Ensure that this module gets loaded after a reboot by adding to /etc/modules:
```bash
sudo  sh -c 'grep -q 8021q /etc/modules || echo 8021q >> /etc/modules'
```

```bash
auto bond0
iface bond0 inet manual
    bond-slaves eth1 eth2
    bond-mode balance-rr
    bond-miimon 100 # частота мониторинга состояния соединений для каждого из подключенных интерфейсов в милисекундах


auto bond0.10
iface bond0.10 inet static
    address 192.168.1.10
    netmask 255.255.255.0
    gateway 192.168.1.1
    vlan-raw-device bond0
```
