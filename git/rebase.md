команда rebase merge commit'а не создает

Перебазировать ветку feature/FSP-1234
```bash
git checkout feature/FSP-1234
git rebase master
```
В ветку feature/FSP-1234 будет добавлен последний коммит в master
Затем поверх него будут добавлены коммиты из feature/FSP-1234
После можно делать fast-forward слияние без merge commit
```bash
git merge feature/FSP-1234
```

После разрешения конфликтов слияния при rebase
Продолжить слияние rebase:
```bash
git rebase --continue
```
Отменить слияние:
```bash
git rebase --abort
```

---

Применить коммиты с master, потом поверх - с временной зоны
```bash
git fetch
git rebase origin/master
```

---

```bash
git checkout feature/FSP-1234
git add .
git commit -m "add ..."
git checkout master
git add .
git commit -m "do sth ..."
git checkout feature/FSP-1234
git rebase master
# зарезолвить конфликты
git rebase --continue
```

---

Поменять порядок(pick)/сообщения(reword) коммитов
```bash
git rebase -i HEAD~3
```

Объединить два коммита в один
```bash
pick a52340c msg1
squash 53adc9f one commit yayayayyaya
```

Внести изменения в коммит
```bash
edit a52340c msg1
:wq
# внести изменения в файлы
git add .
git commit --amend  # зафиксировать изменения
git rebase --continue # продолжить rebase
```
