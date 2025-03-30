1. Скачивает удаленную ветку с удаленного репозитория (обновляет ветку origin/master)
2. Сливает  удаленную ветку с локальной веткой (производит актуализацию вашей локальной ветки)
```bash
git pull origin master
git pull <remote> <branch>
```
- То же самое для любой другой ветки (git pull origin название_ветки)

`git pull origin master` = `git fetch` + `git merge origin/master`
