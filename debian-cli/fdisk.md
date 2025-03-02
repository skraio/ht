список устройств и разделов
```bash
fdisk -l
```


1. Check Current Disk Layout
   Confirm the layout of your disk and partitions using:
   ```bash
   lsblk
   df -h
   ```

2. Unmount the Partition (if needed)
   If the partition is in use, unmount it:
   ```bash
   sudo umount /
   ```

3. Resize the Partition
   - Launch `fdisk` for `sda`:
     ```bash
     sudo fdisk /dev/sda
     ```
   - Delete the existing `sda1` partition (its data will remain intact temporarily):
     Type `d` and press Enter.
   - Recreate the partition with the full disk size:
     Type `n`, choose the default options to create a primary partition starting at the same sector as before, and use the entire disk size.
   - Mark the partition as bootable:
     Type `a` to toggle the bootable flag.
   - Write the changes:
     Type `w` to save and exit `fdisk`.

4. Resize the Filesystem
    After resizing the partition, resize the filesystem to occupy the entire partition:
    ```bash
    sudo resize2fs /dev/sda1
    ```

    Check the updated layout:
    ```bash
    lsblk
    df -h
    ```

Reboot the system to ensure all changes are applied:
```bash
sudo reboot
```
