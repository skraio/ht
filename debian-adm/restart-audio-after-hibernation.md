```bash
sudo su -
lspci -vvv
ls /sys/bus/pci/devices/ | grep 00:1f.3
echo 1 > /sys/bus/pci/devices/0000:00:1f.3/remove
echo 1 > /sys/bus/pci/rescan
```

```bash
echo 1 > /sys/bus/pci/devices/0000:00:1f.3/remove
sleep 1
echo 1 > /sys/bus/pci/rescan
```
