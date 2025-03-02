Список модулей текущего (загруженного) ядра
```bash
ls -al /lib/modules/$(uname -r)
```

Отобразить список установленных модулей
```bash
find /lib/modules/$(uname -r) -name *.ko
```
