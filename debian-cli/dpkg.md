установка пакета
```bash
dpkg -i имя_deb-файла
```

удаление пакета;
```bash
dpkg -r package
```

удаление пакета и конфигурационных файлов;
```bash
dpkg -P package
```

список всех установленных пакетов;
```bash
dpkg -l
```

детальная информация о пакете;
```bash
dpkg -s package
```

список файлов пакета;
```bash
dpkg -L package
```

принадлежность файла к пакету
```bash
dpkg -S file
```

----------------------------------------------------------------------------------------------------

Check if package is installed
```bash
dpkg -l | grep freeipa
```

Clean up the package manager
```bash
sudo dpkg --purge freeipa-client
```

