Обновление информации о пакетах (синхронизирует информацию о пакетах, хранимую в локальном кеше, с
информацией из репозиториев);
```bash
update
```

Поиск пакетов согласно информации из локального кеша;
```bash
search
```

upgrade обновляет пакеты новыми версиями, доступными в репозиториях
```bash
upgrade
```

dist-upgrade также удаляет старые и ненужные зависимости пакетов
```bash
dist-upgrade
```

----------------------------------------------------------------------------------------------------

Check if package is installed
```bash
sudo apt list --installed | grep apache2
```

Purge package
```bash
sudo apt purge --auto-remove freeipa-client
```

Clean up the package manager
```bash
sudo apt autoremove --purge
sudo apt clean
```


Fix missing:
```bash
sudo apt install -f
```

Проверка текущего приоритета:
```bash
apt policy
```

Проверка приоритета для конкретного пакета
```bash
apt-cache policy <имя_пакета>
```
