Для просмотра системного журнала полностью
```bash
journalctl
```


Для просмотра последних событий и вывода новых событий по мере их появления
```bash
journalctl -f
```


Сообщения от юнита
```bash
journalctl -u имя_юнита
```


Сообщения от ядра
```bash
journalctl -k
```

Сообщения за период
```bash
journalctl --since "дата" --until "дата"Формат даты: YYYY-MM-DD HH:MM:SS
```
