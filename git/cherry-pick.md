Используется тогда, когда нам надо "взять" один или несколько коммитов из другой ветки в целевую
ветку

```bash
git checkout production
git cherry-pick хэш_коммита
```

Перенести коммит из другой ветки, но при этом поменять сообщение коммита
```bash
git cherry-pick --edit
```

Перенести изменения из коммита из другой ветки, но при этом не хотим делать коммит в нашей ветке.
Хотим, чтобы изменения просто попали в отслеживаемую зону.
> если мы хотим внести небольшие правки в тот коммит, который мы забираем из другой ветки
> или слияние двух коммитов из другой ветки в один коммит
```bash
git cherry-pick --no-commit
```
