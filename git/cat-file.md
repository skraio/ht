```bash
git cat-file -p <sha>
```

Чтобы восстановить удаленный ресурс, нужно пройтись по SHA до нужных файлов и сделать
```bash
git cat-file -p <sha> > file1234.md
```


Альтернативно(много истории):
```bash
git merge <sha>
```

Альтернативно(один коммит):
(должно быть чистое working tree - не должно изменений)
```bash
git cherry-pick <sha>
```
