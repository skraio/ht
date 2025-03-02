# Предварительная настройка

```bash
sudo hostnamectl set-hostname <имя_узла>
```
sudo vim /etc/hosts
```bash
127.0.0.1       localhost
<ip-адрес_узла> <имя_узла>
```

Перезапустить терминальную оболочку:
```bash
exec su - $USER
```

# Создание локального репозитория

```bash
ls -lh
-rw-r--r-- 1 root root 14G июн 5 19:30 abc.iso
```

Создать необходимые каталоги, смонтировать iso-образы, а также скопировать их содержимое в
соответствующие каталоги, которые расположены в каталоге /opt.
```bash
sudo mkdir /mnt/abc
sudo mount abc.iso /mnt/abc
sudo cp -r /mnt/* /opt/
```


Конечное содержимое каталога /opt выглядит следующим образом:
```bash
ls -l /opt
dr-xr-xr-x 5 root root 4096 июн 5 19:58 abc
```

После чего подключить указанные репозитории:
```bash
sudo vim /etc/apt/sources.list
deb file:///opt/abc/ 1.7_x86-64 main non-free contrib
```

И выполнить обновление системы.
```bash
sudo apt update
sudo apt dist-upgrade -y
```

# Развёртывание HTTP-репозитория

Для развёртывания HTTP-репозитория будет использован веб-сервер Apache2.
Установить apache2:
```bash
sudo apt install apache2 -y
```

Настроить apache2:
```bash
sudo rm /var/www/html/index.html
sudo ln -s /opt /var/www/html
sudo systemctl restart apache2
sudo systemctl enable apache2
```

Для проверки корректности работы пакетного репозитория необходимо на Jump-машине установить Web-браузер Firefox.
Для этого необходимо:

Указать репозитории пакетного сервера, приведя файл /etc/apt/sources.list к следующему виду:
```bash
sudo vim /etc/apt/sources.list
deb http://192.168.66.2/opt/abc/ 1.7_x86-64 main non-free contrib
```

Установить Firefox:
```bash
sudo apt update
sudo apt install firefox -y
```

После чего проверить корректность отображения сервера-репозитория, открыв Web-браузер и перейдя по адресу:
```bash
http://192.168.66.2/opt/
```
