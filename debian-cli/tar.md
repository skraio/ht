Создать архив(c — создать, v — показать процесс, f — имя архива):
```bash
tar -cvf archive.tar file1 file2 dir/
```

Создать сжатый архив (z — сжатие Gzip)
```bash
tar -czvf archive.tar.gz file1 file2
```

Распаковать архив (x — извлечь)
```bash
tar -xvf archive.tar
```

----------------------------------------------------------------------------------------------------

Создать 7z-архив: (a — добавить файлы)
```bash
7z a archive.7z file1 file2 dir/
```

Распаковать архив:
```bash
7z x archive.7z
```

Посмотреть содержимое архива:
```bash
7z l archive.7z
```
