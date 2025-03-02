```bash
sudo apt install lvm2 -y
```


Создание физических томов(можно и для разделов vda1)
```bash
sudo pvcreate /dev/vda
```


Создание группы томов
```bash
sudo vgcreate vg1 /dev/sdb /dev/sdc
```

Создание логического тома
```bash
sudo lvcreate -L 9G -n lv1 vg1
```
-L – размер в мегабайтах, гигабайтах и т. д. Нужно явным образом указывать единицы измерения, например: 25 ГБ;
-n – имя для нового логического тома

```bash
sudo mkfs.ext4 /dev/vg1/lv1
sudo mount /dev/vg1/lv1 /mnt
```
