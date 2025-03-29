```bash
git reset [--soft | --mixed | --hard] [commit hash | HEAD]
```
по-умолчанию:
```bash
git reset = git reset --mixed HEAD
```

---
Сценарий
```
commit1 > commit2 > commit3 > commit4(HEAD)
```

1. `--soft` - возвращает проект к указанному коммиту, при этом переводит все коммиты после
   указанного в отслеживаемую (staged - green) зону
```bash
git reset --soft HEAD~2
```
- `commit1 > commit2(HEAD) > commit3(staged) > commit4(staged)`

2. `--mixed` - возвращает проект к указанному коммиту, при этом переводит все коммиты после
   указанного в неотслеживаемую (unstaged - red, нужно потом делать add) зону
```bash
git reset --mixed HEAD~2
```
`commit1 > commit2(HEAD) > commit3(unstaged) > commit4(unstaged)`

3. `--hard` - возвращает проект к указанному коммиту, при этом полностью и безвозвратно удаляет все
   коммиты после указанного
```bash
git reset --hard HEAD~2
```
`commit1 > commit2(HEAD)`

---

правило - опубликованное в публичном репозитории нельзя перезатирать с `git reset --hard`

